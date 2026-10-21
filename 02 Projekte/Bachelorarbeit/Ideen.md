---
tags: [bachelorarbeit, ideen]
erstellt: 2026-08-11
---

# Ideen & Gedankenblitze

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!note] Nutzung
> Schreib hier alles rein, was dir beim Coden einfällt und für die Thesis relevant sein könnte — ohne Struktur, einfach raus damit. Aufräumen später.
> 
> Format: `DATUM — Gedanke` reicht.

---

2026-08-11 — Das Submodul-Problem war ein gutes Beispiel für die Schwierigkeit, Entwicklung und Dokumentation parallel zu halten. Könnte als Anekdote für Kapitel 05 (Herausforderungen bei der Entwicklung) taugen.

2026-10-04 — Die Kapselung der Telefónica-Schnittstelle hinter einem Vertrag (ADR-009) zahlt sich aus, falls die echte Anbindung noch vor der Abgabe kommt: Dann lässt sich in 5.4 zeigen, dass der Tausch der Ersatzimplementierung ohne Änderung der Fachlogik möglich war. Das wäre ein konkreter Beleg für das Dependency-Inversion-Prinzip aus 2.4.

2026-10-04 — Die Gebrauchstauglichkeit (Forschungsfrage 4) braucht keine eigene Studie: DIN EN ISO 9241-11 definiert sie über Effektivität, Effizienz und Zufriedenheit, und die Testdurchläufe messen mit Fehlerquote und Eingabezeit schon zwei davon. Die Kurzbefragung deckt die dritte ab.

2026-10-05 — Beim Schreiben der Grundlagen nicht nur Begriffe aneinanderreihen: Jeder Absatz braucht eine Überleitung zum nächsten Begriff und einen Satz, wofür er später gebraucht wird. Zum Beispiel muss Prozesssicherheit ausdrücklich von der Arbeitssicherheit am Mast abgegrenzt werden, sonst liegt die Verwechslung bei diesem Thema nahe.

2026-10-12 — Beim Erklären von Entwurfsentscheidungen trägt das Muster aus 3.2 am weitesten: erst die naheliegende Lösung, dann warum sie scheitert, dann die gewählte. In Kapitel 5 hat das an fast jeder Stelle funktioniert (eine Anwendung statt drei, Microservices, Regel reparieren, E-Mail-Antworten, Protokoll je Endpunkt).

2026-10-12 — Die Kommentare im AsiMiNu-Code sind eine sehr gute Quelle für Beispiele in der Arbeit. Der Fünf-Minuten-Begrenzer (zwei Instanzen zählen doppelt), die Anomalieerkennung (Überlappung heißt Korrektur, Anschluss heißt Stückelung) und das Prüfprotokoll ohne Anfrageinhalt sind dort schon fachlich begründet.

2026-10-12 — Ein echtes, mit dem Code des Systems erzeugtes JWT (Abb. 5.2) zeigt mehr als jede Beschreibung. Dabei fiel auf, dass die Firmenkennung nicht im Token steht, sondern serverseitig nachgeschlagen wird.

2026-10-18 — Ein Methodenbegriff wird verständlich, wenn man ihn gegen sein Gegenteil stellt und am eigenen Fall zeigt. „Gestaltungsorientiert“ wurde erst klar über den Vergleich mit einer verhaltensorientierten Arbeit, die nur zählen würde, wie oft Anfragen unvollständig ankommen.

2026-10-18 — Beim Faktencheck für Beispiele lohnt es sich, die ADRs selbst zu öffnen statt sich auf Erinnerung zu verlassen. Das SMS-Beispiel in 3.2 klang plausibel, hatte aber gar keinen eigenen ADR, nur einen Hinweis in ADR-002.

2026-10-18 — Seitenzahlen aus PDFs immer an der Fußzeile prüfen. Beim Memorandum standen sie unten, nicht oben, und der erste Beleg war dadurch um eine Seite verschoben.

2026-10-21 — Eine erfahrene Fachperson kann eine Evaluation realistischer machen als ein gestellter Testlauf. Den größten Aufwand im Prozess, die Wartezeit auf Rückfragen, kann ein Termin mit einer Kollegin, die sofort antwortet, gar nicht abbilden.

2026-10-21 — Bearbeitungszeit und Durchlaufzeit trennen. Pro Anfrage arbeitet die BayFu nur rund eine halbe Minute, aber jede zweite Anfrage liegt Stunden bis Tage in einer Rückfrage. Der Nutzen des Systems liegt vor allem in der Durchlaufzeit.

2026-10-21 — Die manuelle Prüfung fängt heute fast alle Fehler ab, auch die Korrekturen, die AsiMiNu-AdHoc falsch liest, weil die Mitarbeiterin immer zusätzlich ins Postfach schaut. Das bestätigt die Entscheidung vom 17.09. (Prüfung als Schutzinstanz, nicht dramatisieren) und zeigt, woran die Qualität heute hängt: an der Aufmerksamkeit einer Person.
