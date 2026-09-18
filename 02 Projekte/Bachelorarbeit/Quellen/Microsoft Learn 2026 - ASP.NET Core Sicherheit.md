---
tags: [bachelorarbeit, quelle]
bibtex-key: MicrosoftAspNetSecurity2024
autor: Microsoft Corporation
jahr: 2026
titel: "ASP.NET Core Security-Dokumentation"
typ: Online (Herstellerdokumentation)
themenbereich: Sicherheit (JWT, TOTP, DSGVO)
status: ausgewertet
---

# Sicherheitsaspekte für ASP.NET Core (Microsoft Learn)

← zurück zu [[Zitate und Quellen]]

## Vollzitat (für das Literaturverzeichnis, Online-Dokument)

Microsoft Corporation: Sicherheitsaspekte für ASP.NET Core. In: Microsoft Learn, ASP.NET Core in .NET 10.0. URL: https://learn.microsoft.com/de-de/aspnet/core/security/?view=aspnetcore-10.0 (zuletzt aktualisiert am 24.05.2026, gesichert am 02.09.2026 -- bitte tatsächliches Abrufdatum prüfen/anpassen falls du die Seite schon früher gespeichert hast)

## Kurzzitat (Verweis im Fließtext)

Microsoft Corporation 2026, ASP.NET Core Security-Dokumentation

## Zitierfähigkeit -- kurz eingeordnet

Offizielle Hersteller-/Frameworkdokumentation (kein Blog, keine private Seite), gemäß eurer Zitierregeln (`04 Ressourcen/Wissenschaftliches Arbeiten/Zitieren und Quellenarbeit.md`) am ehesten vergleichbar mit "Webseiten anerkannter Organisationen" -- für die Beschreibung technischer Sachverhalte (wie ASP.NET Core Security-Mechanismen tatsächlich funktionieren) gut geeignet, nicht als Beleg für wissenschaftliche Aussagen. Da es eine lebende, sich ändernde Seite ist: Version/Datum wie oben archivieren, ggf. zusätzlich per web.archive.org sichern.

## Kernaussagen (bereits im Volltext unten vorhanden)

- Authentifizierung vs. Autorisierung, Kernkonzept mit Raum-Metapher
- Sichere Authentifizierungsflows: Empfehlung Managed Identities statt Resource Owner Password Credentials (ROPG)
- Konfigurationsdaten-Richtlinien: nie Kennwörter im Klartext, Secret Manager für Dev
- Verwandte Inhalte verlinken direkt auf TOTP-QR-Code-Aktivierung (relevant für euer JWT/TOTP-Sicherheitskonzept)

## Verwendung in der Arbeit

- Kapitel 02 (Grundlagen, Sicherheit): bereits referenziert via `\cite{MicrosoftAspNetSecurity2024}`

## Original-Inhalt (vollständig übernommen, Stand siehe Vollzitat oben)

# Sicherheitsaspekte für ASP.NET Core

