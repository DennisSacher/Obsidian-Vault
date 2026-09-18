---
tags: [bachelorarbeit, planung, gliederung]
status: aktiv
date: 2026-09-09
---

# Gliederungsvarianten

← zurück zu [[Bachelorarbeit AsiMinu App]] · verwandt: [[Kapitelplanung]]

Stand 09.09.2026. Grundlage: Auswertung von Exposé, LaTeX-Kapitelstruktur samt Todo-Blöcken,
[[Kapitelplanung]], [[ADR-zu-Kapitel]], den TH-Referenzdokumenten, `thesis.bib` und den 57 ADRs.
Die ausformulierten Fassungen liegen als Word-Dokumente auf dem Desktop.

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

## Zu klären im Betreuergespräch

- Welche Variante wird umgesetzt?
- Zielumfang 55 bis 60 Seiten Fließtext?
- Wie viele Entwurfsentscheidungen sollen vertieft diskutiert werden?
- Eigenes Diskussionskapitel vor der Zusammenfassung?
