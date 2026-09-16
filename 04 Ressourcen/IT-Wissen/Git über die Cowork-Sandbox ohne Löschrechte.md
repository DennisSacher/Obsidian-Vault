---
tags: [it-wissen, git, cowork]
status: aktiv
date: 2026-09-16
---

# Git über die Cowork-Sandbox ohne Löschrechte

Wenn Claude über die Cowork-Sandbox auf einen verbundenen Ordner zugreift, kann es dort
**Dateien lesen, schreiben und überschreiben, aber nicht löschen**. Jeder `rm`, `rmdir` oder
`unlink` scheitert mit `Operation not permitted`, auch bei Dateien, die Claude selbst angelegt
hat und die ihm laut Rechten gehören.

Das ist ärgerlich, weil Git ständig Sperrdateien anlegt und wieder entfernt.

## Das Symptom

```
warning: unable to unlink '.git/index.lock': Operation not permitted
fatal: Unable to create '.git/refs/heads/main.lock': File exists.
```

Bricht eine Git-Operation ab, etwa weil die Verbindung kurz weg war, bleibt die Sperrdatei
liegen. Danach ist jede weitere Schreiboperation blockiert, und weil Claude die Sperrdatei
nicht löschen kann, bleibt das Repo dauerhaft gesperrt.

## Was nicht hilft

Die Freigabe über `device_request_delete_permission` hat am 16.09.2026 mehrfach gemeldet,
Löschen sei jetzt erlaubt, funktioniert hat es trotzdem nicht. Auch ein Verschieben mit `mv`
auf ein anderes Dateisystem scheitert, weil `mv` dabei die Quelldatei entfernen muss.

## Was hilft

**1. Sperrdatei per Rename innerhalb desselben Ordners beiseiteräumen.** Ein Rename auf
demselben Dateisystem ist kein Löschvorgang und wird durchgelassen:

```bash
mkdir -p _to_delete
mv .git/index.lock "_to_delete/index.lock.$(date +%s)"
```

**2. Commit über Git-Plumbing bauen**, damit gar keine Sperrdatei auf dem Index nötig ist. Ein
temporärer Index außerhalb des verbundenen Ordners umgeht das Problem vollständig:

```bash
export GIT_INDEX_FILE=/tmp/mein-index
cp .git/index /tmp/mein-index
git add <pfade>
TREE=$(git write-tree)
OLD=$(git rev-parse HEAD)
COMMIT=$(git commit-tree "$TREE" -p "$OLD" -F /tmp/commit-message.txt)
```

**3. Den Branch-Zeiger von Hand schreiben**, weil `git update-ref` an seiner eigenen
`.lock`-Datei scheitert. `refs/heads/<branch>` ist eine simple Textdatei mit dem Commit-Hash,
und Überschreiben ist erlaubt:

```bash
printf '%s\n' "$COMMIT" > .git/refs/heads/main
printf '%s %s %s <%s> %s %s\tcommit: <text>\n' \
  "$OLD" "$COMMIT" "$(git config user.name)" "$(git config user.email)" \
  "$(date +%s)" "$(date +%z)" >> .git/logs/refs/heads/main
cp /tmp/mein-index .git/index
```

Der Reflog-Eintrag ist optional, aber ohne ihn fehlt der Commit in `git reflog`.

Danach mit `git log --oneline -3` und `git fsck --connectivity-only` gegenprüfen. Die
zurückbleibenden `tmp_obj_*`-Dateien unter `.git/objects/` und die verwaisten Commit-Objekte
aus Fehlversuchen sind harmlos und verschwinden bei der nächsten Garbage Collection.

## Zwei Stolperfallen dabei

**Commit-Nachricht in eine Datei schreiben** und mit `-F` übergeben. Ein mehrzeiliges Heredoc
innerhalb einer Kommandosubstitution in einer `&&`-Kette bricht gerne stillschweigend ab, und
mit unterdrücktem stderr sucht man lange.

**`git commit-tree` braucht eine Identität.** Ist im Repo keine gesetzt, bricht es mit
`Author identity unknown` ab. Statt die Konfiguration zu ändern, die Identität des letzten
Commits per Umgebungsvariable übernehmen:

```bash
export GIT_AUTHOR_NAME="$(git log -1 --format=%an)"
export GIT_AUTHOR_EMAIL="$(git log -1 --format=%ae)"
export GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
export GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
```

## Wenn Claude eine Datei löschen soll

Solange die Freigabe nicht greift, bleibt nur: in einen Unterordner `_to_delete/` im selben
verbundenen Ordner verschieben und Bescheid sagen, damit du den Ordner selbst leerst. Genau so
sind am 16.09.2026 mehrere verwaiste Sperrdateien im Bachelorarbeit-Repo und im Vault gelandet.

Siehe auch: [[Bachelorarbeit AsiMinu App]]
