---
tags: [bachelorarbeit, adrs]
erstellt: 2026-08-11
---

# ADR-zu-Kapitel-Mapping

← zurück zu [[Bachelorarbeit AsiMinu App]]

> [!info] Woher kommen die ADRs?
> Die aktuellen ADR-Dateien (ADR-002 bis ADR-054) liegen in:
> `Bachelorarbeit/asiminu-projekt/docs/Bachelorarbeit/ADR-*.md`
> 
> Die ADR-Kompendium-Zusammenfassung: `Bachelorarbeit/thesis/ADR-Kompendium.md`

**Legende:** ✅ Im Text behandelt | 🔶 Erwähnt, nicht ausgeführt | ⬜ Noch offen

| ADR | Titel (Kurzfassung) | Kapitel | Status | Notiz |
|---|---|---|---|---|
| ADR-002 | Auth-Provisioning Variante B (Token-Setup) | 04/05 | 🔶 | referenziert in Kap. 04 (Rollenmodell) + Kap. 05 (Sicherheitskonzept), noch nicht ausgeführt |
| ADR-003 | JWT-Parsing ohne NuGet (manuelles Base64url) | 05 | ⬜ | |
| ADR-004 | SMTP-Entkopplung via IMailSender | 05 | ⬜ | |
| ADR-005 | Microsoft Graph API für E-Mail | 05 | ⬜ | |
| ADR-006 | Standort-Entfernung aus Nutzerprofil | 04 | ⬜ | |
| ADR-007 | Separate CRQ-Datenbank (AsiMinu_Crq) | 04 | 🔶 | referenziert in Kap. 04 (Datenmodell), noch nicht ausgeführt |
| ADR-008 | Portal-Zugangskontrolle via requiredRole | 05 | ⬜ | |
| ADR-009 | TEF-Service-Interface und Stub | 04/05 | 🔶 | referenziert in Kap. 05 (Backend-Service), noch nicht ausgeführt |
| ADR-010 | Stateful 2FA via Challenge-Token | 05 | 🔶 | referenziert in Kap. 05 (Sicherheitskonzept), noch nicht ausgeführt |
| ADR-011 | Passwort-Reset ohne TOTP-Reset | 05 | 🔶 | referenziert in Kap. 05 (Sicherheitskonzept), noch nicht ausgeführt |
| ADR-012 | Fire-and-Forget Upload-Pattern | 05 | ⬜ | |
| ADR-013 | AMR-ID-Generierung via pg_advisory_lock | 05 | 🔶 | referenziert in Kap. 04 (Datenmodell) + Kap. 06 (Herausforderungen), noch nicht ausgeführt |
| ADR-014 | RENAME COLUMN statt DROP/ADD | 05 | ⬜ | |
| ADR-015 | SiteCategory-Ausblendung (Least Privilege) | 05 | 🔶 | referenziert in Kap. 04 (Rollenmodell), noch nicht ausgeführt |
| ADR-016 | Halbstündliche Zeitintervalle im CRQ-Formular | 05 | ⬜ | |
| ADR-017 | Refresh-Token-System (localStorage) | 05 | ⬜ | |
| ADR-018 | DateTime-Timezone-Behandlung (Blazor WASM) | 05 | ⬜ | |
| ADR-019 | Account-Lockout (5 Versuche, 1h) | 05 | 🔶 | referenziert in Kap. 05 (Sicherheitskonzept), noch nicht ausgeführt |
| ADR-020 | Postgres-Hosting in Azure (Flexible Server) | 04 | 🔶 | referenziert in Kap. 05 (Deployment) + Kap. 06 (Herausforderungen), noch nicht ausgeführt |
| ADR-021 | Geteilter Key Vault mit Präfix-Isolation | 04 | 🔶 | referenziert in Kap. 05 (Deployment), noch nicht ausgeführt |
| ADR-022 | Initial-Admin-Bootstrap (lokale API) | 05 | ⬜ | |
| ADR-023 | Dedizierter Bootstrap-Endpunkt | 05 | 🔶 | referenziert in Kap. 05 (Deployment), noch nicht ausgeführt |
| ADR-024 | Absolute Session-Obergrenze (24h) | 05 | 🔶 | referenziert in Kap. 05 (Sicherheitskonzept) + Kap. 06 (Herausforderungen), noch nicht ausgeführt |
| ADR-025 | Speicherlimit erhöht statt Streaming-Parser | 05 | 🔶 | referenziert in Kap. 05 (Admin-Panel), noch nicht ausgeführt |
| ADR-026 | CSP Rollout (Report-Only → erzwingend) | 05 | ⬜ | |
| ADR-027 | CSP Import-Map-Hash pipeline-seitig | 05 | ⬜ | |
| ADR-028 | News-Feature-Datenmodell (AuthDbContext) | 05 | ⬜ | |
| ADR-029 | Refresh-Token Race-Condition-Fix | 05 | ⬜ | |
| ADR-030 | CRQ-Zeitraum-Validierungsregeln erweitert | 05 | ⬜ | |
| ADR-031 | Freeze-Zeitraum-Datenmodell | 05 | ⬜ | |
| ADR-032 | Grund-Pflichtprüfung manuell je Endpunkt | 05 | ⬜ | |
| ADR-033 | RegistrationRequest bekommt UserId-Feld | 05 | ⬜ | |
| ADR-034 | Datenschutz als Singleton-Upload (Markdig) | 05 | ⬜ | |
| ADR-035 | AGB-Versionierung + zweistufige Akzeptanz | 05 | ⬜ | |
| ADR-036 | CRQ-Bearbeiter als Pflichtfeld | 05 | ⬜ | |
| ADR-037 | Kontodeaktivierung als Antrags-Workflow | 05 | ⬜ | |
| ADR-038 | Support-Ungelesen-Badge (GesehenVonAdmin) | 05 | ⬜ | |
| ADR-039 | Entra-Gate vor Admin-Panel (SWA Easy Auth) | 05 | ⬜ | |
| ADR-040 | Verschlüsselungsstrategie (CMK, getrennte Identitäten) | 04/05 | ⬜ | |
| ADR-041 | Netzsegmentierung (NSG, Egress-Kontrolle) | 04/05 | ⬜ | |
| ADR-042 | Firmen-Vorschlagsliste als Lookup-Tabelle | 05 | ⬜ | |
| ADR-043 | Admin-Panel-Sidebar (reiner Blazor-Toggle) | 05 | ⬜ | |
| ADR-044 | AGB-Version löschen nur wenn unakzeptiert | 05 | ⬜ | |
| ADR-045 | INC-E-Mail-Worker aus Studentenprojekt | 04/05 | ⬜ | |
| ADR-046 | AsiMinu-AdHoc-Integration (REST, Service-Account) | 04/05 | ⬜ | |
| ADR-047 | TicketSpecialist-Rollenmodell | 04/05 | ⬜ | |
| ADR-048 | TEF-Callback zweistufige Statuskette | 05 | ⬜ | |
| ADR-049 | Spaltentrenner ohne JavaScript | 05 | ⬜ | |
| ADR-050 | Dashboard-Diagramm ohne Chart-Bibliothek | 05 | ⬜ | |
| ADR-051 | Löschlauf als geplanter Container-Apps-Job | 04/05 | ⬜ | |
| ADR-052 | Prüfprotokoll (Filter + Dienst, Doppelablage) | 04/05 | ⬜ | |
| ADR-053 | Operator-Rolle für reine Betriebs-Einsicht | 05 | ⬜ | neu 11.08.2026 aus Submodul, jetzt in [[Kapitelplanung]] als Lücke vermerkt |
| ADR-054 | Fassungsnummern und scharfe Qualitätstore | 05/06 | ⬜ | neu 12.08.2026 aus Submodul (Submodul-Update 3311c97 → 4182ae3), noch nicht in Kapitelplanung berücksichtigt |

---

## Auswertung

- **Gesamt:** 53 ADR-Dateien (ADR-002–ADR-054, ADR-001 liegt außerhalb der Submodul-Nummerierung und wird separat als `entscheidung-applicationuser-layer.pdf` referenziert)
- **Behandelt (✅):** 0
- **Erwähnt (🔶):** 13 (ADR-001 zusätzlich im Text erwähnt, aber nicht in dieser Tabelle geführt)
- **Noch offen (⬜):** 40

> [!info] Stand 12.08.2026
> Alle Kapitel liegen noch als Gliederung mit `\quellen{}`/`\todo[inline]{}`-Platzhaltern vor (Ausnahme: Kap. 01 vollständig, Kap. 07 teilweise). Die 13 🔶-ADRs sind dort namentlich erwähnt, aber inhaltlich noch nicht ausgeführt — sobald Kap. 04/05/06 tatsächlich geschrieben werden, wandern sie zu ✅.

> [!tip] Tipp
> Nicht alle 53 ADRs brauchen ein eigenes Unterkapitel. Viele lassen sich in übergeordnete Themen gruppieren (z.B. alle Auth-ADRs zusammen, alle Sicherheits-ADRs zusammen). Das [[Kapitelplanung]]-Dokument hilft dabei.
