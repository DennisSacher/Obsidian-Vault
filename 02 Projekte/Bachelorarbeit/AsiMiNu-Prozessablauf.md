---
tags: [bachelorarbeit, fachlicher-kontext]
status: aktiv
date: 2026-09-16
---

# AsiMiNu-Prozessablauf

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!important] Verbindliche Referenz
> Diese Notiz beschreibt den tatsächlichen fachlichen Ablauf einer AsiMiNu-Anfrage.
> Sie ist die Referenz für alle fachlichen Aussagen im Thesis-Text. Wenn Kapiteltexte,
> das Exposé oder ältere Konzeptpapiere dem widersprechen, gilt diese Notiz.
> Grundlage ist `AsiMiNu_Workflow_1.docx` von Dennis, übergeben am 16.09.2026.
> Die ausführliche Fassung mit Zuordnung zu den Thesis-Kapiteln liegt im Repo unter
> `thesis/Fachlicher-Kontext-AsiMiNu.md`.

Siehe auch: [[AsiMiNu-Projekthintergrund]] für die Frage, warum es das Projekt gibt.

## Worum es im Kern geht

An einem Mobilfunkmast betreiben mehrere Netzbetreiber gleichzeitig eigene
Basisstationen. Muss ein Bauunternehmen dort arbeiten und dabei in den
Arbeitssicherheitsbereich der aktiven Antennen eines fremden Betreibers geraten,
braucht es von jedem dieser Betreiber eine befristete Abschaltung. Genau dafür gibt es
die AsiMiNu-Anfrage. Für Telefónica bearbeitet die BayFu diese Anfragen, und dieser
Bearbeitungsweg ist der Prozess, den die Bachelorarbeit automatisiert.

## Der Ablauf in acht Schritten

**1. Ausgangssituation.** Ein Generalunternehmer (GU) wird von einem Netzbetreiber
beauftragt, Arbeiten an einem Mobilfunkmasten durchzuführen, etwa Umbau- oder
Erweiterungsmaßnahmen. Am selben Mast betreiben häufig mehrere Netzbetreiber
gleichzeitig ihre eigene Basisstation, zum Beispiel Vodafone, Telefónica, Telekom und
1&1. Jeder Betreiber ist ausschließlich für sein eigenes Equipment verantwortlich.

**2. Interner Antrag beim eigenen Auftraggeber.** Der GU meldet seine geplanten
Arbeitszeiten zunächst im Ticketsystem seines Auftraggebers an, bei Telefónica
beispielsweise im TSM (Technical Site Management). Dadurch unterdrückt das NOC seines
Auftraggebers die Alarme im gemeldeten Zeitfenster, sodass das manuelle Abschalten vor
Ort keinen Fehlalarm auslöst.

**3. Das eigentliche Problem.** Dieser interne Antrag betrifft ausschließlich die
Netzelemente des Auftraggebers. Die Antennen der übrigen Betreiber am Mast bleiben
aktiv. Muss der GU in deren unmittelbarer Nähe arbeiten, besteht durch die Strahlung
aktiver Sendeanlagen ein Arbeitssicherheitsrisiko.

**4. Die AsiMiNu-Anfrage.** Nur wenn sich der GU im Arbeitssicherheitsbereich dieser
fremden aktiven Antennen bewegen muss, stellt er an jeden weiteren am Mast vertretenen
Betreiber eine gesonderte Arbeitssicherheitsanfrage, den AsiMiNu-Request (auch
MinuAsi-Request). Darin steht, wer ihn beauftragt hat, welche Arbeiten geplant sind und
wann genau sie stattfinden sollen.

**5. Weiterleitung und Prüfung durch die BayFu.** Bei Telefónica wird die Anfrage
zuerst in das Ticketsystem eingelesen und dann über organisatorische Regelungen an die
BayFu weitergeleitet. Die BayFu prüft sie auf Vollständigkeit und fachliche Richtigkeit
und überträgt sie bei korrektem Befund in das interne Telefónica-System. Nach
Genehmigung des Change Tickets gehen die Daten automatisch ans NOC, das die betroffenen
Netzelemente zu den angegebenen Zeiten abschaltet und die Alarme unterdrückt.

