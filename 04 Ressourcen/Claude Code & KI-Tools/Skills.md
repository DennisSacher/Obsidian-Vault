---
tags: [ressource, claude-code, skills]
status: aktiv
date: 2026-09-29
---

# Skills

Zentrale Bibliothek aller eigenen und übernommenen Claude-Code-Skills. Die Skill-Ordner liegen unter `Skills/` direkt neben dieser Notiz und sind das Original. Installiert wird über den Skill `skills-verwalten`, z. B. mit "installiere grill-me in dieses Repo" oder "richte meine Skills ein".

Gehört zu [[Claude Code & KI-Tools]].

## Regeln

- **Global** und im **Vault** sind Skills Junctions auf die Bibliothek. Änderungen wirken sofort überall.
- In **anderen Repos** sind Skills Kopien, die dort mit-committet werden. Wird eine Kopie geändert, bietet Claude an, die Änderung zurück in die Bibliothek zu spielen.
- Skill-Namen sind in der ganzen Bibliothek eindeutig.
- Laufzeit-Dateien (`.venv/`, `__pycache__/`, `node_modules/`) sind per `.gitignore` ausgeschlossen und werden per Setup neu erzeugt.
- Der Ordner `Skills/` ist in Obsidian unter "Excluded files" eingetragen, damit die technischen Dateien Suche und Graph nicht zumüllen.
- Die Anthropic-Skills (docx, pdf, pptx usw.) sind nicht hier, die synchronisiert die Claude-App selbst.
- Neuer Rechner: Vault klonen, Claude im Vault starten, "richte meine Skills ein" sagen.

## Verzeichnis

| Name | Beschreibung | Herkunft | Standard-Ziel |
|---|---|---|---|
| skills-verwalten | Bibliothek verwalten: installieren, Rechner einrichten, Änderungen zurückspielen | eigen | global |
| grill-me | Löchert mit Fragen zu einem Plan, bis ein gemeinsames Verständnis steht | eigen | global |
| excalidraw-diagram | Excalidraw-Diagramme, die visuell argumentieren, inkl. PNG-Rendering | angepasst von https://github.com/coleam00/excalidraw-diagram-skill | global |
| defuddle | Webseiten als sauberes Markdown extrahieren | vermutlich https://github.com/kepano/obsidian-skills (nicht verifiziert) | Vault |
| json-canvas | Obsidian-Canvas-Dateien (.canvas) erstellen und bearbeiten | vermutlich https://github.com/kepano/obsidian-skills (nicht verifiziert) | Vault |
| obsidian-bases | Obsidian Bases (.base) mit Views, Filtern, Formeln | vermutlich https://github.com/kepano/obsidian-skills (nicht verifiziert) | Vault |
| obsidian-cli | Vault über die Obsidian-CLI steuern | vermutlich https://github.com/kepano/obsidian-skills (nicht verifiziert) | Vault |
| obsidian-markdown | Obsidian Flavored Markdown (Wikilinks, Callouts, Embeds) | vermutlich https://github.com/kepano/obsidian-skills (nicht verifiziert) | Vault |
| asiminu-session-start | AsiMinu-Coding-Session starten | eigen | auf Anfrage (AsiMinu-Repo) |
| asiminu-session-end | AsiMinu-Coding-Session beenden, Doku und Commits | eigen | auf Anfrage (AsiMinu-Repo) |
| thesis-session-start | Bachelorarbeit-Schreibsession starten | eigen | auf Anfrage (BA-Repo) |
| thesis-session-end | Bachelorarbeit-Schreibsession beenden | eigen | auf Anfrage (BA-Repo) |

## Wo installiert (Stand 2026-09-29)

- **AsiMinu-Firmen-Repo** (`asiminu-projekt`, Bayfu Azure DevOps): enthält asiminu-session-start/-end unter den **alten Namen** `session-start`/`session-end`. Bewusst nicht umbenannt, weil es das Firmen-Repo ist.
- **BA-Repo**: thesis-session-start/-end als Kopie.

## Setup-Hinweise

- **excalidraw-diagram**: einmalig im Ordner `references/` des Skills `uv sync` und `uv run playwright install chromium` ausführen.
