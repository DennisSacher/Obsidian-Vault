---
tags: [bachelorarbeit, quelle]
bibtex-key: Lano2023
autor: Kevin Lano, Sobhan Yassipour Tehrani
jahr: 2023
titel: "Introduction to Software Architecture: Innovative Design using Clean Architecture and Model-Driven Engineering"
typ: Buch (Lehrbuch, Springer UTiCS)
themenbereich: Architektur (Clean Architecture, DDD)
status: teilweise gelesen
---

# Introduction to Software Architecture (Lano, Yassipour Tehrani, 2023)

← zurück zu [[Zitate und Quellen]]

> [!info] Rolle in der Arbeit
> Laut Kommentar in `thesis.bib` (23.09.2026) ist dieses Buch der **Ersatz für Martin 2017 (Clean Architecture)**, weil die TH Rosenheim über SpringerLink Volltextzugriff hat. Es wird bereits in Abschnitt 2.4.1 (`chapters/02/grundlagen.tex`, „Schichtung und Abhängigkeitsregel") zitiert. Lano und Yassipour Tehrani stützen sich selbst ausdrücklich auf Martin (ihre Quelle [63]), die Abbildung 2.1 ist „From [63]".

## Vollzitat (für das Literaturverzeichnis)

Lano, Kevin; Yassipour Tehrani, Sobhan: Introduction to Software Architecture: Innovative Design using Clean Architecture and Model-Driven Engineering. Cham: Springer, 2023 (Undergraduate Topics in Computer Science). ISBN 978-3-031-44142-4 (Print), 978-3-031-44143-1 (eBook). DOI: 10.1007/978-3-031-44143-1

## Kurzzitat (Verweis im Fließtext)

Lano, Yassipour Tehrani 2023 S. XX

> [!tip] Seitenzahlen
> Buchseite = PDF-Seite minus 3 (z.B. Buchseite 35 = PDF-Seite 38). Zitiert wird immer die gedruckte Buchseite.

## Inhaltsübersicht (12 Kapitel, 264 Seiten)

1. Introduction to Software Architecture Concepts (S. 11–34): Begriff, Komponenten, Konnektoren, UML-Komponentendiagramm, Qualitätseigenschaften (Reusability, Maintainability, Extensibility), QoS
2. **Introduction to Clean Architecture Concepts (S. 35–50)**: Dependency Rule, Schichtenmodell, SOLID, ADP, Component Boundaries, Technical Debt auf Architekturebene
3. Development Methods (S. 51–72): MDE, agile Entwicklung und Architektur, Three-Tier, Ableitung von Architekturen aus Anforderungen
4. Compound Components and Complex Connectors (S. 73–80)
5. Architectural Styles (S. 81–98): Adapter, Pipes and Filters, Client/Server, N-Tier, Layered, Blackboard, MVC
6. Mobile Application Architectures (S. 99–136): u.a. DTO/Value Object, Facade, DAO
7. Enterprise Information Systems and Application Servers (S. 137–150): u.a. .NET Enterprise Services
8. Web Application and Enterprise System Architectures (S. 151–176): Client/Presentation/Business Tier, Front Controller, Session Facade
9. Service-oriented Architectures (S. 177–190): Cloud (IaaS/PaaS/SaaS), SOA, REST, Microservices (S. 187)
10. Safety-critical and Embedded Systems Architectures (S. 191–210)
11. Architectural Design for Machine Learning Systems (S. 211–224)
12. Software Architectures and Re-engineering (S. 225–254)

## Kernaussagen und Zitate

### Kapitel 1: Grundbegriffe

- Softwarearchitektur bezeichnet eine globale, übergeordnete Sicht auf ein Softwaresystem: Komponenten und ihre Abhängigkeiten, Technologie- und Plattformentscheidungen, Verteilungsstruktur und Schnittstellen zu externen Systemen (S. 11) — sinngemäß
- Unterscheidung Software Design (Konstruktion einzelner Komponenten, Klassen, Operationen) vs. Architectural Design (Architekturebene) (S. 11) — sinngemäß
- Clean-Architecture-Ziel nach Martin: „The goal of software architecture is to minimize the human resources required to build and maintain the required system." (S. 12) — wörtlich, Zitat von Martin
- Viele Projekte scheitern, weil Architektur unter Zeitdruck ignoriert wird; Ad-hoc-Strukturen werden zunehmend schwer wartbar (S. 13) — sinngemäß

### Kapitel 2: Clean Architecture (in der Arbeit bereits genutzt)

- Clean Architecture zielt auf Wartbarkeit und Evolvierbarkeit, indem sie die **Abhängigkeiten** zwischen Komponenten beschränkt; X hängt von Y ab, wenn X den Namen von Y (oder einer Klasse/Schnittstelle darin) kennt (S. 35) — sinngemäß
- Dependency Rule: „Platform-specific components can depend on platform-independent components but not conversely." (S. 35) — wörtlich
- Die Dependency Rule schützt die Kern-Geschäftskomponenten vor Änderungen an Persistenz- und UI-Technologien, dadurch sinkt der Aufwand bei Technologiewechseln (S. 35 f.) — sinngemäß
- Abstufungen von Abhängigkeit: Independence, syntaktische, semantische und Code-Abhängigkeit (S. 36) — sinngemäß
- Schichtenmodell (Abb. 2.1, S. 36): Core Business Entities → Use Case Interactors → Presenters/Controllers/Gateways → Devices/Databases/Web/UI/External Systems. Erläuterung der Schichten auf **S. 36–37** (Controllers, Presenters, Gateways/DAOs werden erst auf S. 37 beschrieben) — sinngemäß
- SRP: „each component should have only one reason to change" bzw. „services for a single actor" (S. 37) — wörtlich
- OCP: Komponenten durch Hinzufügen neuer Fähigkeiten ändern, nicht durch Modifikation bestehender (S. 39) — sinngemäß
- LSP (S. 39–42), ISP (S. 42 f.) — sinngemäß
- DIP: eher eine Technik, die die Richtung einer konventionellen Aufrufabhängigkeit umkehrt, um die Dependency Rule durchzusetzen; Client besitzt die Required Interface, Supplier implementiert sie (S. 43–45, Abb. 2.4–2.6) — sinngemäß
- DIP muss nicht zwischen allen Modulen gelten, nur wo der Client auf höherer Abstraktionsebene liegt, z.B. Use Case Interactor → Gateway (S. 44) — sinngemäß
- ADP: keine Zyklen im Komponenten-Abhängigkeitsgraphen; Zyklen verursachen zusätzliche Kosten und Verzögerungen und können Endlosrekursion zur Laufzeit erzeugen (S. 45) — sinngemäß
- Begründung der Dependency Rule: stabile Komponenten sollen nicht von änderungsanfälligen abhängen, z.B. ein Business-Entity-Bean nicht von einer Datenbank (S. 45) — sinngemäß
- Component Boundaries: Geschäftsdaten über Value Objects / DTOs übergeben; diese Typen gehören zur Business-Entities-Schicht (S. 46) — sinngemäß
- Architektonische Technical Debt, u.a. plattformspezifischer Code in Business Entities, zu große Interfaces (>10 Operationen), zyklische Abhängigkeiten (S. 47 f.) — sinngemäß

### Kapitel 5: Architekturstile

- N-Tier für Enterprise-Systeme mit bis zu 5 Tiers: Client, Presentation, Business (intern Use Case Interactors + Business Entities), Integration (Gateways), Resource (S. 87) — sinngemäß
- Vorteil N-Tier: Separation of Concerns, Teams können getrennt an UI, Business Tier und Datenressourcen arbeiten; Nachteil: Performance bei verteilten Komponenten (S. 87 f.) — sinngemäß
- Layered Style ist strenger als N-Tier: je Schicht eine Komponente, Kommunikation nur mit direkten Nachbarn (S. 88) — sinngemäß
- Vorteile Layered: Abstraktion, bessere Wartbarkeit, klare Rollen je Schicht, Wiederverwendung/Portabilität (S. 89) — sinngemäß

## Verwendung in der Arbeit

- Kapitel 02, Abschnitt 2.4.1 „Schichtung und Abhängigkeitsregel": `\cite{Lano2023}` (Dependency Rule, Schichten, DIP S. 43 f., ADP S. 45)
- Potenziell weiter nutzbar: Kapitel 04 (Architekturentscheidung, Abgrenzung Layered vs. N-Tier vs. Microservices, Kap. 5 und 9.4), Technical Debt (S. 46–48) für Diskussion/Ausblick

> [!warning] Prüfhinweis Seitenangabe
> In `grundlagen.tex` steht `\cite[S.\,35\,f.]{Lano2023}` für die vier konzentrischen Schichten. Die Abbildung und die ersten beiden Schichten stehen auf S. 36, die Erläuterung der Schnittstellenadapter (Controllers, Presenters, Gateways) und der äußersten Schicht erst auf **S. 37**. Genauer wäre `S.\,36\,f.` bzw. `S.\,35\,ff.`. Die Angaben `S.\,43\,f.` (DIP) und `S.\,45` (ADP) passen.

## Kritische Einordnung

- Qualität/Seriosität: Lehrbuch aus der begutachteten Springer-Reihe „Undergraduate Topics in Computer Science" mit internationalem Advisory Board; Autoren von King's College London und UCL. Basiert auf einem 2010–2023 gehaltenen Modul „Software architecture and design". Gut zitierfähig.
- Aktualität: 2023, sehr aktuell.
- Einschränkungen: Die Clean-Architecture-Inhalte sind eine Sekundärdarstellung von Martin (2017/2018). Für die Arbeit akzeptabel, da Primärquelle nicht zugänglich, im Text aber ggf. transparent machen („nach Martin, zit. in Lano/Yassipour Tehrani"). Beispiele teils Java/Swift/OCL-lastig, nicht .NET-spezifisch. Starker Fokus auf Model-Driven Engineering (AgileUML-Tooling der Autoren), der für AsiMiNu kaum relevant ist.

## Quell-Datei

![[Introduction to Software Architecture.pdf]]
