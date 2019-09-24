---
title: Credenziali del canale-gRPC per sviluppatori WCF
description: Come implementare e usare le credenziali del canale gRPC in ASP.NET Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 61305ee47a2c09a0b2a0fd866beb9b7c102ffeaa
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184582"
---
# <a name="channel-credentials"></a><span data-ttu-id="b52ca-103">Credenziali del canale</span><span class="sxs-lookup"><span data-stu-id="b52ca-103">Channel credentials</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b52ca-104">Come suggerisce il nome, le credenziali del canale sono collegate al canale gRPC sottostante.</span><span class="sxs-lookup"><span data-stu-id="b52ca-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="b52ca-105">Il formato standard delle credenziali del canale usa l'autenticazione del certificato client, in cui il client fornisce un certificato TLS quando effettua la connessione, verificata dal server prima di consentire le chiamate.</span><span class="sxs-lookup"><span data-stu-id="b52ca-105">The standard form of channel credentials uses Client Certificate authentication, where the client provides a TLS certificate when it's making the connection, which is verified by the server before allowing any calls to be made.</span></span>

<span data-ttu-id="b52ca-106">Le credenziali del canale possono essere combinate con le credenziali di chiamata per offrire una sicurezza completa per un servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="b52ca-106">Channel credentials can be combined with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="b52ca-107">Le credenziali del canale dimostrano che l'applicazione client è autorizzata ad accedere al servizio e le credenziali di chiamata forniscono informazioni sulla persona che utilizza l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b52ca-107">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person using the client application.</span></span>

