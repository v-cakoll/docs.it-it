---
title: Protezione di microservizi e applicazioni Web .NET
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Protezione di microservizi e applicazioni Web .NET
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: c2c7d692517c6a46225542936e05656db915bf0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="securing-net-microservices-and-web-applications"></a><span data-ttu-id="70254-103">Protezione di microservizi e applicazioni Web .NET</span><span class="sxs-lookup"><span data-stu-id="70254-103">Securing .NET Microservices and Web Applications</span></span>

<span data-ttu-id="70254-104">È spesso necessario che le risorse e le API esposte da un servizio siano limitate a determinati utenti o client attendibili.</span><span class="sxs-lookup"><span data-stu-id="70254-104">It is often necessary for resources and APIs exposed by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="70254-105">Il primo passaggio per prendere questo tipo di decisioni sull'attendibilità a livello di API è l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="70254-105">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="70254-106">L'autenticazione è il processo di verifica dell'affidabilità dell'identità di un utente.</span><span class="sxs-lookup"><span data-stu-id="70254-106">Authentication is the process of reliably ascertaining a user’s identity.</span></span>

<span data-ttu-id="70254-107">In scenari con microservizi, l'autenticazione viene in genere gestita a livello centrale.</span><span class="sxs-lookup"><span data-stu-id="70254-107">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="70254-108">Se si usa un gateway API, il gateway è un ottimo strumento per l'autenticazione, come illustrato nella figura 11-1.</span><span class="sxs-lookup"><span data-stu-id="70254-108">If you are using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 11-1.</span></span> <span data-ttu-id="70254-109">Se si usa questo approccio, assicurarsi che i singoli microservizi non possano essere raggiunti direttamente (senza il gateway API), a meno che non sia presente un sistema di sicurezza aggiuntivo per autenticare i messaggi, indipendentemente dal fatto che provengano dal gateway.</span><span class="sxs-lookup"><span data-stu-id="70254-109">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![](./media/image1.png)

<span data-ttu-id="70254-110">**Figura 11-1**.</span><span class="sxs-lookup"><span data-stu-id="70254-110">**Figure 11-1**.</span></span> <span data-ttu-id="70254-111">Autenticazione centralizzata con un gateway API</span><span class="sxs-lookup"><span data-stu-id="70254-111">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="70254-112">Se è possibile accedere direttamente ai servizi, per autenticare gli utenti è possibile usare un servizio di autenticazione come Azure Active Directory o un microservizio di autenticazione dedicato con funzione di servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="70254-112">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="70254-113">Le decisioni sull'attendibilità vengono condivise tra i servizi con i token di sicurezza o i cookie.</span><span class="sxs-lookup"><span data-stu-id="70254-113">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="70254-114">Possono essere condivise tra applicazioni, se necessario, in ASP.NET Core con [servizi di protezione dei dati](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications). Questo scenario è illustrato nella Figura 11-2.</span><span class="sxs-lookup"><span data-stu-id="70254-114">(These can be shared between applications, if needed, in ASP.NET Core with [data protection services](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 11-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="70254-115">**Figura 11-2**.</span><span class="sxs-lookup"><span data-stu-id="70254-115">**Figure 11-2**.</span></span> <span data-ttu-id="70254-116">Autenticazione mediante microservizio di identità; l'attendibilità è condivisa con un token di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70254-116">Authentication by identity microservice; trust is shared using an authorization token</span></span>

## <a name="authenticating-using-aspnet-core-identity"></a><span data-ttu-id="70254-117">Autenticazione tramite ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="70254-117">Authenticating using ASP.NET Core Identity</span></span>

