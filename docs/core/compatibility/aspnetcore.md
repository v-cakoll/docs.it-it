---
title: modifiche di interruzione di ASP.NET Core
titleSuffix: ''
description: Elenca le modifiche di rilievo in ASP.NET Core.
ms.date: 01/10/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: c54735cd53fb9cb48eb84045791ccc559fe683cd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093175"
---
# <a name="aspnet-core-breaking-changes"></a>modifiche di interruzione di ASP.NET Core

ASP.NET Core provides the web app development features used by .NET Core.

In questa pagina sono documentate le seguenti modifiche di rilievo:

- [HTTP: Le modifiche del browser SameSite influiscono sull'autenticazione](#http-browser-samesite-changes-impact-authentication)
- [Rimosse le API obsolete antiforscigiano, CORS, diagnostica, MVC e routing](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [Autenticazione: deprecazione di Google](#authentication-google-deprecated-and-replaced)
- [Autenticazione: proprietà HttpContext.Authentication rimossa](#authentication-httpcontextauthentication-property-removed)
- [Autenticazione: tipi Newtonsoft.Json sostituiti](#authentication-newtonsoftjson-types-replaced)
- [Autenticazione: firma OAuthHandler ExchangeCodeAsync modificata](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [Autorizzazione: sovraccarico AddAuthorization spostato in un assembly diversoAuthorization: AddAuthorization overload moved to different assembly](#authorization-addauthorization-overload-moved-to-different-assembly)
- [Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext.Filters](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodoAuthorization: IAuthorizationPolicyProvider implementations require new method](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [Memorizzazione nella cache: proprietà CompactOnMemoryPressure rimossaCaching: CompactOnMemoryPressure property removed](#caching-compactonmemorypressure-property-removed)
- [Memorizzazione nella cache: Microsoft.Extensions.Caching.SqlServer utilizza il nuovo pacchetto SqlClient](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [Memorizzazione nella cache: i tipi "pubternal" ResponseCaching sono stati modificati in interniCaching: ResponseCaching "pubternal" types changed to internal](#caching-responsecaching-pubternal-types-changed-to-internal)
- [Protezione dei dati: DataProtection.AzureStorage usa le nuove API di Archiviazione di AzureData Protection: DataProtection.AzureStorage uses new Azure Storage APIs](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [Hosting: l'host generico limita l'inserimento del costruttore di avvioHosting: Generic host restricts Startup constructor injection](#hosting-generic-host-restricts-startup-constructor-injection)
- [Hosting: reindirizzamento HTTPS abilitato per le app out-of-process di IISHosting: HTTPS redirection enabled for IIS out-of-process apps](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [Hosting: tipi IHostingEnvironment e IApplicationLifetime sostituiti](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilderHosting: ObjectPoolProvider removed from WebHostBuilder dependencies](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [HTTP: estensibilità DefaultHttpContext rimossa](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: HeaderNames campi modificati in static readonly](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: Modifiche all'infrastruttura del corpo della risposta](#http-response-body-infrastructure-changes)
- [HTTP: alcuni cookie SameSite valori predefiniti modificati](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: I/O sincrono disabilitato per impostazione predefinita](#http-synchronous-io-disabled-in-all-servers)
- [Identità: AddDefaultUI method overload removed](#identity-adddefaultui-method-overload-removed)
- [Identità: Modifica della versione del bootstrap dell'interfaccia utente](#identity-default-bootstrap-version-of-ui-changed)
- [Identità: SignInAsync genera un'eccezione per l'identità non autenticataIdentity: SignInAsync throws exception for unauthenticated identity](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [Identità: il costruttore SignInManager accetta il nuovo parametro](#identity-signinmanager-constructor-accepts-new-parameter)
- [Identità: l'interfaccia utente usa la funzionalità delle risorse Web staticheIdentity: UI uses static web assets feature](#identity-ui-uses-static-web-assets-feature)
- [Kestrel: adattatori di connessione rimossi](#kestrel-connection-adapters-removed)
- [Kestrel: assembly HTTPS vuoto rimosso](#kestrel-empty-https-assembly-removed)
- [Kestrel: richiesta di intestazioni rimorchio spostato in nuova collezione](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Kestrel: cambia il livello di astrazione del trasporto](#kestrel-transport-abstractions-removed-and-made-public)
- [Localizzazione: API contrassegnate come obsolete](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [Registrazione: la classe DebugLogger resa internaLogging: DebugLogger class made internal](#logging-debuglogger-class-made-internal)
- [MVC: suffisso asincrono azione controller rimosso](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult spostato in Microsoft.AspNetCore.Mvc.Core](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: strumento di precompilazione deprecato](#mvc-precompilation-tool-deprecated)
- [MVC: tipi modificati in interni](#mvc-pubternal-types-changed-to-internal)
- [MVC: shim di compatibilità API Web rimosso](#mvc-web-api-compatibility-shim-removed)
- [Razor: la compilazione di runtime spostata in un pacchettoRazor: Runtime compilation moved to a package](#razor-runtime-compilation-moved-to-a-package)
- [Stato sessione: API obsolete rimosse](#session-state-obsolete-apis-removed)
- [Framework condiviso: rimozione di assembly da Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [Framework condiviso: Microsoft.AspNetCore.All rimosso](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: HandshakeProtocol.SuccessHandshakeData sostituito](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: metodi HubConnection rimossi](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: costruttori HubConnectionContext modificati](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: modifica del nome del pacchetto client JavaScript](#signalr-javascript-client-package-name-changed)
- [SignalR: API obsolete](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SPAA: SpaServices e NodeServices contrassegnati come obsoleti](#spas-spaservices-and-nodeservices-marked-obsolete)
- [SPAAs: modifica predefinita del fallback del logger della console SpaServices e NodeServices](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [Framework di destinazione: .NET Framework non supportatoTarget framework: .NET Framework not supported](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-31"></a>ASP.NET Core 3.1

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a>ASP.NET Core 3.0

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
