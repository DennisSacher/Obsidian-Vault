# Vault Context

Dieses Vault ist das Zweites Gehirn von Dennis Sacher.

## Über mich

Dennis Sacher, 25 Jahre alt, Informatik-Student (8. Semester, TH Rosenheim) und Werkstudent bei der Bayfu GmbH in Kolbermoor. Schreibt gerade seine Bachelorarbeit über die AsiMinu App (voraussichtlicher Abschluss Oktober 2026), programmiert hauptsächlich in C#/ASP.NET Core und baut sich nebenbei Expertise in KI und Finanzen auf, mit dem Ziel eigene Projekte bzw. eine eigene Firma zu starten. Ausführliches Profil in 00 Kontext/Über mich.md.

## Vault-Struktur

- 00 Kontext/: Persönliches Kontext-Profil (Über mich.md, ICP.md, Angebot.md, Schreibstil.md, Branding.md). Zentrale Referenz für alle inhaltlichen Aufgaben, insbesondere rund um das Projekt Anonis. Lies diese Dateien wenn du Content erstellst, Business-Themen bearbeitest oder Angebote formulierst.
- 01 Inbox/: Schnelle Gedanken, Brain Dumps, unverarbeitete Notizen. Alles was noch keinen festen Platz hat landet hier.
- 02 Projekte/: Aktive Projekte mit konkretem Ziel und Enddatum (aktuell: Bachelorarbeit AsiMinu App, Anonis). Projekte starten als einzelne .md Datei. Nur bei komplexen Projekten mit mehreren Dateien wird ein Unterordner erstellt.
- 03 Bereiche/: Laufende Verantwortungsbereiche ohne Enddatum (Werkstudent Bayfu, KI-Weiterbildung, Finanzen & Investieren, Crossfit & Gesundheit). Jeder Bereich ist ein eigener Ordner, weil Bereiche über die Zeit wachsen und mehrere Dateien sammeln.
- 04 Ressourcen/: Referenzmaterial, Wissen, gesammelte Informationen (C# & ASP.NET Core, Claude Code & KI-Tools, Docker & Azure, ETFs & Aktien, IT-Wissen). Jedes Thema ist ein eigener Ordner.
- 05 Daily Notes/: Tägliches Logbuch. Was an einem Tag passiert ist, welche Entscheidungen getroffen wurden, was offen ist. Gibt Claude die Kontinuität zwischen Sessions.
- 06 Archiv/: Abgeschlossene Projekte und inaktive Bereiche. Aus dem aktiven Blickfeld, aber durchsuchbar.
- 07 Anhänge/: Bilder, PDFs, Medien. Obsidian legt hier automatisch alle eingefügten Dateien ab.

## Regeln für dieses Vault

- Nutze [[Wikilinks]] für Verknüpfungen zwischen Notizen
- Neue Notizen ohne klaren Platz kommen in 01 Inbox/
- Halte Notizen atomar: eine Idee pro Notiz wo möglich. Ausnahme: Daily Notes fassen einen ganzen Tag zusammen.
- Daily Notes benennen im Format: YYYY-MM-DD.md (z.B. 2026-07-29.md). So sortieren sie automatisch chronologisch.
- Nutze YAML Frontmatter: tags, status (aktiv/abgeschlossen/pausiert), date
- Dateinamen in normaler Schreibweise mit Leerzeichen und Großbuchstaben: Beschreibender Name.md
- Neue Projekte bekommen eine einzelne .md Datei direkt unter 02 Projekte/. Einen Unterordner nur anlegen wenn das Projekt mehrere Dateien braucht.
- Bereiche und Ressourcen sind immer Ordner, weil sie über die Zeit wachsen
- Abgeschlossene Projekte nach 06 Archiv/ verschieben. Nur auf Anweisung von Dennis, nicht eigenständig.
- Wenn du Dateien erstellst oder verschiebst, erkläre kurz warum
- Bevor du Dateien löschst oder überschreibst, frag nach
- Wenn Dennis sagt "merk dir das" oder "speicher das", speichere es dort wo es thematisch hingehört. Schreibregeln nach 00 Kontext/Schreibstil.md, Projekt-Infos in die jeweilige Projekt-Datei, technische Erkenntnisse in 04 Ressourcen/, Vault-Regeln in diese CLAUDE.md. Im Zweifel kurz fragen wo es hin soll.
- Dennis schreibt geduzt, keine Gedankenstriche als Satztrenner, höflicher und netter Ton. Diese Regeln gelten auch für Claude beim Formulieren von Texten für Dennis.

## Session-Routinen

### Bei Session-Start
1. Prüfe 01 Inbox/ auf neue Notizen, zeige was drin liegt, und biete an die Einträge in die passenden Ordner einzusortieren

### Kontext bei Bedarf
Wenn Dennis fragt "Was ist gerade aktuell?", "Wo war ich stehen geblieben?" oder ähnliches: Lies die letzten 2-3 Daily Notes in 05 Daily Notes/ und die aktiven Projekt-Dateien in 02 Projekte/ um ein Briefing zu geben.

### Bei Session-Ende
Wenn Dennis die Session beendet oder du merkst dass ein natürliches Ende erreicht ist, biete an:
1. Einen Daily Note Eintrag in 05 Daily Notes/ zu erstellen mit einer Zusammenfassung des Tages
2. Neue Erkenntnisse als Notizen zu speichern
3. Die Inbox aufzuräumen falls nötig
