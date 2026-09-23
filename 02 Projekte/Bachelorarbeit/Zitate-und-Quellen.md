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

> [!success] Stand 18.09.2026 — Lücke geschlossen
> Die beiden fehlenden Quellen wurden am 18.09.2026 recherchiert und in `thesis.bib` eingetragen. Beide sind frei zugänglich.

- [[ISO 24765 2017 - Systems and Software Engineering Vocabulary]] — `\cite{ISO24765}` — Glossar-Standard für Systems- und Software-Engineering; liefert die Definition von „change request" als formaler Änderungsantrag (3.547, S. 66). Lizenzierter Volltext über die TH Rosenheim (IEEE Xplore), PDF im Vault. Verwendet in: Kapitel 2.1.1. **Achtung:** Die Statusverfolgung über den Lebenszyklus steht so nicht in der Norm, siehe Prüfhinweis in der Notiz.
- **Serrano, N. / Faustino, J. (2021)** — *IT Service Management Software Tools*, MDPI *Information* 12(3), Artikel 111. DOI: 10.3390/info12030111 — `\cite{SerranoFaustino2021}` — Open-Access-Übersichtsartikel zu ITSM und ITIL als meistverbreitetem Framework; dient als Definitionsquelle für ITSM und zur Beschreibung wiederkehrender Herausforderungen bei ITSM-Einführungen. Verwendet in: Kapitel 2.1.1 und 2.5.2.

## Themenbereich: Architektur (Clean Architecture, DDD)

- [[Newman 2015 - Building Microservices]] — Newman 2015, `\cite{Newman2021}` (Auflage in thesis.bib korrigiert, siehe Notiz)
- [[Lano, Yassipour Tehrani 2023 - Introduction to Software Architecture]] — Lano, Yassipour Tehrani 2023, `\cite{Lano2023}` (Ersatz für Martin 2017 Clean Architecture, genutzt in 2.4.1)

## Themenbereich: Web-Technologien (Blazor, ASP.NET Core)

- **OMG DMN 1.4 (2023)** — `\cite{OMGDMN2023}` — Object Management Group, Decision Model and Notation Standard Version 1.4; frei bei omg.org. Verwendet in: Kapitel 2.2.1.

## Themenbereich: Cloud / Azure

*(noch leer)*

## Themenbereich: Sicherheit (JWT, TOTP, DSGVO, IT-Sicherheitsprinzipien)

> Neu ergänzt 18.09.2026

- **RFC 6238 (TOTP)** — `\cite{RFC6238}` — IETF-Standard für zeitbasierte Einmalpasswörter; frei bei datatracker.ietf.org. Verwendet in: Kapitel 2.4.2.
- **RFC 7519 (JWT)** — `\cite{RFC7519}` — IETF-Standard für JSON Web Tokens; frei bei datatracker.ietf.org. Verwendet in: Kapitel 2.4.2.
- **NIST SP 800-63B** — `\cite{NIST80063B2025}` — NIST-Richtlinie zu digitaler Identität / Authentifizierung; frei bei nvlpubs.nist.gov. Verwendet in: Kapitel 2.4.2.
- **Sandhu et al. (1996)** — `\cite{Sandhu1996}` — RBAC-Grundlagenarbeit. Verwendet in: Kapitel 2.4.2.
- **Saltzer & Schroeder (1975)** — `\cite{SaltzerSchroeder1975}` — Prinzip der geringsten Rechte. Verwendet in: Kapitel 2.4.2.
- **NIST SP 800-162** — `\cite{NIST800162}` — ABAC-Richtlinie. Verwendet in: Kapitel 2.4.2.
- [[Gadatsch, Mangiapane 2017 - IT-Sicherheit]] — Gadatsch, Mangiapane 2017, `\cite{GadatschMangiapane2017}` (Autor-Vorname in thesis.bib korrigiert, siehe Notiz)
- [[Lang, Löhr (Hrsg.) 2025 - IT-Sicherheit]] — Lang, Löhr (Hrsg.) 2025, `\cite{Loehr2024}` — Sammelband mit 17 Kapiteln zu Technologien und Best Practices; relevant für 2.4.2 (CIA-Triade, Authentifizierung, Autorisierung, Auditing S. 33–35), 5.11 (Defense in Depth S. 44), 5.8 (Input-Validierung als SEI-CERT-Grundsatz S. 300). ~~**Achtung:** BibTeX-Eintrag hat 3 Fehler~~ — korrigiert 23.09.2026 (Hrsg. Lang ergänzt, Jahr auf 2025, address + isbn ergänzt), Details in der Notiz.
- [[Microsoft Learn 2026 - ASP.NET Core Sicherheit]] — Microsoft Corporation 2026, `\cite{MicrosoftAspNetSecurity2024}`

## Themenbereich: Prozess- und Datenqualitätsmanagement

*(neuer Themenbereich, ergänzt am 02.09.2026 für die eingegangenen Quellen zu BPM/Datenqualität)*

- [[Weske 2024 - Business Process Management]] — Weske 2024, `\cite{Weske2024}` — 4. Aufl., Springer; Standardwerk BPM (Konzepte, Sprachen, Architekturen); liefert Definition Geschäftsprozess (S. 5), BPM-Lebenszyklus mit 4 Phasen (S. 11–16) und RPA-Konzept (S. 57–60). Verwendet in: Kapitel 1 (bereits im Code), 2.2 (BPM-Grundlagen), 2.5 (RPA Stand der Technik). BibTeX-Felder address/isbn/doi am 23.09.2026 ergänzt.
- [[Hildebrand2025 - Daten- und Informationsqualität (6. Aufl., Springer Vieweg)]] — Hildebrand, Mielke, Gebauer (Hrsg.) 2025, `\cite{Hildebrand2025}` — 6. Aufl., Springer Vieweg; Praxishandbuch zu Informationsqualität; zentral: 15 IQ-Dimensionen in 4 Kategorien (S. 26–28), TDQM-Phasen (S. 67–84). Verwendet in: Kap. 2.3 (DQ-Dimensionen-Definition), Kap. 6/7 (Evaluation: Vollständigkeit, Fehlerfreiheit, Konsistenz). BibTeX und Quellen-Notiz lagen bereits vor — PDF am 23.09.2026 kopiert, Notiz um Offset, IQ-Dimensionen und PDF-Embed ergänzt.
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
