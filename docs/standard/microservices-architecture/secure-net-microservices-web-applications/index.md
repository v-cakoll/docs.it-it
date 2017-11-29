---
title: Protezione di microservizi e applicazioni Web .NET
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Protezione di microservizi e applicazioni Web .NET
keywords: Docker, microservizi, ASP.NET, contenitore
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 147aa099e440f5e5eb1dd6450946274aef91033a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="securing-net-microservices-and-web-applications"></a>Protezione di microservizi e applicazioni Web .NET

È spesso necessario che le risorse e le API esposte da un servizio siano limitate a determinati utenti o client attendibili. Il primo passaggio per prendere questo tipo di decisioni sull'attendibilità a livello di API è l'autenticazione. L'autenticazione è il processo di verifica dell'affidabilità dell'identità di un utente.

In scenari con microservizi, l'autenticazione viene in genere gestita a livello centrale. Se si usa un gateway API, il gateway è un ottimo strumento per l'autenticazione, come illustrato nella figura 11-1. Se si usa questo approccio, assicurarsi che i singoli microservizi non possano essere raggiunti direttamente (senza il gateway API), a meno che non sia presente un sistema di sicurezza aggiuntivo per autenticare i messaggi, indipendentemente dal fatto che provengano dal gateway.

![](./media/image1.png)

**Figura 11-1**. Autenticazione centralizzata con un gateway API

Se è possibile accedere direttamente ai servizi, per autenticare gli utenti è possibile usare un servizio di autenticazione come Azure Active Directory o un microservizio di autenticazione dedicato con funzione di servizio token di sicurezza. Le decisioni sull'attendibilità vengono condivise tra i servizi con i token di sicurezza o i cookie. Possono essere condivise tra applicazioni, se necessario, in ASP.NET Core con [servizi di protezione dei dati](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications). Questo scenario è illustrato nella Figura 11-2.

![](./media/image2.png)

**Figura 11-2**. Autenticazione mediante microservizio di identità; l'attendibilità è condivisa con un token di autorizzazione

## <a name="authenticating-using-aspnet-core-identity"></a>Autenticazione tramite ASP.NET Core Identity

Il meccanismo principale in ASP.NET Core per identificare gli utenti di un'applicazione è il sistema di appartenenze [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity). ASP.NET Core Identity archivia informazioni sugli utenti (comprese le informazioni di accesso, i ruoli e le attestazioni) in un archivio dati configurato dallo sviluppatore. In genere, l'archivio dati di ASP.NET Core Identity è un archivio di Entity Framework fornito nel pacchetto Microsoft.AspNetCore.Identity.EntityFrameworkCore. È tuttavia possibile usare archivi personalizzati o altri pacchetti di terze parti per archiviare le informazioni sull'identità in Archiviazione tabelle di Azure, in DocumentDB o in altre posizioni.

Il codice seguente proviene dal modello di progetto applicazione Web di ASP.NET Core con l'autenticazione dell'account utente singolo selezionata. Illustra come configurare ASP.NET Core Identity tramite EntityFramework.Core nel metodo Startup.ConfigureServices.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

Una volta configurato, ASP.NET Core Identity può essere abilitato chiamando app.UseIdentity nel metodo Startup.Configure del servizio.

L'uso di ASP.NET Core Identity consente diversi scenari:

-   Creazione di nuove informazioni utente usando il tipo UserManager (userManager.CreateAsync).

-   Autenticazione degli utenti tramite il tipo SignInManager. È possibile usare signInManager.SignInAsync per accedere direttamente o signInManager.PasswordSignInAsync per confermare l'esattezza della password dell'utente e quindi concedere l'accesso.

-   Identificazione di un utente in base alle informazioni archiviate in un cookie (che viene letto dal middleware di ASP.NET Core Identity) in modo che le successive richieste provenienti da un browser includeranno l'identità e le attestazioni dell'utente connesso.

