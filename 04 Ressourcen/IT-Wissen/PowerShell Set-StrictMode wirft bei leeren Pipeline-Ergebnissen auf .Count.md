---
tags: [ressource, powershell]
status: aktiv
date: 2026-09-02
---

# PowerShell Set-StrictMode wirft bei leeren Pipeline-Ergebnissen auf .Count

## Die Erkenntnis

Unter `Set-StrictMode -Version Latest` liefert eine Pipeline, die auf nichts trifft
(`Where-Object`/`ForEach-Object`/`Select-Object -Unique` ohne Treffer), `$null` statt eines
leeren Arrays. `$null` hat in PowerShell keine Eigenschaften — auch nicht `.Count` —, und
Strict Mode meldet das als Fehler statt es wie sonst still zu `$null` bzw. `0` zu machen.
Ohne Strict Mode fällt das nie auf, weil `$null.Count` dort klaglos `$null` zurückgibt statt
zu werfen.

## Das Fehlerbild

```
The property 'Count' cannot be found on this object. Verify that the property exists.
```

Zeigt auf die Zeile mit `.Count`, nicht auf die Pipeline, die das leere Ergebnis erzeugt hat
— bei einer Variable, die drei Zeilen vorher zugewiesen wurde, ist das erst mal nicht
offensichtlich. Besonders tückisch: der Fehler tritt nur auf, wenn die Pipeline zufällig
gerade leer läuft (z. B. beim allerersten Durchlauf, bevor Testdaten vorhanden sind) — beim
Testen mit befüllten Beispieldaten bleibt er unsichtbar.

## Die Lösung

Jede Variable, die aus einer Pipeline befüllt wird und später mit `.Count` geprüft wird,
mit `@(...)` umschließen: `$x = @($liste | Where-Object {...})`. `@()` erzwingt ein
echtes Array, auch mit null oder einem Treffer, und `.Count` funktioniert dann garantiert.

## Wann das für dich relevant wird

Immer wenn ein PowerShell-Skript mit `Set-StrictMode -Version Latest` läuft (guter Stil,
weil er auch Tippfehler in Variablennamen früh auffängt) und irgendwo `$pipelineErgebnis.Count`
oder `$pipelineErgebnis.Length` direkt nach einer `Where-Object`/`ForEach-Object`/
`Select-Object -Unique`-Zuweisung steht. Reines `+=`-Aufbauen ab `$x = @()` ist davon nicht
betroffen, das bleibt immer ein Array.

## Fundstelle

Bachelorarbeit-Repo, `thesis/dashboard/` (neues Fortschritts-Dashboard, 02.09.2026): dreimal
in Folge beim ersten Testlauf von `update.ps1`/`lib/Thesis-Parser.ps1` reproduziert (leere
Wortlisten, leere Zitat-Listen, leere Statusgewicht-Listen bei den allerersten geparsten
Abschnitten), jeweils mit `@(...)` behoben und danach fehlerfrei durchgelaufen.
