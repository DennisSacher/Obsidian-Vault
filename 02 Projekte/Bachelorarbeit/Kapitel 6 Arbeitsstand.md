---
tags: [bachelorarbeit, evaluation, arbeitsstand]
status: aktiv
date: 2026-09-30
---

# Kapitel 6 Arbeitsstand

← zurück zu [[Bachelorarbeit AsiMinu App]] · Konzept dahinter: [[Evaluationsplan]] · Protokoll: [[02 Projekte/Bachelorarbeit/Arbeitsprotokolle/2026-09-30|Arbeitsprotokoll 30.09.2026]]

Diese Notiz hält fest, welche Messungen für Kapitel 6 (Evaluation und Diskussion) anstehen, was schon gemessen ist und wo es weitergeht. Sie wird nach jedem Schritt ergänzt.

> [!important] Hier geht es weiter
> **Schritt 2: Qualitätstore der Pipeline.** Aus der Pipeline-Konfiguration und aus SonarCloud ablesen, welche Prüfungen eine Auslieferung blockieren. Vorher die zwei offenen Reste aus Schritt 1 erledigen (siehe unten).
> Vereinbarte Arbeitsweise: Schritt für Schritt, der nächste Schritt beginnt erst, wenn Dennis „fertig“ schreibt.

## Evaluationsstand (eingefroren)

| | |
|---|---|
| Fassung | 1.33.1 |
| Commit | `e7ca1ca` vom 30.09.2026 |
| Regel | Für die Arbeit wird danach nicht mehr gepullt, auch wenn am Projekt weiterentwickelt wird |

Das Submodul `Repo/asiminu-projekt` und der Arbeitsordner `Desktop/AsiMiNu_Project_Intern` stehen beide auf diesem Commit.

## Die zehn Schritte

| # | Schritt | Braucht | Status |
|---|---|---|---|
| 1 | Testlauf mit Abdeckung | nur Dennis | **gemessen und in 6.2.1 geschrieben**, zwei Reste offen |
| 2 | Qualitätstore der Pipeline | nur Dennis | **als Nächstes** |
| 3 | Abgleich mit dem externen Testkatalog (352 Fälle) | nur Dennis | offen, Vorarbeit liegt in `docs/05-implementierung/testkatalog-abgleich-2026-08-17.md` |
| 4 | Abnahme der 18 Must-Anforderungen (Anhang B) | nur Dennis | offen |
| 5 | Automatisierungsquote: alte Regel gegen neue Regelbasis auf der echten Standortdatei | nur Dennis | offen |
| 6 | Nachvollziehbarkeit aus dem Prüfprotokoll | nur Dennis | offen |
| 7 | Pilotdurchlauf | BayFu | offen |
| 8 | Testdurchläufe alt gegen neu | BayFu | offen, **kritischer Pfad** |
| 9 | Kurzbefragung | BayFu | offen |
| 10 | Anfragevolumen pro Monat erfragen | BayFu | offen |

Schritte 1 bis 6 tragen das Kapitel notfalls allein. Schritt 8 ist die wichtigste Ergänzung, Schritt 9 am ehesten verzichtbar.

## Messergebnisse

### Schritt 1: Testlauf mit Abdeckung (30.09.2026)

| Wert | Ergebnis |
|---|---|
| Tests | 2350 bestanden, 0 fehlgeschlagen, 0 übersprungen (89 Sekunden) |
| Abdeckung laut SonarCloud, Zeilen und Zweige | 86,9 % auf rund 11.000 Zeilen |
| Lokal: Zeilen | 89,9 % (11.553 von 12.849) |
| Lokal: Zweige | 76,3 % (3.250 von 4.257) |
| Lokal: kombiniert wie bei Sonar | 86,5 % (14.803 von 17.106) |
| SonarCloud sonst | 0 Sicherheitsbefunde, 0 Zuverlässigkeitsbefunde, 6 Wartbarkeitshinweise, 7 akzeptierte Befunde, 2,2 % Duplikate auf 64.000 Zeilen |

