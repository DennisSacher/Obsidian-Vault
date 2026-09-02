---
tags: [ressource, latex, bibtex]
status: aktiv
date: 2026-09-02
---

# BibTeX-Kommentare funktionieren nur zwischen Einträgen, nicht darin

## Die Erkenntnis

In einer `.tex`-Datei leitet `%` überall einen Kommentar ein. In einer `.bib`-Datei gilt das
nur *zwischen* zwei `@book{...}`/`@article{...}`-Blöcken. Steht eine `%`-Zeile direkt nach
der öffnenden Klammer eines Eintrags (oder sonst irgendwo dazwischen), erwartet BibTeX an
dieser Stelle einen Feldnamen, findet aber `%`, meldet „missing a field name" und verwirft
den kompletten restlichen Eintrag, nicht nur die eine Zeile. Das Ergebnis sieht harmlos aus:
kein LaTeX-Fehler, das Dokument kompiliert scheinbar durch, aber Autor, Titel, Verlag und
Jahr dieses einen Eintrags sind plötzlich leer.

## Das Fehlerbild

`pdflatex`/`latexmk` selbst zeigt nichts Auffälliges. Erst im separaten `bibtex`-Lauf (bzw.
in der `.blg`-Log-Datei) taucht „You're missing a field name---line X of file thesis.bib"
auf, gefolgt von „I'm skipping whatever remains of this entry". Im späteren
`pdflatex`-Durchlauf wirkt das dann wie mehrere unabhängige Warnungen ("empty author",
"empty title", "missing publisher", "empty year") für denselben Eintrag, was den
eigentlichen Auslöser (die einzelne Kommentarzeile weiter oben) leicht verschleiert.

## Die Lösung

Erklärende Kommentare zu einem Bib-Eintrag immer *vor* die `@book{...}`-Zeile setzen, nie
dazwischen. BibTeX ignoriert alles außerhalb der geschweiften Klammern eines Eintrags
vollständig, das ist der sichere Ort für Anmerkungen wie „Auflage geprüft, Key aus
Kompatibilitätsgründen nicht umbenannt". Alternativ, falls die Anmerkung im Eintrag selbst
sichtbar bleiben soll: ein eigenes Feld wie `note` oder `annote` verwenden statt `%`.

## Wann das für dich relevant wird

Immer wenn du in einer `.bib`-Datei nachträglich Metadaten korrigierst oder ergänzt und dazu
eine Begründung direkt am Eintrag festhalten willst. Besonders tückisch, weil der Fehler erst
beim tatsächlichen `bibtex`-Lauf auffällt und ein einzelner kaputter Eintrag den Rest des
Dokuments nicht sichtbar stört, wenn man die Kompilier-Logs nicht genau liest.

## Fundstelle

Bachelorarbeit-Repo, `thesis/BA-Text/latex-projekt/thesis.bib`: drei nachträglich mit
Prüfhinweisen versehene Einträge (`LangmannTuri2020`, `Newman2021`,
`GadatschMangiapane2017`) verloren dadurch beim Commit `a980d03` (02.09.2026) ihre
kompletten Feldinhalte. Beim routinemäßigen Durchkompilieren vor dem Commit aufgefallen und
in `c508a52` behoben (Kommentare vor die jeweilige Eintragszeile verschoben, Inhalt sonst
unverändert).
