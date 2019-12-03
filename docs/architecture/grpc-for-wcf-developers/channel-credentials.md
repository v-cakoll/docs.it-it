---
title: Credenziali del canale-gRPC per sviluppatori WCF
description: Come implementare e usare le credenziali del canale gRPC in ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 133de2c732e72844f249f11bfe22b5980b828b89
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711497"
---
# <a name="channel-credentials"></a><span data-ttu-id="f891d-103">Credenziali del canale</span><span class="sxs-lookup"><span data-stu-id="f891d-103">Channel credentials</span></span>

<span data-ttu-id="f891d-104">Come suggerisce il nome, le credenziali del canale sono collegate al canale gRPC sottostante.</span><span class="sxs-lookup"><span data-stu-id="f891d-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="f891d-105">Il formato standard delle credenziali del canale usa l'autenticazione del certificato client.</span><span class="sxs-lookup"><span data-stu-id="f891d-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="f891d-106">In questo processo, il client fornisce un certificato TLS quando effettua la connessione e quindi il server verifica questa operazione prima di consentire le chiamate.</span><span class="sxs-lookup"><span data-stu-id="f891d-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="f891d-107">È possibile combinare le credenziali del canale con le credenziali di chiamata per offrire una sicurezza completa per un servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="f891d-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="f891d-108">Le credenziali del canale dimostrano che l'applicazione client è autorizzata ad accedere al servizio e le credenziali di chiamata forniscono informazioni sulla persona che sta utilizzando l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="f891d-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="f891d-109">L'autenticazione del certificato client funziona per gRPC nello stesso modo in cui funziona per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f891d-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="f891d-110">Per ulteriori informazioni, vedere [configurare l'autenticazione del certificato in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="f891d-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="f891d-111">Per finalità di sviluppo è possibile usare un certificato autofirmato, ma per la produzione è necessario usare un certificato HTTPS appropriato firmato da un'autorità attendibile.</span><span class="sxs-lookup"><span data-stu-id="f891d-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="f891d-112">Aggiungere l'autenticazione del certificato al server</span><span class="sxs-lookup"><span data-stu-id="f891d-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="f891d-113">Configurare l'autenticazione del certificato a livello di host, ad esempio nel server gheppio, e nella pipeline ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f891d-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="f891d-114">Configurare la convalida del certificato in gheppio</span><span class="sxs-lookup"><span data-stu-id="f891d-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="f891d-115">È possibile configurare gheppio (il ASP.NET Core Server HTTP) per richiedere un certificato client e, facoltativamente, per eseguire una convalida del certificato fornito, prima di accettare le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f891d-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="f891d-116">Questa operazione viene eseguita nel metodo `CreateWebHostBuilder` della classe `Program`, anziché in `Startup`.</span><span class="sxs-lookup"><span data-stu-id="f891d-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="f891d-117">L'impostazione `ClientCertificateMode.RequireCertificate` fa in modo che il gheppio rifiuti immediatamente qualsiasi richiesta di connessione che non fornisce un certificato client, ma questa impostazione non convaliderà un certificato fornito.</span><span class="sxs-lookup"><span data-stu-id="f891d-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="f891d-118">Aggiungere il callback `ClientCertificateValidation` per consentire a gheppio di convalidare il certificato client nel momento in cui viene stabilita la connessione, prima che venga attivata la pipeline ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f891d-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="f891d-119">In questo caso, il callback garantisce che sia stato emesso dalla stessa autorità di *certificazione* del certificato del server.</span><span class="sxs-lookup"><span data-stu-id="f891d-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span> 

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="f891d-120">Aggiungere l'autenticazione del certificato ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f891d-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="f891d-121">Il pacchetto NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) fornisce l'autenticazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="f891d-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="f891d-122">Aggiungere il servizio di autenticazione del certificato nel metodo `ConfigureServices` e aggiungere l'autenticazione e l'autorizzazione alla pipeline ASP.NET Core nel metodo `Configure`.</span><span class="sxs-lookup"><span data-stu-id="f891d-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="f891d-123">Fornire le credenziali del canale nell'applicazione client</span><span class="sxs-lookup"><span data-stu-id="f891d-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="f891d-124">Con il pacchetto di `Grpc.Net.Client`, è possibile configurare i certificati in un'istanza <xref:System.Net.Http.HttpClient> fornita al `GrpcChannel` usato per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f891d-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="f891d-125">Combinare ChannelCredentials e CallCredentials</span><span class="sxs-lookup"><span data-stu-id="f891d-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="f891d-126">È possibile configurare il server per l'uso di certificati e l'autenticazione basata su token.</span><span class="sxs-lookup"><span data-stu-id="f891d-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="f891d-127">A tale scopo, applicare le modifiche apportate al certificato al server gheppio e usare il middleware JWT Bearer in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f891d-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="f891d-128">Per fornire `ChannelCredentials` e `CallCredentials` nel client, usare il metodo `ChannelCredentials.Create` per applicare le credenziali di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f891d-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="f891d-129">È comunque necessario applicare l'autenticazione del certificato usando l'istanza di <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="f891d-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="f891d-130">Se si passa un argomento al costruttore `SslCredentials`, il codice client interno genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f891d-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="f891d-131">Il parametro `SslCredentials` è incluso solo nel metodo di `Create` del pacchetto di `Grpc.Net.Client` per mantenere la compatibilità con il pacchetto `Grpc.Core`.</span><span class="sxs-lookup"><span data-stu-id="f891d-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="f891d-132">È possibile usare il metodo `ChannelCredentials.Create` per un client senza autenticazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="f891d-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="f891d-133">Si tratta di un modo utile per passare le credenziali del token a ogni chiamata effettuata sul canale.</span><span class="sxs-lookup"><span data-stu-id="f891d-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="f891d-134">Una versione dell' [applicazione gRPC di esempio FullStockTicker con l'autenticazione del certificato aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) è su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f891d-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f891d-135">[Precedente](call-credentials.md)
>[Successivo](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="f891d-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
