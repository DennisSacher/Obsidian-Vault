---
tags: [bachelorarbeit, testdurchläufe]
status: aktiv
date: 2026-10-20
---

# Ablauf Testtag 21.10.2026

Schritt-für-Schritt-Ablauf für die Testdurchläufe A und B. Grundlage: `Testfälle Testdurchläufe.docx` (Abschnitte 3 bis 6) und [[Arbeitsprotokolle/2026-10-19|Arbeitsprotokoll 19.10.2026]].

## Was die GU-Person bekommt

Die GU-Person sitzt am besten mit im Raum, an einem eigenen Rechner. Sie bekommt die Karten nacheinander auf Papier und die Templates als Dateien. Im Voraus bekommt sie nur die Dateien.

**Auf den GU-Rechner legen (per Mail oder USB-Stick, vor dem Termin):** den Inhalt von `Excel-Templates/Templates_fuer_1,2,3,4,5,6/`

- `Template alter Weg_fuer_1.xlsx`, `_fuer_3`, `_fuer_5`, `_fuer_6` (je eine eigene Datei für TF 1, 3, 5 und 6)
- `Template TF 2.xlsx`
- `Template TF 4 ursprünglich.xlsx`. Das ist genau die Datei, die an der ersten TF-4-Mail hängt. Die GU-Person muss diese ursprüngliche Anfrage korrigieren.

`Excel-Templates/Im_Vornhinein/` enthält die Vorab-Dateien (TF 4 und TF 5 ursprünglich) und bleibt bei dir.

**Nicht mitschicken:** das Testfall-Dokument, das Protokoll, `Template TF 5 ursprünglich.xlsx` und die Karten. Die Testperson soll die eingebauten Fehler nicht kennen.

**Außerdem braucht die GU-Person:**

- ein Mailkonto, mit dem sie ans Testpostfach schreiben kann
- das GU-Panel, mit „Test GU“ angemeldet

**Zu den Templates:**

- In den leeren Templates sind Ticketersteller-E-Mail und VEFK (Mustermann Max) schon vorbelegt. Die WorkInfo entsteht, sobald die GU-Person die Kartenangaben einträgt. Baukoordinator und Techniker muss sie dabei aus der Liste wählen.
- Wird das VEFK-Feld gelöscht oder ein Name gewählt, der nicht in der Liste steht, zeigt die WorkInfo #NV. So verhält sich das Original auch. Falls es passiert, als Beobachtung zum alten Weg notieren.
- Bei Tag 1 und Tag 2 sind 10 Stunden SA-Dauer vorbelegt (aus dem Original). Überschreibt die GU-Person den Wert nicht, steht in der WorkInfo „ca. 10 Std“.
- In `Template TF 2.xlsx` steht bei Erika absichtlich keine Telefonnummer.

**Zwei praktische Punkte:**

- Leg dir von allen Templates eine Sicherungskopie an. Die GU-Person verändert die Dateien beim Ausfüllen, und für Durchgang B brauchst du sie wieder im Ausgangszustand. Das gilt vor allem für TF 4.
- Für jeden Testfall die passende Datei `Template alter Weg_fuer_X.xlsx` nehmen. So steht nichts vom vorigen Testfall drin.

**Morgens als Erstes prüfen:** Automatik **an**, im CC-Panel TF 4 **Neu** und TF 5 **Übertragen**, in AdHoc TF 4 **Offen** und TF 5 **Gesendet**.

## Durchgang A

### Vor dem ersten Testfall

1. Begrüßen und in zwei Sätzen erklären: Gemessen wird der Prozess, nicht die Person.
2. Die CC-Person bekommt das Hinweisblatt.
3. Ins Protokoll (Blatt Durchläufe, Zeilen Nr 1 bis 12) die Kürzel **P1** (GU) und **P2** (CC) in die Spalten F und G eintragen, dazu das Datum **20.10.2026** in Spalte H.

### Bei jedem Testfall gleich

