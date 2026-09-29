---
name: thesis-session-end
description: Bachelorarbeit-Session beenden — erfasst alle Schreib-Änderungen, aktualisiert ADR-Coverage und Kapitelfortschritt in Obsidian, erstellt ein Tagesprotokoll im Vault und committet alles ins Repo.
when_to_use: Aufrufen wenn der User die Thesis-Arbeit für heute beenden möchte, z.B. "ich bin fertig", "session beenden", "tagesabschluss", "alles committen", "end of day", "für heute reicht es"
allowed-tools: Read Glob Grep Edit Write PowerShell Bash(git *)
---

Du beendest die heutige Bachelorarbeit-Session. Führe alle Phasen vollständig und der Reihe nach aus. Überspringe keine Phase.

---

## Phase 1: Heutige Änderungen erfassen

**1a) Git-Überblick:**

```powershell
Set-Location "C:\Users\DSacher\Desktop\Bachelorarbeit"
git status --short
git diff HEAD --stat
```

Notiere welche `.tex`-Dateien geändert wurden. Das sind die Kapitel, an denen heute gearbeitet wurde.

**1b) Geänderte LaTeX-Kapitel lesen:**

Lies alle `.tex`-Dateien die laut `git diff --stat` geändert wurden. Beachte:
- Neue Abschnitte die heute hinzugekommen sind
- Offene `% TODO`, `% FIXME` oder `% XXX` Kommentare im Text
- Abschnitte die noch als Platzhalter dastehen (z.B. `[PLATZHALTER]`, `\dots` an unpassender Stelle)

**1c) Wortanzahl-Delta schätzen:**

```powershell
# Wörter in allen Kapitel-TEX-Dateien (LaTeX-Befehle grob herausgefiltert)
Get-ChildItem "thesis\BA-Text\latex-projekt\chapters" -Recurse -Filter "*.tex" | ForEach-Object {
    $content = Get-Content $_.FullName -Raw
    # LaTeX-Befehle entfernen und Wörter zählen (Näherung)
    $text = $content -replace '\\[a-zA-Z]+\{[^}]*\}', ' ' -replace '\\[a-zA-Z]+', ' ' -replace '[{}%]', ' '
    $words = ($text -split '\s+' | Where-Object { $_ -ne '' }).Count
    [PSCustomObject]@{ Datei = $_.Name; Wörter = $words }
} | Sort-Object Datei | Format-Table
```

Vergleiche mit dem was im Obsidian-Kapitelplan als letzter Stand eingetragen ist.

---

## Phase 2: LaTeX-Qualitätsprüfung

Lies `thesis/BA-Text/latex-projekt/thesis.bib` und prüfe:
- Wurden heute im Text `\cite{...}` verwendet? Sind alle zitierten Keys auch in der `.bib`-Datei vorhanden?
- Gibt es unbenutzte `.bib`-Einträge?

Suche in den geänderten TEX-Dateien nach:
```powershell
Select-String -Path "thesis\BA-Text\latex-projekt\chapters\**\*.tex" -Pattern "TODO|FIXME|PLATZHALTER|XXX|cite\{\}" -Recurse
```

Liste alle Treffer auf — das sind Stellen die in einer späteren Session fertiggestellt werden müssen.

---

## Phase 3: Obsidian-Vault aktualisieren

Der Vault liegt unter `C:\Users\DSacher\Desktop\Obsidian-Vault\`. Lies zuerst alle relevanten Dateien, dann schreibe die Updates.

### 3a) ADR-Coverage automatisch aktualisieren

Grepe alle Kapitel-TEX-Dateien nach ADR-Erwähnungen:

```powershell
$gefundeneAdrs = Get-ChildItem "thesis\BA-Text\latex-projekt\chapters" -Recurse -Filter "*.tex" |
    Select-String -Pattern "ADR-\d{3}" -AllMatches |
    ForEach-Object { $_.Matches.Value } |
    Sort-Object -Unique
