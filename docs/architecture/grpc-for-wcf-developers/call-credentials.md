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
# <a name="call-credentials"></a>Credenziali di chiamata

Le credenziali di chiamata sono tutte basate su un tipo di token passato nei metadati con ogni richiesta.

## <a name="ws-federation"></a>WS-Federation

ASP.NET Core supporta WS-Federation usando il pacchetto NuGet di [WSFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) . WS-Federation è l'alternativa più vicina disponibile all'autenticazione di Windows, che non è supportata su HTTP/2. Gli utenti vengono autenticati tramite Active Directory Federation Services (ADFS), che fornisce un token che può essere utilizzato per l'autenticazione con ASP.NET Core.

Per ulteriori informazioni su come iniziare a usare questo metodo di autenticazione, vedere l'articolo [autenticare gli utenti con WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) .

## <a name="jwt-bearer-tokens"></a>Token di porta JWT

Lo standard del [token Web JSON](https://jwt.io) consente di codificare le informazioni relative a un utente e le relative attestazioni in una stringa codificata e di firmare tale token in modo che il consumer possa verificare l'integrità del token usando la crittografia a chiave pubblica. È possibile usare vari servizi, ad esempio IdentityServer4, per autenticare gli utenti e generare token OpenID Connect (OIDC) da usare con le API gRPC e HTTP.

ASP.NET Core 3,0 è in grado di gestire i token Web JSON usando il pacchetto di JWT Bearer. La configurazione è esattamente identica per un'applicazione gRPC come applicazione MVC ASP.NET Core.

Questo capitolo è incentrato sui token di JWT Bearer poiché sono più semplici da sviluppare con WS-Federation.

## <a name="adding-authentication-and-authorization-to-the-server"></a>Aggiunta dell'autenticazione e dell'autorizzazione al server

Per impostazione predefinita, il pacchetto di JWT Bearer non è incluso in ASP.NET Core 3,0. Installare il pacchetto NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) nell'app.

Aggiungere il servizio di autenticazione nella classe Startup e configurare il gestore di JWT Bearer.

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

Per la proprietà `IssuerSigningKey` è necessaria un'implementazione di `Microsoft.IdentityModels.Tokens.SecurityKey` con i dati di crittografia necessari per convalidare i token firmati. Questo token deve essere archiviato in modo sicuro in un *Server Secrets* come Azure Azure Vault.

Aggiungere quindi il servizio di autorizzazione, che controlla l'accesso al sistema.

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
> L'autenticazione e l'autorizzazione sono due passaggi distinti. Viene utilizzata l'autenticazione per determinare l'identità dell'utente. L'autorizzazione decide se l'utente è autorizzato ad accedere a diverse parti del sistema.

Aggiungere ora il middleware di autenticazione e autorizzazione alla pipeline ASP.NET Core nel metodo `Configure`.

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

Infine, applicare l'attributo `[Authorize]` ai servizi o ai metodi da proteggere e usare la proprietà `User` del `HttpContext` sottostante per verificare le autorizzazioni.

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

## <a name="providing-call-credentials-in-the-client-application"></a>Fornire le credenziali di chiamata nell'applicazione client

Una volta ottenuto un token JWT da un server di identità, è possibile usarlo per autenticare le chiamate gRPC dal client aggiungendolo come intestazione di metadati nella chiamata, come indicato di seguito:

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

A questo punto, il servizio gRPC è stato protetto usando i token di porta JWT come credenziali di chiamata. Una versione dell' [applicazione gRPC di esempio portfolio con autenticazione e autorizzazione aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) è su GitHub.

>[!div class="step-by-step"]
>[Precedente](security.md)
>[Successivo](channel-credentials.md)
