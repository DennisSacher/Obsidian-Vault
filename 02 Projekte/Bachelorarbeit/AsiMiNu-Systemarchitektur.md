---
tags: [bachelorarbeit, architektur, referenz]
status: aktiv
date: 2026-10-07
---

# AsiMiNu-Systemarchitektur

Gesamtbild des gebauten Systems in der Umgebung **Test**: alle ausgerollten Bausteine, wo die Daten liegen, wie Generalunternehmer, Change Coordinator und Admin mit dem System arbeiten, welche Daten zwischen den Teilen fließen und wie alles in Azure verteilt ist. Gedacht als Referenz zum Hineinzoomen, nicht als Abbildung für die Arbeit (dort gibt es Abb. 5.1).

![[AsiMiNu-Systemarchitektur.png]]

Bearbeitbare Quelle: [[AsiMiNu-Systemarchitektur.excalidraw]]

## Lesehilfe

- **Leserichtung:** Nutzer links, Panels, API in der Mitte, Datenbank rechts, externe Partner ganz rechts, Auslieferung unten.
- **Rahmen:** Azure → Ressourcengruppe `AsiMinu2.0-test` → VNet → Subnetze. Die gemeinsame Ressourcengruppe `AsiMinu2.0-shared` (Key Vault, Registry, Aktionsgruppe) nutzen alle Umgebungen.
- **Farbige Pfeile** zeigen die Wege der drei Rollen, graue Pfeile die Datenflüsse zwischen Systemteilen. Jeder Pfeil nennt Inhalt und Protokoll.
- **Gestrichelt** ist der Zielzustand der Telefónica-Anbindung.
- **① ② ③** verweisen auf die Beispieldaten links unten (alle Werte sind Platzhalter).

## Was man wissen muss

- **Telefónica ist noch nicht echt angebunden.** Die API holt vor jeder „Übertragung“ ein OAuth2-Token beim Tokenendpunkt (Token-Probe) und vergibt dann eine simulierte CRQ-Nummer (`TefServiceStub`, ADR-009). Antragsdaten gehen heute nicht an Telefónica. Der Rückkanal `POST /api/crq/callback` mit `X-Api-Key` ist im Code fertig (ADR-048), das Format des Hinwegs legt Telefónica noch fest.
- **Admin- und CC-Panel** sind zusätzlich durch einen Entra-ID-Login der Static Web App geschützt. Das GU-Panel ist öffentlich. Die eigentliche Anmeldung an der API läuft bei allen über Passwort, TOTP und JWT.
- **Datenbank:** Der Flexible Server hat öffentlichen Zugang, eingeschränkt durch Firewall-Regeln. Die Container Apps erreichen ihn über den Private Endpoint im VNet.
- **Sicherungen:** Der Sicherungsjob hat eine eigene Managed Identity, damit die Anwendung die Sicherungen nicht überschreiben oder löschen kann.

## Quellen und Stand

Abgeleitet aus dem Code und den Bicep-Dateien im Repo (`asiminu-projekt/infra/main.bicep`, `main.parameters.test.json`, `Test-azure-pipeline.yml`, `src/`), Stand 07.10.2026. Dev ist gleich aufgebaut (`10.10.0.0/16`). Prod ist vorbereitet, aber noch nicht ausgerollt.

Verwandt: [[AsiMiNu-Prozessablauf]], [[Bachelorarbeit AsiMinu App]]