- **Eingabezeit:** Die Stoppuhr startet, wenn die GU-Person das Template bzw. das Formular öffnet. Sie stoppt beim Klick auf Senden bzw. Anfrage einreichen. Start und Ende als hh:mm:ss in die Spalten I und J.
- **Prüfzeit:** Die Stoppuhr startet, wenn die CC-Person die Mail bzw. die Anfrage öffnet. Sie stoppt, wenn sie entschieden hat (validiert, abgelehnt oder Rückfrage gestellt). Zeiten in L und M.
- **Rückfrage:** Spalte O ja oder nein, Dauer der Klärung in Minuten in P.
- Danach die Spalten R bis U (Ergebnis, Konsistent, Fehler, Eingriff) und bei Bedarf X (Bemerkung).
- Jeden Fehler als eigene Zeile ins Blatt **Fehler**, den Feldvergleich mit der Karte ins Blatt **Datenqualität**. Nur die Felder vergleichen, die auf der Karte stehen.
- Zu Inhalten nichts sagen, nur Fragen zum Ablauf beantworten. Jede Hilfe kommt als Eingriff ins Protokoll.
- Nach dem Testfall die Karte wieder einsammeln.

### Spickzettel Protokoll (Blatt Durchläufe)

Nur diese Spalten von Hand ausfüllen. A bis E sind vorbelegt, K, N, Q, T und Y bis AD rechnen selbst.

**Live während des Testfalls**

| Spalte | Was rein kommt |
|---|---|
| I / J Eingabe Start / Ende | Uhrzeit, wenn die GU-Person öffnet bzw. absendet |
| L / M Prüfung Start / Ende | Uhrzeit, wenn die CC-Person öffnet bzw. entscheidet. Greift die Automatik, bleibt das leer bzw. 0 |
| O Rückfrage nötig? | ja / nein |
| P Rückfrage [min] | Dauer der Klärung als Zahl, z. B. 3,2 |

> [!tip] Rückfrage richtig messen
> Die Prüfzeit endet (M), sobald die CC-Person die Rückfrage stellt. Ab da läuft nur noch die Rückfrage, bis die CC-Person nach der Klärung endgültig entscheidet. Nicht beides weiterlaufen lassen, sonst zählt die Rückfrage doppelt (Gesamt = Eingabe + Prüfung + Rückfrage). Wartezeit, in der niemand arbeitet, zählt nicht. Fragt die GU-Person bei TF 2 neu nach der Nummer, ist das keine Rückfrage, die Eingabezeit läuft weiter.

**Direkt nach dem Testfall (Dropdowns)**

| Spalte | Bedeutung | Werte |
|---|---|---|
| R Ergebnis | Was am Ende mit der Anfrage passiert ist | *übertragen* (alt: CC hat sie angenommen, sie würde ins TSM gehen) · *vorgemerkt (Automatik)* (neu: System hat selbst validiert) · *manuelle Prüfung* (neu: CC musste ran und hat validiert) · *abgelehnt* · *verworfen* (z. B. AdHoc schluckt die Mail bei TF 5 alt) · *abgebrochen* (Testperson kommt nicht weiter) |
| S Konsistent? | Passen die Angaben **innerhalb** der Anfrage zueinander? Nicht verwechseln mit „korrekt“, das prüft das Blatt Datenqualität. | *ja* / *nein* / *–*, wenn es für den Testfall keine Rolle spielt |
| U Eingriff | Musstest du helfen oder etwas erklären? | ja / nein, bei ja kurz in X beschreiben |
| X Bemerkung | Alles Auffällige als Freitext | |

**Wo S wirklich relevant wird**

- **TF 1 / TF 2:** meist *ja*, wenn nichts Widersprüchliches drinsteht.
- **TF 3:** Betreff `121990074` gegen Template `121990047`. Bleibt die Abweichung unbemerkt, *nein*.
- **TF 4 / TF 6:** Passt die Zahl der Ausfalltage zu den Tageszeilen bzw. zum Zeitraum?
- **TF 5:** Gibt es am Ende eine Anfrage oder zwei? Zwei bedeutet *nein*.

**Einmalig bzw. am Ende**

- F, G, H (GU-Kürzel, CC-Kürzel, Datum) vor dem Durchgang einmal eintragen und nach unten kopieren.
- V und W (DB-Zeitstempel eingereicht, validiert) nur bei den neu-Zeilen. Für Durchgang A **vor dem Löschen** zwischen A und B eintragen, ebenso das Blatt Datenqualität für Nr 1 bis 12.

### Was „Konsistent“ (Spalte S) heißt

