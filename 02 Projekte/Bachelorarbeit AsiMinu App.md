---
tags: [projekt, bachelorarbeit]
status: aktiv
erstellt: 2026-07-29
deadline: 2026-11-09
---

# Bachelorarbeit AsiMinu CRQ-Management-System

Bachelorarbeit über das AsiMinu CRQ-Management-System, entwickelt bei Bayfu GmbH, Kolbermoor. Abgabe: **09.11.2026**.

> [!info] Vorgeschichte des Projekts (ergänzt 09.09.2026)
> Die Arbeit ist die dritte Stufe einer Entwicklung. Zuerst gab es eine Anzeige-App auf Basis
> von Microsoft Power Apps, die eingehende CRQ-Daten strukturiert darstellte, aber keine
> Anbindung an das TEF-System hatte und an die Grenzen der Low-Code-Plattform stieß. Danach
> entstand mit Kollegen die AsiMinu-AdHoc-Lösung, ein .NET-Worker, der E-Mails ausliest und die
> Daten in WorkInfo, WorkInfoTable und WorkInfoSummary ablegt. Erst danach kam die
> Bachelorarbeit. Diese Vorgeschichte ist das stärkste Argument für die Eigenentwicklung und
> gehört in den Stand der Technik.
>
> Zwei weitere Klarstellungen: Das **Admin-Panel war von Anfang an Teil des Auftrags** (als
> Admin-Service im ursprünglichen Umsetzungsplan), keine spätere Ergänzung. Und der ursprüngliche
> Live-Termin 09.07.2026 war **vertraglich mit der TEF vereinbart**; er ist gerissen, weil die
> TEF ihre Schnittstelle nicht rechtzeitig fertigstellen konnte, der Live-Gang liegt jetzt im
> **November 2026**, die Anbindung der echten Schnittstelle ist für Ende September vorgesehen.

> [!info] Repo-Struktur
> - **Code + Docs**: `AsiMiNu_Project_Intern` (Azure DevOps, geteilt mit Team)
> - **Thesis-Text**: `Bachelorarbeit` (GitHub, privat) → `thesis/BA-Text/latex-projekt/`
> - **Fachliche Referenz für den Thesis-Text**: `thesis/Fachlicher-Kontext-AsiMiNu.md` im selben Repo (ausführliche Fassung der beiden Notizen oben)
> - **Aktueller Schreibstand und Konventionen**: `thesis/Schreibstand.md` im selben Repo (Gliederung, getroffene Entscheidungen, was wo erklärt wird, Status je Kapitel)
> - **Projekt-Kontext für Claude**: immer über das Submodul `asiminu-projekt/` im Bachelorarbeit-Repo

## Navigation

- [[AsiMiNu-Prozessablauf]] — **Verbindliche fachliche Referenz:** wie eine AsiMiNu-Anfrage wirklich abläuft, Rollen, Glossar
- [[AsiMiNu-Projekthintergrund]] — **Verbindliche fachliche Referenz:** warum es das Projekt gibt, Vergütungsmodell, Zukunftsvision
- [[Kapitelplanung]] — Welche Kapitel, was kommt wo, Fortschritt
- [[ADR-zu-Kapitel]] — 52 ADRs × Kapitel-Mapping (welche sind schon drin?)
- [[Offene-Fragen]] — Ungeklärtes für Betreuer oder Recherche
- [[Zitate-und-Quellen]] — Literatur-Notizen und BibTeX-Schlüssel
- [[Ideen]] — Freier Gedankenstrom beim Coden
- `02 Projekte/Bachelorarbeit/Arbeitsprotokolle/` — Tagesprotokolle je Schreib-Session
- [[Gliederungsvarianten]] — Vier Strukturvarianten, Bewertung, Empfehlung für Variante D
- [[Evaluationsplan]] — Kennzahlen, Versuchsaufbau und Zeitplan der Wirkungsmessung
- [[Wissenschaftliches Arbeiten]] — Formale Vorgaben, Zitierregeln, Sprachstil der TH Rosenheim (immer vor dem Schreiben von Kapiteltext konsultieren)

## Aktueller Fortschritt

> [!success] Variante D umgesetzt (15.09.2026)
> Die komplette Kapitelstruktur ist auf die am 09.09.2026 empfohlene
> [[Gliederungsvarianten|Variante D]] umgestellt, inklusive Abgleich jedes Abschnitts gegen das
> Abstimmungsdokument mit dem Betreuer (Kurzfassung je Abschnitt, Zielumfang-Begründung je
> Kapitel). Details je Kapitel in [[Kapitelplanung]]. Kapitel 1 (Einleitung) wird gerade als
> erstes fertig ausformuliert, offen ist dort vor allem der neue Abschnitt 1.4 (Abgrenzung des
> Betrachtungsgegenstands).

> [!tip] Live-Dashboard statt manueller Checkliste (seit 02.09.2026)
> Der Kapitel-für-Kapitel-Fortschritt (Status, geschätzte Seiten, fehlende Quellen,
> KI-Fußnoten-Lücken, Tagesempfehlung) wird nicht mehr hier von Hand gepflegt, sondern
> automatisch berechnet: `thesis/dashboard/` im Bachelorarbeit-Repo. Läuft täglich 9 Uhr
> per Windows-Taskplaner, manuell per Desktop-Verknüpfung „Dashboard aktualisieren".
> Abschnittsstatus ändern: `thesis/dashboard/status-setzen.ps1`. [[Kapitelplanung]] bleibt
> als qualitative Planungsnotiz (Schreibreihenfolge, inhaltliche Lücken, Kontext je Kapitel)
> bestehen, nur die reine Statusverfolgung ist ins Dashboard gewandert. Nach der Umbenennung der
> Kapiteldateien am 15.09.2026 noch zu prüfen, ob das Dashboard weiterhin korrekt rechnet, siehe
> [[Offene-Fragen]].

## Rahmendaten

| Feld | Wert |
|---|---|
| Hochschule | Technische Hochschule Rosenheim, Fakultät für Informatik |
| Betreuer (Erstkorrektor) | – |
| Zweitkorrektor | – |
| Bearbeitungszeit | 5 Monate ab Anmeldung (frühestens nach 2 Monaten abgebbar) |
| Abgabe | **09.11.2026** — harte Schreibfrist **30.10.2026** (10 Tage Korrektur-Puffer danach), bestätigt 09.09.2026 |
| Seitenzahl-Ziel | bisher **40–45 Seiten**, Obergrenze 50. Vorschlag seit 09.09.2026: **55–60 Seiten** Fließtext, siehe [[Gliederungsvarianten]]. Aktuelle Kapitelplanung (Variante D) summiert sich auf 56 Seiten, siehe [[Kapitelplanung]]. Die Fakultät gibt keinen Umfang vor, muss mit dem Betreuer abgestimmt werden |
| Sprache | Deutsch |

> [!info] Formale Vorgaben
> Details zu Zulassung, Anmeldung, Abgabe, Gliederungsregeln, Zitierweise und Sprachstil: siehe [[Wissenschaftliches Arbeiten]]. Wichtig: **nur digitale Abgabe** über das DMS-Portal (PDF, VPN nötig), **keine Spiralbindung**, **KI-Nutzung muss dokumentiert werden** (siehe [[Zitieren und Quellenarbeit#KI-Nutzung dokumentieren]] und Kapitel 9/A im LaTeX-Projekt).
