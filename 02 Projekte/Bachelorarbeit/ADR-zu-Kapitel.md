---
tags: [bachelorarbeit, adrs]
erstellt: 2026-08-11
---

# ADR-zu-Kapitel-Mapping

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!info] Woher kommen die ADRs?
> Die aktuellen ADR-Dateien (ADR-002 bis ADR-061) liegen in:
> `Bachelorarbeit/asiminu-projekt/docs/Bachelorarbeit/ADR-*.md`
> 
> Die ADR-Kompendium-Zusammenfassung: `Bachelorarbeit/thesis/ADR-Kompendium.md`

**Legende:** ✅ Im Text behandelt | 🔶 Erwähnt, nicht ausgeführt | ⬜ Noch offen

| ADR | Titel (Kurzfassung) | Kapitel | Status | Notiz |
|---|---|---|---|---|
| ADR-001 | ApplicationUser in Infrastructure (Benutzermodell) | 05 | 🔶 | am 04.10.2026 aus 5.1 gestrichen, nur noch Anhang B (N07) |
| ADR-002 | Auth-Provisioning Variante B (Token-Setup) | 04/05 | 🔶 | 5.2 (Freischaltung der Registrierung), ein Satz |
| ADR-003 | JWT-Parsing ohne NuGet (manuelles Base64url) | 05 | ⬜ | |
| ADR-004 | SMTP-Entkopplung via IMailSender | 05 | ⬜ | |
| ADR-005 | Microsoft Graph API für E-Mail | 05 | ⬜ | |
| ADR-006 | Standort-Entfernung aus Nutzerprofil | 04 | ⬜ | |
| ADR-007 | Separate CRQ-Datenbank (AsiMinu_Crq) | 04 | 🔶 | 5.2 (getrennte Datenbanken), kurz begründet |
| ADR-008 | Portal-Zugangskontrolle via requiredRole | 05 | ⬜ | |
| ADR-009 | TEF-Service-Interface und Stub | 04/05 | ✅ | 5.4 ausführlich (Kapselung der fehlenden Schnittstelle, Ersatzimplementierung) |
| ADR-010 | Stateful 2FA via Challenge-Token | 05 | 🔶 | 5.6 Tabelle Schutzmechanismen der Anmeldung |
| ADR-011 | Passwort-Reset ohne TOTP-Reset | 05 | 🔶 | 5.6 Tabelle Schutzmechanismen der Anmeldung |
| ADR-012 | Fire-and-Forget Upload-Pattern | 05 | ⬜ | |
| ADR-013 | AMR-ID-Generierung via pg_advisory_lock | 05 | 🔶 | 5.2 nur als „erster Anlauf“ ohne Nummer; Nummer nur noch im Anhang-Bauplan C |
| ADR-014 | RENAME COLUMN statt DROP/ADD | 05 | ⬜ | |
| ADR-015 | SiteCategory-Ausblendung (Least Privilege) | 05 | 🔶 | 5.2 (Kritikalitätsstufe für GU ausgeblendet), ein Satz |
| ADR-016 | Halbstündliche Zeitintervalle im CRQ-Formular | 05 | 🔶 | 5.3 (Halbstundenraster im Formular), ein Satz |
| ADR-017 | Refresh-Token-System (localStorage) | 05 | ⬜ | |
| ADR-018 | DateTime-Timezone-Behandlung (Blazor WASM) | 05 | ⬜ | |
| ADR-019 | Account-Lockout (5 Versuche, 1h) | 05 | 🔶 | 5.6 Tabelle Schutzmechanismen der Anmeldung |
| ADR-020 | Postgres-Hosting in Azure (Flexible Server) | 04 | ⬜ | nicht mehr im Text (Vorgeschichte Datenbank entfällt seit 30.09.2026) |
| ADR-021 | Geteilter Key Vault mit Präfix-Isolation | 04 | ⬜ | nicht mehr im Text |
| ADR-022 | Initial-Admin-Bootstrap (lokale API) | 05 | ⬜ | |
| ADR-023 | Dedizierter Bootstrap-Endpunkt | 05 | ⬜ | nicht mehr im Text |
| ADR-024 | Absolute Session-Obergrenze (24h) | 05 | 🔶 | 5.6 Tabelle Schutzmechanismen der Anmeldung |
| ADR-025 | Speicherlimit erhöht statt Streaming-Parser | 05 | ⬜ | am 04.10.2026 aus 5.5 gestrichen (ADR-Regel: Implementierungsdetail) |
| ADR-026 | CSP Rollout (Report-Only → erzwingend) | 05 | ⬜ | |
| ADR-027 | CSP Import-Map-Hash pipeline-seitig | 05 | ⬜ | |
| ADR-028 | News-Feature-Datenmodell (AuthDbContext) | 05 | ⬜ | |
| ADR-029 | Refresh-Token Race-Condition-Fix | 05 | ⬜ | |
| ADR-030 | CRQ-Zeitraum-Validierungsregeln erweitert | 05 | ✅ | 5.3 ausführlich (wo eine Regel steht: gemeinsame Bibliothek gegen Endpunkt) |
| ADR-031 | Freeze-Zeitraum-Datenmodell | 05 | ⬜ | |
| ADR-032 | Grund-Pflichtprüfung manuell je Endpunkt | 05 | ✅ | 5.3 ausführlich, zusammen mit ADR-030 |
| ADR-033 | RegistrationRequest bekommt UserId-Feld | 05 | ⬜ | |
| ADR-034 | Datenschutz als Singleton-Upload (Markdig) | 05 | ⬜ | |
| ADR-035 | AGB-Versionierung + zweistufige Akzeptanz | 05 | ⬜ | |
| ADR-036 | CRQ-Bearbeiter als Pflichtfeld | 05 | ✅ | 5.3 (Fehler durch nachgebaute Regelkopie) und 5.5 (feste Zuständigkeit) |
| ADR-037 | Kontodeaktivierung als Antrags-Workflow | 05 | ⬜ | |
| ADR-038 | Support-Ungelesen-Badge (GesehenVonAdmin) | 05 | ⬜ | |
| ADR-039 | Entra-Gate vor Admin-Panel (SWA Easy Auth) | 05 | ⬜ | |
| ADR-040 | Verschlüsselungsstrategie (CMK, getrennte Identitäten) | 04/05 | ⬜ | |
| ADR-041 | Netzsegmentierung (NSG, Egress-Kontrolle) | 04/05 | ⬜ | |
| ADR-042 | Firmen-Vorschlagsliste als Lookup-Tabelle | 05 | ⬜ | |
| ADR-043 | Admin-Panel-Sidebar (reiner Blazor-Toggle) | 05 | ⬜ | |
| ADR-044 | AGB-Version löschen nur wenn unakzeptiert | 05 | ⬜ | |
| ADR-045 | INC-E-Mail-Worker aus Studentenprojekt | 04/05 | ⬜ | |
| ADR-046 | AsiMinu-AdHoc-Integration (REST, Service-Account) | 04/05 | 🔶 | 5.1 (gemeinsame REST-Schnittstelle), Anhang B N06 |
| ADR-047 | TicketSpecialist-Rollenmodell | 04/05 | 🔶 | 5.2 (Geltungsbereich des Change Coordinators), ein Satz |
| ADR-048 | TEF-Callback zweistufige Statuskette | 05 | 🔶 | 5.4 (toleranter Rückkanal), ein Satz |
| ADR-049 | Spaltentrenner ohne JavaScript | 05 | ⬜ | |
| ADR-050 | Dashboard-Diagramm ohne Chart-Bibliothek | 05 | ⬜ | |
| ADR-051 | Löschlauf als geplanter Container-Apps-Job | 04/05 | ⬜ | |
| ADR-052 | Prüfprotokoll (Filter + Dienst, Doppelablage) | 04/05 | ✅ | 5.6 ausführlich (globaler Filter, keine Inhalte), Befund in 6.4 |
| ADR-053 | Operator-Rolle für reine Betriebs-Einsicht | 05 | ⬜ | am 04.10.2026 gestrichen (Operator-Rolle nur noch in Tabelle 5.1 ohne ADR) |
| ADR-054 | Fassungsnummern und scharfe Qualitätstore | 05/06 | 🔶 | 5.6 (blockierende Qualitätstore), Ergebnisse in 6.2 |
| ADR-055 | Automatisierung als einstellbare Regel | 05 | ✅ | 5.4 ausführlich (147 Schreibweisen, konfigurierbare Regelbasis), Messung in 6.4 |
| ADR-056 | Automatik als Lauf zu festen Uhrzeiten | 05 | 🔶 | 5.4 (Ausführung, Nachholen, Sperre), kurz |
| ADR-057 | CRQ-Chat-Panel statt Mail-Reply | 05 | ✅ | 5.5 ausführlich (Fehlerklasse der E-Mail-Zuordnung) |
| ADR-058 | Einzelbetrieb der Datenbank per Dateisperre | 05 | ⬜ | nicht im Text |
| ADR-059 | Firmenzugehörigkeit über Firmen-ID | 05 | 🔶 | 5.2, ein Satz |
| ADR-060 | Rückkehr zu PostgreSQL Flexible Server | 05 | 🔶 | 5.6 (verwalteter Dienst), nur Endzustand |
| ADR-061 | AMR-Nummer aus PostgreSQL-Sequenz | 05 | 🔶 | 5.2, seit 04.10.2026 nur noch kurz; Listing E.1 |