ASP.NET Core Identity supporta inoltre l'[autenticazione a due fattori](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).

Per scenari di autenticazione che usano dell'archivio dati degli utenti locale e vengono salvano in modo permanente l'identità tra le richieste tramite dei cookie (come avviene per le applicazioni web MVC), ASP.NET Identity Core è una soluzione consigliata.

## <a name="authenticating-using-external-providers"></a>Autenticazione tramite provider esterni

ASP.NET Core supporta inoltre l'uso di [provider di autenticazione esterni](https://docs.microsoft.com/aspnet/core/security/authentication/social/) per consentire agli utenti di accedere tramite flussi di [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). Ciò significa che gli utenti possono accedere con processi di autenticazione esistenti di provider come Microsoft, Google, Facebook o Twitter e associare le identità a un'identità di ASP.NET Core nell'applicazione.

Per usare l'autenticazione esterna, includere il middleware di autenticazione appropriato nella pipeline di elaborazione della richiesta HTTP dell'applicazione. Questo middleware è responsabile della gestione delle richieste di route URI dal provider di autenticazione, dell'acquisizione di informazioni di identità e della messa a disponibile delle stesse tramite il metodo SignInManager.GetExternalLoginInfo.

Di seguito sono elencati i provider di autenticazione esterni comuni e i pacchetti NuGet associati.

**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount

**Google:** Microsoft.AspNetCore.Authentication.Google

**Facebook:** Microsoft.AspNetCore.Authentication.Facebook

**Twitter:** Microsoft.AspNetCore.Authentication.Twitter

In tutti i casi, il middleware è registrato con una chiamata a un metodo di registrazione simile a app.Use{ExternalProvider}Authentication in Startup.Configure. Questi metodi di registrazione accettano un oggetto di opzioni che contiene un ID applicazione e informazioni segrete (una password, ad esempio), in base alle esigenze dal provider. I provider di autenticazione esterni richiedono la registrazione dell'applicazione (come spiegato nella [documentazione di ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) per poter informare l'utente di quale applicazione richiede l'accesso alla sua identità.

Una volta registrato il middleware in Startup.Configure, è possibile richiedere agli utenti di accedere da qualsiasi azione del controller. in questo modo si crea un oggetto AuthenticationProperties che include il nome del provider di autenticazione e un URL di reindirizzamento. È quindi possibile restituire una risposta Challenge che passa l'oggetto AuthenticationProperties. Nel codice seguente viene illustrato un esempio.

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

Il parametro redirectUrl include l'URL a cui il provider esterno deve reindirizzare l'utente dopo l'autenticazione. L'URL deve rappresentare un'azione che connetterà l'utente in base alle informazioni di identità esterne, come nell'esempio semplificato seguente:

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

Se si sceglie l'opzione di autenticazione **Account utente individuali** quando si crea il progetto di applicazione Web ASP.NET Code in Visual Studio, tutto il codice necessario per l'accesso con un provider esterno è già presente nel progetto, come illustrato nella figura 11-3.

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

**Figura 11-3**. Selezione di un'opzione per l'uso dell'autenticazione esterna quando si crea un progetto di applicazione Web

Oltre all'autenticazione esterna dei provider elencati in precedenza, sono disponibili pacchetti di terze parti che forniscono middleware per l'uso di molti altri provider di autenticazione esterni. Per un elenco, vedere il repository [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) in GitHub.

Naturalmente, è anche possibile creare il proprio middleware di autenticazione esterno.

## <a name="authenticating-with-bearer-tokens"></a>Autenticazione con bearer token

L'autenticazione con ASP.NET Core Identity (o Identity più provider di autenticazione esterni) funziona bene per molti scenari di applicazioni Web in cui è appropriato archiviare le informazioni dell'utente in un cookie. In altri scenari, tuttavia, i cookie non sono un mezzo naturale per salvare in modo permanente e trasmettere i dati.

