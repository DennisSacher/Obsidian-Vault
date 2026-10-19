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
- [x] Wie viele ADRs sollen explizit diskutiert werden — alle 57 (Stand 09.09.2026, wächst laufend) oder eine Auswahl?
  - *Entschieden 04.10.2026:* dreistufige Regel, ausführlich nur Entscheidungen, die eine Forschungsfrage tragen (derzeit 7). Siehe [[ADR-zu-Kapitel]].
- [ ] Soll das Sicherheitskonzept ein eigenes Kapitel bekommen oder in Realisierung integriert bleiben (aktueller Stand: integriert)?

## Für die Bayfu (Freigaben, ergänzt 16.09.2026)

- [x] *Entfällt 04.10.2026: 1.1 nennt nur noch die neutrale Aussage.* **Darf das Vergütungsmodell in der Arbeit stehen?** Einzelabrechnung vorher, jetzt Einmalzahlung plus Pauschale für Betrieb und Wartung. Die Arbeit wird von der Hochschule archiviert und in der Regel veröffentlicht. Betroffen ist Abschnitt 1.1 der Einleitung. Ohne Freigabe reicht die neutrale Aussage, dass die Bayfu künftig alle Anfragen zentral übernimmt und den Prozess im Gegenzug automatisiert. Details in [[AsiMiNu-Projekthintergrund]].
- [ ] Ebenfalls freigabepflichtig, derzeit bewusst nicht im Text: dass die Bayfu insgesamt weniger einnimmt als zuvor, die Angabe zum verbleibenden Personalbedarf von ein bis zwei Personen, und dass andere Firmen sich über den Prozess dazuverdienen wollten.
- [ ] **Was genau hat der Kollege beigetragen?** Wird für Abschnitt 1.4 (Abgrenzung) gebraucht, dort steht aktuell ein Platzhalter. Das Abstimmungsdokument verlangt die Angabe ausdrücklich, und ungenaue Angaben zur Eigenleistung sind bei einer Abschlussarbeit heikel.
  - *Stand 05.10.2026:* Der Platzhalter in 1.4 ist aus dem Text entfernt. AsiMiNu-AdHoc steht dort jetzt als Teil des Ist-Prozesses, „gemeinsam mit einem Kollegen entstanden“. Offen bleibt, ob daraus etwas ins neue System übernommen wurde und wie der Beitrag von Alexander Morbitzer am AsiMiNu-System (rund 350 von 600 Commits) in der Abgrenzung der Eigenleistung erscheint.
  - *Präzisiert 17.09.2026:* Möglicherweise ist damit die AsiMinu-AdHoc-Übergangslösung gemeint, die du mit einem Kollegen gebaut hast. Zwei Teilfragen: Wurde daraus etwas in das AsiMinu-System übernommen, etwa der Excel-Parser oder das Datenmodell? Und hat derselbe Kollege zusätzlich am AsiMinu-System selbst mitgewirkt? Siehe [[AsiMiNu-Prozessablauf]].

## Für den Betreuer (ergänzt 16.09.2026)

- [x] *Erledigt 04.10.2026: Kapitel 1 auf 5 Seiten gekürzt, Gesamtziel 40 Seiten.* **Zielumfang für Kapitel 1.** Das Abstimmungsdokument sieht vier Seiten vor, der fertige
  Entwurf liegt bei knapp sechs. Der fachliche Kontext (drei Parteien, zwei Schaltfälle,
  firmeneigener Begriff) braucht diesen Platz. Argument: Was Kapitel 1 an Erklärung leistet,
  muss Kapitel 4 nicht noch einmal leisten. Zwei Kürzungshebel sind vorbereitet, 1.5 auf einen
  Absatz und der Absatz „Einordnung in die längerfristige Zielsetzung" in 1.2.

## Neu am 04./05.10.2026