---

## Auswertung

- **Gesamt:** 61 ADRs in dieser Tabelle (ADR-001 bis ADR-061; ADR-061 entstand am 30.09.2026 nach dem eingefrorenen Evaluationsstand)
- **Behandelt (✅):** 7
- **Erwähnt (🔶):** 18
- **Noch offen (⬜):** 36

> [!info] Stand 04.10.2026
> Seit der Kürzung gilt in Kapitel 5 eine dreistufige ADR-Regel (siehe `thesis/Schreibstand.md`):
> ausführlich (✅) nur Entscheidungen, die Datenqualität, Automatisierung oder Prozesssicherheit
> tragen; Entscheidungen, die nur eine Anforderung umsetzen, stehen mit einem Satz im Text (🔶);
> Implementierungsdetails bleiben den ADRs vorbehalten (⬜). ⬜ heißt deshalb nicht mehr
> „noch zu schreiben“, sondern meist „bewusst nicht im Text“.

> [!tip] Tipp
> Nicht alle 53 ADRs brauchen ein eigenes Unterkapitel. Viele lassen sich in übergeordnete Themen gruppieren (z.B. alle Auth-ADRs zusammen, alle Sicherheits-ADRs zusammen). Das [[Kapitelplanung]]-Dokument hilft dabei.