Ad esempio, in un'API Web di ASP.NET Core che espone endpoint RESTful a cui potrebbero accedere applicazioni a pagina singola, client nativi o anche da altre API Web, in genere è consigliabile usare l'autenticazione con bearer token. Questi tipi di applicazioni non usano i cookie, ma possono recuperare facilmente un bearer token e includerlo nell'intestazione di autorizzazione delle richieste successive. Per consentire l'autenticazione del token, ASP.NET Core supporta diverse opzioni di utilizzo di [OAuth 2.0](https://oauth.net/2/) e [OpenID Connect](http://openid.net/connect/).

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a>Autenticazione con un provider di identità OAuth 2.0 o OpenID Connect

Se le informazioni dell'utente sono archiviate in Azure Active Directory o in un'altra soluzione di identità che supporta OpenID Connect o OAuth 2.0, è possibile usare il pacchetto Microsoft.AspNetCore.Authentication.OpenIdConnect per eseguire l'autenticazione tramite il flusso di lavoro di OpenID Connect. Per [l'autenticazione con Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), ad esempio, un'applicazione Web ASP.NET Core può usare il middleware del pacchetto, come illustrato nell'esempio seguente:

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

I valori di configurazione sono i valori di Azure Active Directory che vengono creati quando l'applicazione è [registrata come client di Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad). Un ID client singolo può essere condiviso tra più microservizi in un'applicazione, se tutti i microservizi devono autenticare gli utenti autenticati tramite Azure Active Directory.

Si noti che quando si usa questo flusso di lavoro, il middleware di ASP.NET Core Identity non è necessario, poiché tutte le operazioni di archiviazione e autenticazione delle informazioni degli utenti vengono gestite da Azure Active Directory.

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a>Rilascio di token di sicurezza da un servizio ASP.NET Core

