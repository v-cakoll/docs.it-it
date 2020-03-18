---
title: Implementazione dei tentativi di chiamate HTTP con backoff esponenziale con Polly
description: Informazioni su come gestire gli errori HTTP con Polly e IClientClientFactory.
ms.date: 03/03/2020
ms.openlocfilehash: 49396dd545a05699278254474c77acf1483e0e0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846796"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-ihttpclientfactory-and-polly-policies"></a>Implementare tentativi di chiamata HTTP con backoff esponenziale con criteri IClientClientFactory e PollyImplement HTTP call retries with exponential backoff with IClientClientFactory and Polly policies

L'approccio consigliato per i tentativi con backoff esponenziale prevede l'uso di librerie .NET più avanzate, ad esempio la [libreria open source Polly](https://github.com/App-vNext/Polly).

Polly è una libreria .NET che fornisce funzionalità di resilienza e di gestione degli errori temporanei. È possibile implementare queste funzionalità applicando i criteri di Polly, ad esempio Retry, Circuit Breaker, Bulkhead Isolation, Timeout e Fallback. Polly è destinato a .NET Framework 4.x e .NET Standard 1.0, 1.1 e 2.0 (che supporta .NET Core).

I passaggi seguenti illustrano come utilizzare i tentativi Http con Polly integrato in `IHttpClientFactory`, come illustrato nella sezione precedente.

**Fare riferimento ai pacchetti ASP.NET Core 3.1Reference the ASP.NET Core 3.1 packages**

`IHttpClientFactory`è disponibile poiché .NET Core 2.1 è consigliabile usare i pacchetti ASP.NET Core 3.1 più recenti da NuGet nel progetto. In genere è inoltre necessario `Microsoft.Extensions.Http.Polly`fare riferimento al pacchetto di estensione .

**Configurare un client con i criteri di ripetizione dei tentativi di Polly, in Avvio**

Come illustrato nelle sezioni precedenti, è necessario definire una configurazione HttpClient client denominata o tipizzata nel metodo Startup.ConfigureServices(...) standard, ma ora si aggiunge il codice incrementale che specifica i criteri dei tentativi HTTP con backoff esponenziale, come riportato di seguito:

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

Il metodo **AddPolicyHandler()** aggiunge i criteri agli oggetti `HttpClient` che verranno usati. In questo caso, viene aggiunto un criterio di Polly per i tentativi Http con backoff esponenziale.

Per avere un approccio più modulare, i criteri di ripetizione HTTP possono essere definiti in un metodo separato nel file `Startup.cs`, come illustrato nel codice seguente:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

Con Polly è possibile definire i criteri di ripetizione con il numero di tentativi, la configurazione del backoff esponenziale e le azioni da eseguire quando si verifica un'eccezione HTTP, ad esempio la registrazione dell'errore. In questo caso, i criteri vengono configurati per provare sei volte con un tentativo esponenziale, a partire da due secondi.

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a>Aggiungere una strategia di instabilità ai criteri di ripetizione

I normali criteri di ripetizione possono influire sul sistema quando scalabilità e concorrenza sono elevate e sono presenti molti conflitti. Per risolvere i picchi di tentativi simili provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità all'algoritmo o ai criteri di ripetizione. Ciò può migliorare le prestazioni complessive del sistema end-to-end grazie all'aggiunta di casualità nel backoff esponenziale. Permette di diluire i picchi quando si verificano problemi. Il principio è illustrato nell'esempio seguente:

```csharp
Random jitterer = new Random();
var retryWithJitterPolicy = HttpPolicyExtensions
    .HandleTransientHttpError()
    .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
    .WaitAndRetryAsync(6,    // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                      + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

Polly fornisce algoritmi di jitter pronti per la produzione tramite il sito web del progetto.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Modello di ripetizione dei tentativi**  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- **Polly e IHttpClientFactory**  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- **Polly (libreria .NET con funzionalità di resilienza e gestione degli errori temporanei)**  
  <https://github.com/App-vNext/Polly>

- **Polly: Riprova con Jitter**  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- **Marc Brooker. Jitter: Migliorare le cose con la casualità**  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
>[Successivo](use-httpclientfactory-to-implement-resilient-http-requests.md)
>[precedente](implement-circuit-breaker-pattern.md)
