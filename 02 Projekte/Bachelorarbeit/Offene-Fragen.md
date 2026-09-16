---
tags: [bachelorarbeit, fragen]
erstellt: 2026-08-11
---

# Offene Fragen

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!note] Nutzung
> Für jede Frage: Quelle notieren, wann sie beantwortet wurde, und ggf. welche Entscheidung getroffen wurde.

## Für den Betreuer

- [ ] Welchen Fokus soll Kapitel 06 (Realisierung) haben? Breite (alle Features kurz) oder Tiefe (ausgewählte Features ausführlich)? Laut Abstimmungsdokument aktuell drei Tiefenschwerpunkte: Backend, TEF-Automatisierung, Sicherheit.
- [ ] Wie viele ADRs sollen explizit diskutiert werden — alle 57 (Stand 09.09.2026, wächst laufend) oder eine Auswahl?
- [ ] Soll das Sicherheitskonzept ein eigenes Kapitel bekommen oder in Realisierung integriert bleiben (aktueller Stand: integriert)?

## Für die Bayfu (Freigaben, ergänzt 16.09.2026)

- [ ] **Darf das Vergütungsmodell in der Arbeit stehen?** Einzelabrechnung vorher, jetzt Einmalzahlung plus Pauschale für Betrieb und Wartung. Die Arbeit wird von der Hochschule archiviert und in der Regel veröffentlicht. Betroffen ist Abschnitt 1.1 der Einleitung. Ohne Freigabe reicht die neutrale Aussage, dass die Bayfu künftig alle Anfragen zentral übernimmt und den Prozess im Gegenzug automatisiert. Details in [[AsiMiNu-Projekthintergrund]].
- [ ] Ebenfalls freigabepflichtig, derzeit bewusst nicht im Text: dass die Bayfu insgesamt weniger einnimmt als zuvor, die Angabe zum verbleibenden Personalbedarf von ein bis zwei Personen, und dass andere Firmen sich über den Prozess dazuverdienen wollten.
- [ ] **Was genau hat der Kollege beigetragen?** Wird für Abschnitt 1.4 (Abgrenzung) gebraucht, dort steht aktuell ein Platzhalter. Das Abstimmungsdokument verlangt die Angabe ausdrücklich, und ungenaue Angaben zur Eigenleistung sind bei einer Abschlussarbeit heikel.

## Für die Recherche

- [ ] Welche wissenschaftlichen Quellen gibt es zu „Change Request Management in KMU"?
- [ ] ITIL 4 vs. ITIL 3 — welche Version ist für den Bayfu-Kontext relevanter?
- [ ] Gibt es Literatur zu Blazor WASM für Enterprise-Anwendungen?

## Formale Compliance (aus Schreibrichtlinien-Abgleich 12.08.2026)

- [ ] **KI-Nutzung ist laut Fakultätsvorgabe per Fußnote im Text zu dokumentieren** (Anfang/Ende des betroffenen Abschnitts, System+Version+Datum) — bisher hat kein einziges Kapitel eine solche Fußnote, obwohl Kapitel 01 mit KI-Unterstützung entstand. Muss vor Abgabe rückwirkend geklärt werden: welche Abschnitte wie stark KI-unterstützt entstanden sind, dann Fußnoten nachtragen + `ki_erklaerung.tex`-Tabelle final ausfüllen.
  - *Update 02.09.2026:* wird jetzt automatisch vom [[Bachelorarbeit AsiMinu App|Dashboard]] (`thesis/dashboard/`) nachverfolgt — bestätigt aktuell genau die 4 Sektionen in Kapitel 01 als offen (als KI-unterstützt markiert, aber noch keine erkennbare Fußnote im Text).
  - *Update 15.09.2026:* betrifft jetzt zusätzlich alle neun Kapitel, weil die komplette Umstellung auf Variante D sowie die Kurzfassungs- und Budget-Notizen mit KI-Unterstützung entstanden sind, und Kapitel 01 wird gerade weiter mit KI-Unterstützung überarbeitet (Word-Arbeitsdokument). Vor Abgabe entsprechend breiter gegenchecken, nicht nur Kapitel 01.
- [ ] `thesis.bib` hat aktuell nur 20 Einträge, Richtgröße laut Vorgabe sind 25–30+ Quellen (~2 Zitate/Seite) — bei fortschreitendem Kapitelausbau im Blick behalten, nicht erst am Ende nachzählen.
  - *Update 02.09.2026:* Dashboard zeigt live 13 von 20 Bib-Einträgen bereits im Text referenziert — Zähler „X von 25–30+" steht ab jetzt automatisch im Dashboard, kein manuelles Nachzählen mehr nötig.

## Technisch (noch ungeklärt)

- [ ] Gerichtsstand in den AGB (Entwurf: Kolbermoor) → mit Rechtsabteilung Bayfu bestätigen
- [ ] USt-IdNr. (DE327797562) und aktuelle Geschäftsführernamen im Impressum → gegen aktuelle Handelsregisterauszug prüfen
- [ ] `WertBeiGenehmigung`-Klon in den ADRs: welche Implementierungsdetails sind schutzwürdig und sollten in der öffentlichen BA nicht zu detailliert stehen?
- [ ] `thesis/dashboard/` nach der Umbenennung der Kapiteldateien im Zuge von Variante D (15.09.2026) prüfen: liest es noch die richtigen Pfade (z. B. `chapters/04/ist_analyse_anforderungen.tex` statt der alten `ist_analyse.tex`/`anforderungen_architektur.tex`, `herausforderungen.tex` entfällt komplett), oder müssen `update.ps1`/`status-setzen.ps1` angepasst werden? Siehe [[Kapitelplanung]].
