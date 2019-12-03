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
# <a name="channel-credentials"></a>Credenziali del canale

Come suggerisce il nome, le credenziali del canale sono collegate al canale gRPC sottostante. Il formato standard delle credenziali del canale usa l'autenticazione del certificato client. In questo processo, il client fornisce un certificato TLS quando effettua la connessione e quindi il server verifica questa operazione prima di consentire le chiamate.

È possibile combinare le credenziali del canale con le credenziali di chiamata per offrire una sicurezza completa per un servizio gRPC. Le credenziali del canale dimostrano che l'applicazione client è autorizzata ad accedere al servizio e le credenziali di chiamata forniscono informazioni sulla persona che sta utilizzando l'applicazione client.

L'autenticazione del certificato client funziona per gRPC nello stesso modo in cui funziona per ASP.NET Core. Per ulteriori informazioni, vedere [configurare l'autenticazione del certificato in ASP.NET Core](/aspnet/core/security/authentication/certauth).

Per finalità di sviluppo è possibile usare un certificato autofirmato, ma per la produzione è necessario usare un certificato HTTPS appropriato firmato da un'autorità attendibile.

## <a name="add-certificate-authentication-to-the-server"></a>Aggiungere l'autenticazione del certificato al server

Configurare l'autenticazione del certificato a livello di host, ad esempio nel server gheppio, e nella pipeline ASP.NET Core.

### <a name="configure-certificate-validation-on-kestrel"></a>Configurare la convalida del certificato in gheppio

È possibile configurare gheppio (il ASP.NET Core Server HTTP) per richiedere un certificato client e, facoltativamente, per eseguire una convalida del certificato fornito, prima di accettare le connessioni in ingresso. Questa operazione viene eseguita nel metodo `CreateWebHostBuilder` della classe `Program`, anziché in `Startup`.

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

L'impostazione `ClientCertificateMode.RequireCertificate` fa in modo che il gheppio rifiuti immediatamente qualsiasi richiesta di connessione che non fornisce un certificato client, ma questa impostazione non convaliderà un certificato fornito. Aggiungere il callback `ClientCertificateValidation` per consentire a gheppio di convalidare il certificato client nel momento in cui viene stabilita la connessione, prima che venga attivata la pipeline ASP.NET Core. In questo caso, il callback garantisce che sia stato emesso dalla stessa autorità di *certificazione* del certificato del server. 

### <a name="add-aspnet-core-certificate-authentication"></a>Aggiungere l'autenticazione del certificato ASP.NET Core

Il pacchetto NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) fornisce l'autenticazione del certificato.

Aggiungere il servizio di autenticazione del certificato nel metodo `ConfigureServices` e aggiungere l'autenticazione e l'autorizzazione alla pipeline ASP.NET Core nel metodo `Configure`.

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

## <a name="provide-channel-credentials-in-the-client-application"></a>Fornire le credenziali del canale nell'applicazione client

Con il pacchetto di `Grpc.Net.Client`, è possibile configurare i certificati in un'istanza <xref:System.Net.Http.HttpClient> fornita al `GrpcChannel` usato per la connessione.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Combinare ChannelCredentials e CallCredentials

È possibile configurare il server per l'uso di certificati e l'autenticazione basata su token. A tale scopo, applicare le modifiche apportate al certificato al server gheppio e usare il middleware JWT Bearer in ASP.NET Core.

Per fornire `ChannelCredentials` e `CallCredentials` nel client, usare il metodo `ChannelCredentials.Create` per applicare le credenziali di chiamata. È comunque necessario applicare l'autenticazione del certificato usando l'istanza di <xref:System.Net.Http.HttpClient>. Se si passa un argomento al costruttore `SslCredentials`, il codice client interno genera un'eccezione. Il parametro `SslCredentials` è incluso solo nel metodo di `Create` del pacchetto di `Grpc.Net.Client` per mantenere la compatibilità con il pacchetto `Grpc.Core`.

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
> È possibile usare il metodo `ChannelCredentials.Create` per un client senza autenticazione del certificato. Si tratta di un modo utile per passare le credenziali del token a ogni chiamata effettuata sul canale.

Una versione dell' [applicazione gRPC di esempio FullStockTicker con l'autenticazione del certificato aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) è su GitHub.

>[!div class="step-by-step"]
>[Precedente](call-credentials.md)
>[Successivo](encryption.md)
