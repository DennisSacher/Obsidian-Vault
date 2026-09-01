---
tags: [ressource, latex, todonotes]
status: aktiv
date: 2026-09-01
---

# LaTeX todonotes bricht bei verschachtelten Listen ab

## Die Erkenntnis

Das `todonotes`-Paket zeichnet seine `\todo[inline]{...}`-Boxen intern über `tikz`. Sobald
du in so eine Box eine `itemize`- oder `enumerate`-Umgebung packst, bricht die
Kompilierung komplett ab, mit einem wenig sprechenden Fehler wie
`Undefined control sequence \@todonotes@drawInlineNote`. Das ist kein Tippfehler von dir,
sondern eine echte Grenze des Pakets: Listenumgebungen brauchen vertikalen Modus und
eigene Absatzmechanik, die innerhalb einer tikz-Node so nicht funktioniert.

## Das Fehlerbild

Fatal Error, keine PDF-Ausgabe mehr, egal wie klein der Rest des Dokuments ist. Die
Fehlermeldung zeigt auf eine interne todonotes-Zeile, nicht auf deinen eigentlichen Text,
das macht die Ursache beim ersten Blick in den Log schwer zu erkennen.

## Die Lösung

Innerhalb von `\todo{...}` keine `\begin{itemize}`/`\begin{enumerate}` verwenden.
Stattdessen als durchlaufenden Fließtext mit manueller Nummerierung schreiben, zum
Beispiel `\textbf{(1)} Erster Punkt ... \textbf{(2)} Zweiter Punkt ...`. Sieht in der
gerenderten Box etwas kompakter aus, kompiliert aber zuverlässig, auch bei langen,
strukturierten Notizen mit vielen Teilpunkten.

## Wann das für dich relevant wird

Immer wenn du dir in einem LaTeX-Dokument ausführliche `\todo`-Stichpunkte als
Schreibgerüst anlegst (zum Beispiel Gliederungs- oder Kapitelplanung) und dabei mehr als
einen Gedanken pro Box unterbringen willst. Echte Listen außerhalb von `\todo`-Boxen sind
davon nicht betroffen, die funktionieren ganz normal.

## Fundstelle

Bachelorarbeit-Repo, `thesis/BA-Text/latex-projekt/`: beim Ausformulieren sehr
ausführlicher Kapitel-Todos (01.09.2026) mit `\begin{enumerate}` innerhalb von
`\todo[inline]{...}` reproduziert, nach Umbau auf `\textbf{(1)}`-Stil behoben und mit
`latexmk -pdf` durchkompiliert verifiziert.
