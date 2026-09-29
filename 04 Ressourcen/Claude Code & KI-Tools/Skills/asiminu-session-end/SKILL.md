---
name: asiminu-session-end
description: AsiMinu-Coding-Session beenden — aktualisiert STATUS.md/CLAUDE.md (nur echte offene Punkte, Erledigtes wandert ins Archiv statt sich anzuhäufen), legt bei Bedarf Erweiterungsdokument/ADR an, schreibt ein Tagesprotokoll und committet/pusht.
when_to_use: Aufrufen wenn der User eine AsiMinu-Coding-Session beenden möchte, z.B. "ich bin fertig", "session beenden", "alles committen und pushen", "tagesabschluss", "end of day"
allowed-tools: Read Glob Grep Edit Write PowerShell Bash(git *)
---

Du beendest die heutige AsiMinu-Coding-Session. Führe alle Phasen vollständig und der Reihe nach aus.

**Grundregel dieses Skills (seit 01.09.2026):** `STATUS.md` und `CLAUDE.md` werden bei jeder Session
automatisch/vollständig gelesen — sie bleiben deshalb absichtlich schlank. Neue offene Punkte kommen
kurz und knapp hinein; erledigte Punkte werden **nicht** inline durchgestrichen und behalten, sondern
mit Datum in die passende Archiv-Datei verschoben und aus `STATUS.md`/`CLAUDE.md` gelöscht:
- `docs/Bachelorarbeit/STATUS-verlauf-archiv.md` — für `STATUS.md`
- `docs/Bachelorarbeit/CLAUDE-todo-archiv.md` — für `CLAUDE.md`

---

## Phase 1: Heutige Änderungen erfassen

```powershell
Set-Location "C:\Users\DSacher\Desktop\Bachelorarbeit\asiminu-projekt"
git status --short
git diff HEAD --stat
git log --oneline -10
```

Verschaffe dir einen Überblick: welche Features/Bugfixes/Refactorings sind heute entstanden, welche
Dateien wurden angefasst, gibt es neue ADRs oder architektonische Entscheidungen.

---

## Phase 2: STATUS.md aktualisieren

