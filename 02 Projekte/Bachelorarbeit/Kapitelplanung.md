---
tags: [bachelorarbeit, planung]
erstellt: 2026-08-11
---

# Kapitelplanung

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!tip] LaTeX-Dateien
> `Bachelorarbeit/thesis/BA-Text/latex-projekt/chapters/` → ein Ordner je Kapitel (Pfad seit
> der Submodul-Umstellung im August um `BA-Text/` erweitert)

> [!important] Stand 02.09.2026 — Gliederung erweitert, Status-Tracking ins Dashboard gewandert
> Die Kapitelgliederung wurde am 01.09.2026 deutlich erweitert (Commit `d6d1841`): Kapitel 05
> hat jetzt **7 statt 5 Sektionen** — die unten unter „Echte Lücken" genannten fehlenden
> Sektionen **ChangeCoordinator-Panel/CRQ-Chat** und **TEF-Automatisierung** sind damit
> geschlossen, existieren jetzt als eigene `\section`. Alle Todo-Blöcke in Kapitel 2–9 wurden
> außerdem sehr ausführlich mit ADR-Verweisen befüllt. Der echte Abgabetermin ist **22.10.2026**
> (nicht die weiter unten in diesem Dokument genannten 31.10.2026 — das war eine vorläufige
> Angabe), harte Schreibfrist zum Schreiben selbst: **12.10.2026**.
>
> Die „Status: …"-Zeilen je Kapitel unten sind ab jetzt **nicht mehr die aktuelle
> Wahrheit** — dafür gibt es seit heute `thesis/dashboard/` (automatisch generiertes
> Dashboard, berechnet Status/Seiten/Ampeln/Tagesempfehlung direkt aus den `.tex`-Dateien).
> Die inhaltlichen Notizen unten (Quellmaterial, ADR-Bezüge, Lücken-Analyse,
> Schreibreihenfolge) bleiben trotzdem wertvoll und werden nicht dupliziert.

> [!warning] Stand 13.08.2026 — Zwei Sessions in Folge ohne Kapiteltext
> Weder am 11.08. noch am 12.08. wurde an Kapitel 03 weitergeschrieben (12.08. war reine Formalia-Session). Kapitel 03 bleibt seit Beginn der Planung unverändert auf „Gliederung". Bei 79 verbleibenden Tagen bis zur Deadline (31.10.2026) sollte diese Session tatsächlich Kapiteltext produzieren, sonst wächst der Rückstand weiter (6 von 9 Kapiteln noch reine Gliederung).
> - Neu entdeckt beim Gegenlesen von `ist_analyse.tex`: In Abschnitt „Prozessbeschreibung" steht als einziger Fließtext das Wort „hi" (offenbar ein alter Test-Platzhalter) — beim Ausformulieren von 03.1 entfernen.
> - AsiMinu-Submodul aktualisiert (`4182ae3` → `fd9d8d6`): neue Chatfunktion im CRQ (inkl. Ungelesen-Benachrichtigungen in CC-/GU-Panel) und Automatisierungsseite mit einstellbaren Uhrzeiten für automatische Läufe — für Kapitel 05 (Entwurf/Realisierung) und ggf. Kapitel 04 (Anforderungen) relevant, bisher nirgends in der Kapitelplanung berücksichtigt.
>
> [!info] Stand 12.08.2026 — Formale Vorgaben eingearbeitet
> Dennis hat die offiziellen TH-Rosenheim-Schreibrichtlinien nachgereicht (siehe [[Wissenschaftliches Arbeiten]]). Kein Kapiteltext wurde heute geschrieben, aber die LaTeX-Struktur wurde daraufhin angepasst:
> - Neues Pflicht-Verzeichnis `chapters/abkuerzungsverzeichnis.tex` angelegt und in `toc.tex` eingebunden (Position v der vorgeschriebenen Verzeichnis-Reihenfolge, war komplett gefehlt — auch die offizielle Fakultätsvorlage hat es nicht, ist aber laut Formvorgaben-PDF Pflicht). Bisher nur CRQ/GU/TEF eingetragen — muss mit jedem neuen Kapitel wachsen.
> - `title.tex`: Platzhalter „Studiengang" und „Zweitprüfer" sind jetzt ausgefüllt (Informatik B.Sc., Prof. Dr. rer. pol Laura Marcus)
> - `natger.bst`-Zitierstil gegen die offizielle Fakultäts-LaTeX-Vorlage (ZIP) abgeglichen — identisch, keine Änderung nötig
> - **Offener Compliance-Punkt:** KI-Nutzung ist laut Vorgabe per Fußnote im Text zu dokumentieren, das fehlt bisher komplett (auch in Kapitel 01, das mit KI-Unterstützung entstand) — siehe [[Offene-Fragen]]