Die Fehler in TF 2 bis TF 6 sind absichtlich eingebaut. Gemessen wird nicht, ob die Testperson etwas falsch macht, sondern ob der Prozess den eingebauten Fehler abfängt (wie beim Test eines Rauchmelders). S beantwortet nur: **Widersprechen sich am Ende noch zwei Angaben?** Bewertet wird das Endergebnis, also nach einer Rückfrage. Ob die Angaben zur Karte passen, ist Korrektheit und gehört ins Blatt Datenqualität. Eine fehlende Angabe (TF 2) ist Unvollständigkeit, kein Widerspruch, S bleibt dann *ja*. *–* nur, wenn es nichts zu bewerten gibt (z. B. abgebrochen).

### Worum es in den Testfällen geht

Jeder Testfall bildet eine Schwachstelle aus Kapitel 4 nach. „Optimal“ heißt nur: Es passiert, was erwartet wird. Läuft es anders, ist das trotzdem ein Ergebnis und kommt ehrlich in 6.3.

| TF | Szenario | Merkmal | Erwartet alt | Erwartet neu | Was es zeigt |
|---|---|---|---|---|---|
| 1 | Korrekte Anfrage | Effizienz | CC prüft und nimmt an, Abtippen kommt aus der Beobachtung | Automatik merkt vor, Prüfzeit 0 | Grundlinie für den Zeitvergleich, CC-Arbeit entfällt im Normalfall |
| 2 | Telefonnummer fehlt | Vollständigkeit | Lücke fällt erst bei CC auf (oder gar nicht), Rückfrage nötig | Knopf gesperrt, Lücke fällt beim GU auf, keine Rückfrage | Fehlerprüfung wandert nach vorne |
| 3 | Zahlendreher Betreff/Template | Konsistenz, Korrektheit | Offen, ob CC es merkt, im schlimmsten Fall falscher Standort im TSM | Standort nur einmal über Suche, Widerspruch unmöglich | Widerspruch technisch ausgeschlossen |
| 4 | Korrektur vor Übertragung (3 → 1 Tag) | Konsistenz | Korrektur kommt mit 3 Tagen an, fällt kaum auf | Gleicher Datensatz, gleiche AMR-Nummer, Verlauf im Chat | Korrektur eindeutig und nachvollziehbar |
| 5 | Korrektur nach Übertragung | Nachvollziehbarkeit | AdHoc verwirft ohne Rückmeldung oder doppelter CR | Gleicher Datensatz, GU sieht Verlauf, Telefónica erfährt nichts | Korrektur geht nicht verloren, Grenze ohne Schnittstelle |
| 6 | Kritischer Standort, 10 Tage | Prozesssicherheit | Kritikalität hängt allein am Wissen der CC | Begründung Pflicht, keine Automatik, Grund sichtbar | Kritische Fälle landen gezielt beim Menschen |

### Sonderfälle

**TF 3 alt: Wie soll die CC reagieren?** Nichts vorgeben, sie arbeitet wie im Alltag. Immer notieren, welche Nummer sie ins TSM übernehmen würde (und welche AdHoc anzeigt).

| CC-Reaktion | Protokoll |
|---|---|
| Merkt es, fragt nach | O ja, P Minuten, S ja |
| Merkt es, nimmt ohne Rückfrage die Template-Nummer | O nein, S ja, in X notieren. Richtig nur, weil das Template zufällig stimmt |
| Merkt es nicht, Template-Nummer | O nein, S nein |
| Merkt es nicht, Betreff-Nummer | O nein, S nein, Fehler im Endergebnis ja |

**TF 4 alt: Woran erkennt die CC die Korrektur?** Wahrscheinlich gar nicht, das ist der Punkt. TF 4 steht in AdHoc auf Offen, also überschreibt AdHoc den Eintrag als Korrektur. Es liest aber alle Zeilen, auch die weiß beschrifteten Tage 2 und 3. In AdHoc steht danach wieder 09.11. bis 11.11. (3 Tage), im Template-Anhang dagegen Anzahl Tage 1. Auffallen kann es nur, wenn die CC beides vergleicht. Keinen Hinweis geben. Beobachten: Öffnet sie den Anhang, vergleicht sie, zeigt AdHoc einen Hinweis aufs Überschreiben? Am Ende fragen, welchen Zeitraum sie ins TSM übernehmen würde. 3 Tage: Fehler im Endergebnis, S nein. 1 Tag: in X festhalten, **wie** sie es gemerkt hat.
*Nachtrag 21.10.2026:* Laut CC schaut sie immer auch in Mailpostfach und Template, und der GU schreibt die Änderung meist in den Mailtext. Im Alltag fängt sie TF 4 darüber ab, siehe [[Expertenbefragung Change-Koordinatorin]].

