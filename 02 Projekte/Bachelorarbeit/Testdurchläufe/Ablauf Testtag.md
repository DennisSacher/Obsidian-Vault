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
