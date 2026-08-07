---
tags: [projekt]
status: aktiv
erstellt: 2026-07-29
---

# Anonis

## Ziel
Anonis ist eine geplante B2B-SaaS-Plattform (Hybrid: Cloud + On-Premise), die Unternehmensdokumente automatisch pseudonymisiert, bevor sie an externe KI-Tools wie ChatGPT oder Claude weitergegeben werden. Ziel: sensible Daten (Namen, IBAN, Adressen, interne Projektnamen etc.) schützen und DSGVO-konforme KI-Nutzung ermöglichen. Details zu Zielgruppe und Geschäftsmodell in 00 Kontext/ICP.md und 00 Kontext/Angebot.md.

## Status
Businessplan fertig ausgearbeitet. Nächster Schritt: Python-CLI-Prototyp bauen zur Validierung mit 3-5 Pilotkunden, bevor mehr Entwicklungszeit in die volle SaaS-Lösung investiert wird.

## Nächste Schritte
- [ ] Python-CLI-Prototyp bauen (Erkennungs-Engine: Regex + spaCy-NER + Firmenprofil-Matching)
- [ ] 3-5 Pilotkunden für Validierung finden

## Notizen
Dennis arbeitet allein an dem Projekt und nutzt Claude als zentralen Sparringspartner. Kerntechnologie: Regex + spaCy-NER + Firmenprofil-Matching zur Erkennung sensibler Begriffe, Ersetzung durch nummerierte Platzhalter mit optionaler Rückübersetzung.
