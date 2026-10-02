---
tags: [bachelorarbeit, evaluation, arbeitsstand]
status: aktiv
date: 2026-09-30
---

# Kapitel 6 Arbeitsstand

← zurück zu [[Bachelorarbeit AsiMinu App]] · Konzept dahinter: [[Evaluationsplan]] · Protokoll: [[02 Projekte/Bachelorarbeit/Arbeitsprotokolle/2026-09-30|Arbeitsprotokoll 30.09.2026]]

Diese Notiz hält fest, welche Messungen für Kapitel 6 (Evaluation und Diskussion) anstehen, was schon gemessen ist und wo es weitergeht. Sie wird nach jedem Schritt ergänzt.

> [!important] Hier geht es weiter
> **Alle Schritte, die Dennis allein machen kann (1 bis 6), sind erledigt.** Als Nächstes zur Wahl: den Konzeptteil von Kapitel 6 (6.1, 6.3, 6.5) an das tatsächlich Gemessene anpassen, die Schritte 7 bis 10 mit der BayFu planen (Termine!), oder mit dem Diskussionsteil beginnen. Empfehlung: zuerst Termine für die Testdurchläufe anfragen, weil sie von anderen abhängen, und in der Wartezeit den Konzeptteil überarbeiten.
> Alles mit dem Skill vermenschlichen geschrieben.
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
| 1 | Testlauf mit Abdeckung | nur Dennis | **erledigt**, in 6.2.1 geschrieben |
| 2 | Qualitätstore der Pipeline | nur Dennis | **erledigt** (02.10.), in 6.2.1 geschrieben |
| 3 | Manueller Funktionstest gegen den externen Testkatalog (347 Fälle) | nur Dennis | **erledigt** (02.10.), in 6.2.2 geschrieben |
| 4 | Abnahme der 18 Must-Anforderungen (Anhang B) | nur Dennis | **erledigt** (02.10.), in 6.2.3 geschrieben; N05 ausgeklammert |
| 5 | Automatisierungsquote: alte Regel gegen neue Regelbasis auf der echten Standortdatei | nur Dennis | **erledigt** (02.10.), in 6.4.2 geschrieben |
| 6 | Nachvollziehbarkeit aus dem Prüfprotokoll | nur Dennis | **erledigt** (02.10.), in 6.4.2 geschrieben; Fehler gefunden, Korrektur liegt lokal und ist getestet, Abstimmung mit Alexander offen |
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
- [x] SonarCloud-Analyse gehört zu Fassung 1.33.1 (bestätigt 02.10.2026). **Versionsnummer und Messdatum stehen auf Wunsch des Betreuers nicht im Text**, nur hier intern
- [x] Die 7 akzeptierten Befunde: entfällt, laut Betreuer nicht erwähnen (02.10.2026)

**Schritt 1 ist damit vollständig abgeschlossen.**

### Schritt 2: Qualitätstore der Pipeline (02.10.2026)

Quelle: `Dev-azure-pipeline.yml`, ADR-054 und die Pipeline-Läufe, ausgelesen mit `az pipelines runs list` und der Timeline-API.

| Prüfung | Blockiert die Auslieferung? |
|---|---|
| Automatisierte Tests | ja |
| SonarCloud Quality Gate (`sonar.qualitygate.wait=true`) | ja |
| Trivy: Quellcode samt Abhängigkeiten, Geheimnisse, Konfiguration (HIGH, CRITICAL) | ja |
| Trivy: Container-Abbilder (HIGH, CRITICAL) | ja |
| NuGet-Prüfung auf verwundbare Pakete | nein, nur Bericht |

`PushImages` hängt an den Stufen CodeQuality, StaticSecurity und ImageSecurity. Ausnahmen nur über `infra/.trivyignore.yaml` mit Ablaufdatum. Ist die Trivy-Datenbank nicht erreichbar, entfallen die Scans mit Warnung.

**Wirksamkeit seit Einführung (Läufe der Dev-Pipeline bis einschließlich 1.33.1.1):**

| | Anzahl |
|---|---|
| Läufe gesamt | 42 (davon 2 abgebrochen) |
| erfolgreich | 25 |
| gescheitert | 15 |
| davon durch SonarCloud Quality Gate | 11 (`QUALITY GATE STATUS: FAILED`) |
| davon durch fehlschlagende Tests | 2 (1.17.2.4, 1.17.4.1) |
| davon durch Trivy-Abbild-Gate | 1 (1.33.0.1, behoben mit `e7ca1ca`, Sicherheitsupdates des Basis-Abbilds) |
| davon beim Ausrollen, kein Qualitätstor | 1 (1.32.0.1, Frontend-Einstellungen) |

Im Text: „Von 40 abgeschlossenen Läufen hielten die Prüfungen 14 an.“

### Schritt 3: Manueller Funktionstest gegen den externen Testkatalog (02.10.2026)

