---
name: skills-verwalten
description: Verwaltet Dennis' Skill-Bibliothek im Obsidian-Vault. Skills global oder in ein Repo installieren, einen neuen Rechner einrichten, Änderungen an installierten Skills zurück in die Bibliothek spielen, neue Skills in die Bibliothek aufnehmen und fremde Skills vom Original-Repo aktualisieren. Aufrufen bei Sätzen wie "lade/installiere Skill X in dieses Repo", "installiere X global", "richte meine Skills ein", "welche Skills habe ich", "übernimm die Änderung in die Bibliothek", "speicher diesen Skill in meiner Bibliothek", "aktualisiere Skill X", "gibt es Updates für meine Skills", oder immer dann, wenn ein Skill neu erstellt oder in einem Repo verändert wurde.
---

# Skill-Bibliothek verwalten

Dennis speichert alle eigenen und übernommenen Skills zentral in seinem Obsidian-Vault (Git-Repo `github.com/DennisSacher/Obsidian-Vault`). Die Bibliothek ist das Original. Installierte Skills sind Junctions (global, Vault) oder Kopien (andere Repos).

## Pfade

- **Vault:** Umgebungsvariable `OBSIDIAN_VAULT`. Ist sie nicht gesetzt: Dennis einmal nach dem Vault-Pfad fragen und sie dann dauerhaft setzen (`setx OBSIDIAN_VAULT "<pfad>"`, wirkt erst in neuen Shells, in der laufenden Session den Pfad direkt verwenden).
- **Bibliothek:** `$OBSIDIAN_VAULT/04 Ressourcen/Claude Code & KI-Tools/Skills/<name>/`
- **Übersicht:** `$OBSIDIAN_VAULT/04 Ressourcen/Claude Code & KI-Tools/Skills.md` (Tabelle mit Name, Beschreibung, Herkunft, Standard-Ziel). Immer zuerst lesen, sie ist das Verzeichnis.
- **Global:** `~/.claude/skills/<name>`
- **Vault-lokal:** `$OBSIDIAN_VAULT/.claude/skills/<name>` (in der Vault-.gitignore)
- **Repo:** `<repo>/.claude/skills/<name>`

## Installationsregeln

| Ziel | Art | Warum |
|---|---|---|
| global | Junction | Nur Dennis' Rechner, soll immer den aktuellen Bibliotheksstand haben |
| Vault | Junction | Keine Dopplung im selben Git-Repo |
| anderes Repo | Kopie | Skill soll Teil des Repos sein und mit-committet werden |

Junction anlegen (PowerShell):
```powershell
New-Item -ItemType Junction -Path "<ziel>\<name>" -Target "<bibliothek>\<name>"
```

**Achtung beim Entfernen einer Junction:** nur mit `cmd /c rmdir "<pfad>"` oder `(Get-Item "<pfad>").Delete()`. Niemals `rm -rf` oder `Remove-Item -Recurse`, das kann den Inhalt der Bibliothek löschen. Vorher mit `(Get-Item "<pfad>").LinkType` prüfen, ob es wirklich eine Junction ist.

Bevor ein bestehender Ordner am Ziel ersetzt wird: Inhalt mit der Bibliothek vergleichen (`diff -r`). Weicht er ab, Dennis die Unterschiede zeigen und fragen, ob sie zuerst in die Bibliothek übernommen werden sollen. Nichts ungefragt überschreiben.

## Abläufe

### Skill installieren
1. `Skills.md` lesen, Skill-Namen auflösen. Bei unklarem Namen nachfragen statt raten.
2. Ziel bestimmen: "global" → Junction nach `~/.claude/skills/`. "in dieses Repo" → Kopie nach `<aktuelles Repo>/.claude/skills/` (Laufzeit-Ordner wie `.venv/`, `__pycache__/`, `node_modules/` nicht mitkopieren).
3. Hat der Skill eine README mit Setup-Schritten (z. B. excalidraw-diagram: `uv sync` und `uv run playwright install chromium` im Ordner `references/`), Dennis fragen, ob das Setup jetzt laufen soll.
4. Hinweis geben: neue Skills sind erst in einer neuen Session verfügbar.