**6. Manuelle Abschaltung beim eigenen Auftraggeber.** Für die eigentlichen Arbeiten
muss der GU zusätzlich den Strom des betreffenden Netzelements vor Ort manuell
abschalten. Auch dafür unterdrückt das NOC seines Auftraggebers die Alarme im zuvor
gemeldeten Zeitfenster.

**7. Arbeitsbeginn.** Erst wenn alle AsiMiNu-Anfragen an alle beteiligten Betreiber
bearbeitet sind, sind sämtliche relevanten Netzelemente abgeschaltet und der GU kann
sicher arbeiten.

**8. Abmeldung am Abend.** Am Ende jedes Arbeitstages meldet sich der GU bei jedem
beteiligten NOC wieder ab, damit die Netzelemente über Nacht erneut aktiviert werden.
Unterbleibt die Abmeldung, entsteht beim betroffenen NOC ein Incident, weil davon
ausgegangen wird, dass sich noch jemand unangekündigt am Mast aufhält.

> [!tip] Zwei Details, die beim Schreiben leicht verloren gehen
> Die AsiMiNu-Anfrage ist kein Regelschritt jeder Baumaßnahme, sondern an die Bedingung
> aus Schritt 4 geknüpft. Und der Auftraggeber des GU ist in aller Regel ein anderer
> Betreiber als Telefónica, der GU tritt Telefónica gegenüber also als Dritter ohne
> Vertragsbeziehung auf.

## Beteiligte Rollen

| Rolle | Aufgabe im Prozess |
|---|---|
| GU (Generalunternehmer) | Führt die Bauarbeiten aus; stellt den internen Antrag beim Auftraggeber und die AsiMiNu-Requests an alle weiteren Betreiber. |
| Auftraggeber (z. B. Vodafone) | Beauftragt den GU; verwaltet den internen Antrag im eigenen System; steuert Abschaltung und Alarmunterdrückung über das eigene NOC. |
| Weitere Netzbetreiber (z. B. Telefónica, Telekom, 1&1) | Betreiben eigene Netzelemente am selben Mast; erhalten die AsiMiNu-Requests und veranlassen darüber die Abschaltung. |
| BayFu | Prüft und bearbeitet eingehende AsiMiNu-Requests für Telefónica und trägt genehmigte Anfragen ins interne Telefónica-System ein. |
| NOC | Schaltet Netzelemente zu den gemeldeten Zeiten ab, unterdrückt die Alarme und meldet einen Incident bei fehlender Abmeldung. |

Der Change Coordinator als interne Bearbeitungsrolle bei der BayFu, im System die Rolle
`TicketSpecialist` mit eigenem Panel, kommt erst im realisierten System dazu. Im
manuellen Ist-Prozess gibt es ihn noch nicht als eigenständige Rolle.

## Begriffe

| Begriff | Bedeutung |
|---|---|
| AsiMiNu / MinuAsi | Arbeitssicherheitsanfrage, mit der ein GU einen Netzbetreiber bittet, sein Netzelement für einen definierten Zeitraum abzuschalten. |
| NOC | Network Operation Center; überwacht den Netzbetrieb und reagiert auf Alarme. |
| TSM | Technical Site Management; internes System der Telefónica für Standort- und Arbeitszeitmeldungen. |
| RAN | Radio Access Network; die aktive Sendetechnik am Standort. |
| MNO | Mobile Network Operator; Mobilfunknetzbetreiber. |
| CRQ | Change Request; so heißt der Vorgang im Telefónica-Zielsystem, inklusive offizieller CRQ-Nummer. |
| Incident | Störungsmeldung beim NOC, wenn sich der GU nicht fristgerecht ab- oder anmeldet. |

**Verhältnis AsiMiNu zu CRQ:** Der AsiMiNu-Request ist die Anfrage aus Sicht des GU.
Nach Prüfung durch die BayFu und Eintragung ins Telefónica-System wird daraus ein
Change Request mit offizieller CRQ-Nummer. Der Thesis-Text verwendet durchgängig den
Begriff Change Request, meint damit aber genau diesen Vorgang.
