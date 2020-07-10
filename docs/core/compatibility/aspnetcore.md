---
title: ASP.NET Core modifiche di rilievo
titleSuffix: ''
description: Elenca le modifiche di rilievo in ASP.NET Core.
ms.date: 07/08/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: ca9e615e88964e1c37e9c0b721bca8c34bf671ac
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174393"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="50eda-103">ASP.NET Core modifiche di rilievo</span><span class="sxs-lookup"><span data-stu-id="50eda-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="50eda-104">ASP.NET Core fornisce le funzionalità di sviluppo di app Web usate da .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50eda-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="50eda-105">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="50eda-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="50eda-106">Sono state rimosse le API obsolete, CORS, Diagnostics, MVC e routing</span><span class="sxs-lookup"><span data-stu-id="50eda-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="50eda-107">Autenticazione: deprecazione di Google +</span><span class="sxs-lookup"><span data-stu-id="50eda-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="50eda-108">Autenticazione: Proprietà HttpContext. Authentication rimossa</span><span class="sxs-lookup"><span data-stu-id="50eda-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="50eda-109">Autenticazione: Newtonsoft.Jssui tipi sostituiti</span><span class="sxs-lookup"><span data-stu-id="50eda-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="50eda-110">Autenticazione: OAuthHandler ExchangeCodeAsync firma modificata</span><span class="sxs-lookup"><span data-stu-id="50eda-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="50eda-111">Autorizzazione: l'overload di AddAuthorization è stato spostato in un assembly diverso</span><span class="sxs-lookup"><span data-stu-id="50eda-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="50eda-112">Autorizzazione: IAllowAnonymous rimosso da AuthorizationFilterContext. filters</span><span class="sxs-lookup"><span data-stu-id="50eda-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="50eda-113">Autorizzazione: le implementazioni di IAuthorizationPolicyProvider richiedono un nuovo metodo</span><span class="sxs-lookup"><span data-stu-id="50eda-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="50eda-114">Azure: pacchetti di integrazione di Azure con prefisso Microsoft rimossi</span><span class="sxs-lookup"><span data-stu-id="50eda-114">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="50eda-115">Blazer: spazi vuoti non significativi rimossi dai componenti in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="50eda-115">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="50eda-116">Caching: la proprietà CompactOnMemoryPressure è stata rimossa</span><span class="sxs-lookup"><span data-stu-id="50eda-116">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="50eda-117">Caching: Microsoft. Extensions. Caching. SqlServer usa il nuovo pacchetto SqlClient</span><span class="sxs-lookup"><span data-stu-id="50eda-117">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="50eda-118">Caching: i tipi di "pubternal" di ResponseCaching sono stati modificati in Internal</span><span class="sxs-lookup"><span data-stu-id="50eda-118">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="50eda-119">Protezione dei dati: dataprotection. AzureStorage usa le nuove API di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="50eda-119">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="50eda-120">Estensioni: modifiche dei riferimenti al pacchetto che interessano alcuni pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="50eda-120">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="50eda-121">Hosting: AspNetCoreModule V1 rimosso dal bundle di hosting di Windows</span><span class="sxs-lookup"><span data-stu-id="50eda-121">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="50eda-122">Hosting: l'host generico limita l'inserimento del costruttore di avvio</span><span class="sxs-lookup"><span data-stu-id="50eda-122">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="50eda-123">Hosting: reindirizzamento HTTPS abilitato per le app out-of-process di IIS</span><span class="sxs-lookup"><span data-stu-id="50eda-123">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="50eda-124">Hosting: tipi IHostingEnvironment e IApplicationLifetime sostituiti</span><span class="sxs-lookup"><span data-stu-id="50eda-124">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="50eda-125">Hosting: ObjectPoolProvider rimosso dalle dipendenze WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="50eda-125">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="50eda-126">Tipi HTTP: gheppio e IIS BadHttpRequestException contrassegnati come obsoleti e sostituiti</span><span class="sxs-lookup"><span data-stu-id="50eda-126">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="50eda-127">HTTP: browser navigava sullostesso sito modifiche che influiscano sull'autenticazione</span><span class="sxs-lookup"><span data-stu-id="50eda-127">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="50eda-128">HTTP: DefaultHttpContext estensibilità rimosso</span><span class="sxs-lookup"><span data-stu-id="50eda-128">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="50eda-129">HTTP: HeaderNames campi modificati in ReadOnly statico</span><span class="sxs-lookup"><span data-stu-id="50eda-129">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="50eda-130">HTTP: HttpClient istanze create dai codici di stato IHttpClientFactory log Integer</span><span class="sxs-lookup"><span data-stu-id="50eda-130">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="50eda-131">HTTP: modifiche dell'infrastruttura del corpo della risposta</span><span class="sxs-lookup"><span data-stu-id="50eda-131">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="50eda-132">HTTP: alcuni cookie navigava sullostesso sito valori predefiniti modificati</span><span class="sxs-lookup"><span data-stu-id="50eda-132">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="50eda-133">HTTP: i/o sincrono disabilitato per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="50eda-133">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="50eda-134">HttpSys: rinegoziazione certificato client disabilitata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="50eda-134">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="50eda-135">Identità: overload del metodo AddDefaultUI rimosso</span><span class="sxs-lookup"><span data-stu-id="50eda-135">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="50eda-136">Identità: modifica della versione bootstrap dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="50eda-136">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="50eda-137">Identity: SignInAsync genera un'eccezione per l'identità non autenticata</span><span class="sxs-lookup"><span data-stu-id="50eda-137">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="50eda-138">Identity: il costruttore SignInManager accetta il nuovo parametro</span><span class="sxs-lookup"><span data-stu-id="50eda-138">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="50eda-139">Identità: l'interfaccia utente usa la funzionalità statica di asset Web</span><span class="sxs-lookup"><span data-stu-id="50eda-139">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="50eda-140">IIS: vengono mantenute le stringhe di query del middleware UrlRewrite</span><span class="sxs-lookup"><span data-stu-id="50eda-140">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="50eda-141">Gheppio: modifiche di configurazione in fase di esecuzione rilevate per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="50eda-141">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="50eda-142">Gheppio: adapter di connessione rimossi</span><span class="sxs-lookup"><span data-stu-id="50eda-142">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="50eda-143">Gheppio: versioni del protocollo TLS supportate predefinite modificate</span><span class="sxs-lookup"><span data-stu-id="50eda-143">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="50eda-144">Gheppio: assembly HTTPS vuoto rimosso</span><span class="sxs-lookup"><span data-stu-id="50eda-144">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="50eda-145">Gheppio: HTTP/2 disabilitato su TLS in versioni incompatibili di Windows</span><span class="sxs-lookup"><span data-stu-id="50eda-145">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="50eda-146">Gheppio: intestazioni del trailer della richiesta spostate in una nuova raccolta</span><span class="sxs-lookup"><span data-stu-id="50eda-146">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="50eda-147">Gheppio: modifiche ai livelli di astrazione del trasporto</span><span class="sxs-lookup"><span data-stu-id="50eda-147">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="50eda-148">Localizzazione: API contrassegnate come obsolete</span><span class="sxs-lookup"><span data-stu-id="50eda-148">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="50eda-149">Localizzazione: API "Pubternal" rimosse</span><span class="sxs-lookup"><span data-stu-id="50eda-149">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="50eda-150">Localizzazione: classe ResourceManagerWithCultureStringLocalizer e membro dell'interfaccia WithCulture rimossi</span><span class="sxs-lookup"><span data-stu-id="50eda-150">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="50eda-151">Registrazione: classe DebugLogger creata internamente</span><span class="sxs-lookup"><span data-stu-id="50eda-151">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="50eda-152">MVC: suffisso asincrono azione controller rimosso</span><span class="sxs-lookup"><span data-stu-id="50eda-152">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="50eda-153">MVC: JsonResult spostato in Microsoft. AspNetCore. Mvc. Core</span><span class="sxs-lookup"><span data-stu-id="50eda-153">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="50eda-154">MVC: strumento di precompilazione deprecato</span><span class="sxs-lookup"><span data-stu-id="50eda-154">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="50eda-155">MVC: tipi modificati in Internal</span><span class="sxs-lookup"><span data-stu-id="50eda-155">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="50eda-156">MVC: shim di compatibilità API Web rimosso</span><span class="sxs-lookup"><span data-stu-id="50eda-156">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="50eda-157">Razor: la compilazione di runtime è stata spostata in un pacchetto</span><span class="sxs-lookup"><span data-stu-id="50eda-157">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="50eda-158">Stato sessione: API obsolete rimosse</span><span class="sxs-lookup"><span data-stu-id="50eda-158">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="50eda-159">Framework condiviso: rimozione di assembly da Microsoft. AspNetCore. app</span><span class="sxs-lookup"><span data-stu-id="50eda-159">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="50eda-160">Framework condiviso: Microsoft. AspNetCore. All rimosso</span><span class="sxs-lookup"><span data-stu-id="50eda-160">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="50eda-161">SignalR: HandshakeProtocol. SuccessHandshakeData sostituito</span><span class="sxs-lookup"><span data-stu-id="50eda-161">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="50eda-162">SignalR: Metodi HubConnection rimossi</span><span class="sxs-lookup"><span data-stu-id="50eda-162">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="50eda-163">SignalR: costruttori HubConnectionContext modificati</span><span class="sxs-lookup"><span data-stu-id="50eda-163">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="50eda-164">SignalR: modifica del nome del pacchetto client JavaScript</span><span class="sxs-lookup"><span data-stu-id="50eda-164">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="50eda-165">SignalR: il protocollo dell'hub MessagePack è stato spostato nel pacchetto MessagePack 2. x</span><span class="sxs-lookup"><span data-stu-id="50eda-165">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="50eda-166">SignalR: tipo di opzioni del protocollo dell'hub MessagePack modificato</span><span class="sxs-lookup"><span data-stu-id="50eda-166">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="50eda-167">SignalR: API obsolete</span><span class="sxs-lookup"><span data-stu-id="50eda-167">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="50eda-168">SignalR: Metodi UseSignalR e UseConnections rimossi</span><span class="sxs-lookup"><span data-stu-id="50eda-168">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="50eda-169">Spa: modifica predefinita di fallback del logger della console SpaServices e NodeServices</span><span class="sxs-lookup"><span data-stu-id="50eda-169">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="50eda-170">Spa: SpaServices e NodeServices contrassegnati come obsoleti</span><span class="sxs-lookup"><span data-stu-id="50eda-170">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="50eda-171">File statici: tipo di contenuto CSV modificato in conforme agli standard</span><span class="sxs-lookup"><span data-stu-id="50eda-171">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="50eda-172">Framework di destinazione: .NET Framework non supportato</span><span class="sxs-lookup"><span data-stu-id="50eda-172">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="50eda-173">ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="50eda-173">ASP.NET Core 5.0</span></span>

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

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="50eda-174">ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="50eda-174">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="50eda-175">ASP.NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="50eda-175">ASP.NET Core 3.0</span></span>

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
