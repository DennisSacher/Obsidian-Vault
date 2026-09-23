---
tags: [bachelorarbeit, planung]
erstellt: 2026-08-11
aktualisiert: 2026-09-16
---

# Kapitelplanung

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!tip] LaTeX-Dateien
> `Bachelorarbeit/thesis/BA-Text/latex-projekt/chapters/` → ein Ordner je Kapitel

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

## Kapitelstruktur

### 01 – Einleitung
**LaTeX:** `chapters/01/einleitung.tex` — **Status: alle fünf Abschnitte als Entwurf
ausformuliert (16.09.2026), warten auf Dennis' Durchsicht**

> [!warning] Der aktuelle Text steht noch nicht im LaTeX
> Die fertige Fassung liegt in
> `thesis/BA-Text/Arbeitsdokumente/Einleitung_Entwurf_v3_2026-09-16.docx`. Die `.tex` enthält
> weiterhin die ältere Fassung mit leerem Abschnitt 1.4. Der Einbau erfolgt erst nach der
> Durchsicht. Bis dahin ist die `.tex` **kein** gültiger Stand von Kapitel 1.

- [x] 1.1 Unternehmenskontext: BayFu und Telefónica — komplett neu geschnitten, erklärt jetzt
  den vollständigen fachlichen Ablauf einer AsiMiNu-Anfrage samt Rollen, Change-Request-Begriff
  und Vergütungsmodell. Neu dazu **Abbildung 1.1** (`figures/abb-1-1-prozessuebersicht.*`)
- [x] 1.2 Ausgangslage und Problemstellung — erklärt den Ablauf nicht mehr, sondern setzt beim
  Ist-Zustand an; rund 340 Wörter kürzer als vorher
- [x] 1.3 Zielsetzung und Forschungsfragen — Fragen unverändert im Wortlaut des Exposés,
  nur der Einstiegsabsatz neu
- [x] 1.4 Abgrenzung des Betrachtungsgegenstands — **erstmals ausformuliert**, ein Platzhalter
  bleibt: der Beitrag des Kollegen
- [x] 1.5 Aufbau der Arbeit — sieben statt neun Kapitel

**Offen bei Kapitel 1:** keine einzige Literaturquelle in 1.1, Umfang bei knapp sechs statt
vier Seiten, Freigabe der BayFu für das Vergütungsmodell. Siehe [[Offene-Fragen]].

**Kernaussage:** Warum braucht Bayfu ein CRQ-Management-System, und was ist Gegenstand dieser
Arbeit?

### 02 – Grundlagen
**LaTeX:** `chapters/02/grundlagen.tex` — **Status: Gliederung mit sehr ausführlichen
Todo-Bauplänen**, 11 Unterabschnitte

CRQ-Begriffe, Prozessredesign, Automatisierungsgrade, Regeln und Konfiguration,
Qualitätsdimensionen, Validierung, Schichtung/Architekturprinzipien, Auth-Grundlagen und
Security, Low-Code, ITSM, Einordnung der Eigenlösung.

### 03 – Vorgehen
**LaTeX:** `chapters/03/vorgehen.tex` — **Status: Gliederung mit Todo-Bauplänen**, 3 Abschnitte
(neu als eigenständiges Kapitel in Variante D)

Forschungslogik, Erhebung des Ist-Zustands, Entscheidungsverfahren für die Architektur- und
Realisierungsentscheidungen.

### 04 – Ist-Analyse und Anforderungen
**LaTeX:** `chapters/04/ist_analyse_anforderungen.tex` — **Status: Gliederung mit sehr
ausführlichen Todo-Bauplänen**, 9 Abschnitte (führt die früheren Kapitel „Ist-Analyse" und
„Anforderungen" zusammen, weil die Anforderung die direkte Antwort auf die jeweilige
Schwachstelle ist)

Ablauf des bestehenden Prozesses, Akteure, Fehler bei der Erfassung, Medienbrüche, fehlende
Nachvollziehbarkeit, funktionale Anforderungen, nicht-funktionale Anforderungen,
rollenbezogene Anforderungen, Priorisierung.