Quelle: `Testkatalog_AsiMinu_Checkliste_Ist-Stand 1.xlsx` (Downloads, laut Dennis Endstand). Entstehung laut Dennis: Ein BayFu-Mitarbeiter ließ die Funktionen per KI aus dem Code in eine Excel-Liste schreiben, ein Praktikant der BayFu hat sie über die Oberflächen getestet (auf Test). Darf als „externer Testkatalog“ erwähnt werden, ohne Angebots- und Kundennummer.

| Ergebnis | Anzahl |
|---|---|
| Testfälle gesamt | 347 (der Abgleich vom 17.08. nannte noch 352) |
| bestanden | 193 |
| fehlgeschlagen | 1 (ADM-002: Suche nach Vor- und Nachname zusammen findet nichts) |
| nicht anwendbar | 2 |
| blockiert, Voraussetzung fehlte | 28 (Telefónica-Schnittstelle, Entra-ID-Anmeldung, Passwort- und 2FA-Reset durch Admin, Aktualisieren beim Standortimport u. a.) |
| nicht durchgeführt | 123 (überwiegend Schnittstellen, Sicherheit, Datenschutz, Betrieb) |

Bedienbarkeitstests 12 von 12 bestanden. Tester und Datum sind im Excel nicht eingetragen.

**Einordnung (wichtig):** Weil der Katalog aus dem Code abgeleitet ist, zeigt er nur, dass Funktionen wie gebaut arbeiten, nicht dass die Anforderungen erfüllt sind. Im Text deshalb als unabhängiger manueller Funktionstest dargestellt, nicht als Anforderungsprüfung. Die Anforderungsprüfung leistet Schritt 4. Dennis sagte zuerst „alle getestet, alle bis auf einen bestanden“; das Excel zeigt, dass das nur für die durchgeführten Fälle gilt. Im Text steht deshalb „Von 194 durchgeführten Testfällen bestanden 193“. Das Excel liegt als Beleg unter `Bachelorarbeit/thesis/Referenzdokumente/Testkatalog_AsiMinu_Checkliste_Ist-Stand.xlsx`.

### Schritt 4: Abnahme der Must-Anforderungen (02.10.2026)

Methode: Zu jedem Abnahmekriterium aus Anhang B einen automatisierten Test gesucht, der genau diesen Fall prüft (Tests in `src/backend/AsiMinu.Tests`).

| Anf. | Ergebnis | Beleg |
|---|---|---|
| F01 | erfüllt | Panels: `Solange_Felder_fehlen_ist_der_Knopf_gesperrt` |
| F02 | erfüllt | `CrqControllerTests.Ein_unbekannter_Standort_wird_abgewiesen` |
| F03 | erfüllt | `Zeitraum_und_SA_Dauer_lassen_sich_nachtraeglich_aendern`, `Ende_vor_Start_wird_abgelehnt` |
| F04 | erfüllt | API-Tests direkt gegen den Server: unbekannter Standort, Vergangenheit, Halbstundenraster |
| F05 | erfüllt | `Die_AMR_Nummern_werden_fortlaufend_vergeben`, `Nach_dem_Loeschen_wird_die_AMR_ID_nicht_erneut_vergeben` |
| F06 | teilweise | Korrektur überschreibt alte Werte (Kapitel 5) |
| F08 | erfüllt | `Ohne_Grund_wird_nicht_abgelehnt`, `Der_Antragsteller_sieht_den_Grund_der_Ablehnung` |
| F09 | erfüllt | `CrqChatTests.Der_GU_sieht_den_Verlauf_seines_eigenen_Antrags` |
| F11 | erfüllt (an Ersatzschnittstelle) | `Ein_unkritischer_Standort_wird_fuer_die_Automatik_vorgemerkt`, `Eine_vorgemerkte_Anfrage_geht_hinaus` |
| F12 | erfüllt | `Ein_kritischer_Standort_bleibt_zur_Pruefung_liegen` |
| N01 | erfüllt | `Schritt_1_gibt_noch_kein_Zugriffsmerkmal_heraus`, `Ein_falscher_Faktor_wird_abgewiesen` |
| N02 | erfüllt | `GU_Rolle_darf_nichts`, `Controllers_are_admin_only` u. a. |
| N03 | teilweise | Protokoll ohne Inhalte (Kapitel 5) |
| N04 | teilweise | manueller Statusendpunkt prüft Ausgangsstatus nicht (Kapitel 5) |
| N05 | ausgeklammert | nur mit Anwendern prüfbar; Dennis plant evtl. eigenen Usability-Abschnitt mit Testperson |
| N06 | erfüllt | Architektur (Web-Apps) und manueller Funktionstest im Browser, kein automatisierter Test |
| R01 | erfüllt | `Eine_fremde_Anfrage_laesst_sich_nicht_im_Detail_ansehen` u. a. |
| R02 | erfüllt | `Eine_Genehmigung_legt_das_Konto_an...`, `Eine_unbekannte_Kennung_ergibt_401` |

### Schritt 5: Automatisierungsquote (02.10.2026, Zwischenstand)