<span data-ttu-id="70254-118">Il meccanismo principale in ASP.NET Core per identificare gli utenti di un'applicazione è il sistema di appartenenze [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="70254-118">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="70254-119">ASP.NET Core Identity archivia informazioni sugli utenti (comprese le informazioni di accesso, i ruoli e le attestazioni) in un archivio dati configurato dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="70254-119">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="70254-120">In genere, l'archivio dati di ASP.NET Core Identity è un archivio di Entity Framework fornito nel pacchetto Microsoft.AspNetCore.Identity.EntityFrameworkCore.</span><span class="sxs-lookup"><span data-stu-id="70254-120">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the Microsoft.AspNetCore.Identity.EntityFrameworkCore package.</span></span> <span data-ttu-id="70254-121">È tuttavia possibile usare archivi personalizzati o altri pacchetti di terze parti per archiviare le informazioni sull'identità in Archiviazione tabelle di Azure, in DocumentDB o in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="70254-121">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, DocumentDB, or other locations.</span></span>

<span data-ttu-id="70254-122">Il codice seguente proviene dal modello di progetto applicazione Web di ASP.NET Core con l'autenticazione dell'account utente singolo selezionata.</span><span class="sxs-lookup"><span data-stu-id="70254-122">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="70254-123">Illustra come configurare ASP.NET Core Identity tramite EntityFramework.Core nel metodo Startup.ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="70254-123">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="70254-124">Una volta configurato, ASP.NET Core Identity può essere abilitato chiamando app.UseIdentity nel metodo Startup.Configure del servizio.</span><span class="sxs-lookup"><span data-stu-id="70254-124">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s Startup.Configure method.</span></span>

<span data-ttu-id="70254-125">L'uso di ASP.NET Core Identity consente diversi scenari:</span><span class="sxs-lookup"><span data-stu-id="70254-125">Using ASP.NET Code Identity enables several scenarios:</span></span>

-   <span data-ttu-id="70254-126">Creazione di nuove informazioni utente usando il tipo UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="70254-126">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

-   <span data-ttu-id="70254-127">Autenticazione degli utenti tramite il tipo SignInManager.</span><span class="sxs-lookup"><span data-stu-id="70254-127">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="70254-128">È possibile usare signInManager.SignInAsync per accedere direttamente o signInManager.PasswordSignInAsync per confermare l'esattezza della password dell'utente e quindi concedere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="70254-128">You can use signInManager.SignInAsync to sign in directly, or signInManager.PasswordSignInAsync to confirm the user’s password is correct and then sign them in.</span></span>

