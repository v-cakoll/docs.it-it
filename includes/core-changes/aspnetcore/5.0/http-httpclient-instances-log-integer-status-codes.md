---
ms.openlocfilehash: 44d33fb28e66e590e4604c6dd2c73616e4c5e943
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728283"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a>HTTP: HttpClient istanze create dai codici di stato IHttpClientFactory log Integer

<xref:System.Net.Http.HttpClient>istanze create dai <xref:System.Net.Http.IHttpClientFactory> codici di stato http di log come numeri interi anziché con i nomi dei codici di stato.

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

La registrazione usa le descrizioni testuali dei codici di stato HTTP. Si considerino i messaggi di log seguenti:

```
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a>Nuovo comportamento

La registrazione usa i valori integer dei codici di stato HTTP. Si considerino i messaggi di log seguenti:

```
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a>Motivo della modifica

Il comportamento originale di questa registrazione è incoerente con altre parti di ASP.NET Core che hanno sempre usato valori integer. L'incoerenza rende i log difficili da eseguire per eseguire query tramite sistemi di registrazione strutturati, ad esempio [elasticsearch](https://www.elastic.co/elasticsearch/). Per altri contesti, vedere [DotNet/Extensions # 1549](https://github.com/dotnet/extensions/issues/1549).

L'utilizzo di valori integer è più flessibile del testo perché consente l'esecuzione di query su intervalli di valori.

È stato preso in considerazione l'aggiunta di un altro valore di log per acquisire il codice di stato Integer. Sfortunatamente, questa operazione introdurrebbe un'altra incoerenza con il resto del ASP.NET Core. La registrazione HttpClient e la registrazione di server/hosting HTTP `StatusCode` usano già lo stesso nome di chiave.

#### <a name="recommended-action"></a>Azione consigliata

L'opzione migliore consiste nell'aggiornare le query di registrazione per usare i valori integer dei codici di stato. Questa opzione può causare difficoltà nella scrittura di query in più versioni ASP.NET Core. Tuttavia, l'utilizzo di numeri interi a questo scopo è molto più flessibile per l'esecuzione di query sui log.

Se è necessario forzare la compatibilità con il comportamento precedente e usare i codici di stato testuale `IHttpClientFactory` , sostituire la registrazione con i propri:

1. Copiare le versioni di .NET Core 3,1 delle classi seguenti nel progetto:

    * [LoggingHttpMessageHandlerBuilderFilter](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [LoggingHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [LoggingScopeHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [HttpHeadersLogValue](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. Rinominare le classi per evitare conflitti con i tipi pubblici nel pacchetto NuGet [Microsoft. Extensions. http](https://www.nuget.org/packages/Microsoft.Extensions.Http) .

1. Sostituire l'implementazione predefinita di `LoggingHttpMessageHandlerBuilderFilter` con una propria nel `Startup.ConfigureServices` metodo del progetto. Ad esempio:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        var descriptors = services.Where(
            s => s.ServiceType == typeof(IHttpMessageHandlerBuilderFilter));
        foreach (var descriptor in descriptors)
        {
            services.Remove(descriptor);
        }

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
