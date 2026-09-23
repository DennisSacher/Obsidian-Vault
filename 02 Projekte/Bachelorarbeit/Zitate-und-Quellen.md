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

- **ISO/IEC/IEEE 24765:2017** — `\cite{ISO24765}` — Glossar-Standard für Systems- und Software-Engineering; liefert die Definition von „change request" als formal eingereichter Änderungsantrag, der mit seinen Statusinformationen über den gesamten Lebenszyklus nachverfolgt wird. Frei bei IEEE Xplore (Open Standard). Verwendet in: Abschnitt 1.1, Kapitel 2.1.1.
- **Serrano, N. / Faustino, J. (2021)** — *IT Service Management Software Tools*, MDPI *Information* 12(3), Artikel 111. DOI: 10.3390/info12030111 — `\cite{SerranoFaustino2021}` — Open-Access-Übersichtsartikel zu ITSM und ITIL als meistverbreitetem Framework; dient als Definitionsquelle für ITSM und zur Beschreibung wiederkehrender Herausforderungen bei ITSM-Einführungen. Verwendet in: Kapitel 2.1.1 und 2.5.2.

## Themenbereich: Architektur (Clean Architecture, DDD)

- [[Newman 2015 - Building Microservices]] — Newman 2015, `\cite{Newman2021}` (Auflage in thesis.bib korrigiert, siehe Notiz)

## Themenbereich: Web-Technologien (Blazor, ASP.NET Core)

- **OMG DMN 1.4 (2023)** — `\cite{OMGDMN2023}` — Object Management Group, Decision Model and Notation Standard Version 1.4; frei bei omg.org. Verwendet in: Kapitel 2.2.1.

## Themenbereich: Cloud / Azure

*(noch leer)*

## Themenbereich: Sicherheit (JWT, TOTP, DSGVO)

> Neu ergänzt 18.09.2026

- **RFC 6238 (TOTP)** — `\cite{RFC6238}` — IETF-Standard für zeitbasierte Einmalpasswörter; frei bei datatracker.ietf.org. Verwendet in: Kapitel 2.4.2.
- **RFC 7519 (JWT)** — `\cite{RFC7519}` — IETF-Standard für JSON Web Tokens; frei bei datatracker.ietf.org. Verwendet in: Kapitel 2.4.2.
- **NIST SP 800-63B** — `\cite{NIST80063B2025}` — NIST-Richtlinie zu digitaler Identität / Authentifizierung; frei bei nvlpubs.nist.gov. Verwendet in: Kapitel 2.4.2.
- **Sandhu et al. (1996)** — `\cite{Sandhu1996}` — RBAC-Grundlagenarbeit. Verwendet in: Kapitel 2.4.2.
- **Saltzer & Schroeder (1975)** — `\cite{SaltzerSchroeder1975}` — Prinzip der geringsten Rechte. Verwendet in: Kapitel 2.4.2.
- **NIST SP 800-162** — `\cite{NIST800162}` — ABAC-Richtlinie. Verwendet in: Kapitel 2.4.2.
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
