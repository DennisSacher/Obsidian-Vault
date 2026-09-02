---
tags: [bachelorarbeit, fragen]
erstellt: 2026-08-11
---

# Offene Fragen

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!note] Nutzung
> Für jede Frage: Quelle notieren, wann sie beantwortet wurde, und ggf. welche Entscheidung getroffen wurde.

## Für den Betreuer

- [ ] Welchen Fokus soll Kapitel 05 haben? Breite (alle Features kurz) oder Tiefe (ausgewählte Features ausführlich)?
- [ ] Wie viele ADRs sollen explizit diskutiert werden — alle 54 (Stand 12.08.2026, wächst laufend) oder eine Auswahl?
- [ ] Soll das Sicherheitskonzept ein eigenes Kapitel bekommen oder in Anforderungen/Realisierung integriert werden?

## Für die Recherche

- [ ] Welche wissenschaftlichen Quellen gibt es zu „Change Request Management in KMU"?
- [ ] ITIL 4 vs. ITIL 3 — welche Version ist für den Bayfu-Kontext relevanter?
- [ ] Gibt es Literatur zu Blazor WASM für Enterprise-Anwendungen?

## Formale Compliance (aus Schreibrichtlinien-Abgleich 12.08.2026)

- [ ] **KI-Nutzung ist laut Fakultätsvorgabe per Fußnote im Text zu dokumentieren** (Anfang/Ende des betroffenen Abschnitts, System+Version+Datum) — bisher hat kein einziges Kapitel eine solche Fußnote, obwohl Kapitel 01 mit KI-Unterstützung entstand. Muss vor Abgabe rückwirkend geklärt werden: welche Abschnitte wie stark KI-unterstützt entstanden sind, dann Fußnoten nachtragen + `ki_erklaerung.tex`-Tabelle final ausfüllen.
  - *Update 02.09.2026:* wird jetzt automatisch vom [[Bachelorarbeit AsiMinu App|Dashboard]] (`thesis/dashboard/`) nachverfolgt — bestätigt aktuell genau die 4 Sektionen in Kapitel 01 als offen (als KI-unterstützt markiert, aber noch keine erkennbare Fußnote im Text).
- [ ] `thesis.bib` hat aktuell nur 20 Einträge, Richtgröße laut Vorgabe sind 25–30+ Quellen (~2 Zitate/Seite) — bei fortschreitendem Kapitelausbau im Blick behalten, nicht erst am Ende nachzählen.
  - *Update 02.09.2026:* Dashboard zeigt live 13 von 20 Bib-Einträgen bereits im Text referenziert — Zähler „X von 25–30+" steht ab jetzt automatisch im Dashboard, kein manuelles Nachzählen mehr nötig.

## Technisch (noch ungeklärt)

- [ ] Gerichtsstand in den AGB (Entwurf: Kolbermoor) → mit Rechtsabteilung Bayfu bestätigen
- [ ] USt-IdNr. (DE327797562) und aktuelle Geschäftsführernamen im Impressum → gegen aktuelle Handelsregisterauszug prüfen
- [ ] `WertBeiGenehmigung`-Klon in den ADRs: welche Implementierungsdetails sind schutzwürdig und sollten in der öffentlichen BA nicht zu detailliert stehen?
