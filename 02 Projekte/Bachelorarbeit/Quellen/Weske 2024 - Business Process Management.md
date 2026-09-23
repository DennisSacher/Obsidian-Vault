---
tags: [bachelorarbeit, quelle, bpm, prozessmanagement]
status: aktiv
date: 2026-09-23
bibtex: Weske2024
---

# Weske 2024 — Business Process Management

← zurück zu [[Zitate-und-Quellen]] · verwandt: [[Dumas et al. 2018 - Fundamentals of BPM]], [[Langmann, Turi 2021 - RPA]]

## Vollzitat

**Autor:** Mathias Weske
**Titel:** Business Process Management: Concepts, Languages, Architectures
**Auflage:** 4., vollständig überarbeitete Auflage
**Verlag:** Springer-Verlag GmbH, Berlin
**Jahr:** 2024 (Copyright-Seite: © 2007, 2012, 2019, 2024)
**Print-ISBN:** 978-3-662-69517-3
**eBook-ISBN:** 978-3-662-69518-0
**DOI:** https://doi.org/10.1007/978-3-662-69518-0
**Seiten:** ca. 464 (Haupttext, Arabic-Nummerierung bis S. 451+)
**Bezug:** Persönliches Exemplar (PDF), heruntergeladen 23.09.2026

**Buchseiten-Offset:** Buchseite ≈ PDF-Seite − 17 (verifiziert: PDF-Seite 20 = Buchseite 3). Ab Kapitel 2 möglicherweise Offset 16 — im Zweifel immer am Seitenkopf des PDFs prüfen.

**Neu in der 4. Auflage:** Kapitel zu Robotic Process Automation (Kap. 2.5), Directly Follows Graphs (DFGs, Kap. 4.8), deklarative Prozessmodellierung (Kap. 4.9), Daten-Prozess-Integration.

## Inhaltsübersicht (9 Kapitel, 3 Teile)

### Part I — Foundation

| Kap | Titel | Buchseiten |
|---|---|---|
| 1 | Introduction | 3–23 |
| 2 | Evolution of Enterprise Systems Architectures | 25–71 |

**Kap. 1 Unterabschnitte:** 1.1 Motivation and Definitions (S. 4) · 1.2 Business Process Lifecycle (S. 11) · 1.3 Classifying Business Processes (S. 17) · 1.4 Structure and Organization (S. 21)

**Kap. 2 Unterabschnitte:** 2.1 Traditional Application Development (S. 26) · 2.2 Enterprise Applications and their Integration (S. 28) · 2.3 Enterprise Modelling and Process Orientation (S. 39) · 2.4 Workflow Management (S. 49) · **2.5 Robotic Process Automation (S. 57)** · 2.6 Enterprise Services Computing (S. 60)

### Part II — Business Process Modelling

| Kap | Titel | Buchseiten |
|---|---|---|
| 3 | Business Process Modelling Foundation | 77–127 |
| 4 | Process Modelling Languages | 129–264 |
| 5 | Data and Decisions | 267–292 |
| 6 | Process Choreographies | 295–341 |
| 7 | Properties of Business Processes | 343–383 |

### Part III — Architectures and Methodologies

| Kap | Titel | Buchseiten |
|---|---|---|
| 8 | Business Process Management Architectures | 387–418 |
| 9 | Business Process Management Methodology | 421–435 |

## Kernaussagen mit Seitenzahl

### Kap. 1 — Einführung und Grundbegriffe

- **Definition Geschäftsprozess (Def. 1.1):** „A *business process* consists of a set of activities that are performed in coordination in an organizational and technical environment. These activities jointly realize a business goal. Each business process is enacted by a single organization, but it may interact with business processes performed by other organizations." (S. 5)
- **Definition BPM (Def. 1.2):** „Business process management includes concepts, methods, and techniques to support the design, administration, configuration, enactment, and analysis of business processes." (S. 5)

### Kap. 1.2 — BPM-Lebenszyklus (S. 11–16)

