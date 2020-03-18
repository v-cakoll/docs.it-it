---
title: Credenziali del canale - gRPC per gli sviluppatori WCF
description: Come implementare e utilizzare le credenziali del canale gRPC in ASP.NET Core 3.0.
ms.date: 09/02/2019
ms.openlocfilehash: 9ebe0aecb517e4cc2fe280632c4ecb593da9871c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148205"
---
# <a name="channel-credentials"></a><span data-ttu-id="dc8f4-103">Credenziali del canale</span><span class="sxs-lookup"><span data-stu-id="dc8f4-103">Channel credentials</span></span>

<span data-ttu-id="dc8f4-104">Come implica il nome, le credenziali del canale sono associate al canale gRPC sottostante.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="dc8f4-105">La forma standard delle credenziali del canale utilizza l'autenticazione del certificato client.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="dc8f4-106">In questo processo, il client fornisce un certificato TLS quando effettua la connessione e quindi il server verifica questo prima di consentire qualsiasi chiamata da effettuare.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="dc8f4-107">È possibile combinare le credenziali del canale con le credenziali di chiamata per fornire una sicurezza completa per un servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="dc8f4-108">Le credenziali del canale dimostrano che l'applicazione client è autorizzata ad accedere al servizio e le credenziali di chiamata forniscono informazioni sulla persona che utilizza l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="dc8f4-109">L'autenticazione del certificato client funziona per gRPC nello stesso modo in cui funziona per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="dc8f4-110">Per ulteriori informazioni, vedere [Configurare l'autenticazione del certificato in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="dc8f4-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="dc8f4-111">Ai fini dello sviluppo è possibile usare un certificato autofirmato, ma per la produzione è consigliabile usare un certificato HTTPS appropriato firmato da un'autorità attendibile.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="dc8f4-112">Aggiungere l'autenticazione del certificato al serverAdd certificate authentication to the server</span><span class="sxs-lookup"><span data-stu-id="dc8f4-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="dc8f4-113">Configurare l'autenticazione del certificato sia a livello di host (ad esempio, nel server Kestrel) che nella pipeline ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="dc8f4-114">Configurare la convalida dei certificati in Kestrel</span><span class="sxs-lookup"><span data-stu-id="dc8f4-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="dc8f4-115">È possibile configurare Kestrel (il server HTTP ASP.NET Core) in modo che richieda un certificato client e, facoltativamente, per eseguire la convalida del certificato fornito, prima di accettare le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="dc8f4-116">Questa operazione viene `CreateWebHostBuilder` eseguito `Program` nel metodo `Startup`della classe, anziché in .</span><span class="sxs-lookup"><span data-stu-id="dc8f4-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="dc8f4-117">L'impostazione `ClientCertificateMode.RequireCertificate` fa sì che Kestrel rifiuti immediatamente qualsiasi richiesta di connessione che non fornisce un certificato client, ma questa impostazione non convalida un certificato fornito.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="dc8f4-118">Aggiungere `ClientCertificateValidation` il callback per consentire a Kestrel di convalidare il certificato client nel punto in cui viene stabilita la connessione, prima che la pipeline di ASP.NET Core sia impegnata.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="dc8f4-119">In questo caso, il callback garantisce che sia stato emesso dalla stessa autorità di *certificazione* del certificato server.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="dc8f4-120">Aggiungere ASP.NET'autenticazione del certificato di baseAdd ASP.NET Core certificate authentication</span><span class="sxs-lookup"><span data-stu-id="dc8f4-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="dc8f4-121">Il pacchetto [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet fornisce l'autenticazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="dc8f4-122">Aggiungere il servizio di `ConfigureServices` autenticazione del certificato nel metodo e `Configure` aggiungere l'autenticazione e l'autorizzazione alla pipeline ASP.NET Core nel metodo.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="dc8f4-123">Fornire le credenziali del canale nell'applicazione clientProvide channel credentials in the client application</span><span class="sxs-lookup"><span data-stu-id="dc8f4-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="dc8f4-124">Con `Grpc.Net.Client` il pacchetto, configurare <xref:System.Net.Http.HttpClient> i certificati in `GrpcChannel` un'istanza fornita all'oggetto utilizzato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="dc8f4-125">Combinare ChannelCredentials e CallCredentialsCombine ChannelCredentials and CallCredentials</span><span class="sxs-lookup"><span data-stu-id="dc8f4-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="dc8f4-126">È possibile configurare il server per l'utilizzo dell'autenticazione basata su certificati e token.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="dc8f4-127">A tale scopo, applicare le modifiche del certificato al server Kestrel e utilizzare il middleware del portatore JWT in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="dc8f4-128">Per fornire `ChannelCredentials` `CallCredentials` sia il client `ChannelCredentials.Create` che sul client, utilizzare il metodo per applicare le credenziali di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="dc8f4-129">È comunque necessario applicare l'autenticazione del certificato utilizzando l'istanza. <xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="dc8f4-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="dc8f4-130">Se si passano `SslCredentials` argomenti al costruttore, il codice client interno genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="dc8f4-131">Il `SslCredentials` parametro è `Grpc.Net.Client` incluso `Create` solo nel metodo `Grpc.Core` del pacchetto per mantenere la compatibilità con il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="dc8f4-132">È possibile `ChannelCredentials.Create` utilizzare il metodo per un client senza autenticazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="dc8f4-133">Questo è un modo utile per passare le credenziali del token a ogni chiamata effettuata sul canale.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="dc8f4-134">Una versione [dell'applicazione gRPC di esempio FullStockTicker con l'autenticazione del certificato aggiunto](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) si trova su GitHub.</span><span class="sxs-lookup"><span data-stu-id="dc8f4-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dc8f4-135">[Successivo](call-credentials.md)
>[precedente](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="dc8f4-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
