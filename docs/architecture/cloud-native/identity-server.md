---
title: IdentityServer per le app cloud native
description: Architettura di app .NET cloud native per Azure | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 3797214685d20109b2c5dc4440ae5fc64dfddce6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73087258"
---
# <a name="identityserver-for-cloud-native-applications"></a><span data-ttu-id="85540-103">IdentityServer per applicazioni native del cloud</span><span class="sxs-lookup"><span data-stu-id="85540-103">IdentityServer for cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="85540-104">IdentityServer è un server di autenticazione open source che implementa gli standard OpenID Connect (OIDC) e OAuth 2,0 per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="85540-104">IdentityServer is an open-source authentication server that implements OpenID Connect (OIDC) and OAuth 2.0 standards for ASP.NET Core.</span></span> <span data-ttu-id="85540-105">È progettato per fornire un modo comune per autenticare le richieste a tutte le applicazioni, indipendentemente dal fatto che siano endpoint Web, nativi, per dispositivi mobili o API.</span><span class="sxs-lookup"><span data-stu-id="85540-105">It's designed to provide a common way to authenticate requests to all of your applications, whether they're web, native, mobile, or API endpoints.</span></span> <span data-ttu-id="85540-106">IdentityServer può essere utilizzato per implementare l'accesso Single Sign-on (SSO) per più applicazioni e tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="85540-106">IdentityServer can be used to implement Single Sign-On (SSO) for multiple applications and application types.</span></span> <span data-ttu-id="85540-107">Può essere usato per autenticare gli utenti effettivi tramite moduli di accesso e interfacce utente analoghe, oltre all'autenticazione basata su servizi che in genere comporta il rilascio, la verifica e il rinnovo dei token senza alcuna interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="85540-107">It can be used to authenticate actual users via sign-in forms and similar user interfaces as well as service-based authentication that typically involves token issuance, verification, and renewal without any user interface.</span></span> <span data-ttu-id="85540-108">IdentityServer è progettato per essere una soluzione personalizzabile.</span><span class="sxs-lookup"><span data-stu-id="85540-108">IdentityServer is designed to be a customizable solution.</span></span> <span data-ttu-id="85540-109">Ogni istanza viene in genere personalizzata per adattarsi a una singola organizzazione e/o a un set di esigenze delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="85540-109">Each instance is typically customized to suit an individual organization and/or set of applications' needs.</span></span>

## <a name="common-web-app-scenarios"></a><span data-ttu-id="85540-110">Scenari comuni di app Web</span><span class="sxs-lookup"><span data-stu-id="85540-110">Common web app scenarios</span></span>

<span data-ttu-id="85540-111">In genere, le applicazioni devono supportare alcuni o tutti gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="85540-111">Typically, applications need to support some or all of the following scenarios:</span></span>

- <span data-ttu-id="85540-112">Utenti umani che accedono alle applicazioni Web con un browser.</span><span class="sxs-lookup"><span data-stu-id="85540-112">Human users accessing web applications with a browser.</span></span>
- <span data-ttu-id="85540-113">Utenti umani che accedono alle API Web back-end dalle app basate su browser.</span><span class="sxs-lookup"><span data-stu-id="85540-113">Human users accessing back-end Web APIs from browser-based apps.</span></span>
- <span data-ttu-id="85540-114">Utenti umani nei client mobili/nativi che accedono alle API Web back-end.</span><span class="sxs-lookup"><span data-stu-id="85540-114">Human users on mobile/native clients accessing back-end Web APIs.</span></span>
- <span data-ttu-id="85540-115">Altre applicazioni che accedono alle API Web back-end (senza interfaccia utente o utente attivo).</span><span class="sxs-lookup"><span data-stu-id="85540-115">Other applications accessing back-end Web APIs (without an active user or user interface).</span></span>
- <span data-ttu-id="85540-116">Qualsiasi applicazione potrebbe dover interagire con altre API Web, usando la propria identità o delegando l'identità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="85540-116">Any application may need to interact with other Web APIs, using its own identity or delegating to the user's identity.</span></span>

