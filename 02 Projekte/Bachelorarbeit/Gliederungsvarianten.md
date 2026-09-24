---
tags: [bachelorarbeit, planung, gliederung]
status: aktiv
date: 2026-09-09
---

# Gliederungsvarianten

← zurück zu [[Bachelorarbeit AsiMinu App]] · verwandt: [[Kapitelplanung]]

Stand 09.09.2026. Grundlage: Auswertung von Exposé, LaTeX-Kapitelstruktur samt Todo-Blöcken,
[[Kapitelplanung]], [[ADR-zu-Kapitel]], den TH-Referenzdokumenten, `thesis.bib` und den 57 ADRs.
Die ausformulierten Fassungen (sechs Word-Dokumente) liegen seit 23.09.2026 im Vault unter
`07 Anhänge/Gliederung Bachelorarbeit/`.

> [!success] Entschieden
> Variante D wurde am 09.09.2026 gewählt und am 16.09.2026 auf Wunsch des Betreuers von neun auf
> sieben Kapitel zusammengelegt. Die Inhalte je Abschnitt in aktueller Nummerierung stehen in
> [[Gliederung Variante D - Abschnittsinhalte]], die Schreibregel für Kapitel 5 in
> [[Darstellungsmuster Entwurfsentscheidungen]], die Umfangsbegründung in
> [[Seitenumfang und Proportionen]], die Forschungsfragen samt Kapitelzuordnung in
> [[Forschungsfragen]].

## Die Varianten

| Variante | Ordnungsprinzip des Hauptteils |
|---|---|
| **A — Klassischer Aufbau** | erst die gesamte Umsetzung, danach die Begründung in einem eigenen Kapitel (entspricht der heutigen LaTeX-Struktur, nachgeschärft) |
| **B — Phasenmodell** | eigenes Methodikkapitel, danach je ein Ergebniskapitel pro Projektphase |
| **C — Aufbau nach Fakultätsvorlage** | exakt der empfohlene Aufbau, Entwurf und Realisierung als getrennte Kapitel |
| **D — Entscheidungsorientierter Aufbau** | jede Entwurfsentscheidung wird dort begründet, wo sie beschrieben wird |

## Bewertung

Zehn Kriterien zu je zehn Punkten, bewertet ohne Rücksicht auf bereits geleistete Arbeit:
**A 70, B 71, C 69, D 87.** A, B und C liegen praktisch gleichauf, weil jede ihre Stärke mit
einer Schwäche an anderer Stelle erkauft. A ist redundanzarm und leicht zu schreiben, aber
methodisch stumm und schwach in der Diskussion. B ist methodisch vorbildlich, hat aber starke
Redundanz zwischen Entwurf und Umsetzung. C ist richtlinientreu, verwendet aber ein ganzes
Kapitel auf die schwächsten Alternativen.

## Empfohlen: Variante D

Kapitelfolge: Einleitung, Grundlagen und Stand der Technik, Vorgehen und Untersuchungsdesign,
Ist-Analyse und Anforderungen, Architektur und Systementwurf, Realisierung entlang des
Änderungsantrags, Evaluation, Diskussion, Zusammenfassung und Ausblick.

Drei Eingriffe machen den Unterschied:

- **Entwurfsentscheidungen wandern in die Abschnitte selbst.** Jeder wesentliche Abschnitt der
  Kapitel 5 und 6 folgt dem Muster Entwurfsproblem, erwogene Alternativen mit Verwerfungsgrund,
  gewählte Lösung, Begründung, Umsetzung. Dadurch gelangen acht bis zehn statt drei Entscheidungen
  in die wissenschaftliche Diskussion, und die Richtlinienforderung nach der Diskussion
  alternativer Lösungswege wird durchgängig erfüllt statt an einer Stelle.
- **Ist-Analyse und Anforderungen werden zusammengelegt**, weil die Anforderung die direkte
  Antwort auf die jeweilige Schwachstelle ist. Vermeidet die doppelte Prozessbeschreibung.
- **Die Diskussion bekommt ein eigenes Kapitel** vor der Zusammenfassung, in dem die
  Forschungsfragen einzeln beantwortet werden.

Seitenverteilung bei 55 Seiten Fließtext: 4 / 7 / 3 / 7 / 7 / 12 / 8 / 4 / 3.

## Wesentliche Schwäche und Umgang damit