-   <span data-ttu-id="70254-129">Identificazione di un utente in base alle informazioni archiviate in un cookie (che viene letto dal middleware di ASP.NET Core Identity) in modo che le successive richieste provenienti da un browser includeranno l'identità e le attestazioni dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="70254-129">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="70254-130">ASP.NET Core Identity supporta inoltre l'[autenticazione a due fattori](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="70254-130">ASP.NET Core Identity also supports [two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="70254-131">Per scenari di autenticazione che usano dell'archivio dati degli utenti locale e vengono salvano in modo permanente l'identità tra le richieste tramite dei cookie (come avviene per le applicazioni web MVC), ASP.NET Identity Core è una soluzione consigliata.</span><span class="sxs-lookup"><span data-stu-id="70254-131">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

## <a name="authenticating-using-external-providers"></a><span data-ttu-id="70254-132">Autenticazione tramite provider esterni</span><span class="sxs-lookup"><span data-stu-id="70254-132">Authenticating using external providers</span></span>

<span data-ttu-id="70254-133">ASP.NET Core supporta inoltre l'uso di [provider di autenticazione esterni](https://docs.microsoft.com/aspnet/core/security/authentication/social/) per consentire agli utenti di accedere tramite flussi di [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="70254-133">ASP.NET Core also supports using [external authentication providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) to let users log in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="70254-134">Ciò significa che gli utenti possono accedere con processi di autenticazione esistenti di provider come Microsoft, Google, Facebook o Twitter e associare le identità a un'identità di ASP.NET Core nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70254-134">This means that users can log in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="70254-135">Per usare l'autenticazione esterna, includere il middleware di autenticazione appropriato nella pipeline di elaborazione della richiesta HTTP dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70254-135">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="70254-136">Questo middleware è responsabile della gestione delle richieste di route URI dal provider di autenticazione, dell'acquisizione di informazioni di identità e della messa a disponibile delle stesse tramite il metodo SignInManager.GetExternalLoginInfo.</span><span class="sxs-lookup"><span data-stu-id="70254-136">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="70254-137">Di seguito sono elencati i provider di autenticazione esterni comuni e i pacchetti NuGet associati.</span><span class="sxs-lookup"><span data-stu-id="70254-137">Popular external authentication providers and their associated NuGet packages are shown below.</span></span>

<span data-ttu-id="70254-138">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span><span class="sxs-lookup"><span data-stu-id="70254-138">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span></span>

<span data-ttu-id="70254-139">**Google:** Microsoft.AspNetCore.Authentication.Google</span><span class="sxs-lookup"><span data-stu-id="70254-139">**Google:** Microsoft.AspNetCore.Authentication.Google</span></span>

<span data-ttu-id="70254-140">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span><span class="sxs-lookup"><span data-stu-id="70254-140">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span></span>

<span data-ttu-id="70254-141">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span><span class="sxs-lookup"><span data-stu-id="70254-141">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span></span>

<span data-ttu-id="70254-142">In tutti i casi, il middleware è registrato con una chiamata a un metodo di registrazione simile a app.Use{ExternalProvider}Authentication in Startup.Configure.</span><span class="sxs-lookup"><span data-stu-id="70254-142">In all cases, the middleware is registered with a call to a registration method similar to app.Use{ExternalProvider}Authentication in Startup.Configure.</span></span> <span data-ttu-id="70254-143">Questi metodi di registrazione accettano un oggetto di opzioni che contiene un ID applicazione e informazioni segrete (una password, ad esempio), in base alle esigenze dal provider.</span><span class="sxs-lookup"><span data-stu-id="70254-143">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="70254-144">I provider di autenticazione esterni richiedono la registrazione dell'applicazione (come spiegato nella [documentazione di ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) per poter informare l'utente di quale applicazione richiede l'accesso alla sua identità.</span><span class="sxs-lookup"><span data-stu-id="70254-144">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="70254-145">Una volta registrato il middleware in Startup.Configure, è possibile richiedere agli utenti di accedere da qualsiasi azione del controller.</span><span class="sxs-lookup"><span data-stu-id="70254-145">Once the middleware is registered in Startup.Configure, you can prompt users to log in from any controller action.</span></span> <span data-ttu-id="70254-146">in questo modo si crea un oggetto AuthenticationProperties che include il nome del provider di autenticazione e un URL di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="70254-146">To do this, you create an AuthenticationProperties object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="70254-147">È quindi possibile restituire una risposta Challenge che passa l'oggetto AuthenticationProperties.</span><span class="sxs-lookup"><span data-stu-id="70254-147">You then return a Challenge response that passes the AuthenticationProperties object.</span></span> <span data-ttu-id="70254-148">Nel codice seguente viene illustrato un esempio.</span><span class="sxs-lookup"><span data-stu-id="70254-148">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="70254-149">Il parametro redirectUrl include l'URL a cui il provider esterno deve reindirizzare l'utente dopo l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="70254-149">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="70254-150">L'URL deve rappresentare un'azione che connetterà l'utente in base alle informazioni di identità esterne, come nell'esempio semplificato seguente:</span><span class="sxs-lookup"><span data-stu-id="70254-150">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="70254-151">Se si sceglie l'opzione di autenticazione **Account utente individuali** quando si crea il progetto di applicazione Web ASP.NET Code in Visual Studio, tutto il codice necessario per l'accesso con un provider esterno è già presente nel progetto, come illustrato nella figura 11-3.</span><span class="sxs-lookup"><span data-stu-id="70254-151">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 11-3.</span></span>

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

<span data-ttu-id="70254-152">**Figura 11-3**.</span><span class="sxs-lookup"><span data-stu-id="70254-152">**Figure 11-3**.</span></span> <span data-ttu-id="70254-153">Selezione di un'opzione per l'uso dell'autenticazione esterna quando si crea un progetto di applicazione Web</span><span class="sxs-lookup"><span data-stu-id="70254-153">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="70254-154">Oltre all'autenticazione esterna dei provider elencati in precedenza, sono disponibili pacchetti di terze parti che forniscono middleware per l'uso di molti altri provider di autenticazione esterni.</span><span class="sxs-lookup"><span data-stu-id="70254-154">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="70254-155">Per un elenco, vedere il repository [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) in GitHub.</span><span class="sxs-lookup"><span data-stu-id="70254-155">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="70254-156">Naturalmente, è anche possibile creare il proprio middleware di autenticazione esterno.</span><span class="sxs-lookup"><span data-stu-id="70254-156">It is also possible, of course, to create your own external authentication middleware.</span></span>

## <a name="authenticating-with-bearer-tokens"></a><span data-ttu-id="70254-157">Autenticazione con bearer token</span><span class="sxs-lookup"><span data-stu-id="70254-157">Authenticating with bearer tokens</span></span>

<span data-ttu-id="70254-158">L'autenticazione con ASP.NET Core Identity (o Identity più provider di autenticazione esterni) funziona bene per molti scenari di applicazioni Web in cui è appropriato archiviare le informazioni dell'utente in un cookie.</span><span class="sxs-lookup"><span data-stu-id="70254-158">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="70254-159">In altri scenari, tuttavia, i cookie non sono un mezzo naturale per salvare in modo permanente e trasmettere i dati.</span><span class="sxs-lookup"><span data-stu-id="70254-159">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="70254-160">Ad esempio, in un'API Web di ASP.NET Core che espone endpoint RESTful a cui potrebbero accedere applicazioni a pagina singola, client nativi o anche da altre API Web, in genere è consigliabile usare l'autenticazione con bearer token.</span><span class="sxs-lookup"><span data-stu-id="70254-160">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="70254-161">Questi tipi di applicazioni non usano i cookie, ma possono recuperare facilmente un bearer token e includerlo nell'intestazione di autorizzazione delle richieste successive.</span><span class="sxs-lookup"><span data-stu-id="70254-161">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="70254-162">Per consentire l'autenticazione del token, ASP.NET Core supporta diverse opzioni di utilizzo di [OAuth 2.0](https://oauth.net/2/) e [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="70254-162">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="70254-163">Autenticazione con un provider di identità OAuth 2.0 o OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="70254-163">Authenticating with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="70254-164">Se le informazioni dell'utente sono archiviate in Azure Active Directory o in un'altra soluzione di identità che supporta OpenID Connect o OAuth 2.0, è possibile usare il pacchetto Microsoft.AspNetCore.Authentication.OpenIdConnect per eseguire l'autenticazione tramite il flusso di lavoro di OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="70254-164">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the Microsoft.AspNetCore.Authentication.OpenIdConnect package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="70254-165">Per [l'autenticazione con Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), ad esempio, un'applicazione Web ASP.NET Core può usare il middleware del pacchetto, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="70254-165">For example, to [authenticate against Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), an ASP.NET Core web application can use middleware from that package as shown in the following example:</span></span>

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

<span data-ttu-id="70254-166">I valori di configurazione sono i valori di Azure Active Directory che vengono creati quando l'applicazione è [registrata come client di Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="70254-166">The configuration values are Azure Active Directory values that are created when your application is [registered as an Azure AD client](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span></span> <span data-ttu-id="70254-167">Un ID client singolo può essere condiviso tra più microservizi in un'applicazione, se tutti i microservizi devono autenticare gli utenti autenticati tramite Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70254-167">A single client ID can be shared among multiple microservices in an application if they all need to authenticate users authenticated via Azure Active Directory.</span></span>

<span data-ttu-id="70254-168">Si noti che quando si usa questo flusso di lavoro, il middleware di ASP.NET Core Identity non è necessario, poiché tutte le operazioni di archiviazione e autenticazione delle informazioni degli utenti vengono gestite da Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70254-168">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by Azure Active Directory.</span></span>

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="70254-169">Rilascio di token di sicurezza da un servizio ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="70254-169">Issuing security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="70254-170">Se si vuole rilasciare token di sicurezza per gli utenti locali di ASP.NET Core Identity anziché usare un provider di identità esterna, è possibile avvalersi di alcune utili librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="70254-170">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="70254-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) e [OpenIddict](https://github.com/openiddict/openiddict-core) sono provider OpenID Connect che si integrano facilmente con ASP.NET Core Identity per il rilascio di token di sicurezza da un servizio ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="70254-171">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="70254-172">La [documentazione di IdentityServer4](https://identityserver4.readthedocs.io/en/release/) contiene istruzioni dettagliate per l'uso della libreria.</span><span class="sxs-lookup"><span data-stu-id="70254-172">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/release/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="70254-173">Di seguito sono indicate le operazioni di base per usare IdentityServer4 per il rilascio di token.</span><span class="sxs-lookup"><span data-stu-id="70254-173">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1.  <span data-ttu-id="70254-174">Chiamare app.UseIdentityServer nel metodo Startup.Configure per aggiungere IdentityServer4 alla pipeline di elaborazione delle richieste HTTP dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70254-174">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="70254-175">In questo modo, la libreria fornisce richieste agli endpoint OpenID Connect e OAuth2 come /connect/token.</span><span class="sxs-lookup"><span data-stu-id="70254-175">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2.  <span data-ttu-id="70254-176">IdentityServer4 viene configurato in Startup.ConfigureServices tramite una chiamata a services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="70254-176">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3.  <span data-ttu-id="70254-177">Il server delle identità viene configurato specificando i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="70254-177">You configure identity server by providing the following data:</span></span>

-   <span data-ttu-id="70254-178">Le [credenziali](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) da usare per la firma.</span><span class="sxs-lookup"><span data-stu-id="70254-178">The [credentials](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) to use for signing.</span></span>

-   <span data-ttu-id="70254-179">Le [risorse di identità e API](https://identityserver4.readthedocs.io/en/release/topics/resources.html) a cui gli utenti potrebbero richiedere l'accesso:</span><span class="sxs-lookup"><span data-stu-id="70254-179">The [Identity and API resources](https://identityserver4.readthedocs.io/en/release/topics/resources.html) that users might request access to:</span></span>

<!-- -->

-   <span data-ttu-id="70254-180">Le risorse API rappresentano dati protetti o funzionalità a cui l'utente può accedere con un token di accesso.</span><span class="sxs-lookup"><span data-stu-id="70254-180">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="70254-181">Un esempio di risorsa API è un'API o un set di API Web che richiede l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="70254-181">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

-   <span data-ttu-id="70254-182">Le risorse di identità rappresentano informazioni (attestazioni) che vengono fornite a un client per identificare un utente.</span><span class="sxs-lookup"><span data-stu-id="70254-182">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="70254-183">Le attestazioni possono includere il nome utente, l'indirizzo di posta elettronica e così via.</span><span class="sxs-lookup"><span data-stu-id="70254-183">The claims might include the user name, email address, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="70254-184">I [client](https://identityserver4.readthedocs.io/en/release/topics/clients.html) che si connetteranno per richiedere i token.</span><span class="sxs-lookup"><span data-stu-id="70254-184">The [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) that will be connecting in order to request tokens.</span></span>

-   <span data-ttu-id="70254-185">Il meccanismo di archiviazione delle informazioni degli utenti, ad esempio [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) o un sistema alternativo.</span><span class="sxs-lookup"><span data-stu-id="70254-185">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) or an alternative.</span></span>

<span data-ttu-id="70254-186">Quando si specificano i client e le risorse da usare con IdentityServer4, è possibile passare un oggetto IEnumerable&lt;T&gt; del tipo appropriato ai metodi che accettano archivi di client o risorse in memoria.</span><span class="sxs-lookup"><span data-stu-id="70254-186">When you specify clients and resources for IdentityServer4 to use, you can pass an IEnumerable&lt;T&gt; collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="70254-187">In alternativa, per scenari più complessi, è possibile fornire tipi di provider di client o risorse tramite l'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="70254-187">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="70254-188">Un esempio di configurazione per IdentityServer4 che usa le risorse e i client in memoria forniti da un tipo IClientStore personalizzato è simile al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="70254-188">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a><span data-ttu-id="70254-189">Utilizzo di token di sicurezza</span><span class="sxs-lookup"><span data-stu-id="70254-189">Consuming security tokens</span></span>

<span data-ttu-id="70254-190">L'autenticazione con un endpoint OpenID Connect o l'emissione di token di sicurezza propri coprono alcuni scenari.</span><span class="sxs-lookup"><span data-stu-id="70254-190">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="70254-191">Ma occorre considerare anche i casi in cui un servizio necessita semplicemente di limitare l'accesso agli utenti che hanno token di sicurezza validi forniti da un servizio diverso.</span><span class="sxs-lookup"><span data-stu-id="70254-191">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="70254-192">Per questo scenario è disponibile il middleware di autenticazione che gestisce i token JWT nel pacchetto Microsoft.AspNetCore.Authentication.JwtBearer.</span><span class="sxs-lookup"><span data-stu-id="70254-192">For that scenario, authentication middleware that handles JWT tokens is available in the Microsoft.AspNetCore.Authentication.JwtBearer package.</span></span> <span data-ttu-id="70254-193">JWT è l'acronimo di "[JSON Web Token (token Web JSON)](https://tools.ietf.org/html/rfc7519)" ed è un formato di token di sicurezza comune, definito da RFC 7519, per la comunicazione di attestazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="70254-193">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="70254-194">Un semplice esempio di come usare il middleware con questi token è simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="70254-194">A simple example of how to use middleware to consume such tokens might look like the following example.</span></span> <span data-ttu-id="70254-195">Questo codice deve precedere le chiamate al middleware di ASP.NET Core MVC di base (app. UseMvc).</span><span class="sxs-lookup"><span data-stu-id="70254-195">This code must precede calls to ASP.NET Core MVC middleware (app.UseMvc).</span></span>

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

<span data-ttu-id="70254-196">I parametri in questo caso sono:</span><span class="sxs-lookup"><span data-stu-id="70254-196">The parameters in this usage are:</span></span>

-   <span data-ttu-id="70254-197">Audience rappresenta il destinatario del token in ingresso o la risorsa a cui il token concede l'accesso.</span><span class="sxs-lookup"><span data-stu-id="70254-197">Audience represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="70254-198">Se il valore specificato in questo parametro corrisponde al parametro aud nel token, il token verrà rifiutato.</span><span class="sxs-lookup"><span data-stu-id="70254-198">If the value specified in this parameter does not match the aud parameter in the token, the token will be rejected.</span></span>

-   <span data-ttu-id="70254-199">Authority è l'indirizzo del server di autenticazione che emette i token.</span><span class="sxs-lookup"><span data-stu-id="70254-199">Authority is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="70254-200">Il middleware di autenticazione del bearer token JWT usa questo URI per ottenere la chiave pubblica che può essere usata per convalidare la firma del token.</span><span class="sxs-lookup"><span data-stu-id="70254-200">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="70254-201">Il middleware verifica inoltre che il parametro iss nel token corrisponda a questo URI.</span><span class="sxs-lookup"><span data-stu-id="70254-201">The middleware also confirms that the iss parameter in the token matches this URI.</span></span>

-   <span data-ttu-id="70254-202">AutomaticAuthenticate è un valore booleano che indica se l'utente definito dal token debba essere connesso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="70254-202">AutomaticAuthenticate is a Boolean value that indicates whether the user defined by the token should be automatically signed in.</span></span>

<span data-ttu-id="70254-203">Il parametro RequireHttpsMetadata non viene usato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="70254-203">Another parameter, RequireHttpsMetadata, is not used in this example.</span></span> <span data-ttu-id="70254-204">È utile a scopo di testing. Impostando questo parametro su false, è possibile testare l'applicazione in ambienti in cui non si dispone di certificati.</span><span class="sxs-lookup"><span data-stu-id="70254-204">It is useful for testing purposes; you set this parameter to false so that you can test in environments where you do not have certificates.</span></span> <span data-ttu-id="70254-205">Nelle distribuzioni effettive, i bearer token JWT devono sempre essere passati solo su HTTPS.</span><span class="sxs-lookup"><span data-stu-id="70254-205">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="70254-206">Con questo middleware, i token JWT vengono estratti automaticamente dalle intestazioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="70254-206">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="70254-207">Vengono quindi deserializzati, convalidati (tramite i valori nei parametri Audience e Authority) e archiviati come informazioni utente per farvi riferimento in un secondo momento con azioni MVC o filtri di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="70254-207">They are then deserialized, validated (using the values in the Audience and Authority parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="70254-208">Il middleware di autenticazione con bearer token JWT può supportare anche scenari più avanzati, ad esempio l'uso di un certificato locale per convalidare un token se l'autorità non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="70254-208">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="70254-209">In questo caso, è possibile specificare un oggetto TokenValidationParameters nell'oggetto JwtBearerOptions.</span><span class="sxs-lookup"><span data-stu-id="70254-209">For this scenario, you can specify a TokenValidationParameters object in the JwtBearerOptions object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70254-210">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="70254-210">Additional resources</span></span>

-   <span data-ttu-id="70254-211">**Condividere i cookie tra le app**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span><span class="sxs-lookup"><span data-stu-id="70254-211">**Sharing cookies between applications**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span></span>

-   <span data-ttu-id="70254-212">**Introduzione all'identità**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="70254-212">**Introduction to Identity**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="70254-213">**Rick Anderson. Autenticazione a due fattori con SMS**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span><span class="sxs-lookup"><span data-stu-id="70254-213">**Rick Anderson. Two-factor authentication with SMS**
[*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span></span>

-   <span data-ttu-id="70254-214">**Abilitazione dell'autenticazione con Facebook, Google e altri provider esterni**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span><span class="sxs-lookup"><span data-stu-id="70254-214">**Enabling authentication using Facebook, Google and other external providers**
[*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span></span>

-   <span data-ttu-id="70254-215">**Michell Anicas. An Introduction to OAuth 2**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) (Introduzione a OAuth)</span><span class="sxs-lookup"><span data-stu-id="70254-215">**Michell Anicas. An Introduction to OAuth 2**
[*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span></span>

-   <span data-ttu-id="70254-216">**AspNet.Security.OAuth.Providers** (repository GitHub per i provider OAuth ASP.NET).</span><span class="sxs-lookup"><span data-stu-id="70254-216">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span>
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   <span data-ttu-id="70254-217">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app (Integrazione di Azure AD in un'app Web ASP.NET Core)**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span><span class="sxs-lookup"><span data-stu-id="70254-217">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app**
[*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span></span>

-   <span data-ttu-id="70254-218">**IdentityServer4. Documentazione ufficiale**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span><span class="sxs-lookup"><span data-stu-id="70254-218">**IdentityServer4. Official documentation**
[*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="70254-219">[Precedente] (../implement-resilient-applications/monitor-app-health.md) [Successivo] (authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="70254-219">[Previous] (../implement-resilient-applications/monitor-app-health.md) [Next] (authorization-net-microservices-web-applications.md)</span></span>
