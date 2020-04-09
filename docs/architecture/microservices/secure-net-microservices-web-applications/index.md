---
title: Protezione di microservizi e applicazioni Web .NET
description: Protezione di microservizi e applicazioni Web .NET - Informazioni sulle opzioni di autenticazione per le applicazioni Web ASP.NET Core.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 56ebd95c8a24c7c8d30d3c6acef6650cb63383c6
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988115"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="cb03d-103">Proteggere i microservizi e le applicazioni Web .NET</span><span class="sxs-lookup"><span data-stu-id="cb03d-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="cb03d-104">La protezione dei microservizi e delle applicazioni Web è un argomento molto vasto e con un gran numero di aspetti diversi. Questa sezione si concentra sull'autenticazione, l'autorizzazione e i segreti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="cb03d-105">Implementare l'autenticazione in microservizi e applicazioni Web .NET</span><span class="sxs-lookup"><span data-stu-id="cb03d-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="cb03d-106">In molti casi è necessario che le risorse e le API pubblicate da un servizio siano limitate a determinati utenti o client attendibili.</span><span class="sxs-lookup"><span data-stu-id="cb03d-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="cb03d-107">Il primo passaggio per prendere questo tipo di decisioni sull'attendibilità a livello di API è l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="cb03d-108">L'autenticazione è il processo di verifica affidabile dell'identità di un utente.</span><span class="sxs-lookup"><span data-stu-id="cb03d-108">Authentication is the process of reliably verify a user's identity.</span></span>

<span data-ttu-id="cb03d-109">In scenari di microservizi, l'autenticazione viene in genere gestita centralmente.</span><span class="sxs-lookup"><span data-stu-id="cb03d-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="cb03d-110">Se si usa un gateway API il gateway è un ottimo strumento per l'autenticazione, come illustrato nella figura 9-1.</span><span class="sxs-lookup"><span data-stu-id="cb03d-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="cb03d-111">Se si usa questo approccio, assicurarsi che i singoli microservizi non possano essere raggiunti direttamente (senza il gateway API), a meno che non sia presente un sistema di sicurezza aggiuntivo per autenticare i messaggi, indipendentemente dal fatto che provengano dal gateway.</span><span class="sxs-lookup"><span data-stu-id="cb03d-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![Diagramma che mostra come l'app client per dispositivi mobili interagisce con il back-end.](./media/index/api-gateway-centralized-authentication.png)

<span data-ttu-id="cb03d-113">**Figura 9-1**.</span><span class="sxs-lookup"><span data-stu-id="cb03d-113">**Figure 9-1**.</span></span> <span data-ttu-id="cb03d-114">Autenticazione centralizzata con un gateway API</span><span class="sxs-lookup"><span data-stu-id="cb03d-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="cb03d-115">Quando il gateway API centralizza l'autenticazione, aggiunge le informazioni utente al momento dell'inoltro delle richieste ai microservizi.</span><span class="sxs-lookup"><span data-stu-id="cb03d-115">When the API Gateway centralizes authentication, it adds user information when forwarding requests to the microservices.</span></span> <span data-ttu-id="cb03d-116">Se è possibile accedere direttamente ai servizi, per autenticare gli utenti è possibile usare un servizio di autenticazione come Azure Active Directory o un microservizio di autenticazione dedicato che svolge la funzione di servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cb03d-116">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="cb03d-117">Le decisioni sull'attendibilità vengono condivise tra i servizi tramite cookie o token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cb03d-117">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="cb03d-118">Questi token possono essere condivisi tra ASP.NET applicazioni Core, se necessario, implementando [la condivisione](/aspnet/core/security/cookie-sharing)di cookie. Questo modello è illustrato nella Figura 9-2.</span><span class="sxs-lookup"><span data-stu-id="cb03d-118">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![Diagramma che mostra l'autenticazione tramite microservizi back-end.](./media/index/identity-microservice-authentication.png)

<span data-ttu-id="cb03d-120">**Figura 9-2**.</span><span class="sxs-lookup"><span data-stu-id="cb03d-120">**Figure 9-2**.</span></span> <span data-ttu-id="cb03d-121">Autenticazione mediante microservizio di identità; l'attendibilità è condivisa con un token di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cb03d-121">Authentication by identity microservice; trust is shared using an authorization token</span></span>

