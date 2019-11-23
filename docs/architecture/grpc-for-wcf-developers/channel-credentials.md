---
title: Credenziali del canale-gRPC per sviluppatori WCF
description: Come implementare e usare le credenziali del canale gRPC in ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: b424db49337a2dc6e3d0245d36349e3f408cdf6c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967956"
---
# <a name="channel-credentials"></a>Credenziali del canale

Come suggerisce il nome, le credenziali del canale sono collegate al canale gRPC sottostante. Il formato standard delle credenziali del canale usa l'autenticazione del certificato client, in cui il client fornisce un certificato TLS quando effettua la connessione, verificata dal server prima di consentire le chiamate.

Le credenziali del canale possono essere combinate con le credenziali di chiamata per offrire una sicurezza completa per un servizio gRPC. Le credenziali del canale dimostrano che l'applicazione client è autorizzata ad accedere al servizio e le credenziali di chiamata forniscono informazioni sulla persona che utilizza l'applicazione client.

L'autenticazione del certificato client funziona per gRPC nello stesso modo in cui funziona per ASP.NET Core. Il processo di configurazione verrà riepilogato qui, ma sono disponibili altre informazioni nell'articolo [configurare l'autenticazione del certificato in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .

Per finalità di sviluppo è possibile usare un certificato autofirmato, ma per la produzione è necessario usare un certificato HTTPS appropriato firmato da un'autorità attendibile.

## <a name="adding-certificate-authentication-to-the-server"></a>Aggiunta dell'autenticazione del certificato al server

È necessario configurare l'autenticazione del certificato a livello di host, ad esempio nel server gheppio e nella pipeline ASP.NET Core.

### <a name="configuring-certificate-validation-on-kestrel"></a>Configurazione della convalida del certificato in gheppio

È possibile configurare gheppio (il ASP.NET Core Server HTTP) per richiedere un certificato client e, facoltativamente, eseguire una convalida del certificato fornito prima di accettare le connessioni in ingresso. Questa configurazione viene eseguita nel metodo `CreateWebHostBuilder` della classe `Program`, anziché in `Startup`.

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

Con l'impostazione `ClientCertificateMode.RequireCertificate` si farà in modo che il gheppio rifiuti immediatamente qualsiasi richiesta di connessione che non fornisca un certificato client, ma non convaliderà il certificato. L'aggiunta del callback `ClientCertificateValidation` consente a gheppio di convalidare il certificato client (in questo caso, assicurandosi che sia stato emesso dalla stessa *autorità di certificazione* del certificato del server) al momento della connessione, prima che venga attivata la pipeline di ASP.NET Core.

### <a name="adding-aspnet-core-certificate-authentication"></a>Aggiunta dell'autenticazione del certificato ASP.NET Core

L'autenticazione del certificato è fornita dal pacchetto NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) .

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

## <a name="providing-channel-credentials-in-the-client-application"></a>Fornire le credenziali del canale nell'applicazione client

Con il pacchetto di `Grpc.Net.Client`, i certificati vengono configurati in un'istanza <xref:System.Net.Http.HttpClient> fornita al `GrpcChannel` usato per la connessione.

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

## <a name="combining-channelcredentials-and-callcredentials"></a>Combinazione di ChannelCredentials e CallCredentials

È possibile configurare il server per l'uso dell'autenticazione del certificato e del token applicando le modifiche del certificato al server gheppio e usando il middleware JWT Bearer in ASP.NET Core.

Per specificare sia ChannelCredentials che CallCredentials nel client, usare il metodo `ChannelCredentials.Create` per applicare le credenziali di chiamata. L'autenticazione del certificato deve comunque essere applicata usando l'istanza <xref:System.Net.Http.HttpClient>: se si passa un argomento al costruttore `SslCredentials`, il codice client interno genera un'eccezione. Il parametro `SslCredentials` è incluso solo nel metodo di `Create` del pacchetto di `Grpc.Net.Client` per mantenere la compatibilità con il pacchetto `Grpc.Core`.

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
> È possibile usare il metodo `ChannelCredentials.Create` per un client senza autenticazione del certificato, come un modo utile per passare le credenziali del token a ogni chiamata effettuata sul canale.

Una versione dell' [applicazione gRPC di esempio FullStockTicker con l'autenticazione del certificato aggiunta](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) è su GitHub.

>[!div class="step-by-step"]
>[Precedente](call-credentials.md)
>[Successivo](encryption.md)
