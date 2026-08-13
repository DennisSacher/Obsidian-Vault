---
tags: [ressource, csharp, efcore]
status: aktiv
date: 2026-08-13
---

# EF Core Projektion als Expression statt Methode

## Die Erkenntnis

Wenn du in mehreren Controllern oder Services dieselbe Entität auf dasselbe DTO abbildest,
lohnt es sich, diese Abbildung genau einmal als `Expression<Func<TEntity, TDto>>`
auszulagern, statt sie als normale Methode zu schreiben. Der Unterschied ist klein im
Code, aber wichtig in der Wirkung: Eine `Expression` kann EF Core direkt in SQL
übersetzen und in `.Select(...)` einsetzen, sodass nur die wirklich gebrauchten Spalten
aus der Datenbank geladen werden. Eine normale Methode kannst du dagegen erst aufrufen,
nachdem EF Core die komplette Zeile schon geladen hat.

## Warum das mehr ist als eine Stilfrage

Im AsiMinu-Projekt gab es dieselbe Standort-zu-DTO-Abbildung an vier Stellen unabhängig
voneinander geschrieben. Drei davon waren vollständig, die vierte (für die
Incident-Ansicht) hatte nur elf von neunzehn Feldern befüllt, weil sie ursprünglich nur
für das geschrieben wurde, was die Seite zu dem Zeitpunkt brauchte. Als die Seite später
auch die Anschrift zeigen sollte, stand dort "nicht erfasst", obwohl die Daten in der
Datenbank längst vorhanden waren. Das ist eine Fehlerklasse, bei der man zuerst am
falschen Ende sucht: Es sieht nach einem Importfehler aus, ist aber ein vergessenes Feld
in einer von vier Kopien derselben Abbildung.

## Die Lösung

Eine gemeinsame Klasse mit einer einzigen `Expression<Func<TEntity, TDto>>`-Eigenschaft,
die alle Aufrufstellen referenzieren. Zusätzlich lohnt sich ein Test, der per Reflexion
nachzählt, dass jedes beschreibbare Feld des DTOs in der Abbildung tatsächlich belegt
wird. Ein neues DTO-Feld, das du in der Abbildung vergisst, fällt dann sofort auf, statt
erneut unbemerkt zu bleiben.

## Wann das für dich relevant wird

Sobald du merkst, dass du eine Entität-zu-DTO-Abbildung zum zweiten Mal irgendwo im Code
hinschreibst. Der Impuls "kopier ich mir schnell" ist genau der Moment, in dem eine
gemeinsame `Expression`-Klasse sich lohnt, vor allem wenn verschiedene Seiten
unterschiedliche Ausschnitte derselben Entität zeigen sollen.

## Fundstelle

AsiMinu-Repo: `src/backend/AsiMinu.Domain/Services/StandortAbbildung.cs`,
Reflexions-Test in `StandortAbbildungTests.cs`, gefunden und behoben am 12.08.2026.
Details im Tagesprotokoll `docs/Bachelorarbeit/arbeitsprotokolle/2026-08-12-tagesprotokoll.md`.