Vier Phasen in einem zyklischen Modell (Abb. 1.5), ergänzt um Administration und Stakeholder als querschnittliche Dimension:

1. **Design & Analysis:** Prozesse werden identifiziert, modelliert, validiert und verifiziert; Prozessmodellierung (u. a. BPMN) ist die zentrale technische Teilphase. (S. 11–13)
2. **Configuration:** Prozessmodell wird implementiert — entweder durch Richtlinien/Verfahren oder ein dediziertes BPMS; umfasst Systemauswahl, Implementierung, Test und Deployment. (S. 13–14)
3. **Enactment:** Laufzeit der Prozessinstanzen; BPMS steuert die Ausführung gemäß dem Prozessmodell; Monitoring visualisiert den Zustand aktiver Instanzen; Execution Logs werden für spätere Evaluation gesammelt. (S. 14–15)
4. **Evaluation:** Execution Logs werden per Business Activity Monitoring und Process Mining ausgewertet, um Prozesse zu verbessern und in die Design-Phase zurückzuführen. (S. 15)
5. **Administration and Stakeholders (querschnittlich):** Rollen im BPM: Chief Process Officer, Business Engineer, Process Designer, Process Participant, Knowledge Worker, Process Owner, System Architect, Developer. (S. 15–16)

### Kap. 2.5 — Robotic Process Automation (S. 57–60)

- **Architektur RPA:** RPA operiert auf der GUI-Schicht bestehender Anwendungen (Abb. 2.21, S. 58); Softwareroboter = Prozessmodell, in dem Aktivitäten Benutzerinteraktionen darstellen. (S. 58)
- **Abgrenzung:** RPA automatisiert nur einzelne Schritte, die ein einzelner Benutzer ausführt — Weske schlägt „robotic task automation" als treffenderen Begriff vor. (S. 60)
- **Limitation:** Jede Änderung an der GUI der unterliegenden Anwendung muss in der Roboterkonfiguration nachgezogen werden; hoher Wartungsaufwand. (S. 60)

## Verwendung in der Arbeit

| Abschnitt | Bezug | Zitiervorschlag |
|---|---|---|
| 1 Einleitung | BPM als betriebliche Notwendigkeit (bereits im Code: `\cite{Dumas2018,Weske2024}`) | `\cite{Weske2024}` |
| 2.2 Grundlagen BPM | Definition Geschäftsprozess und BPM (Def. 1.1, 1.2), BPM-Lebenszyklus (Abb. 1.5) | `\cite[S.\,5]{Weske2024}`, `\cite[S.\,11\,ff.]{Weske2024}` |
| 2.5 Stand der Technik (Prozessautomatisierung) | RPA-Konzept, Architektur, Abgrenzung | `\cite[S.\,57\,f.]{Weske2024}` |

## Kritische Einordnung

- **Klassisches Standardwerk:** Weske ist *das* Standardlehrbuch für BPM aus Informatik-Perspektive; stärker formal-technisch als Dumas et al. 2018 (eher Managementperspektive).
- **4. Auflage 2024:** Neue Kapitel zu RPA (2.5) und DFGs (4.8) machen dieses Werk zur aktuellsten Fassung; ältere Zitierungen in der Literatur beziehen sich auf frühere Auflagen.
- **Abgrenzung zu Dumas et al. 2018:** Dumas ist breiter, pragmatischer und stärker auf Prozessverbesserung ausgerichtet. Weske ist tiefer in Prozessmodellierungssprachen und formalen Eigenschaften. Beide ergänzen sich; für die Arbeit ist Weske die bessere Quelle für die technische Definition von BPM und den Lebenszyklus, Dumas für die Managementperspektive.
- **Abgrenzung zu Langmann/Turi 2021:** Langmann/Turi fokussieren auf RPA-Praxis und Organisationsperspektive; Weske liefert die konzeptuelle Einordnung von RPA im BPM-Kontext.

## PDF

![[Business Process Management Weske 2024.pdf]]