### 05 – Architektur und Realisierung
**LaTeX:** `chapters/05/architektur_realisierung.tex` — **Status: Gliederung mit
Todo-Bauplänen**, 12 Abschnitte (5 aus dem ehemaligen Kapitel „Architektur" + 7 aus dem
ehemaligen Kapitel „Realisierung"), **am 16.09.2026 auf Wunsch des Betreuers aus zwei
Überkapiteln zu einem zusammengelegt** — reiner Strukturmerge, kein Inhalt gekürzt

Architektur-Teil: Systemkontext, Schichtenschnitt, Benutzermodell, Datentrennung,
Vorgangsidentität, Rollenmodell, Technologieauswahl (Techstack) — jeweils mit den erwogenen
Alternativen. Realisierungs-Teil: Aufbau, Formularentwurf, Fehlervermeidung,
Validierungsregeln, Vorgangsnummer, Regelbasis, Ausführungsmodell, Schnittstellenentwurf,
interne Bearbeitung (Admin-/ChangeCoordinator-Panel), Authentifizierung, Berechtigungen,
Prüfprotokoll, Betrieb. Drei **Tiefenschwerpunkte** laut Abstimmungsdokument: Backend/
serverseitige Validierung, TEF-Automatisierung, Sicherheit — dort ausführlicher als in den
übrigen Abschnitten. Größtes Kapitel (19 Seiten Zielumfang, 7+12).

> [!success] Damit geschlossen (waren vorher echte Lücken in der alten Struktur)
> ChangeCoordinator-Panel/TicketSpecialist-Rollenmodell und INC-Worker sind jetzt als reguläre
> Abschnitte vorhanden, nicht mehr nur im Code umgesetzt und in der Gliederung fehlend.

### 06 – Evaluation und Diskussion
**LaTeX:** `chapters/06/evaluation_diskussion.tex` — **Status: Evaluations-Teil vor der
Umstrukturierung teilweise ausformuliert** (~900 Wörter Methodik/Kennzahnen, Ergebnisse-Abschnitt
bewusst leer bis Testdurchläufe stattfinden), **Diskussions-Teil als Gliederung mit
Todo-Bauplänen**, zusammen 9 Abschnitte (5 Evaluation + 4 Diskussion), **am 16.09.2026 auf
Wunsch des Betreuers aus zwei Überkapiteln zu einem zusammengelegt** — reiner Strukturmerge, kein
Inhalt gekürzt

Evaluations-Teil: Kennzahlen, Testabdeckung, funktionale Abdeckung, Versuchsaufbau,
Messverfahren, Effekt auf Datenqualität, Automatisierung und Prozesssicherheit, Limitationen.
Diskussions-Teil: Beantwortung der sechs Forschungsfragen einzeln, Einordnung in den Stand der
Technik, Übertragbarkeit auf vergleichbare Prozesse, kritische Reflexion der eigenen Lösung.
Übernimmt zwei Inhalte aus dem aufgelösten früheren Kapitel „Herausforderungen": die Reflexion
des Scope-Zuwachses und die exemplarische Fehleranalyse (JWT-Signaturschlüssel-Bug als
Fallstudie).

- [x] Methodik des Vergleichs alt vs. neu
- [x] Kennzahlen (Bearbeitungszeit, Fehlerquote, Datenqualität, Kurzbefragung nach
  DIN EN ISO 9241-110)
- [ ] Ergebnisse und Diskussion — wartet auf Datenerhebung mit Bayfu-Mitarbeitenden

### 07 – Zusammenfassung und Ausblick
**LaTeX:** `chapters/07/zusammenfassung.tex` — **Status: Gliederung mit Todo-Bauplänen**,
2 Abschnitte (seit 16.09.2026 unter `chapters/07/` statt `chapters/09/`)

Zusammenfassung der Ergebnisse (ohne die Forschungsfragen zu wiederholen, das passiert in
Kapitel 06), Ausblick auf TEF-Echtanbindung, Streaming-Parser, objekt-level RBAC und weitere
offene Punkte aus `STATUS.md`.

### Anhang
**LaTeX:** `chapters/07/anhang.tex` (seit 16.09.2026 unter `chapters/07/` statt `chapters/09/`)
— unverändert, enthält u. a. Erhebungsinstrumente, Architekturentscheidungen im Volltext,
Screenshots, Quellcode-Auszüge und die gemäß den Vorgaben der Hochschule Rosenheim
verpflichtende Erklärung zur Verwendung generativer KI-Systeme (`chapters/07/ki_erklaerung.tex`).

---

## Schreibreihenfolge (Empfehlung, aktualisiert 16.09.2026)

1. Ist-Analyse und Anforderungen (04) — bekannter Prozess, direkte Grundlage für alles Weitere
2. Vorgehen (03) — kurz, direkt daraus ableitbar
3. Grundlagen (02) — Theorie nachziehen, wenn klar ist, was gebraucht wird
4. Architektur und Realisierung (05) — das Herzstück, parallel zum [[ADR-zu-Kapitel]]
5. Evaluation und Diskussion (06) — Evaluations-Teil sobald Testdurchläufe mit
   Bayfu-Mitarbeitenden stattgefunden haben, Diskussions-Teil setzt beides voraus
6. Einleitung (01) — ursprünglich für ganz zuletzt vorgesehen; wird seit 15.09.2026 als bewusste
   Ausnahme vorgezogen, weil vier von fünf Abschnitten bereits stehen und nur 1.4 neu ist
7. Zusammenfassung und Ausblick (07) — nach dem Rest

---

> [!success] Stand 23.09.2026 — Tatsächlicher Schreibstand (aus LaTeX-Dateien ermittelt)

| Nr. | Kapitel | Status | Anmerkung |
|---|---|---|---|
| 01 | Einleitung | ✅ vollständig ausformuliert | ~2.960 Wörter / ca. 6,6 Seiten; 5 `\todo`-Marker für offene Punkte (Quellen 1.1, BayFu-Freigabe, Anfragevolumen, Kollegenbeitrag) |
| 02 | Grundlagen | ✅ vollständig | Alle 11 Unterabschnitte ausformuliert. Abschnitt 2.4.1 (Schichtung/Clean Architecture) geschrieben mit Lano & Yassipour Tehrani 2023 (Springer) als Hauptquelle. |
| 03 | Vorgehen | ✅ vollständig ausformuliert | Neu am 22.09.2026: alle 3 Abschnitte fertig (Forschungslogik, Erhebung Ist-Zustand, ADR-Entscheidungsverfahren) |
| 04 | Ist-Analyse und Anforderungen | 🔲 Todo-Baupläne | Nächstes Schreibziel, sehr ausführliche Baupläne vorhanden (249 Zeilen Struktur) |
| 05 | Architektur und Realisierung | 🔲 Todo-Baupläne | 532 Zeilen Struktur, inkl. Variante-D-Darstellungsprinzip und Verweissystem |
| 06 | Evaluation und Diskussion | 🔲 Konzept vorhanden, Daten fehlen | Evaluationskonzept mit Kennzahlen fertig (~900 Wörter); Datenerhebung noch nicht begonnen |
| 07 | Zusammenfassung und Ausblick | 🔲 Todo-Baupläne | 63 Zeilen, nur Gliederung |

**Hinweis:** `Schreibstand.md` im Repo ist für Kapitel 02 und 03 nicht mehr aktuell — ist nach dem Schreiben vom 22.09.2026 nachgezogen worden.