### Neuen Rechner einrichten ("richte meine Skills ein")
1. `OBSIDIAN_VAULT` prüfen bzw. setzen.
2. `Skills.md` lesen und alle Skills mit Standard-Ziel **global** als Junction nach `~/.claude/skills/` legen, alle mit Ziel **Vault** als Junction nach `$OBSIDIAN_VAULT/.claude/skills/`.
3. Setup-Schritte der installierten Skills ausführen (nach Rückfrage).
4. Ergebnis als Tabelle zeigen: Skill, Ziel, Status.

### Änderung zurück in die Bibliothek spielen
Wird ein **kopierter** Skill in einem Repo geändert, anbieten, die Änderung in die Bibliothek zu übernehmen: `diff -r` zeigen, nach Bestätigung zurückkopieren. Junctions brauchen das nicht, dort wird direkt die Bibliothek bearbeitet.

### Neuen Skill aufnehmen
Wenn ein Skill neu erstellt oder aus dem Netz übernommen wird:
1. In der Bibliothek anlegen (Ordnername = `name` im Frontmatter, eindeutig in der ganzen Bibliothek).
2. Zeile in `Skills.md` ergänzen: Name, Kurzbeschreibung, Herkunft (`eigen`, `angepasst von <URL>` oder `<URL>`), Upstream-Stand (bei fremden Skills Kurz-Hash und Datum des Original-Commits, sonst `–`), Standard-Ziel (`global`, `Vault`, `auf Anfrage`).
3. Gewünschtes Ziel installieren.

### Fremden Skill aktualisieren
Für Skills mit Herkunft `<URL>` oder `angepasst von <URL>` in `Skills.md`, z. B. bei "aktualisiere json-canvas" oder "gibt es Updates für meine fremden Skills?".
1. Original-Repo flach in ein temporäres Verzeichnis klonen (`git clone --depth 1 <URL> <temp>`) und den Skill-Ordner darin suchen (Ordner mit `SKILL.md` und passendem `name`). Kein `npx skills`, `git` reicht und führt keinen fremden Code aus.
2. Neuen Upstream-Commit (`git -C <temp> rev-parse --short HEAD`) mit der Spalte `Upstream-Stand` in `Skills.md` vergleichen. Gleich: "keine Updates" melden, fertig.
3. Unterschiede zeigen: `diff -r --strip-trailing-cr <temp>/<skill> <bibliothek>/<skill>`, Laufzeit-Ordner ignorieren.
   - **Herkunft `<URL>` (unverändert übernommen):** Diff kurz zusammenfassen, nach Bestätigung den Bibliotheksordner durch die neue Version ersetzen.
   - **Herkunft `angepasst von <URL>`:** Dennis' eigene Änderungen dürfen nicht verloren gehen. Wenn `Upstream-Stand` bekannt ist, den alten Upstream-Stand zusätzlich holen (`git clone` ohne `--depth` bzw. `git fetch --depth 50`) und per Drei-Wege-Vergleich trennen, was upstream geändert wurde und was Dennis geändert hat. Upstream-Änderungen übernehmen, Dennis' Änderungen behalten, Konflikte einzeln zeigen und fragen. Ohne bekannten Upstream-Stand: beide Seiten zeigen und Datei für Datei entscheiden lassen.
4. Nach dem Update `Upstream-Stand` in `Skills.md` auf den neuen Commit setzen. Hat sich an Setup-Dateien etwas geändert (z. B. `pyproject.toml`, `uv.lock`), anbieten, das Setup neu auszuführen.
5. Temporäres Verzeichnis löschen.

Bei "prüfe alle fremden Skills": Schritte 1 bis 3 für jeden fremden Skill, pro Repo nur einmal klonen, am Ende eine Tabelle zeigen (Skill, Stand alt, Stand neu, Änderungen ja/nein) und erst dann fragen, welche aktualisiert werden sollen.

### Abschluss
Änderungen an der Bibliothek liegen im Vault-Repo. Am Ende anbieten, sie dort zu committen und zu pushen. Kopien in anderen Repos werden im jeweiligen Repo committet.