<span data-ttu-id="b52ca-108">L'autenticazione del certificato client funziona per gRPC nello stesso modo in cui funziona per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b52ca-108">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="b52ca-109">Il processo di configurazione verrà riepilogato qui, ma sono disponibili altre informazioni nell'articolo [configurare l'autenticazione del certificato in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="b52ca-109">The configuration process will be summarized here, but more information is available in the [Configure certificate authentication in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) article.</span></span>

<span data-ttu-id="b52ca-110">Per finalità di sviluppo è possibile usare un certificato autofirmato, ma per la produzione è necessario usare un certificato HTTPS appropriato firmato da un'autorità attendibile.</span><span class="sxs-lookup"><span data-stu-id="b52ca-110">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="adding-certificate-authentication-to-the-server"></a><span data-ttu-id="b52ca-111">Aggiunta dell'autenticazione del certificato al server</span><span class="sxs-lookup"><span data-stu-id="b52ca-111">Adding certificate authentication to the server</span></span>

<span data-ttu-id="b52ca-112">È necessario configurare l'autenticazione del certificato a livello di host, ad esempio nel server gheppio e nella pipeline ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b52ca-112">You need to configure certificate authentication both at the host level, for example on the Kestrel server, and in the ASP.NET Core pipeline.</span></span>

### <a name="configuring-certificate-validation-on-kestrel"></a><span data-ttu-id="b52ca-113">Configurazione della convalida del certificato in gheppio</span><span class="sxs-lookup"><span data-stu-id="b52ca-113">Configuring certificate validation on Kestrel</span></span>

<span data-ttu-id="b52ca-114">È possibile configurare gheppio (il ASP.NET Core Server HTTP) per richiedere un certificato client e, facoltativamente, eseguire una convalida del certificato fornito prima di accettare le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b52ca-114">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate before accepting incoming connections.</span></span> <span data-ttu-id="b52ca-115">Questa configurazione viene eseguita nel `CreateWebHostBuilder` metodo `Program` della classe, anziché in `Startup`.</span><span class="sxs-lookup"><span data-stu-id="b52ca-115">This configuration is done in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

<span data-ttu-id="b52ca-116">L' `ClientCertificateMode.RequireCertificate` impostazione farà sì che il gheppio rifiuti immediatamente qualsiasi richiesta di connessione che non fornisce un certificato client, ma non convaliderà il certificato.</span><span class="sxs-lookup"><span data-stu-id="b52ca-116">The `ClientCertificateMode.RequireCertificate` setting will cause Kestrel to immediately reject any connection request that doesn't provide a client certificate, but it won't validate the certificate.</span></span> <span data-ttu-id="b52ca-117">L'aggiunta `ClientCertificateValidation` della richiamata consente a gheppio di convalidare il certificato client (in questo caso, assicurandosi che sia stato emesso dalla stessa *autorità di certificazione* del certificato del server) al momento della connessione, prima del ASP.NET Core pipeline attivata.</span><span class="sxs-lookup"><span data-stu-id="b52ca-117">Adding the `ClientCertificateValidation` callback enables Kestrel to validate the client certificate (in this case, ensuring that it was issued by the same *Certificate Authority* as the server certificate) at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span>

### <a name="adding-aspnet-core-certificate-authentication"></a><span data-ttu-id="b52ca-118">Aggiunta dell'autenticazione del certificato ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b52ca-118">Adding ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="b52ca-119">L'autenticazione del certificato è fornita dal pacchetto NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) .</span><span class="sxs-lookup"><span data-stu-id="b52ca-119">Certificate authentication is provided by the [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package.</span></span>

<span data-ttu-id="b52ca-120">Aggiungere il servizio di autenticazione del certificato `ConfigureServices` nel metodo e aggiungere l'autenticazione e l'autorizzazione alla pipeline ASP.NET Core `Configure` nel metodo.</span><span class="sxs-lookup"><span data-stu-id="b52ca-120">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="providing-channel-credentials-in-the-client-application"></a><span data-ttu-id="b52ca-121">Fornire le credenziali del canale nell'applicazione client</span><span class="sxs-lookup"><span data-stu-id="b52ca-121">Providing channel credentials in the client application</span></span>

<span data-ttu-id="b52ca-122">Con il `Grpc.Net.Client` pacchetto, i certificati vengono configurati in un' <xref:System.Net.Http.HttpClient> istanza di fornita `GrpcChannel` all'oggetto utilizzato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="b52ca-122">With the `Grpc.Net.Client` package, certificates are configured on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combining-channelcredentials-and-callcredentials"></a><span data-ttu-id="b52ca-123">Combinazione di ChannelCredentials e CallCredentials</span><span class="sxs-lookup"><span data-stu-id="b52ca-123">Combining ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="b52ca-124">È possibile configurare il server per l'uso dell'autenticazione del certificato e del token applicando le modifiche del certificato al server gheppio e usando il middleware JWT Bearer in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b52ca-124">You can configure your server to use both certificate and token authentication by applying the certificate changes to the Kestrel server and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="b52ca-125">Per specificare sia ChannelCredentials che CallCredentials nel client, usare il `ChannelCredentials.Create` metodo per applicare le credenziali di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b52ca-125">To provide both ChannelCredentials and CallCredentials on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="b52ca-126">L'autenticazione del certificato deve comunque essere applicata usando <xref:System.Net.Http.HttpClient> l'istanza: se si passa un argomento `SslCredentials` al costruttore, il codice client interno genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b52ca-126">Certificate authentication still needs to be applied using the <xref:System.Net.Http.HttpClient> instance: if you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="b52ca-127">Il `SslCredentials` parametro viene incluso solo `Grpc.Net.Client` nel `Create` metodo del pacchetto per mantenere la compatibilità con il `Grpc.Core` pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b52ca-127">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> <span data-ttu-id="b52ca-128">È possibile utilizzare il `ChannelCredentials.Create` metodo per un client senza autenticazione del certificato, come un modo utile per passare le credenziali del token a ogni chiamata effettuata sul canale.</span><span class="sxs-lookup"><span data-stu-id="b52ca-128">You can use the `ChannelCredentials.Create` method for a client without certificate authentication, as a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="b52ca-129">Una versione dell' [applicazione gRPC di esempio FullStockTicker con l'autenticazione del certificato aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) è su GitHub.</span><span class="sxs-lookup"><span data-stu-id="b52ca-129">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b52ca-130">[Precedente](call-credentials.md)
>[Successivo](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="b52ca-130">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>