<span data-ttu-id="cb03d-122">Quando l'accesso ai i microservizi è diretto, l'attendibilità, che include autenticazione e autorizzazione, viene gestita da un token di sicurezza emesso da un microservizio dedicato, condiviso tra i microservizi.</span><span class="sxs-lookup"><span data-stu-id="cb03d-122">When microservices are accessed directly, trust, that includes authentication and authorization, is handled by a security token issued by a dedicated microservice, shared between microservices.</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="cb03d-123">Autenticazione tramite ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="cb03d-123">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="cb03d-124">Il meccanismo principale in ASP.NET Core per identificare gli utenti di un'applicazione è il sistema di appartenenza [ASP.NET Core Identity.The](/aspnet/core/security/authentication/identity) primary mechanism in ASP.NET Core for identifying an application's users is the ASP.NET Core Identity membership system.</span><span class="sxs-lookup"><span data-stu-id="cb03d-124">The primary mechanism in ASP.NET Core for identifying an application's users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="cb03d-125">che archivia le informazioni sugli utenti (inclusi dati di accesso, ruoli e attestazioni) in un archivio dati configurato dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="cb03d-125">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="cb03d-126">In genere l'archivio dati di ASP.NET Core Identity è un archivio Entity Framework incluso nel pacchetto `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span><span class="sxs-lookup"><span data-stu-id="cb03d-126">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="cb03d-127">È tuttavia possibile usare archivi personalizzati o altri pacchetti di terze parti per archiviare le informazioni sull'identità in Archiviazione tabelle di Azure, in CosmosDB o in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="cb03d-127">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

> [!TIP]
> <span data-ttu-id="cb03d-128">ASP.NET Core 2.1 e versioni successive fornisce [ASP.NET core Identity](/aspnet/core/security/authentication/identity) come libreria di classi [Razor](/aspnet/core/razor-pages/ui-class), pertanto non verrà visualizzato gran parte del codice necessario nel progetto, come nel caso delle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="cb03d-128">ASP.NET Core 2.1 and later provides [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) as a [Razor Class Library](/aspnet/core/razor-pages/ui-class), so you won't see much of the necessary code in your project, as was the case for previous versions.</span></span> <span data-ttu-id="cb03d-129">Per informazioni dettagliate su come personalizzare il codice Identity in base alle proprie esigenze, vedere [Scaffold Identity in ASP.NET Core projects](/aspnet/core/security/authentication/scaffold-identity).</span><span class="sxs-lookup"><span data-stu-id="cb03d-129">For details on how to customize the Identity code to suit your needs, see [Scaffold Identity in ASP.NET Core projects](/aspnet/core/security/authentication/scaffold-identity).</span></span>

<span data-ttu-id="cb03d-130">Il codice seguente è tratto dal modello di progetto MVC 3.1 dell'applicazione Web di base ASP.NET con l'autenticazione dell'account utente singolo selezionata.</span><span class="sxs-lookup"><span data-stu-id="cb03d-130">The following code is taken from the ASP.NET Core Web Application MVC 3.1 project template with individual user account authentication selected.</span></span> <span data-ttu-id="cb03d-131">Viene illustrato come configurare ASP.NET identità `Startup.ConfigureServices` di base utilizzando Entity Framework Core nel metodo.</span><span class="sxs-lookup"><span data-stu-id="cb03d-131">It shows how to configure ASP.NET Core Identity using Entity Framework Core in the `Startup.ConfigureServices` method.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
    //...
}
```