Quelle: `Desktop/stoLookupBayfu_v1.0.csv` (203.545 Standorte, 147 Schreibweisen der Kategorie). Regel nachgebaut aus `AutomatisierungsPruefung.PruefeStandort`, Skripte im Scratchpad (`standorte.ps1`, `quote.ps1`). Nur die fünf Standortbedingungen, die vier Anfragebedingungen hängen an der einzelnen Anfrage.

Verteilung: Kategorie fehlt 174.760, Kategorie 1: 10.579, 1+: 9.314, 2: 8.362, 3: 530. Alleinversorger: keine Angabe 175.375, ja 12.132, nein 16.038. Datenverkehr leer 175.742, über 100 GB 24.800.

| Konfiguration | Standorte, die die Automatik zulässt |
|---|---|
| Alte, fest verdrahtete Regel | 0 von 203.545 (0 %) |
| A: Werkseinstellung, Kategorien 1, 1+, 2 freigegeben | 699 (0,3 %); von den 28.255 Standorten mit Kategorie 1 bis 2 sind es 2,5 % |
| B: wie A, fehlende Angaben erlaubt | 175.846 (86,4 %) |
| C: nur Kategorie 1 | 665 (0,3 %) |

Häufigste Gründe bei A: Kategorie fehlt (174.760), Alleinversorger (12.016), Datenverkehr über 100 GB (10.682), Router (2.218), Richtfunk (1.977).

**Kernbefund:** Die Quote hängt fast nur daran, wie Standorte ohne Angaben behandelt werden. Das stützt die Kernthese der Arbeit, dass Datenqualität die Voraussetzung für Automatisierung ist.

**Geklärt mit Dennis:** Eine Liste früherer Anfragen gibt es nicht, deshalb Standortsicht statt Anfragesicht. Die BayFu prüft zum Start bewusst alles von Hand, um die Fehlerquellen kennenzulernen, und schaltet die Automatik danach schrittweise über das Admin-Panel ein. Tatsächliche Quote im Betrieb also vorerst 0.

**Geschrieben** in 6.4.2 (Ergebnisse, Automatisierungsgrad), mit eigener KI-Fußnote. Schritt 5 erledigt.

### Schritt 6: Nachvollziehbarkeit aus dem Prüfprotokoll (02.10.2026)

**Befund:** Bei allen Aktionen an Anfragen (`/api/admin/crq/{id}/…`: validieren, ablehnen, uebertragen, assignee, ruecksprache, bearbeiten, status, löschen) und beim Einreichen (`POST /api/crq`) steht im Prüfprotokoll kein Ziel („Betroffen: –“). Bestätigt mit Screenshots aus dem Admin-Panel. Nur die Übertragung über `TefServiceStub` schreibt `CrqAntrag AMR…`.

**Ursache:** `AuditFilter.ZielErmitteln` liefert für den Routenwert `id` den Typ `null`, und `OnActionExecutionAsync` verwirft ein Ziel ohne Typ ganz.

**Entscheidung Dennis: Variante C.** Im Text ehrlich dokumentiert (eingefrorener Stand), Korrektur im Projekt lokal vorbereitet, nicht committet:
- `AuditFilter.cs`: Typ aus dem Pfadabschnitt vor der Kennung, `crq` → `CrqAntrag`; Datenbank-Id wird vor der Ausführung in die AMR-ID übersetzt; neuer Schlüssel `audit.ziel` in `HttpContext.Items` für Ziele, die erst bei der Ausführung entstehen
- `CrqController.cs`: Einreichen legt `CrqAntrag/AMR…` unter `audit.ziel` ab
- Tests: `AdminCrqUndIncidentTests.Die_Bearbeitung_einer_Anfrage_steht_mit_ihrer_AMR_ID_im_Protokoll`, `CrqControllerTests.Das_Einreichen_steht_mit_der_neuen_AMR_ID_im_Protokoll`
- **Getestet 02.10.2026:** Beide neuen Tests bestehen mit der Korrektur und scheitern gegen den alten Code (Gegenprobe per `git stash`). Gesamte Suite mit Korrektur: 2352 bestanden, 0 fehlgeschlagen, 0 übersprungen.
- **Abgestimmt mit Alexander 02.10.2026** und als Fassung 1.34.1 committet, zusammen mit ADR-061. Orange Notiz in 6.4.2 entfernt.

**Text:** 5.11.2 (Prüfprotokoll) korrigiert, 6.2.3 (N03) angepasst, 6.4.2 Absätze zur Prozesssicherheit.

Ergänzt in 5.7: Satz zum Einführungsrundgang im GU-Panel (startet bei der ersten Anmeldung, über das Profil erneut startbar, 24 Halte in `GuRundgang.cs`). Der Lauf 1.33.1.1 der Test-Pipeline steht auf „failed“, weil die manuelle Freigabe für die Testumgebung nicht erteilt wurde. Das ist kein Qualitätstor und kommt nicht in den Text.

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
