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
# <a name="channel-credentials"></a>Credenziali del canale

Come implica il nome, le credenziali del canale sono associate al canale gRPC sottostante. La forma standard delle credenziali del canale utilizza l'autenticazione del certificato client. In questo processo, il client fornisce un certificato TLS quando effettua la connessione e quindi il server verifica questo prima di consentire qualsiasi chiamata da effettuare.

È possibile combinare le credenziali del canale con le credenziali di chiamata per fornire una sicurezza completa per un servizio gRPC. Le credenziali del canale dimostrano che l'applicazione client è autorizzata ad accedere al servizio e le credenziali di chiamata forniscono informazioni sulla persona che utilizza l'applicazione client.

L'autenticazione del certificato client funziona per gRPC nello stesso modo in cui funziona per ASP.NET Core. Per ulteriori informazioni, vedere [Configurare l'autenticazione del certificato in ASP.NET Core](/aspnet/core/security/authentication/certauth).

Ai fini dello sviluppo è possibile usare un certificato autofirmato, ma per la produzione è consigliabile usare un certificato HTTPS appropriato firmato da un'autorità attendibile.

## <a name="add-certificate-authentication-to-the-server"></a>Aggiungere l'autenticazione del certificato al serverAdd certificate authentication to the server

Configurare l'autenticazione del certificato sia a livello di host (ad esempio, nel server Kestrel) che nella pipeline ASP.NET Core.

### <a name="configure-certificate-validation-on-kestrel"></a>Configurare la convalida dei certificati in Kestrel

È possibile configurare Kestrel (il server HTTP ASP.NET Core) in modo che richieda un certificato client e, facoltativamente, per eseguire la convalida del certificato fornito, prima di accettare le connessioni in ingresso. Questa operazione viene `CreateWebHostBuilder` eseguito `Program` nel metodo `Startup`della classe, anziché in .

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

L'impostazione `ClientCertificateMode.RequireCertificate` fa sì che Kestrel rifiuti immediatamente qualsiasi richiesta di connessione che non fornisce un certificato client, ma questa impostazione non convalida un certificato fornito. Aggiungere `ClientCertificateValidation` il callback per consentire a Kestrel di convalidare il certificato client nel punto in cui viene stabilita la connessione, prima che la pipeline di ASP.NET Core sia impegnata. In questo caso, il callback garantisce che sia stato emesso dalla stessa autorità di *certificazione* del certificato server.

### <a name="add-aspnet-core-certificate-authentication"></a>Aggiungere ASP.NET'autenticazione del certificato di baseAdd ASP.NET Core certificate authentication

Il pacchetto [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet fornisce l'autenticazione del certificato.

Aggiungere il servizio di `ConfigureServices` autenticazione del certificato nel metodo e `Configure` aggiungere l'autenticazione e l'autorizzazione alla pipeline ASP.NET Core nel metodo.

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

## <a name="provide-channel-credentials-in-the-client-application"></a>Fornire le credenziali del canale nell'applicazione clientProvide channel credentials in the client application

Con `Grpc.Net.Client` il pacchetto, configurare <xref:System.Net.Http.HttpClient> i certificati in `GrpcChannel` un'istanza fornita all'oggetto utilizzato per la connessione.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Combinare ChannelCredentials e CallCredentialsCombine ChannelCredentials and CallCredentials

È possibile configurare il server per l'utilizzo dell'autenticazione basata su certificati e token. A tale scopo, applicare le modifiche del certificato al server Kestrel e utilizzare il middleware del portatore JWT in ASP.NET Core.

Per fornire `ChannelCredentials` `CallCredentials` sia il client `ChannelCredentials.Create` che sul client, utilizzare il metodo per applicare le credenziali di chiamata. È comunque necessario applicare l'autenticazione del certificato utilizzando l'istanza. <xref:System.Net.Http.HttpClient> Se si passano `SslCredentials` argomenti al costruttore, il codice client interno genera un'eccezione. Il `SslCredentials` parametro è `Grpc.Net.Client` incluso `Create` solo nel metodo `Grpc.Core` del pacchetto per mantenere la compatibilità con il pacchetto.

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
> È possibile `ChannelCredentials.Create` utilizzare il metodo per un client senza autenticazione del certificato. Questo è un modo utile per passare le credenziali del token a ogni chiamata effettuata sul canale.

Una versione [dell'applicazione gRPC di esempio FullStockTicker con l'autenticazione del certificato aggiunto](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) si trova su GitHub.

>[!div class="step-by-step"]
>[Successivo](call-credentials.md)
>[precedente](encryption.md)