<span data-ttu-id="cb03d-132">Dopo aver configurato ASP.NET Core Identity, `app.UseAuthentication()` è `endpoints.MapRazorPages()` possibile abilitarla aggiungendo e come `Startup.Configure` illustrato nel codice seguente nel metodo del servizio:</span><span class="sxs-lookup"><span data-stu-id="cb03d-132">Once ASP.NET Core Identity is configured, you enable it by adding the `app.UseAuthentication()` and `endpoints.MapRazorPages()` as shown in the following code in the service's `Startup.Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    //...
    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
    //...
}
```

> [!IMPORTANT]
> <span data-ttu-id="cb03d-133">Le righe nel codice precedente **DEVONO ESSERE IN ORDINE SHOWN** affinché Identity funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="cb03d-133">The lines in the preceeding code **MUST BE IN THE ORDER SHOWN** for Identity to work correctly.</span></span>

<span data-ttu-id="cb03d-134">L'uso di ASP.NET Core Identity consente diversi scenari:</span><span class="sxs-lookup"><span data-stu-id="cb03d-134">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="cb03d-135">Creazione di nuove informazioni utente usando il tipo UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="cb03d-135">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="cb03d-136">Autenticazione degli utenti tramite il tipo SignInManager.</span><span class="sxs-lookup"><span data-stu-id="cb03d-136">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="cb03d-137">È possibile `signInManager.SignInAsync` utilizzare per accedere `signInManager.PasswordSignInAsync` direttamente o per confermare che la password dell'utente sia corretta e quindi eseguirla.</span><span class="sxs-lookup"><span data-stu-id="cb03d-137">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user's password is correct and then sign them in.</span></span>

- <span data-ttu-id="cb03d-138">Identificare un utente in base alle informazioni archiviate in un cookie (che viene letto da ASP.NET middleware Core Identity) in modo che le richieste successive provenienti da un browser includano l'identità e le attestazioni di un utente connesso.</span><span class="sxs-lookup"><span data-stu-id="cb03d-138">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user's identity and claims.</span></span>

<span data-ttu-id="cb03d-139">ASP.NET Core Identity supporta inoltre l'[autenticazione a due fattori](/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="cb03d-139">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="cb03d-140">Per scenari di autenticazione che usano dell'archivio dati degli utenti locale e vengono salvano in modo permanente l'identità tra le richieste tramite dei cookie (come avviene per le applicazioni web MVC), ASP.NET Identity Core è una soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="cb03d-140">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="cb03d-141">Eseguire l'autenticazione tramite provider esterni</span><span class="sxs-lookup"><span data-stu-id="cb03d-141">Authenticate with external providers</span></span>

<span data-ttu-id="cb03d-142">ASP.NET Core supporta anche l'uso di [provider di autenticazione esterni](/aspnet/core/security/authentication/social/) per consentire agli utenti di accedere tramite flussi di [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="cb03d-142">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="cb03d-143">Ciò significa che gli utenti possono accedere con processi di autenticazione esistenti di provider come Microsoft, Google, Facebook o Twitter e associare queste identità a un'identità di ASP.NET Core nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-143">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="cb03d-144">Per utilizzare l'autenticazione esterna, oltre a includere `app.UseAuthentication()` il middleware di autenticazione come `Startup` indicato in precedenza, utilizzando il metodo, è necessario registrare anche il provider esterno come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cb03d-144">To use external authentication, besides including the authentication middleware as mentioned before, using the `app.UseAuthentication()` method, you also have to register the external provider in `Startup` as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddAuthentication()
        .AddMicrosoftAccount(microsoftOptions =>
        {
            microsoftOptions.ClientId = Configuration["Authentication:Microsoft:ClientId"];
            microsoftOptions.ClientSecret = Configuration["Authentication:Microsoft:ClientSecret"];
        })
        .AddGoogle(googleOptions => { ... })
        .AddTwitter(twitterOptions => { ... })
        .AddFacebook(facebookOptions => { ... });
    //...
}
```