Kapitel 6 gliedert nach dem Prozessweg statt nach Komponenten. Die Komponentenübersicht steht
deshalb in Abschnitt 5.1, und Abschnitt 6.1 erklärt den Aufbau in zwei Sätzen. Außerdem muss die
Auswahl der vertieften Entscheidungen vorab feststehen, sonst wächst Kapitel 6 über sein Budget.

## Bewertungsmatrix im Detail

Nur wissenschaftliche Eignung, ohne Rücksicht auf bereits geleistete Arbeit.

| Kriterium | A | B | C |
|---|---|---|---|
| Passung zur Forschungsfrage | 8 | 8 | 7 |
| Wissenschaftliche Stringenz und roter Faden | 7 | 8 | 8 |
| Darstellung des Stands der Technik | 6 | 7 | 7 |
| Nachvollziehbarkeit der Methodik | 5 | 10 | 6 |
| Sichtbarkeit der eigenen Leistung | 8 | 6 | 8 |
| Verhältnis von Analyse zu Beschreibung | 7 | 6 | 7 |
| Einbindung und Qualität der Evaluation | 7 | 8 | 8 |
| Diskussion und Beantwortung der Fragen | 6 | 9 | 6 |
| Redundanzfreiheit | 7 | 4 | 4 |
| Richtlinienkonformität und Umsetzbarkeit | 9 | 5 | 8 |
| **Gesamt** | **70** | **71** | **69** |

Hinweis zur Entstehung: In der ersten Analyse („Gliederungsanalyse Bachelorarbeit_1.docx") wurde
noch **Variante A** empfohlen, weil die Umsetzbarkeit im Zeitrahmen ein tragendes Kriterium war.
Erst die zweite Bewertung ohne dieses Kriterium führte zu D. Das ist kein Widerspruch, sondern
derselbe Befund unter anderem Maßstab.

## Voraussichtliche Rückfragen und Antworten (auch fürs Kolloquium)

- **Warum gliedert der Realisierungsteil nach dem Prozessweg statt nach Komponenten?** Der
  Datenfluss ist der fachliche Gegenstand; eine komponentenweise Gliederung würde denselben Ablauf
  mehrfach zerschneiden. Komponentenübersicht in 5.1, Leseanleitung in 5.6.
- **Wird das einheitliche Muster nicht eintönig?** Nein, die Tiefe ist dreistufig gestaffelt und
  die vier Entscheidungsarten werden unterschiedlich dargestellt, siehe
  [[Darstellungsmuster Entwurfsentscheidungen]].
- **Wo werden die geforderten Lösungsalternativen diskutiert?** Auf zwei Ebenen: Systemauswahl
  (Low-Code-Ausbau, Standardwerkzeug, Eigenentwicklung) in 2.5, Entwurfsalternativen in den
  Abschnitten von Kapitel 5.
- **Ist die Zusammenlegung von Ist-Analyse und Anforderungen zulässig?** Die Richtlinie verlangt
  sinnvolle Beziehung und Proportion der Kapitel, aber keine Kapitelfolge. Die Zusammenlegung
  vermeidet die doppelte Prozessbeschreibung.
- **Ist die Evaluation belastbar, obwohl die Schnittstelle noch nicht produktiv ist?** Sie ist
  zweigeteilt: technische Verifikation ohne externe Mitwirkung, dazu kontrollierter Vergleich alt
  gegen neu. Fällt die echte Anbindung aus, bleibt die Stub-Messung als Rückfallebene und wird als
  Limitation ausgewiesen.
- **Wie werden eigene und übernommene Teile abgegrenzt?** In 1.4, und die betroffenen Abschnitte
  in Kapitel 5 weisen es erneut aus.
- **Warum ist der Umsetzungsteil so umfangreich?** Drei Weboberflächen, mehrschichtiges Backend,
  drei Datenbestände, vier Rollen, konfigurierbare Automatisierung, Protokollierung, Cloud-Betrieb
  mit Pipeline. Dargestellt werden davon nur drei Schwerpunkte in der Tiefe.

## Zu klären im Betreuergespräch

- Welche Variante wird umgesetzt?
- Zielumfang 55 bis 60 Seiten Fließtext?
- Wie viele Entwurfsentscheidungen sollen vertieft diskutiert werden?
- Eigenes Diskussionskapitel vor der Zusammenfassung?
