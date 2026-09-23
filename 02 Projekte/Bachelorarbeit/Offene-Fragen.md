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
  - *Präzisiert 17.09.2026:* Möglicherweise ist damit die AsiMinu-AdHoc-Übergangslösung gemeint, die du mit einem Kollegen gebaut hast. Zwei Teilfragen: Wurde daraus etwas in das AsiMinu-System übernommen, etwa der Excel-Parser oder das Datenmodell? Und hat derselbe Kollege zusätzlich am AsiMinu-System selbst mitgewirkt? Siehe [[AsiMiNu-Prozessablauf]].

## Für den Betreuer (ergänzt 16.09.2026)

- [ ] **Zielumfang für Kapitel 1.** Das Abstimmungsdokument sieht vier Seiten vor, der fertige
  Entwurf liegt bei knapp sechs. Der fachliche Kontext (drei Parteien, zwei Schaltfälle,
  firmeneigener Begriff) braucht diesen Platz. Argument: Was Kapitel 1 an Erklärung leistet,
  muss Kapitel 4 nicht noch einmal leisten. Zwei Kürzungshebel sind vorbereitet, 1.5 auf einen
  Absatz und der Absatz „Einordnung in die längerfristige Zielsetzung" in 1.2.

## Für die Recherche

- [x] **Erledigt 18.09.2026:** Quelle für CRQ-Definition → `ISO/IEC/IEEE 24765:2017` (`\cite{ISO24765}`), frei bei IEEE Xplore. Für ITSM/ITIL → Serrano/Faustino 2021 (`\cite{SerranoFaustino2021}`), Open Access. Beide in `thesis.bib` eingetragen, in Kapitel 2.1.1 und 1.1 verwendet. Siehe [[Zitate-und-Quellen]].
- [ ] Welche wissenschaftlichen Quellen gibt es zu „Change Request Management in KMU"?
- [ ] ITIL 4 vs. ITIL 3 — welche Version ist für den Bayfu-Kontext relevanter?
- [ ] Gibt es Literatur zu Blazor WASM für Enterprise-Anwendungen?
- [x] **Clean Architecture Quelle (erledigt 23.09.2026):** Lano & Yassipour Tehrani 2023 (Springer UTiCS, ISBN 978-3-031-44142-4) als Hauptquelle für Abschnitt 2.4.1 gewählt. TH Rosenheim hat Volltext-Zugriff. Martin 2017 wird nicht mehr benötigt.

## Formale Compliance (aus Schreibrichtlinien-Abgleich 12.08.2026)

- [ ] **KI-Nutzung ist laut Fakultätsvorgabe per Fußnote im Text zu dokumentieren** (Anfang/Ende des betroffenen Abschnitts, System+Version+Datum) — bisher hat kein einziges Kapitel eine solche Fußnote, obwohl Kapitel 01 mit KI-Unterstützung entstand. Muss vor Abgabe rückwirkend geklärt werden: welche Abschnitte wie stark KI-unterstützt entstanden sind, dann Fußnoten nachtragen + `ki_erklaerung.tex`-Tabelle final ausfüllen.
  - *Update 02.09.2026:* wird jetzt automatisch vom [[Bachelorarbeit AsiMinu App|Dashboard]] (`thesis/dashboard/`) nachverfolgt — bestätigt aktuell genau die 4 Sektionen in Kapitel 01 als offen (als KI-unterstützt markiert, aber noch keine erkennbare Fußnote im Text).
  - *Update 15.09.2026:* betrifft jetzt zusätzlich alle neun Kapitel, weil die komplette Umstellung auf Variante D sowie die Kurzfassungs- und Budget-Notizen mit KI-Unterstützung entstanden sind, und Kapitel 01 wird gerade weiter mit KI-Unterstützung überarbeitet (Word-Arbeitsdokument). Vor Abgabe entsprechend breiter gegenchecken, nicht nur Kapitel 01.
- [ ] `thesis.bib` hat aktuell nur 20 Einträge, Richtgröße laut Vorgabe sind 25–30+ Quellen (~2 Zitate/Seite) — bei fortschreitendem Kapitelausbau im Blick behalten, nicht erst am Ende nachzählen.
  - *Update 02.09.2026:* Dashboard zeigt live 13 von 20 Bib-Einträgen bereits im Text referenziert — Zähler „X von 25–30+" steht ab jetzt automatisch im Dashboard, kein manuelles Nachzählen mehr nötig.

## Nachzuziehen (ergänzt 16.09.2026)

- [ ] **Quelldokument korrigieren.** In `AsiMiNu_Workflow_1.docx` steht, die Anfrage werde bei
  Telefónica „ins Ticketing System geparst". Das stimmt nicht, Telefónica leitet die E-Mail nur
  weiter. Die Referenzdokumente sind korrigiert und tragen einen Warnhinweis, das Word-Dokument
  selbst noch nicht. Siehe [[AsiMiNu-Prozessablauf]].

## Technisch (noch ungeklärt)

- [ ] Gerichtsstand in den AGB (Entwurf: Kolbermoor) → mit Rechtsabteilung Bayfu bestätigen
- [ ] USt-IdNr. (DE327797562) und aktuelle Geschäftsführernamen im Impressum → gegen aktuelle Handelsregisterauszug prüfen
- [ ] `WertBeiGenehmigung`-Klon in den ADRs: welche Implementierungsdetails sind schutzwürdig und sollten in der öffentlichen BA nicht zu detailliert stehen?
- [ ] `thesis/dashboard/` nach der Umbenennung der Kapiteldateien im Zuge von Variante D (15.09.2026) prüfen: liest es noch die richtigen Pfade (z. B. `chapters/04/ist_analyse_anforderungen.tex` statt der alten `ist_analyse.tex`/`anforderungen_architektur.tex`, `herausforderungen.tex` entfällt komplett), oder müssen `update.ps1`/`status-setzen.ps1` angepasst werden? Siehe [[Kapitelplanung]].
