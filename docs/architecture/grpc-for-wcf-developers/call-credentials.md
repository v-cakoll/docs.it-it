---
title: Credenziali di chiamata-gRPC per sviluppatori WCF
description: Come implementare e usare le credenziali di chiamata gRPC in ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 01f21f58ed4235f45509c948c84653cd99d35618
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711529"
---
# <a name="call-credentials"></a><span data-ttu-id="260dc-103">Credenziali di chiamata</span><span class="sxs-lookup"><span data-stu-id="260dc-103">Call credentials</span></span>

<span data-ttu-id="260dc-104">Le credenziali di chiamata sono tutte basate su un token passato nei metadati con ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="260dc-104">Call credentials are all based on a token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="260dc-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="260dc-105">WS-Federation</span></span>

<span data-ttu-id="260dc-106">ASP.NET Core supporta WS-Federation usando il pacchetto NuGet di [WSFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) .</span><span class="sxs-lookup"><span data-stu-id="260dc-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="260dc-107">WS-Federation è l'alternativa più vicina disponibile all'autenticazione di Windows, che non è supportata su HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="260dc-107">WS-Federation is the closest available alternative to Windows Authentication, which isn't supported over HTTP/2.</span></span> <span data-ttu-id="260dc-108">Gli utenti vengono autenticati tramite Active Directory Federation Services (AD FS), che fornisce un token che può essere usato per l'autenticazione con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="260dc-108">Users are authenticated by using Active Directory Federation Services (AD FS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="260dc-109">Per ulteriori informazioni su come iniziare a usare questo metodo di autenticazione, vedere [autenticare gli utenti con WS-Federation in ASP.NET Core](/aspnet/core/security/authentication/ws-federation).</span><span class="sxs-lookup"><span data-stu-id="260dc-109">For more information on how to get started with this authentication method, see [Authenticate users with WS-Federation in ASP.NET Core](/aspnet/core/security/authentication/ws-federation).</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="260dc-110">Token di porta JWT</span><span class="sxs-lookup"><span data-stu-id="260dc-110">JWT Bearer tokens</span></span>

<span data-ttu-id="260dc-111">Lo standard JWT ( [JSON Web token](https://jwt.io) ) fornisce un modo per codificare le informazioni su un utente e le relative attestazioni in una stringa codificata.</span><span class="sxs-lookup"><span data-stu-id="260dc-111">The [JSON Web Token](https://jwt.io) (JWT) standard provides a way to encode information about a user and their claims in an encoded string.</span></span> <span data-ttu-id="260dc-112">Fornisce anche un modo per firmare il token, in modo che il consumer possa verificare l'integrità del token usando la crittografia a chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="260dc-112">It also provides a way to sign that token, so that the consumer can verify the integrity of the token by using public key cryptography.</span></span> <span data-ttu-id="260dc-113">È possibile usare vari servizi, ad esempio IdentityServer4, per autenticare gli utenti e generare token OpenID Connect (OIDC) da usare con le API gRPC e HTTP.</span><span class="sxs-lookup"><span data-stu-id="260dc-113">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="260dc-114">ASP.NET Core 3,0 può gestire token JWT usando il pacchetto JWT Bearer.</span><span class="sxs-lookup"><span data-stu-id="260dc-114">ASP.NET Core 3.0 can handle JWTs by using the JWT Bearer package.</span></span> <span data-ttu-id="260dc-115">La configurazione è esattamente identica per un'applicazione gRPC, così come per un'applicazione MVC ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="260dc-115">The configuration is exactly the same for a gRPC application as it is for an ASP.NET Core MVC application.</span></span> <span data-ttu-id="260dc-116">Qui, ci concentreremo sui token di JWT Bearer, perché sono più facili da sviluppare con rispetto a WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="260dc-116">Here, we'll focus on JWT Bearer tokens, because they're easier to develop with than WS-Federation.</span></span>

## <a name="add-authentication-and-authorization-to-the-server"></a><span data-ttu-id="260dc-117">Aggiungere l'autenticazione e l'autorizzazione al server</span><span class="sxs-lookup"><span data-stu-id="260dc-117">Add authentication and authorization to the server</span></span>

<span data-ttu-id="260dc-118">Per impostazione predefinita, il pacchetto di JWT Bearer non è incluso in ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="260dc-118">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="260dc-119">Installare il pacchetto NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) nell'app.</span><span class="sxs-lookup"><span data-stu-id="260dc-119">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="260dc-120">Aggiungere il servizio di autenticazione nella classe Startup e configurare il gestore di JWT Bearer:</span><span class="sxs-lookup"><span data-stu-id="260dc-120">Add the Authentication service in the Startup class, and configure the JWT Bearer handler:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

<span data-ttu-id="260dc-121">Per la proprietà `IssuerSigningKey` è necessaria un'implementazione di `Microsoft.IdentityModels.Tokens.SecurityKey` con i dati di crittografia necessari per convalidare i token firmati.</span><span class="sxs-lookup"><span data-stu-id="260dc-121">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="260dc-122">Archiviare questo token in modo sicuro in un *Server Secrets*, ad esempio Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="260dc-122">Store this token securely in a *secrets server*, like Azure Key Vault.</span></span>

<span data-ttu-id="260dc-123">Aggiungere quindi il servizio di autorizzazione, che controlla l'accesso al sistema:</span><span class="sxs-lookup"><span data-stu-id="260dc-123">Next, add the Authorization service, which controls access to the system:</span></span>

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> <span data-ttu-id="260dc-124">L'autenticazione e l'autorizzazione sono due passaggi distinti.</span><span class="sxs-lookup"><span data-stu-id="260dc-124">Authentication and authorization are two separate steps.</span></span> <span data-ttu-id="260dc-125">Si usa l'autenticazione per determinare l'identità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="260dc-125">You use authentication to determine the user's identity.</span></span> <span data-ttu-id="260dc-126">Si utilizza l'autorizzazione per decidere se l'utente è autorizzato ad accedere a diverse parti del sistema.</span><span class="sxs-lookup"><span data-stu-id="260dc-126">You use authorization to decide whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="260dc-127">Aggiungere ora il middleware di autenticazione e autorizzazione alla pipeline ASP.NET Core nel metodo `Configure`:</span><span class="sxs-lookup"><span data-stu-id="260dc-127">Now add the authentication and authorization middleware to the ASP.NET Core pipeline in the `Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="260dc-128">Infine, applicare l'attributo `[Authorize]` ai servizi o ai metodi da proteggere e usare la proprietà `User` del `HttpContext` sottostante per verificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="260dc-128">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="provide-call-credentials-in-the-client-application"></a><span data-ttu-id="260dc-129">Fornire le credenziali di chiamata nell'applicazione client</span><span class="sxs-lookup"><span data-stu-id="260dc-129">Provide call credentials in the client application</span></span>

<span data-ttu-id="260dc-130">Dopo aver ottenuto un token JWT da un server di identità, è possibile usarlo per autenticare le chiamate gRPC dal client aggiungendolo come intestazione di metadati nella chiamata, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="260dc-130">After you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

<span data-ttu-id="260dc-131">A questo punto, il servizio gRPC è stato protetto usando i token di porta JWT come credenziali di chiamata.</span><span class="sxs-lookup"><span data-stu-id="260dc-131">Now you've secured your gRPC service by using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="260dc-132">Una versione dell' [applicazione gRPC di esempio portfolio con autenticazione e autorizzazione aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) è su GitHub.</span><span class="sxs-lookup"><span data-stu-id="260dc-132">A version of the [portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="260dc-133">[Precedente](security.md)
>[Successivo](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="260dc-133">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
