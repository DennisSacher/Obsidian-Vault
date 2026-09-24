---
tags: [bachelorarbeit, planung, forschungsfragen]
status: aktiv
date: 2026-09-23
---

# Forschungsfragen

← zurück zu [[Bachelorarbeit AsiMinu App]] · verwandt: [[Gliederung Variante D - Abschnittsinhalte]], [[Evaluationsplan]], [[Gliederungsvarianten]]

Wortlaut wie in `chapters/01/einleitung.tex`, Abschnitt 1.3 (unverändert aus dem Exposé vom 26.03.2026). Beantwortet werden alle Fragen gebündelt in **Abschnitt 6.6 „Beantwortung der Forschungsfragen"**, einzeln und in derselben Reihenfolge, je ein bis zwei Absätze pro Frage, ohne neue Gliederungspunkte.

## Hauptforschungsfrage

> Wie kann ein manueller Change-Request-Prozess durch eine automatisierte Systemlösung optimiert werden, und welche Auswirkungen hat dies auf Effizienz, Datenqualität und Prozesssicherheit?

Die Frage hat zwei Teile: ein **Wie** (beantwortet durch Entwurf und Umsetzung, belegt über die ADRs) und eine **Wirkung** (beantwortet nur durch die empirische Messung, siehe [[Evaluationsplan]]). Der zweite Teil ist nicht durch Umformulieren zu retten, sondern nur durch die tatsächliche Erhebung.

**Zielsetzung:** Analyse, Konzeption und prototypische Umsetzung eines Systems, das den Prozess von der Antragstellung durch den GU bis zur Übergabe an das Zielsystem durchgängig unterstützt, inklusive Dateneingabe durch die GUs sowie interner Bearbeitung, Validierung und Statusverfolgung bei BayFu.

## Unterfragen und wo sie beantwortet werden

Kapitelnummern nach der aktuellen 7-Kapitel-Struktur (seit 16.09.2026).

| Nr. | Unterfrage (Kurzform) | Material entsteht in | Beantwortet in |
|---|---|---|---|
| FF1 | **Prozessanalyse:** Aufbau und Schwachstellen des Ist-Prozesses, größter Zeit- und Fehleraufwand | 4.1, 4.2 | 6.6 |
| FF2 | **Anforderungen und Systemdesign:** funktionale/nicht-funktionale Anforderungen, geeignete skalierbare und wartbare Architektur | 4.3, 4.4, 5.1 bis 5.5 | 6.6 |
| FF3 | **Datenqualität und Validierung:** Reduktion von Eingabefehlern durch Eingabemasken und Validierung, nötige Regeln | 5.7, 5.8, 6.4.1 | 6.6 |
| FF4 | **Benutzerfreundlichkeit (UI/UX):** intuitive, fehlerarme Oberfläche, Unterschied zur Excel-Lösung | 5.7.2, Kurzbefragung in 6.3 | 6.6 |
| FF5 | **Automatisierung und Integration:** welche Schritte vollständig automatisierbar, wo manuelle Prüfung bleibt; konfigurierbare Regelbasis vs. fest verdrahtete Logik | 5.9, 6.4.2 | 6.6 (**wichtigste, ausführlichste Antwort**) |
| FF6 | **Evaluation und Nutzen:** Auswirkungen auf Bearbeitungszeit, Fehlerquote, Datenqualität, Prozesssicherheit und Nachvollziehbarkeit | 6.1 bis 6.5 | 6.6 |

**Stärkster Einzelbefund der Arbeit (für FF5):** Die alte, fest im Quelltext verankerte Automatisierungsregel war gegen die echte Standortdatei zu 100 % wirkungslos. Ihr gegenüber steht die gemessene Automatisierungsquote der konfigurierbaren Regelbasis (ADR-055/056).

## Bekannte Schwachstellen der Fragen (Analyse vom 09.09.2026)

