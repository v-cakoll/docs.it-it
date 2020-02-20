---
title: Implementazione dei tentativi di chiamate HTTP con backoff esponenziale con Polly
description: Informazioni su come gestire gli errori HTTP con Polly e HttpClientFactory.
ms.date: 01/30/2020
ms.openlocfilehash: 60943360c9674f93b246b37b2667b48dab659e0e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502660"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a>Implementazione dei tentativi di chiamate HTTP con backoff esponenziale con i criteri di Polly e HttpClientFactory

L'approccio consigliato per i tentativi con backoff esponenziale prevede l'uso di librerie .NET più avanzate, ad esempio la [libreria open source Polly](https://github.com/App-vNext/Polly).

Polly è una libreria .NET che fornisce funzionalità di resilienza e di gestione degli errori temporanei. È possibile implementare queste funzionalità applicando i criteri di Polly, ad esempio Retry, Circuit Breaker, Bulkhead Isolation, Timeout e Fallback. Polly targets .NET Framework 4. x e .NET Standard 1,0, 1,1 e 2,0 (che supporta .NET Core).

Tuttavia, la scrittura di codice personalizzato per usare la libreria di Polly con HttpClient può essere molto complessa. Nella versione originale di eShopOnContainers si è verificato un [blocco predefinito di ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/commit/0c317d56f3c8937f6823cf1b45f5683397274815#diff-e6532e623eb606a0f8568663403e3a10) basato su Polly. Tuttavia, con il rilascio di [HttpClientFactory](use-httpclientfactory-to-implement-resilient-http-requests.md), l'implementazione della comunicazione http resiliente con Polly è diventata molto più semplice, in modo che il blocco di compilazione sia stato deprecato da eShopOnContainers.

I passaggi seguenti mostrano come usare i tentativi HTTP con Polly integrato in HttpClientFactory, come spiegato nella sezione precedente.

**Fare riferimento ai pacchetti di ASP.NET Core 3,1**

`HttpClientFactory` è disponibile a partire da .NET Core 2,1, tuttavia è consigliabile usare i pacchetti di ASP.NET Core 3,1 più recenti di NuGet nel progetto. In genere è anche necessario fare riferimento al pacchetto di estensione `Microsoft.Extensions.Http.Polly`.

**Configurare un client con i criteri di ripetizione di Polly, in Startup**

Come illustrato nelle sezioni precedenti, è necessario definire una configurazione HttpClient client denominata o tipizzata nel metodo Startup.ConfigureServices(...) standard, ma ora si aggiunge il codice incrementale che specifica i criteri dei tentativi HTTP con backoff esponenziale, come riportato di seguito:

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

Il metodo **AddPolicyHandler()** aggiunge i criteri agli oggetti `HttpClient` che verranno usati. In questo caso si aggiungono i criteri di Polly per i tentativi HTTP con backoff esponenziale.

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

Polly fornisce algoritmi di jitter pronti per la produzione tramite il sito Web del progetto.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Retry pattern** (Modello di ripetizione dei tentativi)  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- **Polly e HttpClientFactory**  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- **Polly (libreria .NET con funzionalità di resilienza e di gestione degli errori temporanei)**  
  <https://github.com/App-vNext/Polly>

- **Polly: Riprova con jitter**  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- **Marc Brooker. Jitter: migliorare le prestazioni con la casualità**  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
>[Precedente](explore-custom-http-call-retries-exponential-backoff.md)
>[Successivo](implement-circuit-breaker-pattern.md)