<span data-ttu-id="cb03d-145">Alcuni provider di autenticazione esterni comuni e i pacchetti NuGet associati sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="cb03d-145">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="cb03d-146">**Provider**</span><span class="sxs-lookup"><span data-stu-id="cb03d-146">**Provider**</span></span>  | <span data-ttu-id="cb03d-147">**Pacchetto**</span><span class="sxs-lookup"><span data-stu-id="cb03d-147">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="cb03d-148">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="cb03d-148">**Microsoft**</span></span> | <span data-ttu-id="cb03d-149">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="cb03d-149">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="cb03d-150">**Google**</span><span class="sxs-lookup"><span data-stu-id="cb03d-150">**Google**</span></span>    | <span data-ttu-id="cb03d-151">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="cb03d-151">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="cb03d-152">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="cb03d-152">**Facebook**</span></span>  | <span data-ttu-id="cb03d-153">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="cb03d-153">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="cb03d-154">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="cb03d-154">**Twitter**</span></span>   | <span data-ttu-id="cb03d-155">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="cb03d-155">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="cb03d-156">In tutti i casi, è necessario completare una procedura di registrazione della domanda di lavoro dipendente dal fornitore e che in genere comporta:</span><span class="sxs-lookup"><span data-stu-id="cb03d-156">In all cases, you must complete an application registration procedure that is vendor dependent and that usually involves:</span></span>

1. <span data-ttu-id="cb03d-157">Recupero di un ID applicazione client.</span><span class="sxs-lookup"><span data-stu-id="cb03d-157">Getting a Client Application ID.</span></span>
2. <span data-ttu-id="cb03d-158">Recupero di un segreto dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="cb03d-158">Getting a Client Application Secret.</span></span>
3. <span data-ttu-id="cb03d-159">Configurazione di un URL di reindirizzamento gestito dal middleware di autorizzazione e dal provider registrato</span><span class="sxs-lookup"><span data-stu-id="cb03d-159">Configuring an redirection URL, that's handled by the authorization middleware and the registered provider</span></span>
4. <span data-ttu-id="cb03d-160">Facoltativamente, la configurazione di un URL di disconnessione per gestire correttamente la disconnessione in uno scenario Single Sign-On (SSO).</span><span class="sxs-lookup"><span data-stu-id="cb03d-160">Optionally, configuring a sign-out URL to properly handle sign out in a Single Sign On (SSO) scenario.</span></span>

<span data-ttu-id="cb03d-161">Per informazioni dettagliate sulla configurazione dell'app per un provider esterno, vedere [Autenticazione del provider esterno nella documentazione di ASP.NET Core](/aspnet/core/security/authentication/social/)).</span><span class="sxs-lookup"><span data-stu-id="cb03d-161">For details on configuring your app for an external provider, see the [External provider authentication in the ASP.NET Core documentation](/aspnet/core/security/authentication/social/)).</span></span>

>[!TIP]
><span data-ttu-id="cb03d-162">Tutti i dettagli sono gestiti dal middleware di autorizzazione e servizi menzionati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="cb03d-162">All details are handled by the authorization middleware and services previously mentioned.</span></span> <span data-ttu-id="cb03d-163">Quindi, è sufficiente scegliere l'opzione di autenticazione **dell'account utente individuale** quando si crea il progetto di applicazione web codice ASP.NET in Visual Studio, come illustrato nella figura 9-3, oltre a registrare i provider di autenticazione menzionati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="cb03d-163">So, you just have to choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, as shown in Figure 9-3, besides registering the authentication providers previously mentioned.</span></span>

![Screenshot della finestra di dialogo Nuova ASP.NET applicazione Web principale.](./media/index/select-individual-user-account-authentication-option.png)

<span data-ttu-id="cb03d-165">**Figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="cb03d-165">**Figure 9-3**.</span></span> <span data-ttu-id="cb03d-166">Selezione dell'opzione Account utente singoli, per l'utilizzo dell'autenticazione esterna, durante la creazione di un progetto di applicazione Web in Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="cb03d-166">Selecting the Individual User Accounts option, for using external authentication, when creating a web application project in Visual Studio 2019.</span></span>

<span data-ttu-id="cb03d-167">Oltre all'autenticazione esterna dei provider elencati in precedenza, sono disponibili pacchetti di terze parti che forniscono middleware per l'uso di molti altri provider di autenticazione esterni.</span><span class="sxs-lookup"><span data-stu-id="cb03d-167">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="cb03d-168">Per un elenco, vedere il repository AspNet.Security.OAuth.Providers su GitHub.For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repository on GitHub.</span><span class="sxs-lookup"><span data-stu-id="cb03d-168">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repository on GitHub.</span></span>

