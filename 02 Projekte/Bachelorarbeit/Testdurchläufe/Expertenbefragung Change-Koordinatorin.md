---
tags: [bachelorarbeit, testdurchläufe, kapitel-6]
status: aktiv
date: 2026-10-21
---

# Expertenbefragung Change-Koordinatorin (21.10.2026)

Statt der geplanten Testdurchläufe (siehe [[Ablauf Testtag]]) wurden die sechs Testfälle mit der Change-Koordinatorin (CC) der BayFu durchgesprochen. Sie macht seit einem Jahr ausschließlich diese Aufgabe und kennt jeden Fall aus dem Alltag. Ihr Einwand: Ein gespielter GU mit konstruierten Szenarien spiegelt die Realität nicht wider. Deshalb wurden ihre Erfahrungswerte erfragt und einzelne Schritte gemessen.

> [!note] Nummerierung
> Im mündlichen Bericht waren TF 2 und TF 3 vertauscht. Hier stehen sie richtig: TF 2 = Telefonnummer fehlt, TF 3 = Zahlendreher Betreff/Template.

## Gemessene und geschätzte Zeiten

| Schritt | Wert | Herkunft |
|---|---|---|
| GU füllt Template aus, hängt es an, schreibt Standort in den Betreff, sendet | 4:30 min | gemessen (Kollegin spielt GU) |
| dasselbe, erfahrener GU | ca. 3:30 min | Schätzung |
| CC prüft Template (richtig ausgefüllt oder nicht) | ca. 10 bis 15 s, gemessen 15 s | gemessen |
| CC trägt Daten ins TSM ein | 15 s im besten Fall, realistisch ca. 1 min | Aussage CC (15 s), Einschätzung Dennis (1 min) |
| Anteil der Anfragen mit Rückfrage | ca. 50 % | Aussage CC |
| Rückfrage per Mail bis zur Antwort des GU | 2 Stunden bis 1 Woche | Aussage CC, hängt vom GU ab |
| Zusatzprüfung kritischer Standort (TF 6) | ca. 10 bis 15 min | Aussage CC (korrigiert, nicht 15 bis 20) |
| GU gibt Anfrage im neuen GU-Panel ein | 58 s | gemessen, dieselbe Kollegin wie beim Template (vorher von Dennis selbst ca. 1:00 bis 1:30 min) |

Bei kritischen Standorten prüft die CC unter anderem über eine Website („Athea“, Schreibweise prüfen), ob Standorte in der Nähe den Ausfall kompensieren können und ob der Standort zur kritischen Infrastruktur gehört. Anlass sind z. B. Ausfallzeiten von 8 oder 10 Tagen.

Die Eingabezeit des GU ist laut CC in allen Testfällen ungefähr gleich, solange er die Daten im Kopf hat. Länger wird es, wenn er erst jemanden anrufen muss.

## Ablauf je Testfall (alter Weg)

**Allgemein:** Die CC schaut nie nur in AsiMiNu-AdHoc, sondern immer parallel ins Mailpostfach und ins Template. So sieht sie auch Mails, die AdHoc keinem CRQ zuordnen konnte oder nicht eingelesen hat.

