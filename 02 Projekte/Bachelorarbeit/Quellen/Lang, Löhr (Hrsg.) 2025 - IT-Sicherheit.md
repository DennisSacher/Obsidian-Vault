---
tags: [bachelorarbeit, quelle, it-sicherheit]
status: aktiv
date: 2026-09-23
bibtex: Loehr2024
---

# Lang, Löhr (Hrsg.) 2025 — IT-Sicherheit

← zurück zu [[Zitate-und-Quellen]] · verwandt: [[Gadatsch, Mangiapane 2017 - IT-Sicherheit]], [[Gliederung Variante D - Abschnittsinhalte]]

## Vollzitat

**Hrsg.:** Michael Lang, Hans Löhr
**Titel:** IT-Sicherheit: Technologien und Best Practices für die Umsetzung im Unternehmen
**Auflage:** 2., überarbeitete Auflage
**Verlag:** Carl Hanser Verlag GmbH & Co. KG, München
**Jahr:** 2025 (Copyright-Seite: © 2025)
**Print-ISBN:** 978-3-446-48082-7
**E-Book-ISBN:** 978-3-446-48116-9
**Seiten:** 444
**Bezug:** Über Hanser eLibrary, TH Rosenheim Lizenz (lizenzierter Zugang), heruntergeladen 23.09.2026

> [!success] BibTeX-Eintrag korrigiert (23.09.2026)
> Die drei Fehler im Eintrag `Loehr2024` wurden behoben:
> 1. `editor` → `{Lang, Michael and Löhr, Hans}` (beide Hrsg. ergänzt)
> 2. `year` → `{2025}` (Copyright-Seite: © 2025)
> 3. Felder `address = {München}`, `isbn = {978-3-446-48082-7}`, `note` mit URL ergänzt
>
> Key `Loehr2024` beibehalten (Umbenennung würde Mehraufwand ohne Nutzen erzeugen).

**Buchseiten-Offset:** Buchseite = PDF-Seite − 16

## Inhaltsübersicht (17 Kapitel + Vorwort)

| Kap | Titel | Autor(en) | Buchseiten |
|---|---|---|---|
| 1 | IT-Sicherheit konsequent und effizient umsetzen | Norbert Pohlmann | 1–26 |
| 2 | Grundprinzipien zur Gewährleistung der IT-Sicherheit | Hagen Lauer, Nicolai Kuntze | 27–47 |
| 3 | Organisation des IT-Sicherheitsmanagements im Unternehmen | Markus Nauroth | 49–67 |
| 4 | Rechtliche Rahmenbedingungen der IT-Sicherheit | Thomas Jansen | 69–87 |
| 5 | Standards und Zertifizierungen | Thomas Lohre | 91–113 |
| 6 | Datenschutz und Informationssicherheit | Stefan Karg | 115–134 |
| 7 | IT-Sicherheit durch Bedrohungs- und Risikoanalysen stärken | Daniel Angermeier | 137–151 |
| 8 | Sicherheitstesten | Jürgen Großmann | 153–179 |
| 9 | Der Faktor Mensch | Kristin Weber | 183–225 |
| 10 | IT-Sicherheit – Aus dem Blickwinkel eines CISO | Ümit Kuşdoğan | 229–254 |
| 11 | Warum IT-Sicherheit zwischen Erfolg und Insolvenz entscheidet | Florian Jörgens | 257–265 |
| 12 | IT-Sicherheit heute und morgen – aus Sicht eines CISO | Markus Schmall | 267–289 |
| 13 | Entwicklung sicherer Software | Nicolai Kuntze, Hagen Lauer | 291–308 |
| 14 | Cybersicherheit in Produktion, Automotive und intelligenten Gebäuden | Marko Schuba, Hans Höfken | 311–336 |
| 15 | Edge Computing: Chancen und Sicherheitsrisiken | Marcel Winandy | 339–361 |
| 16 | Cybersicherheit für kritische Infrastrukturen (KRITIS) | Martin Serror | 363–390 |
| 17 | Sicherheit in der Cloud | Christoph Skornia | 393–409 |

## Kernaussagen mit Seitenzahl

### Kap 2 — Grundprinzipien (Lauer, Kuntze)

