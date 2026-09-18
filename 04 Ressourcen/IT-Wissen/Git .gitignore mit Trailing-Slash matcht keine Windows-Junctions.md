---
tags: [ressource, git]
status: aktiv
date: 2026-09-02
---

# Git .gitignore mit Trailing-Slash matcht keine Windows-Junctions/Symlinks

## Die Erkenntnis

Ein `.gitignore`-Eintrag mit abschließendem `/` (z. B. `ordner/`) matcht laut Git-Spezifikation
nur echte Verzeichnisse. Eine Windows-Junction (`mklink /J`) behandelt Git aber wie einen
Symlink, auch wenn sie auf ein Verzeichnis zeigt. Der Trailing-Slash-Pattern greift deshalb
nicht, obwohl der Pfad exakt stimmt.

## Das Fehlerbild

`git status --short` zeigt den Junction-Ordner trotz `.gitignore`-Eintrag als `??` (untracked)
an. `git check-ignore -v <pfad>` liefert keinen Treffer (exit 1), obwohl derselbe Pfad ohne
Slash sofort matcht.

## Die Lösung

Trailing-Slash im `.gitignore`-Eintrag weglassen: `ordner` statt `ordner/`. Ohne Slash matcht
das Pattern unabhängig vom Dateisystem-Typ (Verzeichnis, Symlink, Junction).

## Wann das für dich relevant wird

Immer wenn ein Ordner in einem Git-Repo über eine NTFS-Junction oder einen Symlink mit einem
anderen Ort verknüpft ist und genau dieser Ordner vom Git-Tracking ausgeschlossen werden soll,
zum Beispiel weil dort ein eigenes, verschachteltes Git-Repo liegt.

## Fundstelle

Obsidian-Vault, `02 Projekte/Bachelorarbeit/Repo` (Junction zum separaten Bachelorarbeit-Repo,
eingerichtet 02.09.2026): `.gitignore`-Eintrag mit Trailing-Slash griff nicht, nach Entfernen
des Slashes von `git check-ignore -v` sofort bestätigt.