- **TF 1 korrekt:** GU 4:30 min, CC prüft ca. 15 s, TSM ca. 15 s.
- **TF 2 Telefonnummer fehlt:** GU 3 bis 4 min. CC erkennt die Lücke schnell und schreibt dem GU eine Mail. Antwort nach 2 Stunden bis 1 Woche. Danach erneut prüfen, dann TSM.
- **TF 3 Zahlendreher:** CC erkennt die Abweichung Betreff/Template in den 10 bis 15 s, weil das häufig vorkommt. Rückfrage per Mail, meist mit der Bitte um eine neue Anfrage. Dauer 2 Stunden bis 1 Woche.
- **TF 4 Korrektur vor TSM:** Der GU schickt meist eine zweite Mail mit neuem Template und schreibt im Mailtext, was sich ändert. Die CC erkennt das über die Mail. Ist noch nichts im TSM, löscht sie die alte Anfrage, übernimmt die neue und trägt sie ins TSM ein. Zeiten wie bei TF 1, ggf. plus Rückfrage. **Korrigiert die Annahme im Ablauf Testtag**, dass die Korrektur kaum auffällt: Im Alltag fängt die CC sie über den Mailtext ab.
- **TF 5 Korrektur nach TSM:** Die CC storniert nichts bei Telefónica, sondern trägt die Daten einfach neu ins TSM ein. AdHoc-Regel laut CC: Überschneiden sich die Zeiträume und ist die erste Anfrage noch nicht abgeschickt, überschreibt AdHoc sie. Überschneiden sie sich nicht, entstehen zwei parallele Anfragen.
  **TSM-Seite (Aussage des BPMN-Verantwortlichen):** Kommt ein neuer Eintrag zum selben Standort mit überschneidendem Zeitraum, wird der alte im TSM **überschrieben**. Nur bei sich nicht überschneidenden Zeiträumen stehen zwei Einträge im TSM. Im Testfall TF 5 überschneiden sich die Zeiträume, es entsteht also **kein** Doppeleintrag. Offen: Gilt die Überschreib-Regel im TSM selbst oder im vorgelagerten BPMN-Prozess? Mit Kapitel 4.1 abgleichen (dort: AdHoc verwirft die Korrektur bei übertragener Anfrage).
- **TF 6 kritischer Standort:** Prüfen ca. 10 bis 15 s, danach ca. 10 bis 15 min Zusatzprüfung: Warum ist der Standort kritisch, ist er es wirklich, ist er der einzige Standort im weiten Umkreis usw.

## Neuer Weg (Einschätzung)

- Fehlende Angaben und Betreff-Fehler können nicht mehr entstehen, die eingereichten Daten sind in der Regel korrekt.
- Unkritische Anfragen mit Automatik: 0 s Bearbeitungszeit für die CC.
- Rückfragen fallen weitgehend weg. Ausnahme: Änderungswünsche wie TF 4 und TF 5 laufen über den Chat und können genauso 2 Stunden bis 1 Woche dauern.
- Kritische Standorte bleiben Handarbeit (ca. 10 bis 15 min).
- GU-Eingabe im GU-Panel 58 s statt 4:30 min (beides dieselbe Person gemessen).
- Rückfragen entstehen laut Dennis meist durch falsch ausgefüllte Templates (vergessene Angaben, falsche Standortnummer usw.). Änderungswünsche sind selten. Der Großteil der Rückfragen ist also durch das neue System vermeidbar. Nicht abgefangen werden Angaben, die formal gültig, aber inhaltlich falsch sind (z. B. falscher Standort in der Suche gewählt).
- Die TSM-Schnittstelle kommt laut Dennis sicher vor dem Produktivgang, ist zum Zeitpunkt der Abgabe aber noch nicht umgesetzt. Im Text deshalb als geplanter Zielzustand („neu mit Schnittstelle“) neben dem heutigen Stand („neu heute“) darstellen.

## Kurzbefragung (Fragebogen, mündlich beantwortet)

Beide Beteiligten (CC und Kollegin in der GU-Rolle), qualitativ, ohne Punktwerte. Zuordnung zu den sieben Aussagen des Fragebogens (Anhang A):