- **CIA-Triade** als klassische Schutzziele: Vertraulichkeit (Confidentiality), Integrität (Integrity), Verfügbarkeit (Availability). (S. 33)
- **Erweiterte Schutzziele** (Gold-Standard): Authentifizierung, Autorisierung, Auditing. (S. 33, 35)
- **Authentifizierung** beschreibt die Möglichkeit, Subjekte und Objekte möglichst eindeutig zu identifizieren; umfasst Tokens, kryptografische Schlüssel, biometrische Faktoren. (S. 35)
- **Autorisierung** prüft nach erfolgreicher Authentifizierung, welche Berechtigungen das Subjekt hat; ein effektives Framework benötigt einen Monitor, ein eindeutiges Regelwerk und Isolation vom Subjekt. (S. 35)
- **Auditing** als Fähigkeit, Handlungen im System nachzuvollziehen und eindeutig zuzuordnen; basiert auf Protokollen und Logs. (S. 35)
- **Security by Design**: Sicherheit muss bereits im Entwurf eine wichtige Rolle spielen, genauso wie Funktionalität oder Benutzbarkeit. Es gibt keine Axiome, die für jedes System einsetzbar wären. (S. 40–41)
- **Keine Security through Obscurity**: Sicherheit darf nie auf der Geheimhaltung der Funktionsweise beruhen (Kerckhoffs 1883); die Sicherheit der Verschlüsselung muss auf dem Schlüssel beruhen. (S. 40)
- **Prinzip der geringsten Berechtigung**: Personen, Systeme und Programme sollen zu jedem Zeitpunkt nur die Berechtigung haben, die zur Bearbeitung unbedingt nötig ist; Berechtigungen nur zeitweise in Anspruch nehmen. (S. 42)
- **Zugriffskontrolle**: Grundlage ist Isolation und ein Regelwerk, das Subjekte, Objekte und Rechte definiert; Monitor/Wächter entscheidet über Zugriffsanfragen und loggt diese (Audit). (S. 43)
- **Defense in Depth**: Überlappender Einsatz von IT-Sicherheitsmaßnahmen von den obersten bis zu den untersten Systemschichten; keine einzelne Maßnahme ist ausreichend. Keine der genannten Maßnahmen ist für sich allein genommen „ausreichend" — erst eine Kombination erzeugt hinreichende Sicherheit. (S. 44–45)
- **Design for Resilience**: Absolut sichere Systeme existieren nicht; erfolgreiche Angriffe müssen mit eingeplant werden („Assume Breach"); Wiederherstellungsstrategie ist oft wertvoller als reine Schutzmaßnahmen. (S. 46)

### Kap 13 — Entwicklung sicherer Software (Kuntze, Lauer)

- **Security by Design über den gesamten Lebenszyklus**: Einzelne Maßnahmen können ohne Einbettung in den Lebenszyklus ihre volle Wirkung nicht entfalten; umfasst Planung, Analyse, Design, Entwicklung, Testen, Ausliefern, Wartung und Dekommissionierung. (S. 291–292)
- **Microsoft Secure Development Lifecycle (SDL)**: Etabliertes Vorgehensmodell; Phasen Training, Requirements, Design, Implementation, Verification, Release, Response. (S. 292)
- **Secure Development Lifecycles** (SDL, CORAS, SDLC, Cigital Touchpoints, CLASP): Verschiedene Methoden zur strukturierten, wiederholbaren Integration von Sicherheit in Entwicklungszyklen. (S. 295–296)
- **SEI CERT Coding Standards** — wichtigste Regeln: (S. 300)
  - *Input validieren*: Eingaben aus nicht vertrauenswürdigen Quellen müssen stets überprüft werden (Länge, Sonderzeichen, fehlerhafte Formate); betrifft alle externen Quellen.
  - *Architektur und Design für Sicherheitsrichtlinien*: Softwarearchitektur muss darauf ausgelegt sein, Sicherheitsrichtlinien umzusetzen und durchzusetzen; Separation of Duties im Sourcecode.
  - *Keep it simple*: Ein Design sollte so einfach wie möglich gehalten werden; Komplexität erhöht Fehlerrisiko.

## Verwendung in der Arbeit

| Abschnitt | Bezug | Zitiervorschlag |
|---|---|---|
| 2.4.2 Sicherheitskonzept | CIA-Triade, Authentifizierung, Autorisierung, Auditing als theoretische Basis der Sicherheitsarchitektur | `\cite[S.\,33\,f.]{Loehr2024}` |
| 5.11 Sicherheit (Authentifizierung/Autorisierung) | Defense in Depth als Begründung für die zweistufige Validierung (Pre-Validator + Backend-Validierung) | `\cite[S.\,44]{Loehr2024}` |
| 5.8 Serverseitige Validierung | Input-Validierung als Sicherheitsgrundsatz (SEI CERT) | `\cite[S.\,300]{Loehr2024}` |
| 6 Evaluation/Diskussion | Prinzip der geringsten Berechtigung als Einordnung des Rollenkonzepts | `\cite[S.\,42]{Loehr2024}` |

> [!tip] Einordnung vs. Gadatsch/Mangiapane 2017
> [[Gadatsch, Mangiapane 2017 - IT-Sicherheit]] ist stärker betriebswirtschaftlich ausgerichtet (IT-Governance, Kosten, Audit-Anforderungen). Lang/Löhr 2025 ist technisch-konzeptuell stärker: Schutzziele, Grundprinzipien, Secure Development Lifecycle. Beide ergänzen sich. Für die Bachelorarbeit ist Lang/Löhr 2025 die bessere Quelle für die Abschnitte über technische Sicherheitsprinzipien, Gadatsch/Mangiapane für organisatorische Aspekte und DSGVO-Bezug.

## Kritische Einordnung

- **Sammelband**, kein einheitliches Werk: Jedes Kapitel hat eigene Autor:innen und eigene Literaturliste. Beim Zitieren im Fließtext immer den Kapitelautor mit angeben oder auf Abschnitte verweisen, nicht pauschal „Lang/Löhr".
- **Praxisorientierung**: Stärke ist der Überblick über Best Practices für Unternehmen; weniger geeignet als theoretische Referenz für Kryptographie oder formale Sicherheitsbeweise.
- **Aktualität**: 2. überarbeitete Auflage (2025), berücksichtigt NIS-2, AI Act, ITSiG 2.0; damit aktueller als viele Einzelwerke.
- **Empfehlung für die Arbeit**: Als Ergänzungsquelle für Abschnitt 5.11 und die Sicherheitsprinzipien in 2.4.2 sehr gut geeignet. Nicht als Hauptquelle für Clean Architecture oder JWT-Standards verwenden — dafür gibt es geeignetere Einzelquellen (RFC 7519, NIST).

## PDF

![[IT-Sicherheit Lang Löhr 2025.pdf]]
