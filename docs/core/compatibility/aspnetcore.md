---
title: modifiche di interruzione di ASP.NET Core
titleSuffix: ''
description: Elenca le modifiche di rilievo in ASP.NET Core.
ms.date: 03/26/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 05272032f2b93c8ae89377a20e6fdafc2ff0eb7b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345335"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="7d934-103">modifiche di interruzione di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7d934-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="7d934-104">ASP.NET Core provides the web app development features used by .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7d934-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="7d934-105">In questa pagina sono documentate le seguenti modifiche di rilievo:</span><span class="sxs-lookup"><span data-stu-id="7d934-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="7d934-106">Rimosse le API obsolete antiforscigiano, CORS, diagnostica, MVC e routing</span><span class="sxs-lookup"><span data-stu-id="7d934-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="7d934-107">Autenticazione: deprecazione di Google</span><span class="sxs-lookup"><span data-stu-id="7d934-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="7d934-108">Autenticazione: proprietà HttpContext.Authentication rimossa</span><span class="sxs-lookup"><span data-stu-id="7d934-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="7d934-109">Autenticazione: tipi Newtonsoft.Json sostituiti</span><span class="sxs-lookup"><span data-stu-id="7d934-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="7d934-110">Autenticazione: firma OAuthHandler ExchangeCodeAsync modificata</span><span class="sxs-lookup"><span data-stu-id="7d934-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="7d934-111">Autorizzazione: sovraccarico AddAuthorization spostato in un assembly diversoAuthorization: AddAuthorization overload moved to different assembly</span><span class="sxs-lookup"><span data-stu-id="7d934-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="7d934-112">Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="7d934-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="7d934-113">Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodoAuthorization: IAuthorizationPolicyProvider implementations require new method</span><span class="sxs-lookup"><span data-stu-id="7d934-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="7d934-114">Azure: rimossi i pacchetti di integrazione di Azure con prefisso MicrosoftAzure: Microsoft-prefixed Azure integration packages removed</span><span class="sxs-lookup"><span data-stu-id="7d934-114">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="7d934-115">Memorizzazione nella cache: proprietà CompactOnMemoryPressure rimossaCaching: CompactOnMemoryPressure property removed</span><span class="sxs-lookup"><span data-stu-id="7d934-115">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="7d934-116">Memorizzazione nella cache: Microsoft.Extensions.Caching.SqlServer utilizza il nuovo pacchetto SqlClient</span><span class="sxs-lookup"><span data-stu-id="7d934-116">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="7d934-117">Memorizzazione nella cache: i tipi "pubternal" ResponseCaching sono stati modificati in interniCaching: ResponseCaching "pubternal" types changed to internal</span><span class="sxs-lookup"><span data-stu-id="7d934-117">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="7d934-118">Protezione dei dati: DataProtection.AzureStorage usa le nuove API di Archiviazione di AzureData Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span><span class="sxs-lookup"><span data-stu-id="7d934-118">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="7d934-119">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span><span class="sxs-lookup"><span data-stu-id="7d934-119">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="7d934-120">Hosting: l'host generico limita l'inserimento del costruttore di avvioHosting: Generic host restricts Startup constructor injection</span><span class="sxs-lookup"><span data-stu-id="7d934-120">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="7d934-121">Hosting: reindirizzamento HTTPS abilitato per le app out-of-process di IISHosting: HTTPS redirection enabled for IIS out-of-process apps</span><span class="sxs-lookup"><span data-stu-id="7d934-121">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="7d934-122">Hosting: tipi IHostingEnvironment e IApplicationLifetime sostituiti</span><span class="sxs-lookup"><span data-stu-id="7d934-122">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="7d934-123">Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilderHosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span><span class="sxs-lookup"><span data-stu-id="7d934-123">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="7d934-124">HTTP: Le modifiche del browser SameSite influiscono sull'autenticazione</span><span class="sxs-lookup"><span data-stu-id="7d934-124">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="7d934-125">HTTP: estensibilità DefaultHttpContext rimossa</span><span class="sxs-lookup"><span data-stu-id="7d934-125">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="7d934-126">HTTP: HeaderNames campi modificati in static readonly</span><span class="sxs-lookup"><span data-stu-id="7d934-126">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="7d934-127">HTTP: Modifiche all'infrastruttura del corpo della risposta</span><span class="sxs-lookup"><span data-stu-id="7d934-127">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="7d934-128">HTTP: alcuni cookie SameSite valori predefiniti modificati</span><span class="sxs-lookup"><span data-stu-id="7d934-128">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="7d934-129">HTTP: I/O sincrono disabilitato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="7d934-129">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="7d934-130">Identità: AddDefaultUI method overload removed</span><span class="sxs-lookup"><span data-stu-id="7d934-130">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="7d934-131">Identità: Modifica della versione del bootstrap dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="7d934-131">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="7d934-132">Identità: SignInAsync genera un'eccezione per l'identità non autenticataIdentity: SignInAsync throws exception for unauthenticated identity</span><span class="sxs-lookup"><span data-stu-id="7d934-132">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="7d934-133">Identità: il costruttore SignInManager accetta il nuovo parametro</span><span class="sxs-lookup"><span data-stu-id="7d934-133">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="7d934-134">Identità: l'interfaccia utente usa la funzionalità delle risorse Web staticheIdentity: UI uses static web assets feature</span><span class="sxs-lookup"><span data-stu-id="7d934-134">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="7d934-135">Kestrel: adattatori di connessione rimossi</span><span class="sxs-lookup"><span data-stu-id="7d934-135">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="7d934-136">Kestrel: assembly HTTPS vuoto rimosso</span><span class="sxs-lookup"><span data-stu-id="7d934-136">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="7d934-137">Kestrel: richiesta di intestazioni rimorchio spostato in nuova collezione</span><span class="sxs-lookup"><span data-stu-id="7d934-137">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="7d934-138">Kestrel: cambia il livello di astrazione del trasporto</span><span class="sxs-lookup"><span data-stu-id="7d934-138">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="7d934-139">Localizzazione: API contrassegnate come obsolete</span><span class="sxs-lookup"><span data-stu-id="7d934-139">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="7d934-140">Registrazione: la classe DebugLogger resa internaLogging: DebugLogger class made internal</span><span class="sxs-lookup"><span data-stu-id="7d934-140">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="7d934-141">MVC: suffisso asincrono azione controller rimosso</span><span class="sxs-lookup"><span data-stu-id="7d934-141">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="7d934-142">MVC: JsonResult spostato in Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="7d934-142">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="7d934-143">MVC: strumento di precompilazione deprecato</span><span class="sxs-lookup"><span data-stu-id="7d934-143">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="7d934-144">MVC: tipi modificati in interni</span><span class="sxs-lookup"><span data-stu-id="7d934-144">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="7d934-145">MVC: shim di compatibilità API Web rimosso</span><span class="sxs-lookup"><span data-stu-id="7d934-145">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="7d934-146">Razor: la compilazione di runtime spostata in un pacchettoRazor: Runtime compilation moved to a package</span><span class="sxs-lookup"><span data-stu-id="7d934-146">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="7d934-147">Stato sessione: API obsolete rimosse</span><span class="sxs-lookup"><span data-stu-id="7d934-147">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="7d934-148">Framework condiviso: rimozione di assembly da Microsoft.AspNetCore.App</span><span class="sxs-lookup"><span data-stu-id="7d934-148">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="7d934-149">Framework condiviso: Microsoft.AspNetCore.All rimosso</span><span class="sxs-lookup"><span data-stu-id="7d934-149">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="7d934-150">SignalR: HandshakeProtocol.SuccessHandshakeData sostituito</span><span class="sxs-lookup"><span data-stu-id="7d934-150">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="7d934-151">SignalR: metodi HubConnection rimossi</span><span class="sxs-lookup"><span data-stu-id="7d934-151">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="7d934-152">SignalR: costruttori HubConnectionContext modificati</span><span class="sxs-lookup"><span data-stu-id="7d934-152">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="7d934-153">SignalR: modifica del nome del pacchetto client JavaScript</span><span class="sxs-lookup"><span data-stu-id="7d934-153">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="7d934-154">SignalR: protocollo Hub MessagePack spostato nel pacchetto MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="7d934-154">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="7d934-155">SignalR: API obsolete</span><span class="sxs-lookup"><span data-stu-id="7d934-155">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="7d934-156">SignalR: metodi UseSignalR e UseConnections rimossi</span><span class="sxs-lookup"><span data-stu-id="7d934-156">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="7d934-157">SPAAs: modifica predefinita del fallback del logger della console SpaServices e NodeServices</span><span class="sxs-lookup"><span data-stu-id="7d934-157">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="7d934-158">SPAA: SpaServices e NodeServices contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="7d934-158">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="7d934-159">Framework di destinazione: .NET Framework non supportatoTarget framework: .NET Framework not supported</span><span class="sxs-lookup"><span data-stu-id="7d934-159">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="7d934-160">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="7d934-160">ASP.NET Core 5.0</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="7d934-161">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7d934-161">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="7d934-162">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7d934-162">ASP.NET Core 3.0</span></span>

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
