---
tags: [bachelorarbeit, quelle, change-request, standard]
bibtex-key: ISO24765
autor: ISO/IEC/IEEE
jahr: 2017
titel: "ISO/IEC/IEEE 24765:2017 Systems and software engineering — Vocabulary"
typ: Norm (Glossar-Standard)
themenbereich: Change Request Management / ITIL
status: teilweise gelesen
---

# ISO/IEC/IEEE 24765:2017 — Systems and Software Engineering Vocabulary

← zurück zu [[Zitate und Quellen]]

> [!warning] Prüfhinweis: Formulierung in Abschnitt 2.1.1 ist so nicht durch die Norm gedeckt
> In `chapters/02/grundlagen.tex` (Zeile 30 f.) steht: „Ein Change Request ist ein formal eingereichter Änderungsantrag, der zusammen mit seinen **Statusinformationen über den gesamten Lebenszyklus nachverfolgt** wird \cite{ISO24765}."
> Die Definition 3.547 (S. 66) sagt nur „formal proposal to modify any document, deliverable, or baseline" bzw. „formal procedure for submitting a request for an adjustment of a configuration item". Von Statusverfolgung über den Lebenszyklus steht dort **nichts**, auch in keinem anderen Eintrag zu change request. Am nächsten kommt 3.783 *configuration status accounting* (S. 92), das Erfassen und Berichten u.a. des „status of proposed changes".
> **Vorschlag:** Den ersten Teil mit `\cite[S.\,66]{ISO24765}` belegen und die Statusverfolgung entweder streichen, separat über 3.783 (S. 92) belegen oder mit einer ITSM-Quelle (z.B. Serrano/Faustino 2021) absichern. Zusätzlich fehlt im Text bisher die Seitenangabe.

## Metadaten