- [ ] **Echte Schnittstelle zu Telefónica vor der Abgabe?** Falls ja, mit dem Betreuer klären, ob
  sie noch in die Evaluation eingeht, denn der Evaluationsstand ist seit dem 30.09.2026
  eingefroren. Liste der dann anzupassenden Stellen in `thesis/Schreibstand.md`.
- [ ] **Testdurchläufe für Kapitel 6:** Wer übernimmt die Eingabe als Generalunternehmer? Für die
  Zufriedenheit nach DIN EN ISO 9241-11 braucht es GU-seitige Testpersonen, nicht nur
  BayFu-Mitarbeitende. Und: fünf Testfälle (Anhang B) oder zehn bis zwölf ([[Evaluationsplan]])?
- [ ] **Seitenzahl des Dumas-Zitats** (Definition Geschäftsprozess, 2. Auflage, vermutlich
  Kapitel 1.1, um S. 6) im PDF nachschlagen. Eine Quellen-Notiz zu Dumas 2018 fehlt noch.
- [ ] **KI-Fußnote in Kapitel 2** ist bei der Überarbeitung am 05.10.2026 verloren gegangen.

## Neu am 09. bis 12.10.2026

- [ ] **KI-Fußnote in Kapitel 5** fehlt am Kapitelanfang, die Datei wurde während der Session
  außerhalb geändert. Bewusst entfernt? Falls nicht, wieder einfügen und dabei die
  Überarbeitung vom 09. bis 12.10.2026 und die Excalidraw-Abbildungen 5.1 bis 5.4 nennen.
  Gleiches Muster wie in Kapitel 2 (05.10.2026).
- [ ] **Submodul-Stand:** Am 09.10.2026 wurde `asiminu-projekt` auf `5741794` (Fassung 1.34.1)
  aktualisiert, obwohl der Evaluationsstand laut Schreibstand bei `e7ca1ca` eingefroren ist.
  Zeiger zurücksetzen oder so lassen? Die Messwerte beziehen sich weiterhin auf `e7ca1ca`.
- [ ] **Läuft die Produktion schon?** 5.6 sagt „in der Produktion sind zwei Instanzen
  vorgesehen“. Gibt es vor Prod eine Freigabe wie vor Test?
- [ ] **Was bedeuten die Werte in eckigen Klammern** bei der Standortkategorie („2 [1-3-1]“)?
  Der Text sagt nur „weitere Angaben“.
- [x] **Kapitel 5 liegt bei 13 Seiten** (Budget 10). **Entschieden 12.10.2026:** Für Dennis in Ordnung, die Arbeit darf etwas länger werden. Keine Kürzung nötig.
- [ ] **F07 in Kapitel 6:** Die Lücke ist in 5.4 jetzt genau beschrieben (Anomalieerkennung
  nur auf dem Weg der Automatik, keine Überschneidungsprüfung im manuellen Weg, kein
  Hinweis im CC-Panel). Bewertung in 6.2 daran angleichen.

## Neu am 12.10.2026 (Testdurchläufe)

- [ ] **Antwort der BayFu** auf die Anfrage zu den Testdurchläufen (Personen, Termin bis 23.10.,
  Monatsvolumen, heutige Bearbeitungsdauer). Stichtag 16.10., sonst Plan B.
- [ ] **Gibt es eine Testinstanz von AsiMiNu-AdHoc?** Davon hängen TF 4 und TF 5 auf dem alten Weg ab.
- [x] **Welche Felder hat die TSM-Eingabemaske?** Entfällt (15.10.2026): Kein TSM-Ersatz, die Abtippzeit wird stattdessen im Betrieb bei 5 bis 10 echten Anfragen beobachtet (Abschnitt 3.5 im Testfall-Dokument, Blatt Beobachtung TSM).
- [ ] **Verhält sich das anonymisierte Excel-Template wie das Original** (Zeilen werden beim
  Verringern der Ausfalltage nur ausgeblendet)?