**TF 5 alt: AdHoc verwirft die Mail.** Dann sieht die CC nichts und es gibt keine Prüfzeit. I/J normal, L/M/P leer, R = verworfen, in X Rückmeldung an GU notieren. Kommt die Mail doch bei der CC an, normal messen.
Achtung Excel: Die Hilfsspalten AA/AC rechnen bei leerer Prüfzeit mit 0. Ein verworfener Durchlauf ginge als „alt mit 0 Minuten Prüfung“ in den Median ein und ließe den alten Weg schneller aussehen. Vor der Auswertung verworfene bzw. abgebrochene Zeilen aus dem Zeitvergleich herausnehmen (Formeln noch nicht angepasst, Stand 21.10.2026).

**TF 5 neu: Ändern nach der Übertragung.** Geht, im Code geprüft: Der Bearbeiten-Endpunkt (`AdminCrqController.BearbeitenAsync`) prüft den Status nicht, Zeitraum, SA-Dauer und CRQ-Nummer sind auch bei *Übertragen* änderbar. „In Rücksprache“ geht nur aus *Neu*, die CC ändert also direkt. Die Änderung wird **nicht** erneut an Telefónica bzw. ins TSM geschickt, im Betrieb müsste die CC das TSM zusätzlich von Hand korrigieren. Grenze für 6.6. Prüfzeit: vom Öffnen der Anfrage bzw. Chatnachricht bis zum Speichern.

### TF 1: korrekte Anfrage (erst alt, dann neu)

**Alt (Nr 1)**

1. Karte TF 1 alt an die GU-Person geben.
2. Sie füllt das Template alter Weg aus und schickt es mit der Standortnummer im Betreff ans Testpostfach.
3. Die CC-Person öffnet die Mail in AdHoc, prüft und entscheidet.

**Neu (Nr 2)**

1. Karte TF 1 neu geben.
2. Die GU-Person reicht die Anfrage im GU-Panel ein.
3. Du prüfst im CC-Panel mit dem Haken „Automatisierte Tickets“, ob die Anfrage vorgemerkt ist. Die CC-Person macht hier nichts, die Prüfzeit ist **0**. Das ist ein Ergebnis und kein fehlender Wert.

### TF 2: Telefonnummer fehlt (erst neu, dann alt)

**Neu (Nr 3)**

1. Karte TF 2 neu geben. Auf der Karte fehlt Erikas Nummer.
2. Die GU-Person füllt das Formular aus. Ohne Nummer bleibt der Knopf zum Einreichen gesperrt.
3. Fragt sie nach der Nummer, gibst du ihr den Zettel. Die Zeit läuft dabei weiter.
4. Sie reicht ein, danach merkt die Automatik vor oder die CC-Person prüft.

**Alt (Nr 4)**

1. Karte TF 2 alt geben. Die GU-Person füllt `Template TF 2.xlsx` ohne Nummer aus und schickt es ab.
2. Die CC-Person prüft. Fällt ihr die Lücke auf, klärt sie das mit der GU-Person per Mail oder Telefon. **Erst dann** bekommt die GU-Person den Zettel.
3. Notieren, wo die Lücke aufgefallen ist und wie lange die Rückfrage gedauert hat. Fragt die GU-Person von sich aus nach der Nummer, kommt das in die Bemerkung.

### TF 3: Zahlendreher im Betreff (erst alt, dann neu)

**Alt (Nr 5)**

1. Karte TF 3 alt geben. Die GU-Person übernimmt den Betreff **genau so** wie auf der Karte (`121990074`) und trägt im Template die richtige Nummer `121990047` ein.
2. Die CC-Person prüft und schreibt auf, welche Nummer sie ins TSM übernehmen würde.
3. Spalte S: **nein**, wenn die Abweichung unbemerkt bleibt.

**Neu (Nr 6)**

1. Karte TF 3 neu geben. Die GU-Person wählt den Standort über die Suche aus und reicht ein.
2. **Danach** bittest du sie, `121990074` in die Standortsuche zu tippen. Notier, was erscheint.
3. Die Automatik merkt vor oder die CC-Person prüft.

