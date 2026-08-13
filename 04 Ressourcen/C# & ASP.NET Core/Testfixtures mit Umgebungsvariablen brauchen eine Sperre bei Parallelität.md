---
tags: [ressource, csharp, testing]
status: aktiv
date: 2026-08-13
---

# Testfixtures mit Umgebungsvariablen brauchen eine Sperre bei Parallelität

## Die Erkenntnis

Wenn du eine `WebApplicationFactory<T>` (oder ein ähnliches Testgerüst) über
Umgebungsvariablen konfigurierst, statt über `appsettings.json` oder Konstruktor-Parameter,
dann gehören diese Variablen dem ganzen Prozess, nicht der einzelnen Testklasse. Solange du
nur eine einzige Fabrik im gesamten Testlauf hast, merkst du davon nichts. Sobald ein
zweiter Test eine eigene, frische Fabrik mit eigenen Verbindungszeichenfolgen braucht,
laufen zwei Fabriken parallel im selben Prozess, und die zweite überschreibt der ersten
still die Umgebungsvariablen, bevor deren Anwendung sie überhaupt gelesen hat.

## Warum du Umgebungsvariablen überhaupt brauchst

In ASP.NET Core lädt `Program.cs` seine Konfiguration in einer festen Reihenfolge, und
lokale User Secrets stehen dabei ziemlich weit oben. Wenn du `IConfiguration` in einem
Test nur über `WebApplicationFactory.ConfigureAppConfiguration` mit
`AddInMemoryCollection` überschreiben willst, reicht das oft nicht: Werte, die
`Program.cs` schon beim Bauen der Services liest (zum Beispiel ein JWT-Schlüssel), sind zu
diesem Zeitpunkt schon aus den User Secrets befüllt. Nur Umgebungsvariablen setzen sich
zuverlässig gegen User Secrets durch.

## Das Fehlerbild

Ziemlich unangenehm zu debuggen: Jeder Test läuft einzeln fehlerfrei durch. Nur im
gemeinsamen Testlauf scheitert plötzlich einer, und die Fehlermeldung zeigt auf die
Fachlogik statt auf das Test-Gerüst. Im AsiMinu-Projekt sah das so aus, dass ein Test für
den allerersten Admin-Bootstrap mit "es existiert bereits ein Admin" scheiterte, obwohl er
in einer eigentlich frischen, leeren Datenbank laufen sollte. Tatsächlich lief er auf der
Datenbank einer anderen, parallel laufenden Testfabrik.

## Die Lösung

Eine statische Sperre um den kompletten Ablauf "Umgebungsvariablen setzen, dann die
Anwendung hochfahren". Dazu am besten direkt danach nachprüfen, dass die eigenen
Verbindungszeichenfolgen tatsächlich angekommen sind, bevor du die Sperre wieder frei
gibst. Sonst tauschst du ein seltenes Rennen gegen ein subtileres.

## Wann das für dich relevant wird

Immer dann, wenn ein Test bewusst eine eigene, isolierte Umgebung braucht statt der
geteilten Testsammlung, zum Beispiel weil ein Endpunkt sich selbst abschaltet, sobald eine
bestimmte Vorbedingung erfüllt ist (hier: sobald ein Admin existiert). Sobald es mehr als
eine Fabrik im selben Prozess gibt, lohnt sich die Frage, ob sie sich gegenseitig die
Umgebungsvariablen wegnehmen können.

## Fundstelle

AsiMinu-Repo: `src/backend/AsiMinu.Tests/Api/ApiFabrik.cs` (Feld `Anlaufsperre`),
gefunden über `BootstrapErstesKontoTests.cs` am 12.08.2026. Details im Tagesprotokoll
`docs/Bachelorarbeit/arbeitsprotokolle/2026-08-12-tagesprotokoll.md`.