$gefundeneAdrs
```

Lies dann `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\ADR-zu-Kapitel.md`.

Für jede gefundene ADR-Nummer die dort noch als `⬜` markiert ist: setze sie auf `🔶` (erwähnt). Falls eine ADR heute erstmals ausführlich erklärt und diskutiert wurde (nicht nur als Referenz): setze sie auf `✅`.

Schreibe die aktualisierte `ADR-zu-Kapitel.md` mit dem Edit-Tool.

Aktualisiere am Ende der Datei auch die Auswertungszeilen:
```
- **Behandelt (✅):** [neue Zahl]
- **Erwähnt (🔶):** [neue Zahl]
- **Noch offen (⬜):** [neue Zahl]
```

### 3b) Kapitelplanung.md aktualisieren

Lies `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Kapitelplanung.md`.

Aktualisiere den Status der heute bearbeiteten Kapitel in der Checkliste. Ersetze `[ ]` durch `[x]` für Abschnitte die heute fertiggestellt wurden. Ergänze neue `- [ ]`-Punkte für Lücken die beim Schreiben aufgefallen sind.

Schreibe die aktualisierte Datei mit dem Edit-Tool.

### 3c) Offene-Fragen.md ergänzen

Lies `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Offene-Fragen.md`.

Ergänze neue offene Fragen die beim Schreiben aufgekommen sind — insbesondere:
- Inhaltliche Fragen für den Betreuer
- Literatur die noch gefunden werden muss
- Technische Details des Projekts die noch verifiziert werden müssen
- Unklarheiten in der Argumentationskette

Schreibe die ergänzte Datei mit dem Edit-Tool.

### 3d) Ideen.md ergänzen

Lies `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Ideen.md`.

Hänge heute entstandene Gedanken im Format `DATUM — Gedanke` an. Quellen: was hat der User heute in den Kapiteln geschrieben, welche interessanten Zusammenhänge sind aufgefallen?

### 3e) Tagesprotokoll im Obsidian erstellen

**Neue Datei:** `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Arbeitsprotokolle\YYYY-MM-DD.md`

(Datum von heute einsetzen, Ordner anlegen falls er noch nicht existiert.)

Struktur:

```markdown
---
tags: [bachelorarbeit, protokoll]
datum: YYYY-MM-DD
---

# Arbeitsprotokoll – TT.MM.JJJJ

← zurück zu [[Bachelorarbeit AsiMinu App]]

## Was heute geschrieben / bearbeitet wurde

[Kapitel und Abschnitte die heute bearbeitet wurden — konkret und präzise]

## Fortschritt je Kapitel

| Kapitel | Vorher | Nachher | Delta (~Wörter) |
|---|---|---|---|
| [Kapitel] | [Status vorher] | [Status nachher] | [+N] |

## Neue ADR-Abdeckung

ADRs die heute erstmals im Text behandelt wurden: [Liste]

## Offene TODOs im Text

[Liste der `% TODO`-Kommentare und Platzhalter die aufgefallen sind]

## Neue offene Fragen

[Was ist heute unklar geworden?]

## Nächste Schritte für die nächste Session

1. [Konkrete Aufgabe mit Kapitel und Abschnitt]
2. [...]
3. [...]

## Submodul-Stand (AsiMinu)

