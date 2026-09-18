---
tags: [bachelorarbeit, evaluation, planung]
status: aktiv
date: 2026-09-09
---

# Evaluationsplan

← zurück zu [[Bachelorarbeit AsiMinu App]] · verwandt: [[Gliederungsvarianten]], [[Kapitelplanung]]

Die empirische Wirkungsmessung ist gesetzt und wird durchgeführt. Dieser Plan beschreibt, wie
sie mit vertretbarem Aufwand so umzusetzen ist, dass die Ergebnisse einer kritischen Prüfung
standhalten. Stand 09.09.2026.

## Zwei Klassen von Kennzahlen

**Gruppe 1, ohne fremde Mitwirkung erhebbar.** Automatisierungsquote aus den Regelläufen
(Vergleichsbasis: die alte fest verdrahtete Regel war gegen die echte Standortdatei wirkungslos,
Ausgangswert also null), Prozesssicherheits-Kennzahl aus dem Prüfprotokoll (ADR-052, alter Wert
ebenfalls nahe null), funktionale Abdeckung des Testfallkatalogs mit 352 Fällen gegen die
Testsuite mit 971 Tests bei 81,3 Prozent Codeabdeckung. Diese Gruppe zuerst erheben, sie sichert
das Kapitel unabhängig von Terminen ab.

**Gruppe 2, nur mit Beteiligung anderer.** Bearbeitungszeit je Ticket getrennt nach Eingabe- und
Prüfseite, Fehlerquote bei der Dateneingabe mit Unterscheidung zwischen im Formular abgefangenen
und durchgereichten Fehlern, Datenqualität nach Vollständigkeit, Konsistenz und Korrektheit,
sowie eine Kurzbefragung zur wahrgenommenen Prozesssicherheit.

## Versuchsaufbau

- **Zehn bis zwölf Testfälle** je Prozessweg, etwa zur Hälfte Normalfälle, zur Hälfte konstruierte
  Fehler- und Grenzfälle. Weniger erlaubt keine sinnvollen Verhältnisangaben, mehr sprengt den
  Zeitrahmen, da jeder Fall zweimal durchlaufen wird.
- **Beteiligte**: zwei bis drei Bayfu-Mitarbeitende für die Prüfseite, für die Eingabeseite wäre
  ein echter GU-Ansprechpartner der Idealfall. Eigene Eingabe ist als Verzerrung auszuweisen.
- **Reihenfolge ausgleichen**: die Hälfte beginnt mit dem alten Weg, die andere mit dem neuen.
  Kostet nichts und verhindert, dass Lerneffekte statt Prozessunterschiede gemessen werden.
- **Gleiche Ausgangsdaten** je Testfall auf beiden Wegen.
- **Zeiterfassung** im neuen Prozess über die Zeitstempel aus der Datenbank, im alten Prozess
  manuell. Die Ungleichheit der Messverfahren gehört in die Limitationen.
- **Pilotdurchlauf** allein vorab, um Messprotokoll und Ablauf zu prüfen.

## Zeitplan

| Zeitraum | Schritt |
|---|---|
| bis 20.09.2026 | Testfallkatalog final, Messprotokoll und Fragebogen erstellen, Konzept mit dem Betreuer abstimmen, Termine mit Bayfu fixieren |
| bis 27.09.2026 | Pilotdurchlauf, Anbindung der echten TEF-Schnittstelle abwarten und testen |
| 28.09. bis 09.10.2026 | Testdurchläufe mit den Beteiligten, Kurzbefragung im Anschluss, parallel Gruppe 1 erheben |
| bis 16.10.2026 | Auswertung, Tabellen und Diagramme, Ergebnisabschnitt schreiben |
| bis 30.10.2026 | Limitationen und Schlusskapitel, Puffer für Nachmessungen |

Der kritische Punkt ist die erste Zeile. Termine, die nicht bis zum 20.09.2026 fest stehen,
finden erfahrungsgemäß nicht mehr rechtzeitig statt. Gleich einen Ausweichtermin mitvereinbaren.

## Erhebungsinstrumente

Messprotokoll als Tabelle mit einer Zeile je Durchlauf: Testfall-Kennung, Prozessweg, Rolle,
Start- und Endzeit, Dauer, Anzahl und Art der Fehler, davon im Formular abgefangen, sowie drei
Spalten für Vollständigkeit, Konsistenz und Korrektheit. Fragebogen mit sieben Aussagen entlang
der Grundsätze der Dialoggestaltung, fünfstufige Skala, dazu zwei offene Fragen. Beides gehört
ausgefüllt und als Leerformular in den Anhang. Nur Testdaten verwenden, Beteiligte anonymisiert
als Person A, B und C.

## Auswertung

Je Kennzahl alter gegen neuen Wert mit absoluter und relativer Veränderung, Übersichtstabelle
voran, Einordnung im Fließtext darunter. Bei dieser Stichprobengröße **keine Signifikanztests**,
stattdessen Median und Spannweite angeben und die Ergebnisse als Indiz und nicht als Nachweis
formulieren.

## Bekannte Fallstricke, offen zu benennen

Selbstmessungsverzerrung, Lerneffekt zwischen erstem und zweitem Durchlauf, verändertes Verhalten
unter Beobachtung, kleine Stichprobe ohne Verallgemeinerbarkeit.
