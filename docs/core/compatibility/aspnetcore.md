---
title: ASP.NET Core modifiche di rilievo
titleSuffix: ''
description: Elenca le modifiche di rilievo in ASP.NET Core.
ms.date: 07/14/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: b73492e0c2f60c2b214984d3987de1e9e6530847
ms.sourcegitcommit: d4f7ba08f2a45a9dbef53be597eed6d4a9410f29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "86402004"
---
# <a name="aspnet-core-breaking-changes"></a>ASP.NET Core modifiche di rilievo

ASP.NET Core fornisce le funzionalità di sviluppo di app Web usate da .NET Core.

In questa pagina sono documentate le modifiche di rilievo seguenti:

- [Sono state rimosse le API obsolete, CORS, Diagnostics, MVC e routing](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [Autenticazione: deprecazione di Google +](#authentication-google-deprecated-and-replaced)
- [Autenticazione: Proprietà HttpContext. Authentication rimossa](#authentication-httpcontextauthentication-property-removed)
- [Autenticazione: Newtonsoft.Jssui tipi sostituiti](#authentication-newtonsoftjson-types-replaced)
- [Autenticazione: OAuthHandler ExchangeCodeAsync firma modificata](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [Autorizzazione: l'overload di AddAuthorization è stato spostato in un assembly diverso](#authorization-addauthorization-overload-moved-to-different-assembly)
- [Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext. filters](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodo](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [Azure: pacchetti di integrazione di Azure con prefisso Microsoft rimossi](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [Blazer: spazi vuoti non significativi rimossi dai componenti in fase di compilazione](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [Caching: la proprietà CompactOnMemoryPressure è stata rimossa](#caching-compactonmemorypressure-property-removed)
- [Caching: Microsoft. Extensions. Caching. SqlServer usa il nuovo pacchetto SqlClient](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [Caching: i tipi di "pubternal" di ResponseCaching sono stati modificati in Internal](#caching-responsecaching-pubternal-types-changed-to-internal)
- [Protezione dei dati: dataprotection. AzureStorage usa le nuove API di archiviazione di Azure](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [Estensioni: modifiche dei riferimenti al pacchetto che interessano alcuni pacchetti NuGet](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [Hosting: AspNetCoreModule V1 rimosso dal bundle di hosting di Windows](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [Hosting: l'host generico limita l'inserimento del costruttore di avvio](#hosting-generic-host-restricts-startup-constructor-injection)
- [Hosting: reindirizzamento HTTPS abilitato per le app out-of-process di IIS](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [Hosting: tipi IHostingEnvironment e IApplicationLifetime sostituiti](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilder](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [Tipi HTTP: gheppio e IIS BadHttpRequestException contrassegnati come obsoleti e sostituiti](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [HTTP: browser navigava sullostesso sito modifiche che influiscano sull'autenticazione](#http-browser-samesite-changes-impact-authentication)
- [HTTP: DefaultHttpContext estensibilità rimosso](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: HeaderNames campi modificati in ReadOnly statico](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: HttpClient istanze create dai codici di stato IHttpClientFactory log Integer](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [HTTP: modifiche dell'infrastruttura del corpo della risposta](#http-response-body-infrastructure-changes)
- [HTTP: alcuni cookie navigava sullostesso sito valori predefiniti modificati](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: i/o sincrono disabilitato per impostazione predefinita](#http-synchronous-io-disabled-in-all-servers)
- [HttpSys: rinegoziazione certificato client disabilitata per impostazione predefinita](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [Identità: overload del metodo AddDefaultUI rimosso](#identity-adddefaultui-method-overload-removed)
- [Identità: modifica della versione bootstrap dell'interfaccia utente](#identity-default-bootstrap-version-of-ui-changed)
- [Identity: SignInAsync genera un'eccezione per l'identità non autenticata](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [Identity: il costruttore SignInManager accetta il nuovo parametro](#identity-signinmanager-constructor-accepts-new-parameter)
- [Identità: l'interfaccia utente usa la funzionalità statica di asset Web](#identity-ui-uses-static-web-assets-feature)
- [IIS: vengono mantenute le stringhe di query del middleware UrlRewrite](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [Gheppio: modifiche di configurazione in fase di esecuzione rilevate per impostazione predefinita](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [Gheppio: adapter di connessione rimossi](#kestrel-connection-adapters-removed)
- [Gheppio: versioni del protocollo TLS supportate predefinite modificate](#kestrel-default-supported-tls-protocol-versions-changed)
- [Gheppio: assembly HTTPS vuoto rimosso](#kestrel-empty-https-assembly-removed)
- [Gheppio: HTTP/2 disabilitato su TLS in versioni incompatibili di Windows](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [Gheppio: intestazioni del trailer della richiesta spostate in una nuova raccolta](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Gheppio: modifiche ai livelli di astrazione del trasporto](#kestrel-transport-abstractions-removed-and-made-public)
- [Localizzazione: API contrassegnate come obsolete](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [Localizzazione: API "Pubternal" rimosse](#localization-pubternal-apis-removed)
- [Localizzazione: Costruttore obsoleto rimosso nel middleware di localizzazione della richiesta](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [Localizzazione: classe ResourceManagerWithCultureStringLocalizer e membro dell'interfaccia WithCulture rimossi](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [Registrazione: classe DebugLogger creata internamente](#logging-debuglogger-class-made-internal)
- [MVC: suffisso asincrono azione controller rimosso](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult spostato in Microsoft. AspNetCore. Mvc. Core](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: strumento di precompilazione deprecato](#mvc-precompilation-tool-deprecated)
- [MVC: tipi modificati in Internal](#mvc-pubternal-types-changed-to-internal)
- [MVC: shim di compatibilità API Web rimosso](#mvc-web-api-compatibility-shim-removed)
- [Razor: la compilazione di runtime è stata spostata in un pacchetto](#razor-runtime-compilation-moved-to-a-package)
- [Sicurezza: codifica del nome del cookie rimossa](#security-cookie-name-encoding-removed)
- [Sicurezza: IdentityModel versioni del pacchetto NuGet aggiornate](#security-identitymodel-nuget-package-versions-updated)
- [Stato sessione: API obsolete rimosse](#session-state-obsolete-apis-removed)
- [Framework condiviso: rimozione di assembly da Microsoft. AspNetCore. app](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [Framework condiviso: Microsoft. AspNetCore. All rimosso](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: HandshakeProtocol. SuccessHandshakeData sostituito](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: Metodi HubConnection rimossi](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: costruttori HubConnectionContext modificati](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: modifica del nome del pacchetto client JavaScript](#signalr-javascript-client-package-name-changed)
- [SignalR: il protocollo dell'hub MessagePack è stato spostato nel pacchetto MessagePack 2. x](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [SignalR: tipo di opzioni del protocollo dell'hub MessagePack modificato](#signalr-messagepack-hub-protocol-options-type-changed)
- [SignalR: API obsolete](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SignalR: Metodi UseSignalR e UseConnections rimossi](#signalr-usesignalr-and-useconnections-methods-removed)
- [Spa: modifica predefinita di fallback del logger della console SpaServices e NodeServices](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [Spa: SpaServices e NodeServices contrassegnati come obsoleti](#spas-spaservices-and-nodeservices-marked-obsolete)
- [File statici: tipo di contenuto CSV modificato in conforme agli standard](#static-files-csv-content-type-changed-to-standards-compliant)
- [Framework di destinazione: .NET Framework non supportato](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a>ASP.NET Core 5,0

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[HttpSys: Client certificate renegotiation disabled by default](~/includes/core-changes/aspnetcore/5.0/httpsys-client-certificate-renegotiation-disabled-by-default.md)]

***

[!INCLUDE[IIS: UrlRewrite middleware query strings are preserved](~/includes/core-changes/aspnetcore/5.0/iis-urlrewrite-middleware-query-strings-are-preserved.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions](~/includes/core-changes/aspnetcore/5.0/kestrel-disables-http2-over-tls.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[Security: Cookie name encoding removed](~/includes/core-changes/aspnetcore/5.0/security-cookie-name-encoding-removed.md)]

***

[!INCLUDE[Security: IdentityModel NuGet package versions updated](~/includes/core-changes/aspnetcore/5.0/security-identitymodel-nuget-package-versions-updated.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a>ASP.NET Core 3,1

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a>ASP.NET Core 3,0

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

***

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

***

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

***

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

***

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

***

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

***

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

***

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

***

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

***

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

***

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

***

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

***

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

***

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

***

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

***

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

***

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

***

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

***

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

***

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

***

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

***

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

***

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

***

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

***

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

***

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

***

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

***

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

***

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

***

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

***

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

***

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

***

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

***

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

***

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

***

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

***

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

***

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

***

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

***

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

***

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

***

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

***

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

***

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

***

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

***

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

***

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

***

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

***