## Kapitelstruktur

### 01 – Einleitung
**LaTeX:** `chapters/01/einleitung.tex` — **Status: Vollständig (Entwurf)**, ~1500 Wörter

- [x] Motivation / Problemstellung
- [x] Zielsetzung der Arbeit (inkl. Hauptforschungsfrage + 6 Unterfragen)
- [x] Aufbau der Arbeit

**Kernaussage:** Warum braucht Bayfu ein CRQ-Management-System?

> [!success] Stand 11.08.2026
> Kapitel ist durchgeschrieben (5 Sektionen, kein `\todo`). Kandidat für Überarbeitung/Feinschliff statt Neuschreiben.

---

### 02 – Grundlagen
**LaTeX:** `chapters/02/grundlagen.tex` — **Status: Gliederung** (nur `\todo[inline]`-Stichpunkte, keine Prosa)

- [ ] Change-Request-Management (ITIL-Kontext) — Sektion „Geschäftsprozessmanagement und Automatisierung"
- [ ] Clean Architecture (theoretisch) — Sektion „Softwarearchitekturprinzipien"
- [ ] Authentifizierung/Autorisierung/IT-Sicherheit (JWT, TOTP, RBAC) — Sektion „Security-Grundlagen"
- [ ] Datenqualität und Eingabevalidierung
- [ ] Verwandte Lösungsansätze (Power-Apps-Ad-hoc-Lösung)

> [!warning] Abweichung von dieser Planung
> „ASP.NET Core & Blazor WASM" und „Azure-Infrastruktur" sind **keine eigenen Sektionen** in `grundlagen.tex` — die konkrete Technologieauswahl liegt stattdessen in Kapitel 04 (`Technologieauswahl und Begründung`) und das Deployment in Kapitel 05 (`Deployment und Betrieb`). Kapitel 02 bleibt bewusst rein theoretisch/generisch.

---

### 03 – Ist-Analyse
**LaTeX:** `chapters/03/ist_analyse.tex` — **Status: Gliederung** (3 Sektionen mit `\todo[inline]`, keine Prosa)

- [ ] Aktueller Prozess bei Bayfu (manuell, Excel, E-Mail) — Sektion „Prozessbeschreibung" — Quellmaterial vorhanden: `docs/04-prozesse/crq-prozessbeschreibung.pdf`, `crq-gesamtprozess-uebersicht.svg`, BPMN-Dateien `docs/03-diagramme/bpmn/crq-creation-prozess.bpmn` + `admin-panel-functions.bpmn`
- [ ] Stakeholder und Rollen (GU, Bayfu-Mitarbeiter, TEF) — Sektion „Beteiligte Akteure"
- [ ] Schwachstellen und Verbesserungspotenziale — Sektion „Schwachstellenanalyse" (Fallbeispiel „ausgeblendete Excel-Zeilen" bereits in Kap. 01 vorweggenommen, muss hier vertieft werden)
- [ ] Beim Ausformulieren: Platzhaltertext „hi" in Sektion „Prozessbeschreibung" entfernen (Fundstelle 13.08.2026)

---

### 04 – Anforderungen & Architektur
**LaTeX:** `chapters/04/anforderungen_architektur.tex` — **Status: Gliederung** (5 Sektionen mit `\todo[inline]`, keine Prosa)

- [ ] Funktionale + nicht-funktionale Anforderungen — eine gemeinsame Sektion (nicht getrennt wie ursprünglich geplant)
- [ ] Rollenmodell (GU/Admin/Least-Privilege, ADR-002/ADR-015)
- [ ] Architekturentscheidung Clean Architecture (ADR-001, Vier-Schichten-Modell)
- [ ] Technologieauswahl (.NET 10, Blazor WASM, EF Core, PostgreSQL)
- [ ] Datenmodell (AMR-Nummer, Auth/CRQ-Trennung ADR-007, Advisory-Lock ADR-013)

> [!note] Fehlt noch als eigener Punkt
> Kein explizites C4-Modell-Unterkapitel und keine dedizierte Erklärung des ADR-Entscheidungsprozesses als eigener Abschnitt — ggf. beim Ausschreiben ergänzen oder bewusst weglassen.

---

### 05 – Entwurf & Realisierung
**LaTeX:** `chapters/05/entwurf_realisierung.tex` — **Status: Gliederung** (5 Sektionen mit `\todo[inline]` + Code-Platzhalter, keine Prosa)