| Feld | Wert |
|---|---|
| Autor/Hrsg. | ISO / IEC / IEEE (erarbeitet von ISO/IEC JTC 1/SC 7 mit der IEEE Computer Society) |
| Titel | Systems and software engineering — Vocabulary |
| Jahr | 2017 (Second edition, 2017-09; ersetzt die 1. Ausgabe 24765:2010) |
| Referenznummer | ISO/IEC/IEEE 24765:2017(E) |
| Verlag | ISO (Genf) / IEEE (New York) |
| Seiten | 536 (PDF), davon S. 2–515 Begriffe (Abschnitt 3, ca. 4.600 Einträge) |
| DOI / URL | https://ieeexplore.ieee.org/document/8016712 |
| Zugang | TH Rosenheim: lizenzierter Volltext via IEEE Xplore (laut PDF-Fußzeile „Authorized licensed use limited to: Hochschule Rosenheim"), **kein** Open Standard |
| Abgerufen | 23.09.2026 |
| BibTeX-Key | `ISO24765` |

## Vollzitat (für das Literaturverzeichnis)

ISO/IEC/IEEE: ISO/IEC/IEEE 24765:2017 Systems and software engineering — Vocabulary. 2. Ausgabe. Genf: International Organization for Standardization, 2017. Online verfügbar über IEEE Xplore: https://ieeexplore.ieee.org/document/8016712 (Zugriff: 23.09.2026)

## Kurzzitat (Verweis im Fließtext)

ISO/IEC/IEEE 24765:2017, S. XX (bzw. Eintrag 3.XXX)

> [!tip] Seitenzahlen
> Druckseite = PDF-Seite minus 9 (z.B. Druckseite 66 = PDF-Seite 75). Die Einträge sind alphabetisch sortiert und nummeriert (3.1 bis ca. 3.4600). Bei Normen ist neben der Seite auch die Eintragsnummer üblich, z.B. „ISO/IEC/IEEE 24765:2017, 3.547".
> Viele Einträge übernehmen Definitionen aus anderen Normen oder dem PMBOK Guide; die Herkunft steht jeweils in eckigen Klammern. Zitiert wird trotzdem 24765.

## Aufbau

1. Scope (S. 1–2): Vokabular für Systems- und Software-Engineering, Print- und Online-Version (SEVOCAB, www.computer.org/sevocab)
2. Normative references (S. 2)
3. Terms, definitions, and abbreviated terms (S. 2–515)
- Annex A: List of References (S. 516), Bibliography (S. 517)

## Kernaussagen und Zitate (Definitionen)

### Change Request Management (Kernbegriffe der Arbeit)

- **3.547 change request** (S. 66): „a formal proposal to modify any document, deliverable, or baseline" [PMBOK 5th ed.] sowie „formal procedure for submitting a request for an adjustment of a configuration item" [ISO/IEC TR 18018:2010] — wörtlich; cf. modification request, request for change
- **3.3423 request for change** (S. 379): Vorschlag für eine Änderung an einem System, Service, einer Komponente oder dem Service-Management-System bzw. funktionale oder nicht-funktionale Änderung an einer bestehenden Anwendung [ISO/IEC 16350:2015] — sinngemäß; das ist der ITIL-nahe Begriff (RfC)
- **3.2500 modification request (MR)** (S. 280): vorgeschlagene Änderungen an einem Produkt in Wartung [IEEE 14764-2006]; kann als corrective, preventive, adaptive oder perfective klassifiziert werden — sinngemäß
- **3.3428 requested change** (S. 380): formal dokumentierter Change Request, der zur Genehmigung eingereicht wird [PMBOK] — sinngemäß
- **3.204 approved change request** (S. 25): Change Request, der den Integrated-Change-Control-Prozess durchlaufen hat und genehmigt wurde [PMBOK] — sinngemäß
- **3.535 change** (S. 65): „the modification of an existing application comprising additions, changes and deletions" — wörtlich
- **3.537 change control** (S. 65): Prozess, in dem Änderungen an Dokumenten, Deliverables oder Baselines identifiziert, dokumentiert, genehmigt oder abgelehnt werden [PMBOK] — sinngemäß
- **3.538 change control board (CCB)** (S. 65): formal eingesetzte Gruppe, die Änderungen prüft, bewertet, genehmigt, zurückstellt oder ablehnt und die Entscheidungen dokumentiert und kommuniziert — sinngemäß
- **3.543 change management** (S. 66): „judicious use of means to effect a change, or a proposed change, to a product or service" — wörtlich
- **3.546 change record** (S. 66): Aufzeichnung, welche Configuration Items von einer genehmigten Änderung wie betroffen sind — sinngemäß
- **3.783 configuration status accounting** (S. 92): Erfassen und Berichten der Informationen für effektives Konfigurationsmanagement; laut Note 1 u.a. der Status vorgeschlagener Änderungen und der Umsetzungsstatus genehmigter Änderungen [ISO/IEC TR 18018:2010] — sinngemäß; **einzige Stelle mit Statusverfolgung**
- **3.1888 impact analysis** (S. 214): Identifikation aller Produkte, die ein Change Request betrifft, plus Aufwandsschätzung — sinngemäß
- **3.2860 perform integrated change control** (S. 318): Prüfen aller Change Requests, Genehmigen und Steuern von Änderungen, Kommunikation der Entscheidung [PMBOK] — sinngemäß
- **3.3713 service desk** (S. 411): kundenseitige Supportgruppe zur zentralen Bearbeitung von Incidents, Change Requests und Beschwerden — sinngemäß

### Prozesse und Anforderungen

- **3.445 business process** (S. 54): „partially ordered set of enterprise activities that can be executed to achieve some desired end-result in pursuit of a given objective of an organization" — wörtlich
- **3.3431 requirement** (S. 380): „statement that translates or expresses a need and its associated constraints and conditions" [ISO/IEC/IEEE 29148] — wörtlich
- **3.1704 functional requirement** (S. 195): Anforderung, die eine Funktion spezifiziert, die ein System ausführen soll [IEEE 730-2014] — sinngemäß
- **3.2621 nonfunctional requirement** (S. 293): beschreibt nicht, was die Software tut, sondern wie sie es tut — sinngemäß
- **3.3943 stakeholder** (S. 435): Person oder Organisation mit Recht, Anteil, Anspruch oder Interesse an einem System [ISO/IEC/IEEE 15288]; Stakeholder können gegensätzliche Interessen haben — sinngemäß
- **3.4462 use case** (S. 494), **3.4483 user story** (S. 497) — sinngemäß
- **3.3219 prototype** (S. 357): vorläufige Version eines Systems als Modell für spätere Stufen; dient u.a. dazu, frühes Nutzerfeedback zu Anforderungen einzuholen [PMBOK] — sinngemäß
- **3.4350 traceability** (S. 481): Grad, in dem sich Beziehungen zwischen Produkten des Entwicklungsprozesses herstellen lassen, z.B. Anforderung ↔ Design — sinngemäß
- **3.298 audit** (S. 36): systematischer, unabhängiger, dokumentierter Prozess zur Prüfung, ob Anforderungen erfüllt sind — sinngemäß

### Architektur und Qualität

- **3.216 architecture** (S. 26): „fundamental concepts or properties of a system in its environment embodied in its elements, relationships, and in the principles of its design and evolution" [ISO/IEC/IEEE 42010] — wörtlich
- **3.698 component** (S. 82), **3.2058 interface** (S. 234), **3.2190 layer** (S. 248) — sinngemäß
- **3.919 coupling** (S. 107): Art und Grad der Abhängigkeit zwischen Softwaremodulen; **3.625 cohesion** (S. 74): Grad, in dem die Aufgaben eines Moduls zusammengehören — sinngemäß
- **3.2314 maintainability** (S. 260): u.a. „degree of effectiveness and efficiency with which a product or system can be modified by the intended maintainers" [ISO/IEC 25010] — wörtlich
- **3.2498 modifiability** (S. 280): Änderbarkeit ohne Einführung von Fehlern oder Qualitätsverlust [ISO/IEC 25010] — sinngemäß
- **3.4181 technical debt** (S. 462): „the deferred cost of work not done at an earlier point in the product life cycle" — wörtlich
- **3.3653 security** (S. 404): u.a. Schutz von Informationen, sodass Unbefugte sie nicht lesen oder ändern können und Befugten der Zugriff nicht verwehrt wird [ISO/IEC 12207] — sinngemäß
- **3.3557 role** (S. 394) — nur allgemein (Beziehungs- bzw. Projektrolle), für RBAC nicht geeignet
- **3.4451 usability** (S. 492): Ausmaß, in dem ein System von bestimmten Nutzern in einem Nutzungskontext effektiv, effizient und zufriedenstellend genutzt werden kann [ISO/IEC 25010] — sinngemäß

### Evaluation

- **3.4500 validation** (S. 499): Bestätigung durch objektive Nachweise, dass die Anforderungen für einen bestimmten Verwendungszweck erfüllt sind; „The right system has been built." — sinngemäß/wörtlich
- **3.4538 verification** (S. 503): Bestätigung durch objektive Nachweise, dass spezifizierte Anforderungen erfüllt sind; „The system has been built right." — sinngemäß/wörtlich

## Verwendung in der Arbeit

- Kapitel 02, Abschnitt 2.1.1 (Begriffe, Akteure und Systemlandschaft): `\cite{ISO24765}` für die Change-Request-Definition (siehe Prüfhinweis oben, Seitenangabe `S.\,66` ergänzen)
- Abschnitt 1.1: im Index als mögliche Referenz vermerkt, aktuell dort aber **nicht** zitiert
- Potenziell weiter nutzbar: Kap. 2 (business process, requirement, stakeholder), Kap. 4 (functional/nonfunctional requirement, architecture, maintainability), Evaluationskapitel (validation vs. verification, usability)

## Verwendetes Zitat / Paraphrase im Text

Sinngemäß paraphrasiert in Abschnitt 2.1.1, kein wörtliches Zitat. Empfohlen: `\cite[S.\,66]{ISO24765}`.

## Kritische Einordnung

- Qualität/Seriosität: Internationale Norm von ISO, IEC und IEEE im Konsensverfahren. Höchste Autorität für Begriffsdefinitionen im Software Engineering.
- Aktualität: 2017. Das Vokabular wird laut Vorwort online über SEVOCAB (www.computer.org/sevocab) weiter gepflegt. Ob inzwischen eine neuere Druckausgabe existiert, ist nicht geprüft. Für Begriffsdefinitionen unkritisch, die 2017er Fassung ist die vorliegende und über die Hochschule zugängliche.
- Einschränkungen: Reines Glossar ohne Erläuterung oder Begründung. Viele Einträge haben mehrere, teils abweichende Definitionen aus verschiedenen Quellnormen; im Text sollte klar sein, welche gemeint ist. Die meisten Change-Request-Definitionen stammen eigentlich aus dem PMBOK Guide (Projektmanagement), nicht aus ITIL.

## Quell-Datei

![[ISO-IEC-IEEE 24765-2017 Systems and Software Engineering Vocabulary.pdf]]
