---
tags: [bachelorarbeit, planung, gliederung]
status: aktiv
date: 2026-09-23
---

# Gliederung Variante D: Abschnittsinhalte

← zurück zu [[Bachelorarbeit AsiMinu App]] · verwandt: [[Gliederungsvarianten]], [[Kapitelplanung]], [[Forschungsfragen]], [[Darstellungsmuster Entwurfsentscheidungen]], [[Seitenumfang und Proportionen]]

Was in welchen Abschnitt gehört, laut dem Abstimmungsdokument für den Betreuer vom 09.09.2026. **Auf die aktuelle 7-Kapitel-Struktur umgerechnet** (seit 16.09.2026 sind die alten Kapitel 5+6 und 7+8 zusammengelegt). Die Abschnittstitel entsprechen dem LaTeX-Stand vom 23.09.2026. Status und Schreibfortschritt je Kapitel: [[Kapitelplanung]].

> [!info] Umrechnung alte → neue Nummern
> Altes Kapitel 5 (Architektur) = 5.1 bis 5.5 · altes Kapitel 6 (Realisierung) = 5.6 bis 5.12 (6.1 → 5.6, 6.2 → 5.7 … 6.7 → 5.12) · altes Kapitel 7 (Evaluation) = 6.1 bis 6.5 · altes Kapitel 8 (Diskussion) = 6.6 bis 6.9 · altes Kapitel 9 = 7.
> In den `\todo`-Blöcken im LaTeX („Kurzfassung lt. Abstimmungsdokument") und in den Word-Originalen stehen teils noch die alten Nummern.

> [!warning] Formaler Befund 23.09.2026: Abschnitt 2.2 hat nur einen Unterabschnitt
> In `grundlagen.tex` steht unter 2.2 der Text zu Automatisierungsgraden und Entscheidungspunkten ohne eigene `\subsection`, danach folgt nur 2.2.1 „Regeln als Konfiguration statt als Programmlogik". Die TH-Richtlinie verlangt **verbindlich mindestens zwei Unterpunkte je Stufe**. Lösung: die Überschrift „Automatisierungsgrade und Entscheidungspunkte" als 2.2.1 wieder einsetzen (so im Variante-D-Plan vorgesehen) oder 2.2 ganz ohne Unterabschnitte führen.

## 1 Einleitung (4 Seiten)

- **1.1 Unternehmenskontext: BayFu und Telefónica.** Wer die beiden Unternehmen sind, wie sie zusammenarbeiten, welche Rolle GU und Change Coordinator haben. Seit 16.09. wird hier der fachliche Ablauf **einmal vollständig** erklärt (siehe `Schreibstand.md`).
- **1.2 Ausgangslage und Problemstellung.** Prozess über Excel und E-Mail bei steigender Antragslast, daraus die konkreten Fehlerquellen und die fehlende Nachvollziehbarkeit. Erklärt den Ablauf nicht erneut.
- **1.3 Zielsetzung und Forschungsfragen.** Hauptfrage und sechs Unterfragen, siehe [[Forschungsfragen]].
- **1.4 Abgrenzung des Betrachtungsgegenstands.** Was Eigenleistung ist, was aus der Low-Code-Lösung und AsiMiNu-AdHoc übernommen wurde, was ein Kollege beigetragen hat (INC-Worker aus einem Studentenprojekt portiert, Löschlauf, Prüfprotokoll, Systemzustands-Dashboard), wo die Systemgrenze zum Zielsystem liegt. Bekommt bewusst Raum, weil die Fakultät die Kennzeichnung eigener und vorhandener Teile **ausdrücklich verlangt**. Die betroffenen Abschnitte in Kapitel 5 nennen die Zuordnung erneut.
- **1.5 Aufbau der Arbeit.** Ein Absatz Kapitelüberblick, höchstens eine halbe Seite.

## 2 Grundlagen und Stand der Technik (8 Seiten)

Nur die Theorie, die später gebraucht wird. Elf Punkte der dritten Ebene; bei sieben Seiten läge der Schnitt dicht an der Untergrenze von 0,5 Seiten je Punkt, deshalb acht.

- **2.1 Der Change-Request-Prozess als Geschäftsprozess**
  - 2.1.1 Begriffe, Akteure und Systemlandschaft: Change Request, Generalunternehmer, Zielsystem und Vorgangsnummer sauber definiert
  - 2.1.2 Prozessanalyse und Redesign als Bezugsrahmen: der theoretische Rahmen, mit dem Kapitel 4 arbeitet
- **2.2 Automatisierung und regelbasierte Entscheidungslogik**
  - (2.2.1) Automatisierungsgrade und Entscheidungspunkte: Skala der Automatisierung, an welchen Stellen Entscheidungen fallen (siehe Warnhinweis oben)
  - 2.2.x Regeln als Konfiguration statt als Programmlogik: Theoriegrundlage für 5.9.1
- **2.3 Datenqualität und Eingabevalidierung**
  - 2.3.1 Qualitätsdimensionen als Messgrundlage: Vollständigkeit, Konsistenz, Korrektheit, **genau diese** werden in Kapitel 6 gemessen
  - 2.3.2 Validierung an der Datenquelle: warum frühe Validierung wirksamer ist als nachgelagerte Prüfung
- **2.4 Architektur, Zugriffsschutz und Nachvollziehbarkeit**
  - 2.4.1 Schichtung und Abhängigkeitsregel: Grundlage für 5.2
  - 2.4.2 Authentifizierung, Autorisierung und Protokollierung: Token-Auth, RBAC, Protokollierung als Grundlage für 5.11
- **2.5 Bestehende Lösungsansätze und Abgrenzung** (2 bis 3 Seiten, rechtfertigt die Eigenentwicklung)
  - 2.5.1 Die erprobte Vorgängerlösung und ihre Grenzen: woran sie gescheitert ist
  - 2.5.2 Standardwerkzeuge des IT-Service-Managements: marktübliche Werkzeuge und ihr fachlicher Zuschnitt
  - 2.5.3 Bewertung der Alternativen und Einordnung der eigenen Lösung, mit **expliziten Bewertungskriterien**: Funktionsabdeckung, Integrierbarkeit in die bestehende Landschaft, Betriebs- und Lizenzkosten, Erweiterbarkeit, Kontrolle über die Fachlogik

> [!tip] Warum die Systemauswahl nur in 2.5 steht
> Die Auswahl Low-Code-Ausbau / Standardwerkzeug / Eigenentwicklung war faktisch vor Beginn der Arbeit entschieden. Darum wird sie kompakt behandelt und **nicht** als rückwirkend konstruierte Auswahlentscheidung dargestellt. Der Fakultätsschritt „Lösungsalternativen" wird auf zwei Ebenen erfüllt: Systemauswahl in 2.5, Entwurfsalternativen in den Abschnitten von Kapitel 5.

## 3 Vorgehen (3 Seiten)

Bewusst knapp, kein Methodikkapitel im engeren Sinn. Das Evaluationsdesign steht vollständig in Kapitel 6 und wird hier nicht vorweggenommen.

- **3.1 Forschungslogik der Arbeit.** Wie die Arbeit als Untersuchung angelegt ist.
- **3.2 Erhebung des Ist-Zustands.** Wie ein bisher nirgends dokumentierter Prozess erschlossen wurde.
- **3.3 Entwurfs- und Entscheidungsverfahren.** Entscheidungssätze (ADRs) als Dokumentationsform, Bewertungskriterien, Umgang mit revidierten Entscheidungen. Begründet zugleich den Aufbau von Kapitel 5.

## 4 Ist-Analyse und Anforderungen (7 Seiten)

Trägt die empirische Grundlage der gesamten Argumentation. Jede Anforderung folgt **sichtbar** aus einer Schwachstelle.

- **4.1 Der bestehende Prozess** (ca. 2,5 Seiten)
  - 4.1.1 Ablauf von der Beantragung bis zur Genehmigung: Vorlage, Versand und manuelle Prüfung Schritt für Schritt
  - 4.1.2 Beteiligte Akteure und Verantwortlichkeiten: wer im Altprozess welche Aufgabe trägt (Aufzählung, kurz halten)
- **4.2 Schwachstellenanalyse** (ca. 2 Seiten, Kern des Kapitels)
  - 4.2.1 Fehlerquellen bei der Erfassung: fehlerhafte Vorlagen, unvollständige Felder, Formatabweichungen
  - 4.2.2 Medienbrüche und doppelte Dateneingabe
  - 4.2.3 Fehlende Nachvollziehbarkeit und Statusverfolgung: kein Status, keine Historie, Rückfragen nur per E-Mail
- **4.3 Abgeleitete Anforderungen** (4.3 und 4.4 zusammen ca. 2,5 Seiten)
  - 4.3.1 Funktionale Anforderungen, jeweils mit Bezug zur Schwachstelle aus 4.2
  - 4.3.2 Nicht-funktionale Anforderungen: Sicherheit, Nachvollziehbarkeit, Antwortzeiten, Betrieb
  - 4.3.3 Rollen- und Berechtigungsanforderungen: welche Rolle welche Daten sieht und welche Aktionen ausführt
- **4.4 Priorisierung und Abnahmekriterien.** Was Pflicht, was optional ist, woran die Erfüllung messbar wird.

## 5 Architektur und Realisierung (19 Seiten = 7 + 12)

### Architekturteil: systemweite Entscheidungen (5.1 bis 5.5, ca. 7 Seiten)

Sechs systemweite Entscheidungen, jede mit Alternativen und Verwerfungsgrund, also gut eine Seite je Entscheidung.

- **5.1 Systemkontext und Komponentenschnitt.** Kontext- und Containersicht: drei Weboberflächen, Backend, Hintergrunddienste, Zielsystem. **Hier steht die Komponentenübersicht**, weil der Realisierungsteil nicht nach Komponenten gliedert.
- **5.2 Schichtung und Abhängigkeitsregel**
  - 5.2.1 Schnitt der Schichten und Richtung der Abhängigkeiten: die vier Projekte (Shared, Domain, Infrastructure, Api) und die erlaubte Abhängigkeitsrichtung
  - 5.2.2 Einordnung des Benutzermodells als Grenzfall: Konflikt zwischen Abhängigkeitsregel und transitiver Infrastrukturabhängigkeit, mit erwogenen Alternativen
- **5.3 Datenhaltung und Datenmodell**
  - 5.3.1 Trennung der Datenbestände: warum Auth, CRQ und INC getrennte Datenbanken bekommen und was dagegen sprach
  - 5.3.2 Vorgangsidentität und nebenläufige Nummernvergabe: eindeutige Vorgangsnummer bei gleichzeitigen Zugriffen, verworfene Alternativen
- **5.4 Rollen- und Berechtigungsmodell.** Vier Rollen, Prinzip der geringsten Rechte, Schnitt der Berechtigungen.
- **5.5 Technologieauswahl und Bewertung der Alternativen.** Gewählte Plattform gegen erwogene Alternativen, jeweils mit Verwerfungsgrund.

### Realisierungsteil: entlang des Wegs eines Antrags (5.6 bis 5.12, ca. 12 Seiten)

Gliedert nach dem **Prozessweg**, nicht nach Komponenten. Drei Tiefenschwerpunkte (5.8, 5.9, 5.11), kompakt bleiben 5.10 und 5.12.

- **5.6 Aufbau des Realisierungsteils und Auswahl der vertieften Themen.** Leseanleitung: erklärt in zwei Sätzen die Gliederung nach dem Prozessweg und legt offen, welche Abschnitte vertieft und welche kompakt behandelt werden. **Ohne diese Leseanleitung sucht ein Gutachter nach einer Komponentenübersicht.**
- **5.7 Strukturierte Erfassung durch den Generalunternehmer** (ca. 2 Seiten)
  - 5.7.1 Formularentwurf und clientseitige Validierung: wie das Formular Fehleingaben abfängt, bevor sie das System erreichen
  - 5.7.2 Gestaltungsentscheidungen zur Fehlervermeidung: kuratiertes Firmenverzeichnis, Aufteilung zusammengesetzter Felder, Pflichtfeldlogik. **Hier wird FF4 verortet.**
- **5.8 Serverseitige Validierung und Verarbeitung** (Tiefenschwerpunkt, ca. 2,5 Seiten)
  - 5.8.1 Validierungsregeln und Fehlerbehandlung: serverseitige Prüfung und Rückmeldung an den Antragsteller
  - 5.8.2 Vergabe der Vorgangsnummer unter Nebenläufigkeit: gewählte Sperrmechanik gegen die verworfenen Alternativen
- **5.9 Regelbasierte Übertragung an das Zielsystem** (Tiefenschwerpunkt, ca. 3 Seiten, **stärkste Eigenleistung**)
  - 5.9.1 Von der fest verdrahteten Regel zur konfigurierbaren Regelbasis: Umstellung, nachdem sich die reale Standortdatenqualität als uneinheitlicher erwies als angenommen
  - 5.9.2 Ausführungsmodell und Nachholverhalten: geplante Läufe zu festen Zeiten, Umgang mit ausgefallenen Läufen
  - 5.9.3 Entwurf gegen eine noch nicht verfügbare Schnittstelle: Entscheiden unter Unsicherheit, Absicherung gegen das Ausfallrisiko
- **5.10 Interne Bearbeitung und Rückfragen** (bewusst kompakt, ca. 1 Seite). Interne Oberflächen und Rückfragenweg; Tabelle statt Prosa, Screenshots im Anhang.
- **5.11 Sicherheit und Nachvollziehbarkeit** (Tiefenschwerpunkt, ca. 2,5 Seiten)
  - 5.11.1 Authentifizierung und Sitzungsführung: Anmeldeverfahren, Zwei-Faktor, Sitzungserneuerung, **inklusive der revidierten Erstentscheidung** (SMS → TOTP)
  - 5.11.2 Durchsetzung der Berechtigungen: Befund, dass Berechtigungen zunächst nicht durchgängig geprüft wurden, und die Nachbesserung
  - 5.11.3 Prüfprotokoll als Grundlage der Prozesssicherheit: lückenlose Protokollierung aller Änderungen
- **5.12 Betrieb, Auslieferung und Qualitätssicherung** (bewusst kompakt, ca. 1 Seite). Cloud-Betrieb, Infrastructure as Code, Pipeline mit Qualitätstoren.

## 6 Evaluation und Diskussion (12 Seiten = 8 + 4)

Durchführung und Messdetails: [[Evaluationsplan]].

### Evaluationsteil (6.1 bis 6.5, ca. 8 Seiten)

- **6.1 Evaluationsziele und Kennzahlen.** Was gemessen wird und warum gerade diese Kennzahlen.
- **6.2 Technische Verifikation** (unabhängig von der Wirkungsmessung belegbar, **kann sofort geschrieben werden**)
  - 6.2.1 Automatisierte Testabdeckung: 971 Tests bei 81,3 % Codeabdeckung (Stand 09.09.2026, vor dem Schreiben aktualisieren)
  - 6.2.2 Funktionale Abdeckung gegen den Testfallkatalog: externer Katalog mit 352 Testfällen
- **6.3 Empirische Wirkungsmessung**
  - 6.3.1 Versuchsaufbau und Durchführung: Testfälle, Teilnehmende, Reihenfolgeausgleich, Pilotdurchlauf
  - 6.3.2 Messverfahren je Kennzahl
- **6.4 Ergebnisse** (Übersichtstabelle Kennzahl / alt / neu / Veränderung voran)
  - 6.4.1 Effizienz und Datenqualität: Bearbeitungszeit und Fehlerquote alt gegen neu
  - 6.4.2 Automatisierungsgrad und Prozesssicherheit: Anteil automatisch übertragener Anträge, Nachvollziehbarkeit
- **6.5 Limitationen der Messung.** Stichprobengröße, Beteiligung, Grenzen der Aussagekraft; die vier Fallstricke aus dem [[Evaluationsplan]] offen benennen.

### Diskussionsteil (6.6 bis 6.9, ca. 4 Seiten)

Erst nach der Auswertung schreiben, aber die Gliederung steht, damit die vorherigen Kapitel darauf hinarbeiten.

- **6.6 Beantwortung der Forschungsfragen.** Die sechs Unterfragen einzeln, gestützt auf die Kapitel 4 bis 6, siehe [[Forschungsfragen]].
- **6.7 Einordnung in den Stand der Technik.** Eigene Ergebnisse gegen Kapitel 2 gespiegelt.
- **6.8 Übertragbarkeit auf vergleichbare Prozesse.** Was sich auf andere Genehmigungsprozesse verallgemeinern lässt. Hebt die Arbeit über den Einzelfall, kostet kaum Platz.
- **6.9 Kritische Reflexion der eigenen Lösung.** Grenzen der Lösung, was heute anders entschieden würde; Abweichung Exposé ↔ Umsetzung als eigenes Ergebnis (nicht als „Herausforderungen" verkaufen).

## 7 Zusammenfassung und Ausblick (3 Seiten)

- **7.1 Zusammenfassung.** Ergebnisse verdichtet, **ohne neue Argumente** und ohne die Forschungsfragen erneut zu beantworten (das passiert in 6.6).
- **7.2 Ausblick.** Offene Punkte und absehbare Weiterentwicklung.

Richtlinie: drei bis vier Seiten, kritische Diskussion erwünscht.

## Anhang A bis F

Erhebungsinstrumente, Anforderungskatalog, ausgewählte Entscheidungssätze (ADRs) im Volltext, Messprotokolle, Screenshots und Quellcode-Auszüge, Erklärung zur Verwendung generativer KI-Systeme. Alles, was beschreibt statt argumentiert, gehört hierhin. Im Haupttext steht Code nur, wenn er eine Aussage trägt; Algorithmen programmiersprachenunabhängig darstellen.

## Quelle

Word-Originale vom 09.09.2026 unter `07 Anhänge/Gliederung Bachelorarbeit/`, vor allem „Gliederung Bachelorarbeit - Drei Varianten zur Abstimmung.docx" (Abschnitt 2.2 und 2.3).