### TF 4: Korrektur vor der Übertragung (erst neu, dann alt)

**Neu (Nr 7)**

1. Karte TF 4 neu geben. Die GU-Person öffnet **Meine Anfragen**, die Anfrage vom 09.11. bis 11.11., und schreibt im Chat, dass nur noch der 09.11. gilt.
2. Die CC-Person setzt die Anfrage auf **In Rücksprache**, ändert den Zeitraum am selben Datensatz auf den 09.11., 08:00 bis 09:00, und validiert.
3. Notieren: dieselbe AMR-Nummer, Verlauf im Chat.

**Alt (Nr 8)**

1. Karte TF 4 alt geben. Die GU-Person öffnet `Template TF 4 ursprünglich.xlsx`, setzt die Anzahl Tage von 3 auf 1 und schickt die Datei erneut ans Testpostfach.
2. Die CC-Person prüft in AdHoc und schreibt auf, welchen Zeitraum sie ins TSM übernehmen würde.
3. Notieren, wie AdHoc reagiert hat (drei Tage gelesen? als Überschneidung behandelt?).

### TF 5: Korrektur nach der Übertragung (erst alt, dann neu)

**Alt (Nr 9)**

1. Karte TF 5 alt geben. Die GU-Person füllt ein frisches Template alter Weg mit 17.11. bis 19.11. aus und schickt es.
2. Beobachten, ob AdHoc die Mail wegen der Überschneidung mit der „Gesendet“-Anfrage verwirft.
3. Notieren, ob die GU-Person eine Rückmeldung bekommt und ob es am Ende eine oder zwei Anfragen gibt.

**Neu (Nr 10)**

1. Karte TF 5 neu geben. Die GU-Person schreibt im Chat an der bestehenden Anfrage (16.11. bis 18.11.).
2. Die CC-Person ändert den Zeitraum am selben Datensatz auf 17.11. bis 19.11.
3. In die Bemerkung: Ohne Schnittstelle erfährt Telefónica nichts von der Korrektur (kommt später in 6.6).

### TF 6: kritischer Standort, 10 Tage (erst neu, dann alt)

**Neu (Nr 11)**

1. Karte TF 6 neu geben. Die GU-Person füllt das Formular mit Standort `120990686` aus, vom 09.11. 08:00 bis 18.11. 17:00.
2. Das System verlangt eine Begründung. Sie trägt die von der Karte ein und reicht ein.
3. Die CC-Person sieht an der Anfrage den Grund für die manuelle Prüfung, prüft und validiert. Notier diesen Grund.

**Alt (Nr 12)**

1. Karte TF 6 alt geben. Die GU-Person trägt Tag 1 bis 5 unter Punkt 7 ein und Tag 6 bis 10 unter Punkt 12, dann schickt sie das Template ab.
2. Die CC-Person prüft. Notieren, ob sie die Kritikalität erkennt und woran.

### Zum Schluss

- Beide füllen den Fragebogen aus.
- Die Zeitstempel aus der Datenbank (eingereicht, validiert) in die Spalten V und W.

## Zwischen A und B

1. Alle Testanfragen aus A im Admin-Panel löschen und Testpostfach bzw. AdHoc leeren.
2. Die Templates aus der Sicherung wieder auf den GU-Rechner kopieren.
3. Automatik aus, TF 4 und TF 5 neu vorab einreichen wie am Morgen. TF 5 von Hand validieren und mit „An TEF übertragen“ übertragen. In AdHoc TF 5 auf „Gesendet“, TF 4 auf „Offen“. Danach Automatik wieder an.
4. Bei der CC-Person „Test CC 2“ anmelden. Das ist eine andere Person als in A.
5. Bemerkungen zu den Vorab-Anfragen auch bei Nr 19 bis 22 ins Protokoll eintragen.

## Durchgang B

Gleicher Ablauf, Zeilen Nr 13 bis 24, aber jeweils **in umgekehrter Reihenfolge**:

| Testfall | Durchgang B |
|---|---|
| TF 1 | neu, dann alt |
| TF 2 | alt, dann neu |
| TF 3 | neu, dann alt |
| TF 4 | alt, dann neu |
| TF 5 | neu, dann alt |
| TF 6 | alt, dann neu |

Das steht auch auf dem Spickzettel.
