---
tags: [bachelorarbeit, schreiben, gliederung]
status: aktiv
date: 2026-09-23
---

# Darstellungsmuster Entwurfsentscheidungen

← zurück zu [[Bachelorarbeit AsiMinu App]] · verwandt: [[Gliederung Variante D - Abschnittsinhalte]], [[ADR-zu-Kapitel]], [[Gliederungsvarianten]]

Die Schreibregel für Kapitel 5 (Architektur und Realisierung), abgeleitet aus dem Leitgedanken von Variante D.

## Leitgedanke

Das wissenschaftlich wertvollste Material der Arbeit sind nicht die gebauten Funktionen, sondern die **57 dokumentierten Entwurfsentscheidungen** (ADR-002 bis ADR-058) mit ihren erwogenen und verworfenen Alternativen. Die Entwurfsentscheidung ist deshalb die **Darstellungseinheit** des Hauptteils. Damit wird die Fakultätsvorgabe, alternative Lösungswege und verworfene Sackgassen zu diskutieren, an jeder relevanten Stelle erfüllt statt an einer einzigen. Ziel: acht bis zehn Entscheidungen vertieft in der Arbeit, nicht nur drei.

## Das Muster

Jeder wesentliche Abschnitt von Kapitel 5 folgt dieser Abfolge:

1. **Entwurfsproblem:** Was war zu entscheiden, und warum ist es nicht trivial?
2. **Erwogene Alternativen** mit Verwerfungsgrund
3. **Gewählte Lösung**
4. **Begründung**
5. **Umsetzung**

Das Muster trägt **im Fließtext**, es kündigt sich **nicht in den Überschriften** an. Eine Entscheidung mit Alternativen, Verwerfungsgründen und Begründung braucht etwa **drei viertel bis eine ganze Seite**. Auf drei Sätze eingedampft wird sie zur Behauptung.

## Dreistufige Staffelung der Tiefe

Damit das Kapitel nicht eintönig wird und im Seitenbudget bleibt:

| Stufe | Anzahl Abschnitte | Umfang | Darstellung |
|---|---|---|---|
| Vertieft | 3 bis 4 | 1,5 bis 2 Seiten | vollständige Alternativendiskussion |
| Kompakt | 4 bis 5 | 0,5 bis 1 Seite | Lösung und Begründung, Alternativen in zwei bis drei Sätzen |
| Darstellend | 2 bis 3 | kurz | ohne Diskussion, Verweis auf den Entscheidungssatz im Anhang |

Die Auswahl, welche Entscheidungen vertieft werden, muss **vor dem Schreiben** feststehen, sonst wächst der Realisierungsteil über sein Budget von 12 Seiten. Die übrigen ADRs kommen in eine Übersichtstabelle mit Verweis auf den Anhang. Tiefenschwerpunkte laut Plan: 5.8 (serverseitige Validierung), 5.9 (Regelbasis), 5.11 (Sicherheit).

## Vier Arten von Entscheidungen

Die Entscheidungen sind unterschiedlicher Art und werden in ihrer jeweiligen Form dargestellt, nicht in ein einheitliches Schema gezwungen:

| Art | Beispiel | Abschnitt |
|---|---|---|
| Vorab abgewogene Auswahlentscheidung | Trennung der Datenbestände (Auth/CRQ/INC) | 5.3.1 |
| Nachträglich revidierte Entscheidung | Ablösung des SMS-Verfahrens durch TOTP | 5.11.1 |
| Entscheidung unter Unsicherheit | Entwurf gegen die noch nicht verfügbare Schnittstelle | 5.9.3 |
| Aus einem Befund entstandene Entscheidung | Umstellung der Automatisierungsregel nach Analyse der realen Standortdatenqualität | 5.9.1 |

## Ebenen statt Phasen

Architekturteil (5.1 bis 5.5) und Realisierungsteil (5.6 bis 5.12) sind nach **Ebene** getrennt, nicht nach Phase: vorne die systemweiten Entscheidungen (Schichtung, Datenhaltung, Rollen, Technologie), hinten der Weg eines Antrags durch das System. Dadurch wird kein Gegenstand zweimal beschrieben. Das war die Hauptschwäche der Varianten B und C, bei denen Entwurf und Umsetzung derselben Sache in zwei Kapiteln standen.

## Kippregel: Argumentation statt Beschreibung

Zusätzliche Seiten verbessern die Arbeit nur, solange sie für **Argumentation** verwendet werden: Begründungen, Alternativen, Einordnungen, Interpretation. Sobald sie **Beschreibung** sind (weitere Funktionen, Klassenübersichten, Konfigurationsdetails, Bedienabläufe), verschlechtern sie die Arbeit, weil sie dann als Systemdokumentation gelesen wird. Prüffrage für jede Seite: *Welche Aussage stützt sie?* Wenn die Antwort lautet „sie zeigt, was das System noch alles kann", gehört der Inhalt in den Anhang oder gar nicht in die Arbeit.

Verdichtungshebel: Feature-Aufzählungen als Tabelle, Screenshots, Code, ADRs im Volltext, Erhebungsinstrumente und Testfallkataloge in den Anhang.

## Quelle

„Gliederungsvarianten Bewertung und Variante D.docx" (Abschnitte 1.4, 1.5, 5) und „Gliederung Bachelorarbeit - Drei Varianten zur Abstimmung.docx" (Abschnitt 8), beide vom 09.09.2026, unter `07 Anhänge/Gliederung Bachelorarbeit/`.