| Nr | Aussage | Alt (Template) | Neu (GU-Panel / CC-Panel) |
|---|---|---|---|
| 1 | ohne Umwege erfassen bzw. prüfen | GU: deutlich schwerer einzureichen | GU: Bedienung und Einfachheit viel besser. CC konnte gut prüfen |
| 2 | wusste, was als Nächstes zu tun ist | Template „offen für Fehler“, nicht immer klar, was zu tun ist | immer klar |
| 3 | Werkzeug verhielt sich wie erwartet | Excel nicht immer | ja |
| 4 | Fehler rechtzeitig und verständlich angezeigt | nein | ja, sofort, weil sonst nicht absendbar |
| 5 | Ablauf unter Kontrolle | GU ja. CC nein, wegen vieler Rückfragen, abhängig vom GU | beide ja |
| 6 | nachvollziehen, was mit der Anfrage passiert ist | für den GU kaum | ja, GU sieht eigene Anfragen, Status und Inhalt. Chat direkt an der Anfrage |
| 7 | würde im Alltag gern damit arbeiten | nein, „zu viele unnötige Fehler“ | beide ja |

Insgesamt mit dem Versuch sehr zufrieden.

## Einordnung für Kapitel 6 (Stand 21.10.2026, noch nicht im Text)

- **Methode ändert sich:** von kontrollierten Testdurchläufen zu einer Expertenbefragung mit Durchgehen der Testfälle und einzelnen Messungen. Stärke: realistisch, ein Jahr Erfahrung. Grenze: eine Person, überwiegend Schätzungen.
- **Bearbeitungszeit gegen Durchlaufzeit trennen:** Die reine Arbeitszeit der CC je unkritischer Anfrage ist mit ca. 30 s (15 s prüfen + 15 s TSM) sehr klein. Der große Hebel ist die **Durchlaufzeit** durch Rückfragen (2 Stunden bis 1 Woche), die bei TF 2 und TF 3 im neuen System entfällt, und die Fehlervermeidung.
- **TSM-Schnittstelle:** „Nicht mehr manuell ins TSM“ gilt erst mit Schnittstelle. Sie ist vor dem Produktivgang fest eingeplant, im Text aber als Zielzustand formulieren, nicht als umgesetzt.
- **TF 5:** Kein Doppeleintrag bei überschneidendem Zeitraum (TSM überschreibt). Die Schwachstelle liegt eher in der Nachvollziehbarkeit (Korrektur per neuer Mail, keine Verknüpfung am Vorgang, Rückmeldung an den GU).
- **Grobe Hochrechnung (256 Anfragen pro Monat, nur Größenordnung):**
  - GU: 4:30 min → 58 s, also gut 3,5 min (rund 79 %) weniger je Anfrage, rund 15 Stunden pro Monat über alle GU.
  - CC: heute ca. 0,5 bis 1,25 min je Anfrage (prüfen + TSM), rund 2 bis 5 Stunden pro Monat. Mit Automatik und Schnittstelle bei unkritischen Anfragen 0.
  - Größter Hebel: Rund 128 Anfragen pro Monat (50 %) brauchen heute eine Rückfrage, die die Anfrage um 2 Stunden bis 1 Woche verzögert und oft eine neue Eingabe durch den GU auslöst. Fehlende Angaben und Betreff-Fehler sind im neuen System ausgeschlossen.
- **Grenzen der Werte:** eine Fachperson, überwiegend Schätzungen, je Weg eine Messung. Reihenfolge bestätigt (21.10.): erst Template, dann GU-Panel. Beim GU-Panel kannte die Kollegin die Daten also schon (Lerneffekt zugunsten des neuen Wegs). Dagegen steht, dass das GU-Panel für sie neu war, das Template aus dem Alltag aber vertraut. Der Unterschied (4:30 min gegen 58 s) ist zu groß, um ihn allein mit dem Lerneffekt zu erklären, zumal beim Template auch Speichern, Anhängen und Betreff dazugehören.

## Offene Fragen

0. **Gründe der Rückfragen** (Dennis fragt am 22.10. nach): In 6.3 steht vorläufig „meist weil eine Angabe fehlt oder die Standortnummer nicht stimmt“, mit Todo im Text.
1. Wie oft kommen kritische Standorte vor?
2. Wie lange dauert das Schreiben der Rückfrage-Mail selbst?
3. TF 5: Überschreiben passiert im TSM oder im BPMN-Prozess davor? Passt das zu Kapitel 4.1?