<span data-ttu-id="85540-117">![tipi di applicazione e scenari](./media/application-types.png)
**figura 8-1**.</span><span class="sxs-lookup"><span data-stu-id="85540-117">![Application types and scenarios](./media/application-types.png)
**Figure 8-1**.</span></span> <span data-ttu-id="85540-118">Tipi di applicazioni e scenari.</span><span class="sxs-lookup"><span data-stu-id="85540-118">Application types and scenarios.</span></span>

<span data-ttu-id="85540-119">In ognuno di questi scenari, la funzionalità esposta deve essere protetta da un uso non autorizzato.</span><span class="sxs-lookup"><span data-stu-id="85540-119">In each of these scenarios, the exposed functionality needs to be secured against unauthorized use.</span></span> <span data-ttu-id="85540-120">Come minimo, questa operazione richiede in genere l'autenticazione dell'utente o dell'entità che effettua una richiesta di una risorsa.</span><span class="sxs-lookup"><span data-stu-id="85540-120">At a minimum, this typically requires authenticating the user or principal making a request for a resource.</span></span> <span data-ttu-id="85540-121">Questa autenticazione può usare uno dei diversi protocolli comuni, ad esempio SAML2p, WS-Fed o OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="85540-121">This authentication may use one of several common protocols such as SAML2p, WS-Fed, or OpenID Connect.</span></span> <span data-ttu-id="85540-122">La comunicazione con le API USA in genere il protocollo OAuth2 e il relativo supporto per i token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="85540-122">Communicating with APIs typically uses the OAuth2 protocol and its support for security tokens.</span></span> <span data-ttu-id="85540-123">La separazione di queste problematiche cruciali in materia di sicurezza e dei relativi dettagli di implementazione dalle applicazioni stesse garantisce coerenza e miglioramento della sicurezza e della gestibilità.</span><span class="sxs-lookup"><span data-stu-id="85540-123">Separating these critical cross-cutting security concerns and their implementation details from the applications themselves ensures consistency and improves security and maintainability.</span></span> <span data-ttu-id="85540-124">L'outsourcing di queste preoccupazioni a un prodotto dedicato, ad esempio IdentityServer, consente a ogni applicazione di risolvere questi problemi.</span><span class="sxs-lookup"><span data-stu-id="85540-124">Outsourcing these concerns to a dedicated product like IdentityServer helps the requirement for every application to solve these problems itself.</span></span>