- [ ] GU-Panel (Registrierung, CRQ-Formular, Folge-CRQ, Statusverfolgung)
- [ ] Backend-Service (Validierung, AMR-Vergabe, TEF-Stub ADR-009)
- [ ] Admin-Panel (Anträge, Benutzerverwaltung, Standort-Excel-Import ADR-025)
- [ ] Sicherheitskonzept (TOTP ADR-010, Provisioning ADR-002, Lockout ADR-019, Refresh-Token ADR-024)
- [ ] Deployment und Betrieb (Azure, Key-Vault-Präfix ADR-021, CI/CD, Bootstrap ADR-023)

> [!bug] Echte Lücken (nicht nur unausgeschrieben — fehlen als Sektion komplett)
> - [ ] **Implementierungsreihenfolge und Vorgehen** — keine eigene Sektion vorhanden
> - [ ] **ChangeCoordinator-Panel / TicketSpecialist-Rollenmodell** (ADR-047) — im Submodul seit 05.08.2026 fertig implementiert, in `entwurf_realisierung.tex` aber noch **gar nicht als Sektion** angelegt
> - [ ] **INC-Worker (Postfach-Integration)** (ADR-045) — ebenfalls implementiert, ebenfalls noch keine Sektion
> - [ ] Neu seit 11.08.2026 im Code: Operator-Rolle (ADR-053), Löschlauf (ADR-051), Prüfprotokoll (ADR-052) — noch nirgends in der Kapitelplanung berücksichtigt
> - [ ] Neu seit 12.08.2026 im Code (Submodul-Update 3311c97 → 4182ae3): Fassungsnummern und scharfe Qualitätstore (ADR-054), neuer `StandortController`, `PaketberichtController` — noch nicht in Kapitelplanung berücksichtigt
> - [ ] Neu seit 13.08.2026 im Code (Submodul-Update 4182ae3 → fd9d8d6): CRQ-Chatfunktion (inkl. Ungelesen-Benachrichtigungen in CC-/GU-Panel) und Automatisierungsseite mit einstellbaren Uhrzeiten für automatische Läufe — noch nicht in Kapitelplanung berücksichtigt

---

### 06 – Herausforderungen während der Entwicklung
**LaTeX:** `chapters/06/herausforderungen.tex` — **Status: Gliederung**

- [ ] Ausgewählte ADRs im Detail (z. B. ADR-013 Advisory-Lock, ADR-020 Postgres-Odyssee)
- [ ] Exemplarische Fehleranalyse (JWT-Signaturschlüssel-Bug als Fallstudie)
- [ ] Abweichungen vom ursprünglichen Konzept (AsiMinu-Dashboard-Erweiterung → eigenständiges System)

### 07 – Evaluation
**LaTeX:** `chapters/07/evaluation.tex` — **Status: Teilweise** (~900 Wörter Methodik/Kennzahlen ausformuliert, Ergebnisse-Abschnitt bewusst leer bis Testdurchläufe stattfinden)

- [x] Methodik des Vergleichs alt vs. neu (Testfallkatalog, Durchführung, Limitationen)
- [x] Kennzahlen (Bearbeitungszeit, Fehlerquote, Datenqualität, Kurzbefragung nach DIN EN ISO 9241-110)
- [ ] Ergebnisse und Diskussion — wartet auf Datenerhebung (Testdurchläufe mit Bayfu-Mitarbeitenden)

### 08 – Zusammenfassung und Ausblick
**LaTeX:** `chapters/08/zusammenfassung.tex` — **Status: Gliederung**

- [ ] Zusammenfassung der Ergebnisse
- [ ] Kritische Reflexion (TEF-Stub, begrenzter Evaluationsumfang)
- [ ] Ausblick (TEF-Echtanbindung, Streaming-Parser, objekt-level RBAC, Domain-Whitelist)

### 09 – Anhang
**LaTeX:** `chapters/09/anhang.tex`, `chapters/09/ki_erklaerung.tex` — enthält u. a. die pflichtige KI-Nutzungserklärung der Hochschule Rosenheim

---

## Schreibreihenfolge (Empfehlung)

1. Ist-Analyse (03) — du kennst den Prozess am besten
2. Anforderungen (04) — direkt aus der Analyse ableitbar
3. Grundlagen (02) — Theorie nachziehen, wenn du weißt was du brauchst
4. Entwurf/Realisierung (05) — das Herzstück, parallel zum [[ADR-zu-Kapitel]]
5. Einleitung (01) — immer zuletzt, wenn du weißt was du geschrieben hast
6. Schluss — nach dem Rest
