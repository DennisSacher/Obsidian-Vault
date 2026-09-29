---
name: thesis-session-start
description: Bachelorarbeit-Session starten — aktualisiert das AsiMinu-Submodul, liest den Thesis-Stand + alle Obsidian-Notizen, aktualisiert die Kapitelplanung zurück in Obsidian und erstellt einen Tagesprotokoll-Stub für heute.
when_to_use: Aufrufen wenn der User die Arbeit an der Bachelorarbeit beginnen möchte, z.B. "lass uns anfangen", "ich möchte an der Thesis weiterschreiben", "was ist der aktuelle Stand?", "starte die Session", "womit fange ich heute an?"
allowed-tools: Read Glob Grep Edit Write PowerShell Bash(git *)
---

Du startest eine neue Schreib-Session für die **Bachelorarbeit: AsiMinu CRQ-Management-System**. Arbeite alle Phasen der Reihe nach ab. Lies die Phasen zuerst vollständig durch, bevor du anfängst.

---

## Phase 0: AsiMinu-Submodul aktualisieren

```powershell
Set-Location "C:\Users\DSacher\Desktop\Bachelorarbeit"
$vorher = git -C asiminu-projekt rev-parse --short HEAD
git submodule update --remote --merge
$nachher = git -C asiminu-projekt rev-parse --short HEAD
if ($vorher -ne $nachher) {
    Write-Host "✅ Submodul aktualisiert: $vorher → $nachher"
    Write-Host "Neue Commits in AsiMinu:"
    git -C asiminu-projekt log --oneline "$vorher..$nachher"
    git commit -am "chore: AsiMinu-Submodul aktualisiert ($vorher → $nachher)"
    git push
} else {
    Write-Host "✅ Submodul bereits aktuell ($nachher) — kein Commit nötig"
}
```

Notiere welche neuen AsiMinu-Commits (falls vorhanden) für Thesis-Inhalte relevant sein könnten — insbesondere neue Features oder ADRs.

---

## Phase 1: Obsidian-Vault vollständig einlesen

Der Vault ist das Gedächtnis zwischen den Sessions. Lies **alle** folgenden Dateien vollständig:

**Planungsdokumente:**
- `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Kapitelplanung.md`
- `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\ADR-zu-Kapitel.md`
- `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Offene-Fragen.md`
- `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Zitate-und-Quellen.md`
- `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Ideen.md`

**Aktueller Stand und Rahmenbedingungen** (immer lesen, bevor Kapiteltext entsteht oder der Status bewertet wird — Gliederung, getroffene Entscheidungen, Schreibkonventionen, Status je Kapitel, offene Punkte):
- `C:\Users\DSacher\Desktop\Bachelorarbeit\thesis\Schreibstand.md`

**Fachlicher Kontext** (verbindliche Referenz für alle inhaltlichen Aussagen — tatsächlicher Prozessablauf einer AsiMiNu-Anfrage, Rollen, Entstehung des Projekts, Vergütungsmodell, Zukunftsvision, Glossar). Vollständig lesen, wenn heute Kapiteltext entsteht:
- `C:\Users\DSacher\Desktop\Bachelorarbeit\thesis\Fachlicher-Kontext-AsiMiNu.md`
- Kurzfassungen im Vault: `02 Projekte\Bachelorarbeit\AsiMiNu-Prozessablauf.md` und `AsiMiNu-Projekthintergrund.md`

**Schreibrichtlinien** (nur kurz gegenlesen, nicht jedes Mal vollständig zusammenfassen — dient als Erinnerung für die heutige Schreibarbeit):
- `C:\Users\DSacher\Desktop\Bachelorarbeit\thesis\Schreibrichtlinien-TH-Rosenheim.md`

**Letztes Tagesprotokoll aus Obsidian:**
Suche mit Glob nach `C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Arbeitsprotokolle\*.md`. Lies die **neueste** Datei vollständig. Extrahiere daraus:
- Den Abschnitt „Nächste Schritte für die nächste Session" — das sind die Aufgaben von gestern
- Den Abschnitt „Neue offene Fragen" — falls noch nicht in Offene-Fragen.md übertragen
- Den Gesamtfortschritt (Wortanzahl-Delta, Kapitelstatus)