<span data-ttu-id="cb03d-169">È anche possibile creare middleware di autenticazione esterna personalizzato per risolvere esigenze particolari.</span><span class="sxs-lookup"><span data-stu-id="cb03d-169">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="cb03d-170">Eseguire l'autenticazione con bearer token</span><span class="sxs-lookup"><span data-stu-id="cb03d-170">Authenticate with bearer tokens</span></span>

<span data-ttu-id="cb03d-171">L'autenticazione con ASP.NET Core Identity (o Identity più provider di autenticazione esterni) funziona bene per molti scenari di applicazioni Web in cui è appropriato archiviare le informazioni dell'utente in un cookie.</span><span class="sxs-lookup"><span data-stu-id="cb03d-171">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="cb03d-172">In altri scenari, tuttavia, i cookie non sono un mezzo naturale per salvare in modo permanente e trasmettere i dati.</span><span class="sxs-lookup"><span data-stu-id="cb03d-172">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="cb03d-173">Ad esempio, in un'API Web di ASP.NET Core che espone endpoint RESTful a cui potrebbero accedere applicazioni a pagina singola, client nativi o anche da altre API Web, in genere è consigliabile usare l'autenticazione con bearer token.</span><span class="sxs-lookup"><span data-stu-id="cb03d-173">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="cb03d-174">Questi tipi di applicazioni non usano i cookie, ma possono recuperare facilmente un bearer token e includerlo nell'intestazione di autorizzazione delle richieste successive.</span><span class="sxs-lookup"><span data-stu-id="cb03d-174">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="cb03d-175">Per consentire l'autenticazione del token, ASP.NET Core supporta diverse opzioni di utilizzo di [OAuth 2.0](https://oauth.net/2/) e [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="cb03d-175">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="cb03d-176">Eseguire l'autenticazione con un provider di identità OpenID Connect o OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="cb03d-176">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="cb03d-177">Se le informazioni dell'utente sono archiviate in Azure Active Directory o in un'altra soluzione di identità che supporta OpenID Connect o OAuth 2.0, è possibile usare il pacchetto **Microsoft.AspNetCore.Authentication.OpenIdConnect** per eseguire l'autenticazione tramite il flusso di lavoro di OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="cb03d-177">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="cb03d-178">Ad esempio per eseguire l'autenticazione con il microservizio Identity.Api in eshopOnContainers, un'applicazione Web ASP.NET Core può usare il middleware del pacchetto, come illustrato nell'esempio semplificato seguente in `Startup.cs`:</span><span class="sxs-lookup"><span data-stu-id="cb03d-178">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");
    var sessionCookieLifetime = configuration.GetValue("SessionCookieLifetimeMinutes", 60);

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
    })
    .AddCookie(setup => setup.ExpireTimeSpan = TimeSpan.FromMinutes(sessionCookieLifetime))
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl.ToString();
        options.SignedOutRedirectUri = callBackUrl.ToString();
        options.ClientId = useLoadTest ? "mvctest" : "mvc";
        options.ClientSecret = "secret";
        options.ResponseType = useLoadTest ? "code id_token token" : "code id_token";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