> [!warning] FF4 hat keinen eigenen Ort
> Die Usability-Frage wird nirgends mit einem eigenen Instrument beantwortet, nur über eine Kurzbefragung mit zwei bis drei Personen. Das trägt keine eigene Forschungsfrage. Drei Auswege wurden vorgeschlagen:
> 1. Streichen und in FF3 integrieren, weil Maskengestaltung und Fehlervermeidung dasselbe Ziel verfolgen
> 2. Behalten und mit einem kleinen echten Instrument beantworten, z.B. einem strukturierten Walkthrough entlang der sieben Grundsätze der DIN EN ISO 9241-110
> 3. **In eine Entwurfsfrage umformulieren** („Welche Gestaltungsentscheidungen wurden zur Fehlervermeidung getroffen und wie lassen sie sich begründen?"). Aufwandsärmste Variante, passt am besten zum tatsächlich Gemachten
>
> Stand heute: Die Fragen stehen weiterhin im Exposé-Wortlaut, Variante D verortet FF4 in 5.7.2 (Gestaltungsentscheidungen zur Fehlervermeidung). Eine Entscheidung dazu ist nicht dokumentiert.

- **Sechs Unterfragen sind viel.** Empfehlung war, auf vier zu reduzieren (Prozessanalyse; Anforderungen und Architektur; Datenqualität und Validierung inkl. Oberflächengestaltung; Automatisierung und Regelbasis). Die Evaluationsfrage wäre dann keine eigene Unterfrage, sondern die Querschnittsfrage, die alle anderen prüft.
- **„Prototypisch" untertreibt:** Das System läuft in zwei Azure-Umgebungen, ist testabgedeckt und hat Rollenmodell, Prüfprotokoll sowie Datenschutz- und AGB-Verwaltung. Die Zielsetzung sollte das nachziehen, statt weiter von einem Prototyp zu sprechen.

## Exposé gegen tatsächliche Umsetzung

Das Exposé (März 2026) ist eine Momentaufnahme der frühen Planung und **kein Maßstab** für den Inhalt. Die Abweichung ist selbst ein Ergebnis und gehört in die kritische Reflexion (6.9).

| Aspekt | Exposé (26.03.2026) | Tatsächliche Umsetzung |
|---|---|---|
| Komponenten | zwei: GU-Frontend und Erweiterung des bestehenden AsiMiNu Web | GU-Panel, Admin-Panel, ChangeCoordinator-Panel, Backend, plus Worker |
| Bestehendes Dashboard | Admin-Panel wird ins Bestandssystem eingefügt | Bestandssystem abgelöst, ChangeCoordinator-Panel neu gebaut |
| Datenhaltung | eine von BayFu verwaltete SQL-Datenbank | drei getrennte PostgreSQL-Datenbanken (Auth/CRQ/INC) |
| Authentifizierung | nicht ausgeführt | eigener Schwerpunkt: TOTP, Challenge-Token, Refresh-Token, Lockout, vier Rollen |
| Automatisierung | „welche Prozessschritte können automatisiert werden" | konfigurierbare Regelbasis mit geplanten Läufen |
| Anbindung Zielsystem | Teil der Lösung | bislang Stub, echte Anbindung für Ende September 2026 geplant |
| Evaluation | Zeitmessung, Fehlerquote, Nutzerverhalten | Konzept steht, siehe [[Evaluationsplan]] |
| Zeitrahmen | Live-Gang 09.07.2026 | verschoben auf November 2026, extern verursacht |

**Verschobener Schwerpunkt:** Das Exposé betont Eingabemaske und Validierung. Die beiden stärksten Eigenleistungen sind tatsächlich die **konfigurierbare Automatisierungslogik** und das **Sicherheits- und Rollenkonzept**. Die Gliederung folgt der tatsächlichen Gewichtung.

## Quelle

Zusammengeführt aus den Gliederungsdokumenten vom 09.09.2026 (Originale unter `07 Anhänge/Gliederung Bachelorarbeit/`) und dem aktuellen LaTeX-Stand vom 23.09.2026.