*Quelle: [learn.microsoft.com/de-de/aspnet/core/security](https://learn.microsoft.com/de-de/aspnet/core/security/?view=aspnetcore-10.0) (ASP.NET Core in .NET 10.0, zuletzt aktualisiert am 24.05.2026)*

ASP.NET Core ermöglicht Entwicklern, Sicherheit zu konfigurieren und zu verwalten. Die folgende Liste enthält Links zu Artikeln zum Arbeiten mit Sicherheit in ASP.NET Core:

- [Authentifizierung](https://learn.microsoft.com/de-de/aspnet/core/security/authentication/?view=aspnetcore-10.0)
- [Autorisierung](https://learn.microsoft.com/de-de/aspnet/core/security/authorization/introduction?view=aspnetcore-10.0)
- [Datenschutz](https://learn.microsoft.com/de-de/aspnet/core/security/data-protection/introduction?view=aspnetcore-10.0)
- [HTTPS-Erzwingung](https://learn.microsoft.com/de-de/aspnet/core/security/enforcing-ssl?view=aspnetcore-10.0)
- [Sicheres Speichern geheimer App-Schlüssel in der Entwicklung](https://learn.microsoft.com/de-de/aspnet/core/security/app-secrets?view=aspnetcore-10.0)
- [XSRF/CSRF-Prävention](https://learn.microsoft.com/de-de/aspnet/core/security/anti-request-forgery?view=aspnetcore-10.0)
- [Cross-Origin Resource Sharing (CORS)](https://learn.microsoft.com/de-de/aspnet/core/security/cors?view=aspnetcore-10.0)
- [Angriffe durch Cross-Site-Scripting (XSS)](https://learn.microsoft.com/de-de/aspnet/core/security/cross-site-scripting?view=aspnetcore-10.0)

Diese Sicherheitsfunktionen ermöglichen Ihnen, robuste und sichere ASP.NET Core-Apps zu erstellen.

Weitere Informationen zu den Sicherheitsinformationen für Blazor, die die Hinweise in diesem Knoten ergänzen oder ersetzen, finden Sie unter [Authentifizierung und Autorisierung in ASP.NET Core Blazor](https://learn.microsoft.com/de-de/aspnet/core/blazor/security/?view=aspnetcore-10.0) sowie in den anderen Artikeln im Knoten Sicherheit und Identity von Blazor.

## ASP.NET Core-Sicherheitsfeatures

ASP.NET Core bietet viele Tools und Bibliotheken, um ASP.NET Core Apps wie integrierte Identitätsanbieter und nicht Microsoft Identitätsdienste wie Facebook, Twitter und LinkedIn zu sichern. ASP.NET Core bietet mehrere Ansätze zum Speichern von App-Geheimnissen.

## Authentifizierung im Vergleich zu Autorisierung

[Bei der Authentifizierung](https://learn.microsoft.com/de-de/aspnet/core/security/authentication/?view=aspnetcore-10.0) handelt es sich um einen Prozess, bei dem ein Benutzer Anmeldeinformationen bereitstellt, die mit Anmeldeinformationen verglichen werden, die in einem Betriebssystem, einer Datenbank, einer App oder einer Ressource gespeichert sind. Wenn die beiden Anmeldeinformationen übereinstimmen, authentifiziert sich der Benutzer erfolgreich. Sie können dann Aktionen ausführen, für die sie autorisiert sind. Der [Autorisierungsprozess](https://learn.microsoft.com/de-de/aspnet/core/security/authorization/introduction?view=aspnetcore-10.0) bestimmt die Aktionen, die der Benutzer ausführen darf.

Eine weitere Möglichkeit, Authentifizierung zu betrachten, besteht darin, sie als eine Möglichkeit zu sehen, einen Raum zu betreten, wobei dieser Raum ein Server, eine Datenbank, eine App oder eine Ressource sein kann. Autorisierung definiert, welche Aktionen der Benutzer an welchen Objekten innerhalb dieses Bereichs (Server, Datenbank oder App) ausführen kann.

## Häufige Sicherheitsrisiken in Software

ASP.NET Core und Entity Framework enthalten Features, mit denen Sie Ihre Apps schützen und Sicherheitsverletzungen verhindern können. Die folgende Liste von Links verweist auf die Dokumentation, die Techniken zur Vermeidung der häufigsten Sicherheitsrisiken in Web-Apps beschreibt:

- [Angriffe durch Cross-Site-Scripting (XSS)](https://learn.microsoft.com/de-de/aspnet/core/security/cross-site-scripting?view=aspnetcore-10.0)
- [SQL-Abfragen > SQL-Einfügungsangriffe](https://learn.microsoft.com/de-de/ef/core/querying/sql-queries#passing-parameters)
- [Cross-Site Request Forgery (XSRF/CSRF)-Angriffe](https://learn.microsoft.com/de-de/aspnet/core/security/anti-request-forgery?view=aspnetcore-10.0)
- [Offene Weiterleitungsangriffe](https://learn.microsoft.com/de-de/aspnet/core/security/preventing-open-redirects?view=aspnetcore-10.0)

Es gibt weitere Sicherheitsrisiken, die Sie kennen sollten. Weitere Informationen finden Sie in den anderen Artikeln im Abschnitt Security and Identity des Inhaltsverzeichnisses.

## Sichere Authentifizierungsflows

Es wird empfohlen, die sicherste Authentifizierungsoption zu verwenden. Bei Azure-Diensten bieten [verwaltete Identitäten](https://learn.microsoft.com/de-de/entra/identity/managed-identities-azure-resources/overview) die sicherste Authentifizierung.

Vermeiden Sie die Verwendung des Resource Owner Password Credentials (ROPG)-Grant:

- Es macht das Kennwort des Benutzers für den Client verfügbar.
- Es ist ein erhebliches Sicherheitsrisiko.
- Verwenden Sie sie nur, wenn andere Authentifizierungsflüsse nicht möglich sind.

Verwaltete Identitäten sind eine sichere Möglichkeit, sich bei Diensten zu authentifizieren, ohne Anmeldeinformationen in Code, Umgebungsvariablen oder Konfigurationsdateien speichern zu müssen. Verwaltete Identitäten sind für Azure-Dienste verfügbar und können mit Azure SQL, Azure Storage und anderen Azure-Diensten verwendet werden:

- [Verwaltete Identitäten in Microsoft Entra für Azure SQL](https://learn.microsoft.com/de-de/azure/azure-sql/database/authentication-azure-ad-user-assigned-managed-identity)
- [Verwaltete Identitäten für App Service und Azure Functions](https://learn.microsoft.com/de-de/azure/app-service/overview-managed-identity)
- [Sichere Authentifizierungsflows](https://learn.microsoft.com/de-de/entra/identity-platform/authentication-flows-app-scenarios#web-app-that-signs-in-a-user)

Wenn die App auf einem Testserver bereitgestellt wird, kann eine Umgebungsvariable verwendet werden, um die Verbindungszeichenfolge auf einen Datenbankserver für Tests festzulegen. Weitere Informationen finden Sie unter [Konfiguration](https://learn.microsoft.com/de-de/aspnet/core/fundamentals/configuration/?view=aspnetcore-10.0). Umgebungsvariablen werden häufig in nur unverschlüsseltem Text gespeichert. Wenn der Computer oder der Prozess kompromittiert ist, können Umgebungsvariablen für nicht vertrauenswürdige Parteien zugänglich sein. Wir raten davon ab, Umgebungsvariablen zum Speichern einer Verbindungszeichenfolge für die Produktion zu verwenden, da dies nicht der sicherste Ansatz ist.

Richtlinien für Konfigurationsdaten:

- Speichern Sie nie Kennwörter oder andere vertrauliche Daten im Konfigurationsanbietercode oder in Nur-Text-Konfigurationsdateien. Das [Secret Manager](https://learn.microsoft.com/de-de/aspnet/core/security/app-secrets?view=aspnetcore-10.0)-Tool kann zum Speichern von Geheimnissen in der Entwicklungsumgebung verwendet werden.
- Verwenden Sie keine Produktionsgeheimnisse in Entwicklungs- oder Testumgebungen.
- Geben Sie Geheimnisse außerhalb des Projekts an, damit sie nicht versehentlich in ein Quellcoderepository übernommen werden können.

Weitere Informationen finden Sie unter:

- [Empfehlungen zu bewährten Methoden für verwaltete Identitäten](https://learn.microsoft.com/de-de/entra/identity/managed-identities-azure-resources/managed-identity-best-practice-recommendations)
- [Verbinden Ihrer Anwendung mit Ressourcen, ohne Anmeldeinformationen in Ihrem Code verwalten zu müssen](https://learn.microsoft.com/de-de/entra/identity/managed-identities-azure-resources/overview-for-developers?tabs=portal%2Cdotnet)
- [Azure-Dienste, die verwaltete Identitäten für den Zugriff auf andere Dienste verwenden können](https://learn.microsoft.com/de-de/entra/identity/managed-identities-azure-resources/managed-identities-status)
- [IETF OAuth 2.0 Security Best Current Practice (Abschnitt 2.4: Resource Owner Password Credentials Grant)](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-security-topics#section-2.4)

Informationen zu anderen Cloudanbietern finden Sie unter:

- [AWS (Amazon Web Services): AWS Schlüsselverwaltungsdienst (KMS)](https://aws.amazon.com/kms/)
- [Übersicht über Google Cloud Schlüsselverwaltungsdienst](https://docs.cloud.google.com/kms/docs/key-management-service)

## Muster für Unternehmens-Web-Apps

Anleitungen zum Erstellen einer zuverlässigen, sicheren, leistungsfähigen, testbaren und skalierbaren ASP.NET Core-App finden Sie unter [Enterprise Web App-Muster](https://learn.microsoft.com/de-de/azure/architecture/web-apps/guides/enterprise-app-patterns/overview). Eine vollständige Beispielweb-App zur Produktionsqualität, die die Muster implementiert, ist verfügbar.

## Verwandte Inhalte

- [Einführung in Identity in ASP.NET Core](https://learn.microsoft.com/de-de/aspnet/core/security/authentication/identity?view=aspnetcore-10.0)
- [Aktivieren der QR-Codegenerierung für die TOTP-Authentifizierung](https://learn.microsoft.com/de-de/aspnet/core/security/authentication/identity-enable-qrcodes?view=aspnetcore-10.0)
- [Verwenden externer Anmeldeanbieter mit Identity in ASP.NET Core](https://learn.microsoft.com/de-de/aspnet/core/security/authentication/social/?view=aspnetcore-10.0)
- [Identity-Verwaltungslösungen für .NET-Web-Apps](https://learn.microsoft.com/de-de/aspnet/core/security/identity-management-solutions?view=aspnetcore-10.0)