Falls noch kein Protokoll existiert (erste Session): notiere das, überspringe diesen Schritt.

---

## Phase 2: Deadline und Git-Stand

```powershell
$deadline = [datetime]"2026-10-31"
$heute = [datetime]::Today
$tage = ($deadline - $heute).Days
$wochen = [math]::Floor($tage / 7)
Write-Host "Deadline: 31.10.2026 — noch $tage Tage ($wochen Wochen)"
```

```powershell
Set-Location "C:\Users\DSacher\Desktop\Bachelorarbeit"
git log --oneline -5
git status --short
```

---

## Phase 3: LaTeX-Kapitel analysieren und Obsidian aktualisieren

### 3a) Alle Kapitel lesen

Suche mit Glob alle `.tex`-Dateien in `thesis/BA-Text/latex-projekt/chapters/` (rekursiv). Lies jede Kapitel-Datei. Lies außerdem:
- `thesis/BA-Text/latex-projekt/thesis.bib`
- `thesis/BA-Text/latex-projekt/chapters/abstract.tex`

Bewerte je Kapitel:
- **Status**: `Leer` / `Gliederung` / `Teilweise` / `Vollständig` / `Überarbeitungsbereit`
- **~Wörter**: grobe Schätzung (LaTeX-Befehle nicht mitzählen)
- **TODO-Kommentare**: alle `% TODO`, `% FIXME`, `% XXX` im Text
- **Hauptlücken**: fehlende Abschnitte, Platzhalter

### 3b) Kapitelplanung.md in Obsidian aktualisieren

Lies die aktuelle `Kapitelplanung.md`. Vergleiche den darin eingetragenen Status je Kapitel mit dem was du gerade aus den TEX-Dateien gesehen hast.

Falls der Status eines Kapitels abweicht (z.B. du siehst dass Kapitel 03 jetzt "Teilweise" ist, aber in der Planung steht noch "Leer"): aktualisiere die Datei mit dem Edit-Tool.

Hänge außerdem unter dem entsprechenden Kapitel neue `- [ ]`-Punkte für frisch entdeckte Lücken an, falls du welche gefunden hast.

---

## Phase 4: ADR-Coverage prüfen und Obsidian aktualisieren

```powershell
$kapitelPfad = "C:\Users\DSacher\Desktop\Bachelorarbeit\thesis\BA-Text\latex-projekt\chapters"
Get-ChildItem $kapitelPfad -Recurse -Filter "*.tex" | ForEach-Object {
    Select-String -Path $_.FullName -Pattern "ADR-\d{3}" -AllMatches
} | ForEach-Object { $_.Matches } | ForEach-Object { $_.Value } | Sort-Object -Unique
```

Vergleiche mit `ADR-zu-Kapitel.md` aus Phase 1:
- ADRs die im Text stehen aber noch `⬜` sind → auf `🔶` setzen
- Aktualisiere die Auswertungszeilen am Ende der Datei

Schreibe Änderungen mit dem Edit-Tool in `ADR-zu-Kapitel.md`.

---

## Phase 5: Heutige Aufgaben festlegen und Protokoll-Stub erstellen

### 5a) Aufgaben ableiten

Leite die **2–4 konkreten Aufgaben für heute** ab aus:
1. Den „Nächste Schritte" des letzten Protokolls (höchste Priorität — Kontinuität)
2. Den offenen Fragen die heute beantwortet werden könnten
3. Dem Deadline-Druck (wie viele Wochen noch, wie weit ist die Thesis)
4. Logischen Abhängigkeiten (Kapitel 04 muss nicht auf Kapitel 02 warten)

Jede Aufgabe muss konkret sein:
- ❌ „Kapitel 02 schreiben"
- ✅ „Abschnitt 2.3 ‚Clean Architecture' ausarbeiten — ca. 400 Wörter, Quelle: ADR-007 + Robert Martin, Abhängigkeit: kein Vorgänger nötig"