[Letzter Commit-Hash und Commit-Message aus asiminu-projekt]
```

Erstelle diese Datei mit dem Write-Tool.

### 3f) Daily Note im Vault ergänzen

Der Vault führt zusätzlich ein **projektübergreifendes** Tageslogbuch unter
`C:\Users\DSacher\Desktop\Obsidian-Vault\05 Daily Notes\YYYY-MM-DD.md` (siehe
`Obsidian-Vault\CLAUDE.md`, Abschnitt „Session-Routinen" → „Bei Session-Ende"). Das ist
etwas anderes als das Bachelorarbeit-Tagesprotokoll aus 3e: die Daily Note deckt den
ganzen Tag über alle Projekte/Bereiche ab (nicht nur die Bachelorarbeit), das
Bachelorarbeit-Protokoll ist rein projektintern mit Kapitel-/ADR-Detailtabellen. Beide
sollen gepflegt werden, keins ersetzt das andere.

1. Prüfe mit `Test-Path`, ob `05 Daily Notes\YYYY-MM-DD.md` (heutiges Datum) schon existiert.
2. **Falls ja:** lies die Datei vollständig, bevor du sie änderst. Sie kann bereits Einträge
   zu anderen Projekten/Bereichen enthalten (Anonis, Werkstudent Bayfu, Crossfit, …) — die
   bleiben unangetastet. Ergänze nur einen eigenen Abschnitt/Bullet-Block zur
   Bachelorarbeit (klar als solcher erkennbar, z. B. unter einer Überschrift
   „Bachelorarbeit" oder als eigener Bullet-Block), mit dem Edit-Tool angehängt statt die
   Datei zu überschreiben.
3. **Falls nein:** lege sie neu an (Write-Tool) mit minimalem Frontmatter (`tags`, `date`)
   und einem Bachelorarbeit-Abschnitt — lass erkennbar Raum für andere Projekte, falls
   später am selben Tag ein weiterer Eintrag dazukommt.
4. Inhalt des Bachelorarbeit-Abschnitts: 2–5 knappe Bullet-Points, keine Kapitel-/ADR-Details
   (die stehen im Tagesprotokoll aus 3e, dorthin verlinken statt duplizieren) — nur was heute
   grob passiert ist und was als Nächstes ansteht, z. B.:
   ```markdown
   ## Bachelorarbeit
   - [Kurzzusammenfassung des Tages, 1-2 Sätze]
   - Details: [[Arbeitsprotokolle/YYYY-MM-DD]]
   - Nächster Schritt: [wichtigste offene Aufgabe]
   ```

---

## Phase 4: Bachelorarbeit-Repo committen und pushen

**4a) Änderungen staged:**

```powershell
Set-Location "C:\Users\DSacher\Desktop\Bachelorarbeit"
git add "thesis/"
git status --short
```

**4b) Commit erstellen:**

Erstelle einen einzigen, aussagekräftigen Commit. Die Message soll konkret benennen welche Kapitel und Abschnitte heute bearbeitet wurden.

Beispiele für gute Commit-Messages:
- `docs(thesis): Kapitel 03 Ist-Analyse vollständig ausgearbeitet`
- `docs(thesis): Kapitel 02 Abschnitt 2.2-2.4 Grundlagen ergänzt`
- `docs(thesis): Einleitung überarbeitet, Kapitel 05 begonnen`

**Commit-Regeln:**
- Kein `Co-Authored-By`
- `.claude/`-Dateien **nicht** committen
- Obsidian-Vault-Änderungen sind ein separates Repo und werden **nicht** hier committet

```powershell
git commit -m "docs(thesis): [HIER KONKRETE MESSAGE EINTRAGEN]"
```

**4c) Push:**

```powershell
git push origin main
```

---

## Phase 5: Session-Abschluss-Ausgabe

Gib eine kompakte Zusammenfassung:

### Was heute erreicht wurde
- Kapitel X: [was konkret]
- Neue ADRs im Text: [Liste]
- Wortanzahl-Delta: ~+N Wörter

### Obsidian-Updates
- ADR-zu-Kapitel.md: N ADRs von ⬜ auf 🔶/✅ gesetzt
- Kapitelplanung.md: Abschnitte X, Y, Z abgehakt
- Tagesprotokoll: `Arbeitsprotokolle/YYYY-MM-DD.md` erstellt
- Daily Note: `05 Daily Notes/YYYY-MM-DD.md` [neu angelegt / bestehenden Eintrag ergänzt]

### Nächste Session: Top-3-Aufgaben
1. [Konkrete Aufgabe]
2. [Konkrete Aufgabe]
3. [Konkrete Aufgabe]

### Commit
`[Commit-Hash]` — `[Commit-Message]`