- [ ] **Wie arbeitet die BayFu im Betrieb, solange die Telefónica-Schnittstelle fehlt?** Tippt der CC
  weiter von Hand ins TSM? Zeigt das CC-Panel die Angaben so, dass man sie gut übernehmen kann?
- [ ] **Submodul-Zeiger** auf `5741794` lassen (Empfehlung) und im Schreibstand vermerken, dass sich
  die Messwerte auf `e7ca1ca` beziehen? Bestätigung von Dennis fehlt.
- [x] **Telefónica-Schnittstelle:** kommt nicht vor der Abgabe (Info Dennis 12.10.2026). Absatz in 1.4
  wieder eingebaut.

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
- [ ] *Stand 05.10.2026: 21 Quellen zitiert, 11 Einträge ungenutzt (u. a. `MicrosoftAspNetSecurity2024`, seit der Kürzung von 2.4 nicht mehr zitiert).* `thesis.bib` hat aktuell nur 20 Einträge, Richtgröße laut Vorgabe sind 25–30+ Quellen (~2 Zitate/Seite) — bei fortschreitendem Kapitelausbau im Blick behalten, nicht erst am Ende nachzählen.
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

## Ergänzt 18.10.2026

- [ ] **Gliederung mit drei Ebenen beim Betreuer ansprechen.** Seit 18.10. gibt es 19 Unterkapitel in 2.4, 5.1 bis 5.4, 5.6, 6.1 und 6.5. Findet er die alte zweistufige Fassung besser, liegt sie als Git-Tag `vor-dritte-ebene-2026-10-18` und als PDF in `thesis/Sicherung/` bereit, Rückweg in `thesis/Schreibstand.md`.
- [ ] **Neue Quelle Österle et al. 2010** ist ein Positionspapier (Rubrik „Kontaktstudium“ der zfbf), Peer-Review unklar. Falls der Betreuer eine international begutachtete Quelle für die Methodik erwartet, Hevner et al. 2004 (MIS Quarterly) ergänzen. Zugang über die TH-Bibliothek prüfen. Siehe [[Österle et al. 2010 - Memorandum gestaltungsorientierte Wirtschaftsinformatik]].
- [ ] **ADR-055 nennt acht Bedingungen, 5.4 nennt neun.** Beim Faktencheck am 18.10. aufgefallen. Prüfen, ob nach dem ADR eine Bedingung dazukam (Abb. 5.4 zeigt die Kennungen aus `AutomatisierungsGrund`).
- [ ] **Unbenutzte Einträge in `thesis.bib` (Stand 18.10.: 22 von 33 zitiert).** Nicht zitiert: KuehnelDeitelhoff2025, Loehr2024, MicrosoftAspNetSecurity2024, MicrosoftAzureSecurity2024, Nielsen1993, RichterFlueckiger2013, Schlick2022, SchmelzerSesselmann2020, Suryn2014, VanDerAalst2018, VomBrockeRosemann2015. Vor der Abgabe entfernen oder zitieren (Richtlinie: jede Quelle im Verzeichnis muss im Text vorkommen).

## Ergänzt 19.10.2026

- [ ] **Kapitel 4, Fall 1 „ausgeblendete Excel-Zeilen“ prüfen.** Das echte Work Info Template v1.51 blendet beim Verringern der Ausfalltage keine Zeilen aus. Datum und Uhrzeit der überzähligen Tage bleiben sichtbar, nur die Beschriftung „Tag n“ wird weiß. Prüfen, auf welcher Template-Version Abb. 4.2 und die Beschreibung von Fall 1 beruhen, und den Text ggf. anpassen. Siehe [[Arbeitsprotokolle/2026-10-19|Arbeitsprotokoll 19.10.2026]].
- [ ] **Wartezeit bei Rückfragen** wird im Test nicht nachgestellt. Für 6.3 bei den Kollegen erfragen (typische Antwortzeit eines GU, Häufigkeit) und als Grenze in 6.6 nennen.