Se si vuole rilasciare token di sicurezza per gli utenti locali di ASP.NET Core Identity anziché usare un provider di identità esterna, è possibile avvalersi di alcune utili librerie di terze parti.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) e [OpenIddict](https://github.com/openiddict/openiddict-core) sono provider OpenID Connect che si integrano facilmente con ASP.NET Core Identity per il rilascio di token di sicurezza da un servizio ASP.NET Core. La [documentazione di IdentityServer4](https://identityserver4.readthedocs.io/en/release/) contiene istruzioni dettagliate per l'uso della libreria. Di seguito sono indicate le operazioni di base per usare IdentityServer4 per il rilascio di token.

1.  Chiamare app.UseIdentityServer nel metodo Startup.Configure per aggiungere IdentityServer4 alla pipeline di elaborazione delle richieste HTTP dell'applicazione. In questo modo, la libreria fornisce richieste agli endpoint OpenID Connect e OAuth2 come /connect/token.

2.  IdentityServer4 viene configurato in Startup.ConfigureServices tramite una chiamata a services.AddIdentityServer.

3.  Il server delle identità viene configurato specificando i dati seguenti:

-   Le [credenziali](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) da usare per la firma.

-   Le [risorse di identità e API](https://identityserver4.readthedocs.io/en/release/topics/resources.html) a cui gli utenti potrebbero richiedere l'accesso:

<!-- -->

-   Le risorse API rappresentano dati protetti o funzionalità a cui l'utente può accedere con un token di accesso. Un esempio di risorsa API è un'API o un set di API Web che richiede l'autorizzazione.

-   Le risorse di identità rappresentano informazioni (attestazioni) che vengono fornite a un client per identificare un utente. Le attestazioni possono includere il nome utente, l'indirizzo di posta elettronica e così via.

<!-- -->

-   I [client](https://identityserver4.readthedocs.io/en/release/topics/clients.html) che si connetteranno per richiedere i token.

-   Il meccanismo di archiviazione delle informazioni degli utenti, ad esempio [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) o un sistema alternativo.

Quando si specificano i client e le risorse da usare con IdentityServer4, è possibile passare un oggetto IEnumerable&lt;T&gt; del tipo appropriato ai metodi che accettano archivi di client o risorse in memoria. In alternativa, per scenari più complessi, è possibile fornire tipi di provider di client o risorse tramite l'inserimento delle dipendenze.

Un esempio di configurazione per IdentityServer4 che usa le risorse e i client in memoria forniti da un tipo IClientStore personalizzato è simile al codice seguente:

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a>Utilizzo di token di sicurezza

L'autenticazione con un endpoint OpenID Connect o l'emissione di token di sicurezza propri coprono alcuni scenari. Ma occorre considerare anche i casi in cui un servizio necessita semplicemente di limitare l'accesso agli utenti che hanno token di sicurezza validi forniti da un servizio diverso.

Per questo scenario è disponibile il middleware di autenticazione che gestisce i token JWT nel pacchetto Microsoft.AspNetCore.Authentication.JwtBearer. JWT è l'acronimo di "[JSON Web Token (token Web JSON)](https://tools.ietf.org/html/rfc7519)" ed è un formato di token di sicurezza comune, definito da RFC 7519, per la comunicazione di attestazioni di sicurezza. Un semplice esempio di come usare il middleware con questi token è simile al codice seguente. Questo codice deve precedere le chiamate al middleware di ASP.NET Core MVC di base (app. UseMvc).

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

I parametri in questo caso sono:

-   Audience rappresenta il destinatario del token in ingresso o la risorsa a cui il token concede l'accesso. Se il valore specificato in questo parametro corrisponde al parametro aud nel token, il token verrà rifiutato.

-   Authority è l'indirizzo del server di autenticazione che emette i token. Il middleware di autenticazione del bearer token JWT usa questo URI per ottenere la chiave pubblica che può essere usata per convalidare la firma del token. Il middleware verifica inoltre che il parametro iss nel token corrisponda a questo URI.

-   AutomaticAuthenticate è un valore booleano che indica se l'utente definito dal token debba essere connesso automaticamente.

Il parametro RequireHttpsMetadata non viene usato in questo esempio. È utile a scopo di testing. Impostando questo parametro su false, è possibile testare l'applicazione in ambienti in cui non si dispone di certificati. Nelle distribuzioni effettive, i bearer token JWT devono sempre essere passati solo su HTTPS.

Con questo middleware, i token JWT vengono estratti automaticamente dalle intestazioni di autorizzazione. Vengono quindi deserializzati, convalidati (tramite i valori nei parametri Audience e Authority) e archiviati come informazioni utente per farvi riferimento in un secondo momento con azioni MVC o filtri di autorizzazione.

Il middleware di autenticazione con bearer token JWT può supportare anche scenari più avanzati, ad esempio l'uso di un certificato locale per convalidare un token se l'autorità non è disponibile. In questo caso, è possibile specificare un oggetto TokenValidationParameters nell'oggetto JwtBearerOptions.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Sharing cookies between applications (Condivisione dei cookie tra applicazioni)**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)

-   **Introduction to Identity (Introduzione a Identity)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Rick Anderson. Two-factor authentication with SMS (Autenticazione a due fattori con SMS)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)

-   **Enabling authentication using Facebook, Google and other external providers (Abilitazione dell'autenticazione con Facebook, Google e altri provider esterni)**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)

-   **Michell Anicas. An Introduction to OAuth 2 (Introduzione a OAuth 2)**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)

-   **AspNet.Security.OAuth.Providers** (repository GitHub per i provider OAuth ASP.NET).
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   **Danny Strockis. Integrating Azure AD into an ASP.NET Core web app (Integrazione di Azure AD in un'app Web di ASP.Net Core)**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)

-   **IdentityServer4. Documentazione ufficiale**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)


>[!div class="step-by-step"]
[Precedente] (../implement-resilient-applications/monitor-app-health.md) [Successivo] (authorization-net-microservices-web-applications.md)