### 5b) Protokoll-Stub in Obsidian anlegen

Erstelle eine neue Datei im Obsidian-Vault. Der Dateiname ist das heutige Datum:
`C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Arbeitsprotokolle\YYYY-MM-DD.md`

Erstelle den Ordner `Arbeitsprotokolle` mit PowerShell falls er noch nicht existiert:
```powershell
New-Item -ItemType Directory -Force "C:\Users\DSacher\Desktop\Obsidian-Vault\02 Projekte\Bachelorarbeit\Arbeitsprotokolle"
```

Inhalt des Stubs — fülle die Planungsabschnitte aus, lasse die Ergebnis-Abschnitte für thesis-session-end leer:

```markdown
---
tags: [bachelorarbeit, protokoll]
datum: YYYY-MM-DD
---

# Arbeitsprotokoll – TT.MM.JJJJ

← zurück zu [[Bachelorarbeit AsiMinu App]]

## Geplante Aufgaben (Session-Start)

1. [Aufgabe 1 — konkret]
2. [Aufgabe 2 — konkret]
3. [Aufgabe 3 — konkret]

## Was heute erreicht wurde
*(wird von thesis-session-end ausgefüllt)*

## Fortschritt je Kapitel
*(wird von thesis-session-end ausgefüllt)*

| Kapitel | Vorher | Nachher | Delta (~Wörter) |
|---|---|---|---|

## Neue ADR-Abdeckung
*(wird von thesis-session-end ausgefüllt)*

## Offene TODOs im Text
*(wird von thesis-session-end ausgefüllt)*

## Neue offene Fragen
*(wird von thesis-session-end ausgefüllt)*

## Nächste Schritte für die nächste Session
*(wird von thesis-session-end ausgefüllt)*

## Submodul-Stand (AsiMinu)
Commit: [aktueller Hash aus Phase 0]
```

Erstelle diese Datei mit dem Write-Tool.

---

## Phase 6: Session-Ausgabe

Gib eine kompakte, strukturierte Übersicht aus:

### 🔄 Submodul
Welche neuen AsiMinu-Features sind seit der letzten Session dazugekommen? (oder: „Kein Update — Stand unverändert")

### ⏰ Deadline
`Noch N Tage (X Wochen)` — kurze Einschätzung ob der Fortschritt realistisch ist.

### 📋 Kapitel-Übersicht

| Kapitel | Titel | Status | ~Wörter | Hauptlücken |
|---|---|---|---|---|
| 01 | Einleitung | ... | ... | ... |
| 02 | Grundlagen | ... | ... | ... |
| 03 | Vorgehen | ... | ... | ... |
| 04 | Ist-Analyse und Anforderungen | ... | ... | ... |
| 05 | Architektur und Realisierung | ... | ... | ... |
| 06 | Evaluation und Diskussion | ... | ... | ... |
| 07 | Zusammenfassung und Ausblick | ... | ... | ... |

### 📌 ADR-Coverage
`N/52 ADRs im Text (✅ X vollständig | 🔶 Y erwähnt | ⬜ Z noch offen)`

### ❓ Offene Fragen für heute
Relevante Punkte aus `Offene-Fragen.md` die heute beantwortet/angegangen werden könnten.

### 💡 Ideen im Blick
Falls in `Ideen.md` etwas steht das für die heutige Schreibarbeit nützlich ist — kurz erwähnen.

### 📚 Literatur-Lücken
Falls in `Zitate-und-Quellen.md` für ein heute geplantes Kapitel noch keine Quellen eingetragen sind — darauf hinweisen.

### ✅ Aufgaben für heute
Die 2–4 konkreten Aufgaben aus Phase 5a — die auch ins Protokoll-Stub eingetragen wurden.

### 📝 Protokoll angelegt
`Obsidian: Arbeitsprotokolle/YYYY-MM-DD.md erstellt — wird von /thesis-session-end ausgefüllt`
