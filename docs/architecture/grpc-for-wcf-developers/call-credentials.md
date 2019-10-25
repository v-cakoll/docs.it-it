---
title: Credenziali di chiamata-gRPC per sviluppatori WCF
description: Come implementare e usare le credenziali di chiamata gRPC in ASP.NET Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5f29d69ec37fe60bcd7ca01391001ea9eb71e7e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846688"
---
# <a name="call-credentials"></a><span data-ttu-id="b7277-103">Credenziali di chiamata</span><span class="sxs-lookup"><span data-stu-id="b7277-103">Call credentials</span></span>

<span data-ttu-id="b7277-104">Le credenziali di chiamata sono tutte basate su un tipo di token passato nei metadati con ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="b7277-104">Call credentials are all based on some kind of token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="b7277-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="b7277-105">WS-Federation</span></span>

<span data-ttu-id="b7277-106">ASP.NET Core supporta WS-Federation usando il pacchetto NuGet di [WSFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) .</span><span class="sxs-lookup"><span data-stu-id="b7277-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="b7277-107">WS-Federation è l'alternativa più vicina disponibile all'autenticazione di Windows, che non è supportata su HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="b7277-107">WS-Federation is the closest available alternative to Windows Authentication, which is not supported over HTTP/2.</span></span> <span data-ttu-id="b7277-108">Gli utenti vengono autenticati tramite Active Directory Federation Services (ADFS), che fornisce un token che può essere utilizzato per l'autenticazione con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7277-108">Users are authenticated using Active Directory Federation Services (ADFS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="b7277-109">Per ulteriori informazioni su come iniziare a usare questo metodo di autenticazione, vedere l'articolo [autenticare gli utenti con WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="b7277-109">For more information on how to get started with this authentication method, see the [Authenticate users with WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) article.</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="b7277-110">Token di porta JWT</span><span class="sxs-lookup"><span data-stu-id="b7277-110">JWT Bearer tokens</span></span>

<span data-ttu-id="b7277-111">Lo standard del [token Web JSON](https://jwt.io) consente di codificare le informazioni relative a un utente e le relative attestazioni in una stringa codificata e di firmare tale token in modo che il consumer possa verificare l'integrità del token usando la crittografia a chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="b7277-111">The [JSON Web Token](https://jwt.io) standard provides a way to encode information about a user and their claims in an encoded string, and to sign that token in such a way that the consumer can verify the integrity of the token using public key cryptography.</span></span> <span data-ttu-id="b7277-112">È possibile usare vari servizi, ad esempio IdentityServer4, per autenticare gli utenti e generare token OpenID Connect (OIDC) da usare con le API gRPC e HTTP.</span><span class="sxs-lookup"><span data-stu-id="b7277-112">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="b7277-113">ASP.NET Core 3,0 è in grado di gestire i token Web JSON usando il pacchetto di JWT Bearer.</span><span class="sxs-lookup"><span data-stu-id="b7277-113">ASP.NET Core 3.0 can handle JSON Web Tokens using the JWT Bearer package.</span></span> <span data-ttu-id="b7277-114">La configurazione è esattamente identica per un'applicazione gRPC come applicazione MVC ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b7277-114">The configuration is exactly the same for a gRPC application as an ASP.NET Core MVC application.</span></span>

<span data-ttu-id="b7277-115">Questo capitolo è incentrato sui token di JWT Bearer poiché sono più semplici da sviluppare con WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="b7277-115">This chapter will focus on JWT Bearer tokens as they're easier to develop with than WS-Federation.</span></span>

## <a name="adding-authentication-and-authorization-to-the-server"></a><span data-ttu-id="b7277-116">Aggiunta dell'autenticazione e dell'autorizzazione al server</span><span class="sxs-lookup"><span data-stu-id="b7277-116">Adding authentication and authorization to the server</span></span>

<span data-ttu-id="b7277-117">Per impostazione predefinita, il pacchetto di JWT Bearer non è incluso in ASP.NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="b7277-117">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="b7277-118">Installare il pacchetto NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) nell'app.</span><span class="sxs-lookup"><span data-stu-id="b7277-118">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="b7277-119">Aggiungere il servizio di autenticazione nella classe Startup e configurare il gestore di JWT Bearer.</span><span class="sxs-lookup"><span data-stu-id="b7277-119">Add the Authentication service in the Startup class and configure the JWT Bearer handler.</span></span>

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

<span data-ttu-id="b7277-120">Per la proprietà `IssuerSigningKey` è necessaria un'implementazione di `Microsoft.IdentityModels.Tokens.SecurityKey` con i dati di crittografia necessari per convalidare i token firmati.</span><span class="sxs-lookup"><span data-stu-id="b7277-120">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="b7277-121">Questo token deve essere archiviato in modo sicuro in un *Server Secrets* come Azure Azure Vault.</span><span class="sxs-lookup"><span data-stu-id="b7277-121">This token should be stored securely in a *secrets server* like Azure KeyVault.</span></span>

<span data-ttu-id="b7277-122">Aggiungere quindi il servizio di autorizzazione, che controlla l'accesso al sistema.</span><span class="sxs-lookup"><span data-stu-id="b7277-122">Next add the Authorization service, which controls access to the system.</span></span>

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
> <span data-ttu-id="b7277-123">L'autenticazione e l'autorizzazione sono due passaggi distinti.</span><span class="sxs-lookup"><span data-stu-id="b7277-123">Authentication and Authorization are two separate steps.</span></span> <span data-ttu-id="b7277-124">Viene utilizzata l'autenticazione per determinare l'identità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b7277-124">Authentication is used to determine the user's identity.</span></span> <span data-ttu-id="b7277-125">L'autorizzazione decide se l'utente è autorizzato ad accedere a diverse parti del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7277-125">Authorization decides whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="b7277-126">Aggiungere ora il middleware di autenticazione e autorizzazione alla pipeline ASP.NET Core nel metodo `Configure`.</span><span class="sxs-lookup"><span data-stu-id="b7277-126">Now add the Authentication and Authorization middleware to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

<span data-ttu-id="b7277-127">Infine, applicare l'attributo `[Authorize]` ai servizi o ai metodi da proteggere e usare la proprietà `User` del `HttpContext` sottostante per verificare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="b7277-127">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

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

## <a name="providing-call-credentials-in-the-client-application"></a><span data-ttu-id="b7277-128">Fornire le credenziali di chiamata nell'applicazione client</span><span class="sxs-lookup"><span data-stu-id="b7277-128">Providing call credentials in the client application</span></span>

<span data-ttu-id="b7277-129">Una volta ottenuto un token JWT da un server di identità, è possibile usarlo per autenticare le chiamate gRPC dal client aggiungendolo come intestazione di metadati nella chiamata, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b7277-129">Once you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

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

<span data-ttu-id="b7277-130">A questo punto, il servizio gRPC è stato protetto usando i token di porta JWT come credenziali di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b7277-130">Now, you've secured your gRPC service using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="b7277-131">Una versione dell' [applicazione gRPC di esempio portfolio con autenticazione e autorizzazione aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) è su GitHub.</span><span class="sxs-lookup"><span data-stu-id="b7277-131">A version of the [Portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b7277-132">[Precedente](security.md)
>[Successivo](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="b7277-132">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
