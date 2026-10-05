---
tags: [bachelorarbeit, planung]
erstellt: 2026-08-11
aktualisiert: 2026-10-05
---

# Kapitelplanung

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!tip] LaTeX-Dateien
> `Bachelorarbeit/thesis/BA-Text/latex-projekt/chapters/` → ein Ordner je Kapitel

> [!important] Aktueller Stand 04.10.2026: Gliederung zweistufig, Ziel 40 Seiten
> Die gültige Kapitelstruktur mit Seitenbudget und Checkliste steht unten unter
> [[#Kapitelstruktur (Stand 04.10.2026)]]. Die folgenden Abschnitte sind historisch.

> [!important] Stand 16.09.2026 — Betreuer-Feedback: von neun auf sieben Kapitel zusammengelegt
> Gespräch mit dem Betreuer zur Gliederung: ihm waren neun Überkapitel zu viele. Auf seinen
> Wunsch wurden **Kapitel 5 (Architektur) und 6 (Realisierung)** zu einem Kapitel zusammengelegt,
> ebenso **Kapitel 7 (Evaluation) und 8 (Diskussion)**. Die Kapitelzuordnung vom 15.09.2026 unten
> ist damit veraltet und durch diese Tabelle ersetzt:
>
> | Neu | Kapitel | Datei | Zielumfang |
> |---|---|---|---|
> | 01 | Einleitung | `chapters/01/einleitung.tex` | 4 Seiten |
> | 02 | Grundlagen | `chapters/02/grundlagen.tex` | 8 Seiten |
> | 03 | Vorgehen | `chapters/03/vorgehen.tex` | 3 Seiten |
> | 04 | Ist-Analyse und Anforderungen | `chapters/04/ist_analyse_anforderungen.tex` | 7 Seiten |
> | 05 | Architektur und Realisierung | `chapters/05/architektur_realisierung.tex` | 19 Seiten (7+12) |
> | 06 | Evaluation und Diskussion | `chapters/06/evaluation_diskussion.tex` | 12 Seiten (8+4) |
> | 07 | Zusammenfassung und Ausblick | `chapters/07/zusammenfassung.tex` | 3 Seiten |
>
> Summe weiterhin 56 Seiten Fließtext — es handelt sich um einen **reinen Strukturmerge**
> (bewusst gegen den Betreuer-Vorschlag „auch inhaltlich straffen" entschieden): Inhalt,
> Todo-Baupläne und Reihenfolge sind unverändert erhalten geblieben, nur die Kapitelgrenze fiel
> weg. Die beiden ehemaligen Kapitel-Label (`ch:realisierung`, `ch:diskussion`) wurden dabei auf
> den jeweils ersten Abschnitt des übernommenen Teils verschoben, alle betroffenen Querverweise
> im Fließtext (`Kapitel~X` → `Abschnitt~X`) und einige Selbstverweise wurden entsprechend
> angepasst. Anhang und KI-Erklärung liegen jetzt unter `chapters/07/` statt `chapters/09/`.
> Datei-technisch relevant: `configuration/document-setup-digital.tex` und
> `-print.tex` enthalten die eigentliche Include-Liste (nicht `chapters/toc.tex`, das nur die
> Verzeichnisse für Inhalt/Abbildungen/Tabellen umfasst).
>
> Aufräumen (noch offen, bewusst nicht ungefragt gelöscht): Die alten Dateien
> `chapters/05/architektur.tex`, `chapters/06/realisierung.tex`, `chapters/07/evaluation.tex`,
> `chapters/08/diskussion.tex` sowie die alten `chapters/09/*`-Dateien liegen noch unverändert
> auf der Platte, werden aber von keiner Include-Liste mehr referenziert. Ebenso noch vorhanden:
> ältere Vor-Variante-D-Karteileichen wie `chapters/03/ist_analyse.tex`,
> `chapters/04/anforderungen_architektur.tex`, `chapters/05/entwurf_realisierung.tex`,
> `chapters/06/herausforderungen.tex`, `chapters/08/zusammenfassung.tex`.
>
> Offen: Kompilier-Test war in der genutzten Sandbox nicht möglich (dortiges TeX Live hat kein
> `ngerman`-Sprachpaket installiert) — bitte einmal im gewohnten Editor/Overleaf durchkompilieren,
> um das lokal zu bestätigen. Inhaltlich wurde stattdessen vollständig geprüft: 102 Labels,
> 0 nicht auflösbare Querverweise, 0 doppelte Labels, Klammern in jeder Datei ausgeglichen, genau
> ein `\chapter{}` und eine grüne Zielumfang-Box je Hauptkapiteldatei.

> [!important] Stand 15.09.2026 — Variante D umgesetzt, komplette Kapitelstruktur neu (historisch, neun Kapitel — seit 16.09.2026 auf sieben reduziert, siehe oben)
> Die am 09.09.2026 empfohlene [[Gliederungsvarianten|Variante D]] wurde vollständig umgesetzt.
> Die Kapitelzuordnung unten ist entsprechend komplett neu geschrieben. Ältere Zuordnungen
> (Kapitel 03 „Ist-Analyse", Kapitel 04 „Anforderungen & Architektur", Kapitel 05 „Entwurf &
> Realisierung", Kapitel 06 „Herausforderungen während der Entwicklung") existieren so nicht
> mehr:
>
> | Neu | Kapitel | Datei | Zielumfang |
> |---|---|---|---|
> | 01 | Einleitung | `chapters/01/einleitung.tex` | 4 Seiten |
> | 02 | Grundlagen | `chapters/02/grundlagen.tex` | 8 Seiten |
> | 03 | Vorgehen | `chapters/03/vorgehen.tex` | 3 Seiten |
> | 04 | Ist-Analyse und Anforderungen | `chapters/04/ist_analyse_anforderungen.tex` | 7 Seiten |
> | 05 | Architektur | `chapters/05/architektur.tex` | 7 Seiten |
> | 06 | Realisierung | `chapters/06/realisierung.tex` | 12 Seiten |
> | 07 | Evaluation | `chapters/07/evaluation.tex` | 8 Seiten |
> | 08 | Diskussion (neu) | `chapters/08/diskussion.tex` | 4 Seiten |
> | 09 | Zusammenfassung und Ausblick | `chapters/09/zusammenfassung.tex` | 3 Seiten |
>
> Summe 56 Seiten Fließtext, nah am vorgeschlagenen Zielkorridor von 55 bis 60 Seiten. Die
> bestehenden, sehr ausführlichen Todo-Baupläne wurden dabei erhalten und an die neue Gliederung
> angepasst, nicht verworfen. Zusätzlich hat jetzt jeder Abschnitt eine türkise
> Kurzfassungs-Notiz und jedes Kapitel eine grüne Begründung des Zielumfangs, beides wörtlich aus
> dem Abstimmungsdokument mit dem Betreuer übernommen.
>
> Offen: prüfen, ob `thesis/dashboard/` nach der Umbenennung noch korrekt rechnet, siehe
> [[Offene-Fragen]].

> [!tip] Schreibkonventionen liegen jetzt im Repo
> Welcher Sachverhalt in welchem Kapitel erklärt wird, welche Begriffe durchgängig gelten und
> welche Entscheidungen wann getroffen wurden, steht seit 16.09.2026 in
> `thesis/Schreibstand.md`. Diese Notiz hier bleibt die qualitative Planungssicht,
> `Schreibstand.md` ist die Arbeitsgrundlage beim Formulieren.

> [!important] Stand 02.09.2026 — Gliederung erweitert, Status-Tracking ins Dashboard gewandert (historisch, bezieht sich auf die alte Struktur)
> Die Kapitelgliederung wurde am 01.09.2026 deutlich erweitert (Commit `d6d1841`): Kapitel 05
> hatte damals **7 statt 5 Sektionen**, die unten unter „Echte Lücken" genannten fehlenden
> Sektionen **ChangeCoordinator-Panel/CRQ-Chat** und **TEF-Automatisierung** waren damit
> geschlossen. Alle Todo-Blöcke in Kapitel 2–9 wurden außerdem sehr ausführlich mit
> ADR-Verweisen befüllt. Seit diesem Tag gibt es `thesis/dashboard/` (automatisch generiertes
> Dashboard, berechnet Status/Seiten/Ampeln/Tagesempfehlung direkt aus den `.tex`-Dateien).
> Läuft täglich 9 Uhr per Windows-Taskplaner, manuell per Desktop-Verknüpfung „Dashboard
> aktualisieren", Abschnittsstatus ändern über `thesis/dashboard/status-setzen.ps1`.

> [!warning] Stand 13.08.2026 — Zwei Sessions in Folge ohne Kapiteltext (historisch)
> Weder am 11.08. noch am 12.08. wurde weitergeschrieben. Neu entdeckt beim Gegenlesen: In der
> damaligen Ist-Analyse stand als einziger Fließtext eines Abschnitts das Wort „hi", ein alter
> Test-Platzhalter, mittlerweile beim Ausformulieren entfernt. AsiMinu-Submodul war zu diesem
> Zeitpunkt auf einer neuen Chatfunktion im CRQ und einer Automatisierungsseite mit
> einstellbaren Uhrzeiten aktualisiert worden.

> [!info] Stand 12.08.2026 — Formale Vorgaben eingearbeitet (historisch)
> Die offiziellen TH-Rosenheim-Schreibrichtlinien wurden nachgereicht (siehe
> [[Wissenschaftliches Arbeiten]]). Neues Pflicht-Verzeichnis `chapters/abkuerzungsverzeichnis.tex`
> angelegt, `title.tex` mit Studiengang und Zweitprüfer ausgefüllt, `natger.bst`-Zitierstil gegen
> die offizielle Fakultäts-LaTeX-Vorlage abgeglichen (identisch). **Offener Compliance-Punkt seit
> damals:** KI-Nutzung ist laut Vorgabe per Fußnote im Text zu dokumentieren, siehe
> [[Offene-Fragen]].

## Kapitelstruktur (Stand 04.10.2026)

Seit dem 04.10.2026 nur noch **zwei Gliederungsebenen** (x.y), keine Unterabschnitte mehr.
Inhaltsverzeichnis: 7 Kapitel, 29 Abschnitte (vorher 79 Einträge). Ziel **40 Seiten** Fließtext,
harte Obergrenze 45. Seiten gemessen ohne Todo-Notizen über `measure.tex`. Details und alle
Entscheidungen in `thesis/Schreibstand.md` im Repo.

| Nr. | Kapitel | Budget | Ist 04.10. | Abschnitte |
|---|---|---|---|---|
| 01 | Einleitung | 5 | 5 | 1.1 Unternehmenskontext · 1.2 Ausgangslage · 1.3 Zielsetzung und Forschungsfragen · 1.4 Abgrenzung · 1.5 Aufbau |
| 02 | Grundlagen und Stand der Technik | 5 | 5 (nach Überarbeitung 2.1 eher 5,5) | 2.1 Geschäftsprozesse und CRQ · 2.2 Regelbasierte Automatisierung · 2.3 Datenqualität und Validierung · 2.4 Architektur- und Sicherheitsprinzipien · 2.5 Bestehende Lösungsansätze |
| 03 | Vorgehen und Methodik | 2 | 2 | 3.1 Forschungslogik und Erhebung · 3.2 Entwurfs- und Entscheidungsverfahren |
| 04 | Ist-Analyse und Anforderungen | 5 | 5 | 4.1 Bestehender Prozess · 4.2 Schwachstellenanalyse · 4.3 Anforderungen und Priorisierung |
| 05 | Architektur und Realisierung | 10 | 8 | 5.1 Architektur und Technologie · 5.2 Datenhaltung und Berechtigungen · 5.3 Erfassung und Validierung · 5.4 Regelbasierte Übertragung · 5.5 Interne Bearbeitung · 5.6 Sicherheit, Nachvollziehbarkeit, Betrieb |
| 06 | Evaluation und Diskussion | 9 | 4 | 6.1 Evaluationsdesign · 6.2 Technische Verifikation · 6.3 Effizienz und Datenqualität · 6.4 Automatisierungsgrad und Prozesssicherheit · 6.5 Beantwortung der Forschungsfragen · 6.6 Grenzen und kritische Reflexion |
| 07 | Zusammenfassung und Ausblick | 3 | Bauplan | 7.1 Zusammenfassung · 7.2 Ausblick (inkl. Übertragbarkeit) |

Hochgerechnet etwa **37 Seiten**, wenn Kapitel 6 und 7 im Budget bleiben.

### Checkliste

- [x] 01 Einleitung auf 5 Seiten gekürzt (04.10.2026), danach von Dennis Satz für Satz überarbeitet
  (Fallbeispiel nur noch in 4.2, Power-Apps-Anwendung gestrichen, Absatz zur Echtanbindung
  auskommentiert, Aufbau der Arbeit als Liste)
- [ ] 02 Grundlagen: Überarbeitung durch Dennis läuft (Stand 05.10.2026: bei 2.1)
  - [x] 2.1 neu formuliert: Übergänge zwischen den Begriffen, Prozesssicherheit von der
    Arbeitssicherheit abgegrenzt, definierte Begriffe fett
  - [x] 2.2 Fallbeispiel verweist auf 4.2
  - [ ] KI-Fußnote am Kapitelanfang fehlt seit der Überarbeitung, wieder einfügen
  - [ ] Seitenzahl für das Dumas-Zitat in 2.1 nachtragen (`S.\,X`)
  - [ ] 2.3 bis 2.5 durchsehen
- [x] 03 Vorgehen: zwei Abschnitte, BPM-Zuordnung nur noch hier, ADR-Regel in 3.2
- [x] 04 Ist-Analyse: drei Abschnitte, Anforderungen verdichtet
  - [ ] in 4.2 „Nachrichten“ durch „E-Mails“ ersetzen
- [x] 05 Architektur und Realisierung: sechs Abschnitte, dreistufige ADR-Regel, Umsetzungstabelle
  in Anhang B
  - [ ] Screenshot GU-Formular (5.3)
  - [ ] PostgreSQL-Begründung und Kühnel/Deitelhoff (5.1), Grund für fehlende
    `isCurrent`-Versionierung (5.2)
- [ ] 06 Evaluation und Diskussion
  - [x] 6.2 Technische Verifikation
  - [x] 6.4 Automatisierungsgrad und Prozesssicherheit
  - [ ] 6.1 Evaluationsdesign an die Durchführung anpassen (Testpersonen, Zahl der Testfälle)
  - [ ] 6.3 Ergebnisse alt gegen neu, Gebrauchstauglichkeit über DIN EN ISO 9241-11
  - [ ] 6.5 Beantwortung der Forschungsfragen
  - [ ] 6.6 Grenzen und kritische Reflexion
- [ ] 07 Zusammenfassung und Ausblick (Bauplan steht, 3 Seiten)
- [ ] Falls die echte Schnittstelle zu Telefónica vor der Abgabe steht: alle Stellen anpassen
  (Liste in `Schreibstand.md`)

> [!info] Historische Planung
> Die Abschnitte oben zu den Ständen vom 16.09., 15.09., 02.09., 13.08. und 12.08.2026 zeigen
> frühere Gliederungen und Zielumfänge (zuletzt 56 Seiten). Sie sind durch die Tabelle in diesem
> Abschnitt ersetzt.