Lies `STATUS.md` vollständig (jetzt kompakt: Infrastruktur/Backend/Auth-Datenmodell/Tech-Stack +
„Offene Punkte").

1. **Erledigte Punkte archivieren:** Für jeden `- [ ]`-Punkt unter „Offene Punkte / Nächste Schritte",
   der laut Git-Log/Code heute (oder in einer früheren, nicht dokumentierten Session) erledigt wurde:
   aus `STATUS.md` entfernen, mit `✅ erledigt (DATUM)` + kurzer Begründung ans Ende von
   `docs/Bachelorarbeit/STATUS-verlauf-archiv.md` anhängen.
2. **Neue offene Punkte ergänzen:** Was ist heute neu liegen geblieben (nicht verifiziert, bewusst
   zurückgestellt, TODO im Code)? Als knappen `- [ ] **Titel** *(DATUM)* — ein Satz` in „Offene Punkte"
   ergänzen. Keine mehrzeiligen Prosa-Blöcke — Details gehören ins Tagesprotokoll (Phase 5) oder ein
   Erweiterungsdokument (Phase 6), hier nur der Verweis.
3. **`Zuletzt aktualisiert`** auf das heutige Datum setzen.
4. Falls sich evergreen-Fakten geändert haben (neue NuGet-Pakete, neue Migration, Tech-Stack-Wechsel):
   die passende Sektion oben (Infrastruktur/.NET Backend/Auth-Datenmodell/Technischer Stack) direkt
   pflegen — das sind Dauerzustände, kein Session-Log.

---

## Phase 3: CLAUDE.md aktualisieren

Lies den Abschnitt „⚠️ Offene To-Dos" in `CLAUDE.md`.

1. **Erledigte Todos archivieren:** analog zu STATUS.md — Eintrag raus, mit Datum + Kurzfassung ans
   Ende von `docs/Bachelorarbeit/CLAUDE-todo-archiv.md` anhängen.
2. **Neue Todos ergänzen:** nur was tatsächlich noch etwas verlangt (offene externe Abhängigkeit,
   unverifizierter Zustand, bewusst zurückgestellte Entscheidung). Kompakt halten (siehe bestehende
   Einträge als Stilvorbild — ein Absatz, keine Debugging-Chronik). Ausführliche Analysen gehören in
   ein Erweiterungsdokument (Phase 6) und werden von dort aus verlinkt, nicht in `CLAUDE.md` ausgebreitet.
3. Falls sich `Key Files`, `Architecture` oder `Documentation` (ADR-Liste) durch die heutige Session
   geändert haben: dort ergänzen (neue Dateien, neue ADR-Zeile).

---

## Phase 4: ADR anlegen, falls heute eine architektonische Entscheidung getroffen wurde

Kriterium: eine bewusste Wahl zwischen mehreren Alternativen mit Begründung (nicht jeder Bugfix).
Falls ja:

```powershell
Get-ChildItem "docs\Bachelorarbeit" -Filter "ADR-*.md" | Sort-Object Name -Descending | Select-Object -First 1
```

Nächste freie Nummer verwenden. Datei `docs/Bachelorarbeit/ADR-0XX-kebab-case-titel.md` anlegen
(Struktur wie bestehende ADRs: Kontext, Entscheidung, Begründung, Alternativen, Datum). In `CLAUDE.md`
unter „Documentation" → ADR-Liste mit einer Zeile ergänzen.

---

## Phase 5: Tagesprotokoll erstellen

Neue Datei `docs/Bachelorarbeit/arbeitsprotokolle/YYYY-MM-DD-tagesprotokoll.md` (heutiges Datum, Muster
der bestehenden Dateien in diesem Ordner beachten — Read eine aktuelle Datei als Vorlage, bevor du
schreibst). Inhalt: was wurde gebaut, welche Dateien, welche Entscheidungen, welche Tests, was ist
offen für die nächste Session. Das ist der Ort für die ausführliche Erzählung — nicht `STATUS.md`.

---

## Phase 6: Erweiterungsdokument anlegen (nur bei substanziellen Sessions)

Falls die Session ein neues Feature oder einen größeren Umbau enthielt (nicht bei reinen Bugfixes/
Kleinigkeiten): `docs/05-implementierung/erweiterungen-YYYY-MM-DD.md` anlegen (Muster: bestehende
Dateien in diesem Ordner), mit Code-Beispielen/Begründungen. Von `CLAUDE.md`/Tagesprotokoll aus
verlinken statt Inhalte zu duplizieren.

---

## Phase 7: Committen und pushen

**Commit-Konvention dieses Repos:** Conventional Commits, `typ(scope): kurze Beschreibung` — siehe
`git log --oneline -15` für aktuelle Beispiele (`feat(...)`, `fix(...)`, `test(...)`, `docs:`,
`refactor(...)`, `chore(...)`).

```powershell
git add -A
git status --short
```

Ein oder mehrere logisch getrennte Commits (nicht alles in einen Wurf, wenn mehrere unabhängige
Themen bearbeitet wurden). Kein `Co-Authored-By`.

```powershell
git commit -m "TYP(SCOPE): HIER KONKRETE MESSAGE"
git push origin main
```

---

## Phase 8: Session-Abschluss-Ausgabe

Gib eine kompakte Zusammenfassung:

### Was heute erreicht wurde
- [Feature/Fix X]: [was konkret]

### STATUS.md / CLAUDE.md
- N Punkte archiviert nach `STATUS-verlauf-archiv.md` / `CLAUDE-todo-archiv.md`
- N neue offene Punkte ergänzt

### Neue Dokumente
- Tagesprotokoll: `docs/Bachelorarbeit/arbeitsprotokolle/YYYY-MM-DD-tagesprotokoll.md`
- [Erweiterungsdokument / ADR, falls angelegt]

### Commits
- `[Hash]` — `[Message]`

### Nächste Session: Top-Aufgaben
1. [Konkrete Aufgabe]
2. [Konkrete Aufgabe]