<span data-ttu-id="85540-125">IdentityServer fornisce il middleware eseguito all'interno di un'applicazione ASP.NET Core e aggiunge il supporto per OpenID Connect e OAuth2 (vedere le [specifiche supportate](http://docs.identityserver.io/en/latest/intro/specs.html)).</span><span class="sxs-lookup"><span data-stu-id="85540-125">IdentityServer provides middleware that runs within an ASP.NET Core application and adds support for OpenID Connect and OAuth2 (see [supported specifications](http://docs.identityserver.io/en/latest/intro/specs.html)).</span></span> <span data-ttu-id="85540-126">Le organizzazioni creeranno una propria app ASP.NET Core usando il middleware IdentityServer per agire come servizio token di sicurezza per tutti i protocolli di sicurezza basati su token.</span><span class="sxs-lookup"><span data-stu-id="85540-126">Organizations would create their own ASP.NET Core app using IdentityServer middleware to act as the STS for all of their token-based security protocols.</span></span> <span data-ttu-id="85540-127">Il middleware IdentityServer espone gli endpoint per supportare le funzionalità standard, tra cui:</span><span class="sxs-lookup"><span data-stu-id="85540-127">The IdentityServer middleware exposes endpoints to support standard functionality, including:</span></span>

- <span data-ttu-id="85540-128">Autorizza (autenticazione dell'utente finale)</span><span class="sxs-lookup"><span data-stu-id="85540-128">Authorize (authenticate the end user)</span></span>
- <span data-ttu-id="85540-129">Token (richiedere un token a livello di codice)</span><span class="sxs-lookup"><span data-stu-id="85540-129">Token (request a token programmatically)</span></span>
- <span data-ttu-id="85540-130">Individuazione (metadati relativi al server)</span><span class="sxs-lookup"><span data-stu-id="85540-130">Discovery (metadata about the server)</span></span>
- <span data-ttu-id="85540-131">Informazioni utente (ottenere informazioni utente con un token di accesso valido)</span><span class="sxs-lookup"><span data-stu-id="85540-131">User Info (get user information with a valid access token)</span></span>
- <span data-ttu-id="85540-132">Autorizzazione del dispositivo (usata per avviare l'autorizzazione del flusso del dispositivo)</span><span class="sxs-lookup"><span data-stu-id="85540-132">Device Authorization (used to start device flow authorization)</span></span>
- <span data-ttu-id="85540-133">Introspezione (convalida token)</span><span class="sxs-lookup"><span data-stu-id="85540-133">Introspection (token validation)</span></span>
- <span data-ttu-id="85540-134">Revoca (revoca dei token)</span><span class="sxs-lookup"><span data-stu-id="85540-134">Revocation (token revocation)</span></span>
- <span data-ttu-id="85540-135">Termina sessione (attiva Single Sign-out in tutte le app)</span><span class="sxs-lookup"><span data-stu-id="85540-135">End Session (trigger single sign-out across all apps)</span></span>

## <a name="getting-started"></a><span data-ttu-id="85540-136">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="85540-136">Getting started</span></span>

<span data-ttu-id="85540-137">IdentityServer4 è open source e gratuito.</span><span class="sxs-lookup"><span data-stu-id="85540-137">IdentityServer4 is open-source and free to use.</span></span> <span data-ttu-id="85540-138">È possibile aggiungerlo alle applicazioni usando i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="85540-138">You can add it to your applications using its NuGet packages.</span></span> <span data-ttu-id="85540-139">Il pacchetto principale è [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) che è stato scaricato più di 4 milioni volte.</span><span class="sxs-lookup"><span data-stu-id="85540-139">The main package is [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) that has been downloaded over four million times.</span></span> <span data-ttu-id="85540-140">Il pacchetto di base non include alcun codice dell'interfaccia utente e supporta solo la configurazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="85540-140">The base package doesn't include any user interface code and only supports in memory configuration.</span></span> <span data-ttu-id="85540-141">Per usarlo con un database, è necessario anche un provider di dati come [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) che usa Entity Framework Core per archiviare i dati di configurazione e operativi per IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="85540-141">To use it with a database, you'll also want a data provider like [IdentityServer4.EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) that uses Entity Framework Core to store configuration and operational data for IdentityServer.</span></span> <span data-ttu-id="85540-142">Per l'interfaccia utente, è possibile copiare i file dal [repository dell'interfaccia utente di avvio rapido](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) nell'applicazione ASP.NET Core MVC per aggiungere il supporto per l'accesso e la disconnessione usando il middleware IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="85540-142">For user interface, you can copy files from the [Quickstart UI repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) into your ASP.NET Core MVC application to add support for sign in and sign out using IdentityServer middleware.</span></span>

## <a name="configuration"></a><span data-ttu-id="85540-143">Configurazione</span><span class="sxs-lookup"><span data-stu-id="85540-143">Configuration</span></span>

<span data-ttu-id="85540-144">IdentityServer supporta diversi tipi di protocolli e provider di autenticazione basata su social network che possono essere configurati come parte di ogni installazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="85540-144">IdentityServer supports different kinds of protocols and social authentication providers that can be configured as part of each custom installation.</span></span> <span data-ttu-id="85540-145">Questa operazione viene in genere eseguita nella classe `Startup` dell'applicazione ASP.NET Core nel metodo `ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="85540-145">This is typically done in the ASP.NET Core application's `Startup` class in the `ConfigureServices` method.</span></span> <span data-ttu-id="85540-146">La configurazione prevede la specifica dei protocolli supportati e i percorsi dei server e degli endpoint che verranno usati.</span><span class="sxs-lookup"><span data-stu-id="85540-146">The configuration involves specifying the supported protocols and the paths to the servers and endpoints that will be used.</span></span> <span data-ttu-id="85540-147">La figura 8-2 illustra una configurazione di esempio ricavata dal progetto dell'interfaccia utente di avvio rapido di IdentityServer4:</span><span class="sxs-lookup"><span data-stu-id="85540-147">Figure 8-2 shows an example configuration taken from the IdentityServer4 Quickstart UI project:</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<inser here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

<span data-ttu-id="85540-148">**Figura 8-2**.</span><span class="sxs-lookup"><span data-stu-id="85540-148">**Figure 8-2**.</span></span> <span data-ttu-id="85540-149">Configurazione di IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="85540-149">Configuring IdentityServer.</span></span>

<span data-ttu-id="85540-150">IdentityServer ospita anche un sito demo pubblico che può essere usato per testare diversi protocolli e configurazioni.</span><span class="sxs-lookup"><span data-stu-id="85540-150">IdentityServer also hosts a public demo site that can be used to test various protocols and configurations.</span></span> <span data-ttu-id="85540-151">Si trova in [https://demo.identityserver.io/](https://demo.identityserver.io/) e include informazioni su come configurarne il comportamento in base al `client_id` fornito.</span><span class="sxs-lookup"><span data-stu-id="85540-151">It's located at [https://demo.identityserver.io/](https://demo.identityserver.io/) and includes information on how to configure its behavior based on the `client_id` provided to it.</span></span>

## <a name="javascript-clients"></a><span data-ttu-id="85540-152">Client JavaScript</span><span class="sxs-lookup"><span data-stu-id="85540-152">JavaScript clients</span></span>

<span data-ttu-id="85540-153">Molte applicazioni native del Cloud sfruttano le API lato server e le applicazioni a pagina singola rich client (Spa) sul front-end.</span><span class="sxs-lookup"><span data-stu-id="85540-153">Many cloud-native applications leverage server-side APIs and rich client single page applications (SPAs) on the front end.</span></span> <span data-ttu-id="85540-154">IdentityServer fornisce un [client JavaScript](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html) (`oidc-client.js`) tramite NPM che è possibile aggiungere alle Spa per consentire loro di usare IdentityServer per l'accesso, la disconnessione e l'autenticazione basata su token di API Web.</span><span class="sxs-lookup"><span data-stu-id="85540-154">IdentityServer ships a [JavaScript client](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html) (`oidc-client.js`) via NPM that can be added to SPAs to enable them to use IdentityServer for sign in, sign out, and token-based authentication of web APIs.</span></span>

## <a name="references"></a><span data-ttu-id="85540-155">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="85540-155">References</span></span>

- [<span data-ttu-id="85540-156">Documentazione di IdentityServer</span><span class="sxs-lookup"><span data-stu-id="85540-156">IdentityServer documentation</span></span>](http://docs.identityserver.io/en/latest/)
- [<span data-ttu-id="85540-157">Tipi di applicazioni</span><span class="sxs-lookup"><span data-stu-id="85540-157">Application types</span></span>](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [<span data-ttu-id="85540-158">Client OIDC JavaScript</span><span class="sxs-lookup"><span data-stu-id="85540-158">JavaScript OIDC client</span></span>](http://docs.identityserver.io/en/latest/quickstarts/6_javascript_client.html)

>[!div class="step-by-step"]
><span data-ttu-id="85540-159">[Precedente](azure-active-directory.md)
>[Successivo](security.md)</span><span class="sxs-lookup"><span data-stu-id="85540-159">[Previous](azure-active-directory.md)
[Next](security.md)</span></span>