<span data-ttu-id="cb03d-179">Si noti che quando si usa questo flusso di lavoro il middleware di ASP.NET Core Identity non è necessario, perché tutte le operazioni di archiviazione e autenticazione delle informazioni degli utenti vengono gestite dal servizio di gestione delle identità.</span><span class="sxs-lookup"><span data-stu-id="cb03d-179">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="cb03d-180">Rilasciare token di sicurezza da un servizio ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cb03d-180">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="cb03d-181">Se si vuole rilasciare token di sicurezza per gli utenti locali di ASP.NET Core Identity anziché usare un provider di identità esterna, è possibile avvalersi di alcune utili librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="cb03d-181">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="cb03d-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) e [OpenIddict](https://github.com/openiddict/openiddict-core) sono provider OpenID Connect che si integrano facilmente con ASP.NET Core Identity per il rilascio di token di sicurezza da un servizio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cb03d-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="cb03d-183">La [documentazione di IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) contiene istruzioni dettagliate per l'uso della libreria.</span><span class="sxs-lookup"><span data-stu-id="cb03d-183">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="cb03d-184">Di seguito sono indicate le operazioni di base per usare IdentityServer4 per il rilascio di token.</span><span class="sxs-lookup"><span data-stu-id="cb03d-184">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="cb03d-185">Si chiama app. UseIdentityServer nel metodo Startup.Configure per aggiungere IdentityServer4 alla pipeline di elaborazione delle richieste HTTP dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-185">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application's HTTP request processing pipeline.</span></span> <span data-ttu-id="cb03d-186">In questo modo, la libreria fornisce richieste agli endpoint OpenID Connect e OAuth2 come /connect/token.</span><span class="sxs-lookup"><span data-stu-id="cb03d-186">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="cb03d-187">IdentityServer4 viene configurato in Startup.ConfigureServices tramite una chiamata a services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="cb03d-187">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="cb03d-188">Il server delle identità viene configurato impostando i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb03d-188">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="cb03d-189">Le [credenziali](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) da usare per la firma.</span><span class="sxs-lookup"><span data-stu-id="cb03d-189">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="cb03d-190">Le [risorse di identità e API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) a cui gli utenti potrebbero richiedere l'accesso:</span><span class="sxs-lookup"><span data-stu-id="cb03d-190">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="cb03d-191">Le risorse API rappresentano dati protetti o funzionalità a cui l'utente può accedere con un token di accesso.</span><span class="sxs-lookup"><span data-stu-id="cb03d-191">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="cb03d-192">Un esempio di risorsa API è un'API o un set di API Web che richiede l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-192">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="cb03d-193">Le risorse di identità rappresentano informazioni (attestazioni) che vengono fornite a un client per identificare un utente.</span><span class="sxs-lookup"><span data-stu-id="cb03d-193">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="cb03d-194">Le attestazioni possono includere il nome utente, l'indirizzo di posta elettronica e così via.</span><span class="sxs-lookup"><span data-stu-id="cb03d-194">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="cb03d-195">I [client](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) che si connetteranno per richiedere i token.</span><span class="sxs-lookup"><span data-stu-id="cb03d-195">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="cb03d-196">Il meccanismo di archiviazione delle informazioni degli utenti, ad esempio [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) o un sistema alternativo.</span><span class="sxs-lookup"><span data-stu-id="cb03d-196">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="cb03d-197">Quando si specificano i client e le risorse da usare con IdentityServer4, è possibile passare una raccolta <xref:System.Collections.Generic.IEnumerable%601> del tipo appropriato ai metodi che accettano archivi di client o risorse in memoria.</span><span class="sxs-lookup"><span data-stu-id="cb03d-197">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="cb03d-198">In alternativa, per scenari più complessi, è possibile fornire tipi di provider di client o risorse tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="cb03d-198">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="cb03d-199">Un esempio di configurazione per IdentityServer4 che usa le risorse e i client in memoria forniti da un tipo IClientStore personalizzato è simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cb03d-199">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //...
    services.AddSingleton<IClientStore, CustomClientStore>();
    services.AddIdentityServer()
        .AddSigningCredential("CN=sts")
        .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
        .AddAspNetIdentity<ApplicationUser>();
    //...
}
```

### <a name="consume-security-tokens"></a><span data-ttu-id="cb03d-200">Usare i token di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb03d-200">Consume security tokens</span></span>

<span data-ttu-id="cb03d-201">L'autenticazione con un endpoint OpenID Connect o l'emissione di token di sicurezza propri coprono alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="cb03d-201">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="cb03d-202">Ma occorre considerare anche i casi in cui un servizio necessita semplicemente di limitare l'accesso agli utenti che hanno token di sicurezza validi forniti da un servizio diverso.</span><span class="sxs-lookup"><span data-stu-id="cb03d-202">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="cb03d-203">Per questo scenario è disponibile il middleware di autenticazione che gestisce i token JWT nel pacchetto **Microsoft.AspNetCore.Authentication.JwtBearer**.</span><span class="sxs-lookup"><span data-stu-id="cb03d-203">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="cb03d-204">JWT è l'acronimo di "[JSON Web Token (token Web JSON)](https://tools.ietf.org/html/rfc7519)" ed è un formato di token di sicurezza comune, definito da RFC 7519, per la comunicazione di attestazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cb03d-204">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="cb03d-205">Un esempio semplificato dell'uso del middleware con questi token può essere simile a questo frammento di codice, tratto dal microservizio Ordering.Api di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="cb03d-205">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="cb03d-206">I parametri in questo caso sono:</span><span class="sxs-lookup"><span data-stu-id="cb03d-206">The parameters in this usage are:</span></span>

- <span data-ttu-id="cb03d-207">`Audience` rappresenta il destinatario del token in ingresso o la risorsa a cui il token concede l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cb03d-207">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="cb03d-208">Se il valore specificato in questo parametro non corrisponde al parametro nel token, il token verrà rifiutato.</span><span class="sxs-lookup"><span data-stu-id="cb03d-208">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="cb03d-209">`Authority` è l'indirizzo del server di autenticazione che emette i token.</span><span class="sxs-lookup"><span data-stu-id="cb03d-209">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="cb03d-210">Il middleware di autenticazione del bearer token JWT usa questo URI per ottenere la chiave pubblica che può essere usata per convalidare la firma del token.</span><span class="sxs-lookup"><span data-stu-id="cb03d-210">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="cb03d-211">Il middleware verifica anche che il parametro `iss` nel token corrisponda a questo URI.</span><span class="sxs-lookup"><span data-stu-id="cb03d-211">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="cb03d-212">Un altro parametro, `RequireHttpsMetadata`, è utile per i test. Impostando questo parametro su false è possibile testare l'applicazione in ambienti in cui non sono presenti certificati.</span><span class="sxs-lookup"><span data-stu-id="cb03d-212">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="cb03d-213">Nelle distribuzioni effettive, i bearer token JWT devono sempre essere passati solo su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb03d-213">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="cb03d-214">Con questo middleware, i token JWT vengono estratti automaticamente dalle intestazioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-214">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="cb03d-215">Vengono quindi deserializzati, convalidati (tramite i valori nei parametri `Audience` e `Authority`) e archiviati come informazioni utente alle quali fare riferimento in seguito con azioni MVC o filtri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb03d-215">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="cb03d-216">Il middleware di autenticazione con bearer token JWT può supportare anche scenari più avanzati, ad esempio l'uso di un certificato locale per convalidare un token se l'autorità non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="cb03d-216">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="cb03d-217">Per questo scenario è possibile specificare un oggetto `TokenValidationParameters` nell'oggetto `JwtBearerOptions`.</span><span class="sxs-lookup"><span data-stu-id="cb03d-217">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb03d-218">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cb03d-218">Additional resources</span></span>

- <span data-ttu-id="cb03d-219">**Condivisione dei cookie tra le applicazioni** </span><span class="sxs-lookup"><span data-stu-id="cb03d-219">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="cb03d-220">**Introduzione all'identità** </span><span class="sxs-lookup"><span data-stu-id="cb03d-220">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="cb03d-221">**Rick Anderson. Autenticazione a due fattori con SMS** </span><span class="sxs-lookup"><span data-stu-id="cb03d-221">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="cb03d-222">**Abilitazione dell'autenticazione tramite Facebook, Google e altri provider esterni** </span><span class="sxs-lookup"><span data-stu-id="cb03d-222">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="cb03d-223">**Michell Anicas. Introduzione a OAuth 2** </span><span class="sxs-lookup"><span data-stu-id="cb03d-223">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="cb03d-224">**AspNet.Security.OAuth.Providers** (repository GitHub per i provider OAuth ASP.NET) </span><span class="sxs-lookup"><span data-stu-id="cb03d-224">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="cb03d-225">**IdentityServer4. Documentazione ufficiale** </span><span class="sxs-lookup"><span data-stu-id="cb03d-225">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="cb03d-226">[Successivo](../implement-resilient-applications/monitor-app-health.md)
>[precedente](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="cb03d-226">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
