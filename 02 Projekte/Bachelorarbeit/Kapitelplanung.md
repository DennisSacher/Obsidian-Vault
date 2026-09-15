---
tags: [bachelorarbeit, planung]
erstellt: 2026-08-11
aktualisiert: 2026-09-15
---

# Kapitelplanung

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!tip] LaTeX-Dateien
> `Bachelorarbeit/thesis/BA-Text/latex-projekt/chapters/` → ein Ordner je Kapitel

> [!important] Stand 15.09.2026 — Variante D umgesetzt, komplette Kapitelstruktur neu
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
**LaTeX:** `chapters/01/einleitung.tex` — **Status: Vier von fünf Abschnitten ausformuliert,
wird gerade final überarbeitet (Word-Arbeitsdokument seit 15.09.2026)**

- [x] 1.1 Unternehmenskontext: BayFu und Telefónica — Text vorhanden, wird gerade überarbeitet
  (u. a. Rolle des ChangeCoordinators ergänzen, Grafik GU→BayFu→TEF erwägen)
- [x] 1.2 Ausgangslage und Problemstellung — fertig, umfangreichster Abschnitt, ggf. beim
  Überarbeiten straffen
- [x] 1.3 Zielsetzung und Forschungsfragen — fertig (Hauptforschungsfrage + 6 Unterfragen)
- [ ] 1.4 Abgrenzung des Betrachtungsgegenstands — **neu in Variante D, noch komplett leer**,
  vier zu klärende Punkte: Systemgrenze TEF-System, Eigenleistung vs. Übernahme, nachträglicher
  Scope-Zuwachs, Abgrenzung zur Incident-Erfassung
- [x] 1.5 Aufbau der Arbeit — fertig (ein Absatz je Kapitel, laut Anforderung eigentlich ein
  einziger Absatz gewünscht)

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

### 05 – Architektur
**LaTeX:** `chapters/05/architektur.tex` — **Status: Gliederung mit Todo-Bauplänen**,
7 Abschnitte

Systemkontext, Schichtenschnitt, Benutzermodell, Datentrennung, Vorgangsidentität, Rollenmodell,
Technologieauswahl (Techstack) — jeweils mit den erwogenen Alternativen.

### 06 – Realisierung
**LaTeX:** `chapters/06/realisierung.tex` — **Status: Gliederung mit sehr ausführlichen
Todo-Bauplänen und Code-Platzhaltern**, 16 Abschnitte, größtes Kapitel (12 Seiten)

Aufbau, Formularentwurf, Fehlervermeidung, Validierungsregeln, Vorgangsnummer, Regelbasis,
Ausführungsmodell, Schnittstellenentwurf, interne Bearbeitung (Admin-/ChangeCoordinator-Panel),
Authentifizierung, Berechtigungen, Prüfprotokoll, Betrieb. Drei **Tiefenschwerpunkte** laut
Abstimmungsdokument: Backend/serverseitige Validierung, TEF-Automatisierung, Sicherheit — dort
ausführlicher als in den übrigen Abschnitten.

> [!success] Damit geschlossen (waren vorher echte Lücken in der alten Struktur)
> ChangeCoordinator-Panel/TicketSpecialist-Rollenmodell und INC-Worker sind jetzt als reguläre
> Abschnitte vorhanden, nicht mehr nur im Code umgesetzt und in der Gliederung fehlend.

### 07 – Evaluation
**LaTeX:** `chapters/07/evaluation.tex` — **Status: vor der Umstrukturierung teilweise
ausformuliert** (~900 Wörter Methodik/Kennzahlen, Ergebnisse-Abschnitt bewusst leer bis
Testdurchläufe stattfinden) — beim nächsten Bearbeiten gegenchecken, ob sich durch die neue
Gliederung an der Textmenge etwas geändert hat

Kennzahlen, Testabdeckung, funktionale Abdeckung, Versuchsaufbau, Messverfahren, Effekt auf
Datenqualität, Automatisierung und Prozesssicherheit, Limitationen.

- [x] Methodik des Vergleichs alt vs. neu
- [x] Kennzahlen (Bearbeitungszeit, Fehlerquote, Datenqualität, Kurzbefragung nach
  DIN EN ISO 9241-110)
- [ ] Ergebnisse und Diskussion — wartet auf Datenerhebung mit Bayfu-Mitarbeitenden

### 08 – Diskussion
**LaTeX:** `chapters/08/diskussion.tex` — **Status: Gliederung mit Todo-Bauplänen**,
4 Abschnitte, **komplett neues Kapitel in Variante D**

Beantwortung der sechs Forschungsfragen einzeln, Einordnung in den Stand der Technik,
Übertragbarkeit auf vergleichbare Prozesse, kritische Reflexion der eigenen Lösung. Übernimmt
zwei Inhalte aus dem aufgelösten früheren Kapitel „Herausforderungen": die Reflexion des
Scope-Zuwachses und die exemplarische Fehleranalyse (JWT-Signaturschlüssel-Bug als Fallstudie).

### 09 – Zusammenfassung und Ausblick
**LaTeX:** `chapters/09/zusammenfassung.tex` — **Status: Gliederung mit Todo-Bauplänen**,
2 Abschnitte

Zusammenfassung der Ergebnisse (ohne die Forschungsfragen zu wiederholen, das passiert in
Kapitel 08), Ausblick auf TEF-Echtanbindung, Streaming-Parser, objekt-level RBAC und weitere
offene Punkte aus `STATUS.md`.

### Anhang
**LaTeX:** `chapters/09/anhang.tex` — unverändert, enthält u. a. Erhebungsinstrumente,
Architekturentscheidungen im Volltext, Screenshots, Quellcode-Auszüge und die gemäß den Vorgaben
der Hochschule Rosenheim verpflichtende Erklärung zur Verwendung generativer KI-Systeme.

---

## Schreibreihenfolge (Empfehlung, aktualisiert 15.09.2026)

1. Ist-Analyse und Anforderungen (04) — bekannter Prozess, direkte Grundlage für alles Weitere
2. Vorgehen (03) — kurz, direkt daraus ableitbar
3. Grundlagen (02) — Theorie nachziehen, wenn klar ist, was gebraucht wird
4. Architektur (05) und Realisierung (06) — das Herzstück, parallel zum [[ADR-zu-Kapitel]]
5. Evaluation (07) — sobald Testdurchläufe mit Bayfu-Mitarbeitenden stattgefunden haben
6. Diskussion (08) — beantwortet die Forschungsfragen, setzt Realisierung und Evaluation voraus
7. Einleitung (01) — ursprünglich für ganz zuletzt vorgesehen; wird am 15.09.2026 als bewusste
   Ausnahme vorgezogen, weil vier von fünf Abschnitten bereits stehen und nur 1.4 neu ist
8. Zusammenfassung (09) — nach dem Rest
