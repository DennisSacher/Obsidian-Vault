---
name: asiminu-session-start
description: Projekt-Session starten — liest und analysiert den kompletten AsiMiNu-Projektstand, bringt veraltete Dokumentation auf den neuesten Stand und gibt einen priorisierten Plan für die nächsten Schritte aus.
when_to_use: Aufrufen wenn der User mit der Arbeit am Projekt beginnen möchte, z.B. "lass uns anfangen", "ich möchte weiterarbeiten", "was ist der aktuelle Stand?", "starte die Session", "womit fangen wir an?"
allowed-tools: Read Glob Grep Edit Bash(git log *) Bash(git status *) Bash(git diff *)
---

Du startest eine neue Arbeitssession am **AsiMiNu CRQ-Management-System** (Bachelorarbeit-Projekt). Analysiere systematisch den gesamten Projektstand und bereite die Session vor.

## Aktueller Git-Stand

Letzte Commits:
!`git log --oneline -15`

Uncommitted Changes:
!`git status --short`

---

## Phase 1: Kern-Dokumente einlesen

Lies diese Dateien vollständig:

1. `STATUS.md` — Hauptfortschritts-Tracker des Projekts
2. `CLAUDE.md` — Projektanweisungen, insbesondere den Abschnitt „⚠️ Offene To-Dos"
3. Das neueste Arbeitsprotokoll: Suche mit Glob nach `docs/Bachelorarbeit/arbeitsprotokolle/*.md`, sortiere nach Dateiname absteigend und lies das neueste

---

## Phase 2: Codebase-Abgleich und Dokumentations-Update

**Seit 01.09.2026 gilt eine Archiv-Pflicht statt Inline-Durchstreichen** — `CLAUDE.md` und
`STATUS.md` werden bei jeder Session automatisch/vollständig gelesen und sollen deshalb nur enthalten,
was noch aktiv etwas verlangt. Erledigte Einträge bleiben **nicht** als `~~Text~~` stehen, sondern
werden verschoben:
- erledigte `CLAUDE.md`-Todos → ans Ende von `docs/Bachelorarbeit/CLAUDE-todo-archiv.md` (mit Datum)
- erledigte `STATUS.md`-Punkte → ans Ende von `docs/Bachelorarbeit/STATUS-verlauf-archiv.md` (mit Datum)

Vergleiche die Kern-Dokumente mit dem git-Log und prüfe folgende Punkte:

**CLAUDE.md — Offene To-Dos:**
- Gibt es Einträge die längst erledigt sind (laut STATUS.md oder git-Log)?
- Falls ja: Eintrag mit `Read`/`Edit` aus `CLAUDE.md` entfernen und mit demselben Wortlaut + Datum
  ans Ende von `docs/Bachelorarbeit/CLAUDE-todo-archiv.md` anhängen (`Edit`-Tool, nicht überschreiben)

**STATUS.md:**
- Ist „Zuletzt aktualisiert" noch korrekt?
- Gibt es unter „Offene Punkte / Nächste Schritte" Punkte die laut git-Log bereits abgeschlossen wurden?
- Falls ja: Eintrag aus `STATUS.md` entfernen und mit ✅-Vermerk + Datum ans Ende von
  `docs/Bachelorarbeit/STATUS-verlauf-archiv.md` anhängen

Führe alle Korrekturen direkt durch. Melde welche Änderungen du vorgenommen hast — inklusive was ins
Archiv gewandert ist.

---

## Phase 3: Session-Zusammenfassung

Gib eine strukturierte Übersicht aus:

### Stand der letzten Session
Was wurde zuletzt gebaut? (Quellen: neuestes Arbeitsprotokoll + git-Log)

### Abgeschlossene Features (Gesamtübersicht)
Welche Hauptkomponenten sind vollständig fertiggestellt?

### Offene Punkte & bekannte Risiken
- Was steht laut STATUS.md noch aus?
- Gibt es Sicherheitsrisiken oder technische Schulden? (Beispiel: DevController noch aktiv, CORS AllowAnyOrigin etc.)

### Empfohlene nächste Schritte
Liste 2–3 konkrete, priorisierte Aufgaben für diese Session — mit kurzer Begründung warum diese als nächstes sinnvoll sind.