Abdeckung je Projekt (lokal, Zeilen / Zweige):

| Projekt | Zeilen | Zweige |
|---|---|---|
| Domain | 98,7 % | 95,5 % |
| Shared | 98,2 % | 92,8 % |
| Api | 91,5 % | 73,5 % |
| GuPanel | 91,1 % | 73,6 % |
| AdminPanel | 90,5 % | 75,6 % |
| Infrastructure | 89,2 % | 82,3 % |
| ChangeCoordinatorPanel | 85,0 % | 66,6 % |
| SharedUi | 84,5 % | 67,5 % |
| LoeschWorker | 78,1 % | 80,0 % |
| IncWorker | 58,1 % | 44,4 % |

Größte Lücken: zwei Dashboard-Seiten (Incidents, TicketBoard), `AdminController`, Mailversand über externe Dienste, Startcode, Incident-Worker. Entscheidung: Abdeckung wird **nicht** weiter erhöht, die Lücken werden im Text benannt.

Die Zahlen sind mit dem Stand vom 12.08.2026 (971 Tests, 81,3 %) nicht direkt vergleichbar, weil die Bezugsmenge seitdem kleiner geworden ist. Im Text steht deshalb nur der aktuelle Stand.

**Offene Reste aus Schritt 1:**
- [ ] Prüfen, dass die SonarCloud-Analyse zu Fassung 1.33.1 gehört
- [ ] Die 7 akzeptierten Befunde ansehen und in einem Satz benennen können

## So wird der Testlauf wiederholt

Im Terminal im Ordner `AsiMiNu_Project_Intern\src`, Docker Desktop muss laufen. Port 55532 aus der Projekt-Anleitung funktioniert auf diesem Rechner nicht, weil Windows den Bereich reserviert. Port 15432 ist frei.

```powershell
docker run -d --name asiminu-test-pg -e POSTGRES_PASSWORD=pruef -e POSTGRES_DB=inc_pruef -p 15432:5432 postgres:16-alpine
dotnet test --settings coverlet.runsettings -e INC_DB_CONNECTION="Host=localhost;Port=15432;Database=inc_pruef;Username=postgres;Password=pruef"
docker rm -f asiminu-test-pg
```

Der Abdeckungsbericht liegt danach unter `backend\AsiMinu.Tests\TestResults\<Kennung>\coverage.cobertura.xml`.

## Was am Konzeptteil von Kapitel 6 noch nicht stimmt

Der vorhandene Text in 6.1 und 6.3 stammt aus der Zeit vor dem 24.09. und ist noch nicht angepasst:

- Die Prozesssicherheits-Kennzahl verspricht eine „lückenlos rekonstruierbare Historie“. Laut Kapitel 5 sind F06 und N03 nur teilweise erfüllt. Die Kennzahl muss ehrlich neu definiert werden.
- Die Automatik ist ab Werk ausgeschaltet und lief nie produktiv. Eine Quote beruht deshalb auf einer Testkonfiguration.
- Der Text spricht von „sechs Kennzahlen“, ausformuliert sind vier.
- Begriffe wie „Pre-Validator“ und `TefServiceStub` kommen in Kapitel 5 nicht vor.
- Der Testfallkatalog verweist für das Fallbeispiel auf 1.2 statt auf 4.2.1.
- [[Evaluationsplan]] nennt zehn bis zwölf Testfälle, Anhang B verknüpft die Abnahmekriterien mit fünf. Das ist noch zu entscheiden.

## Offene Entscheidungen

- Findet die Messung „alt gegen neu“ mit BayFu-Mitarbeitenden statt, und in welchem Umfang? Der Zeitplan im [[Evaluationsplan]] sah Termine bis 20.09. vor und ist überholt.
- Zielumfang von Kapitel 6: geplant 12 Seiten, empfohlen 9 bis 10.
