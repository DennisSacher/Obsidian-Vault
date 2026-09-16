---
tags: [bachelorarbeit, literatur]
erstellt: 2026-08-11
---

# Zitate und Quellen

← zurück zu [[Bachelorarbeit AsiMinu App]]

Ausführliche Quellen-Notizen (Metadaten, Zitate, Bewertung, PDF) liegen einzeln in `02 Projekte/Bachelorarbeit/Quellen/`, PDFs dazu in `07 Anhänge/Quellen/`. Vorlage: `Quellen/_Vorlage Quelle.md`.

> [!tip] Workflow
> 1. Quelle lesen → eigene Notiz in `Quellen/` anlegen (Vorlage kopieren), PDF nach `07 Anhänge/Quellen/` legen und in der Notiz verlinken
> 2. Kurzeintrag mit Link zur Notiz hier unten unter dem passenden Themenbereich ergänzen
> 3. BibTeX-Key in `thesis/latex-projekt/thesis.bib` eintragen
> 4. Im LaTeX-Text per `\cite{key}` referenzieren

## Themenbereich: Change Request Management / ITIL

*(noch leer)*

> [!warning] Diese Lücke ist seit 16.09.2026 dringend
> Ursprünglich für Kapitel 02 und 03 vorgemerkt, inzwischen aber schon in **Abschnitt 1.1**
> nötig: Dort wird der Change Request definiert („formalisierter Antrag, eine geplante Änderung
> an einem produktiven System in einem genau bestimmten Zeitfenster durchführen zu dürfen"),
> und diese Definition braucht einen Beleg. Abschnitt 1.1 hat derzeit keine einzige Quelle,
> obwohl die TH-Vorgabe für die Einleitung ausdrücklich Literaturbezug verlangt.
> Gesucht: ein ITIL- oder ITSM-Standardwerk mit einer zitierfähigen Definition von Change und
> Change Request.

## Themenbereich: Architektur (Clean Architecture, DDD)

- [[Newman 2015 - Building Microservices]] — Newman 2015, `\cite{Newman2021}` (Auflage in thesis.bib korrigiert, siehe Notiz)

## Themenbereich: Web-Technologien (Blazor, ASP.NET Core)

*(noch leer — siehe auch Microsoft-Quelle unter "Sicherheit" unten, thematisch doppelt relevant)*

## Themenbereich: Cloud / Azure

*(noch leer)*

## Themenbereich: Sicherheit (JWT, TOTP, DSGVO)

- [[Gadatsch, Mangiapane 2017 - IT-Sicherheit]] — Gadatsch, Mangiapane 2017, `\cite{GadatschMangiapane2017}` (Autor-Vorname in thesis.bib korrigiert, siehe Notiz)
- [[Microsoft Learn 2026 - ASP.NET Core Sicherheit]] — Microsoft Corporation 2026, `\cite{MicrosoftAspNetSecurity2024}`

## Themenbereich: Prozess- und Datenqualitätsmanagement

*(neuer Themenbereich, ergänzt am 02.09.2026 für die eingegangenen Quellen zu BPM/Datenqualität)*

- [[Batini, Scannapieco 2016 - Data and Information Quality]] — Batini, Scannapieco 2016, `\cite{BatiniScannapieco2016}`
- [[Dumas et al. 2018 - Fundamentals of BPM]] — Dumas et al. 2018, `\cite{Dumas2018}`

## Themenbereich: Prozessautomatisierung (RPA)

*(neuer Themenbereich, ergänzt am 02.09.2026)*

- [[Langmann, Turi 2021 - RPA]] — Langmann, Turi 2021, `\cite{LangmannTuri2020}` (Auflage in thesis.bib korrigiert, siehe Notiz)
- [[van der Aalst et al. 2018 - RPA Editorial]] — van der Aalst, Bichler, Heinzl 2018, `\cite{VanDerAalst2018}` (vollständig ausgewertet, kurzer Artikel)

---

## Vorlagen für BibTeX-Einträge

```bibtex
@book{key,
  author    = {Nachname, Vorname},
  title     = {Titel des Buches},
  year      = {2023},
  publisher = {Verlag},
  address   = {Ort}
}

@online{key,
  author  = {Nachname, Vorname},
  title   = {Titel der Webseite},
  url     = {https://...},
  urldate = {2026-08-11}
}
```
