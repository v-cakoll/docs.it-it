---
title: Implementazione dei tentativi di chiamate HTTP con backoff esponenziale con Polly
description: Informazioni su come gestire gli errori HTTP con Polly e HttpClientFactory.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 07333b84896c223f076e9c36cc90ab7ea7ac37c7
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465724"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a>Implementazione dei tentativi di chiamate HTTP con backoff esponenziale con i criteri di Polly e HttpClientFactory

L'approccio consigliato per i tentativi con backoff esponenziale prevede l'uso di librerie .NET più avanzate, ad esempio la [libreria open source Polly](https://github.com/App-vNext/Polly).

Polly è una libreria .NET che fornisce funzionalità di resilienza e di gestione degli errori temporanei. È possibile implementare queste funzionalità applicando i criteri di Polly, ad esempio Retry, Circuit Breaker, Bulkhead Isolation, Timeout e Fallback. La libreria Polly è compatibile con .NET 4.x e .NET Standard Library 1.0, che supporta .NET Core.

L'uso della libreria Polly con il proprio codice personalizzato con HttpClient, tuttavia, può essere un'operazione estremamente complessa. Nella versione originale di eShopOnContainers si è verificato un [blocco predefinito di ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) basato su Polly. Ma con il rilascio di HttpClientFactory, la comunicazione HTTP resiliente è diventata molto più semplice da implementare, deprecando così il blocco predefinito da eShopOnContainers. 

I passaggi seguenti mostrano come usare i tentativi HTTP con Polly integrato in HttpClientFactory, come spiegato nella sezione precedente.

**Fare riferimento ai pacchetti di ASP.NET Core 2.2**

`HttpClientFactory` è disponibile sin da .NET Core 2.1, tuttavia è consigliabile usare i pacchetti di ASP.NET Core 2.2 più recenti da NuGet nel progetto. In genere è necessario il metapacchetto `AspNetCore` e il pacchetto di estensione `Microsoft.Extensions.Http.Polly`.

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

quindi proveranno per sei volte e i secondi tra ogni tentativo saranno esponenziali, a partire da due secondi.

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a>Aggiungere una strategia di instabilità ai criteri di ripetizione

I normali criteri di ripetizione possono influire sul sistema quando scalabilità e concorrenza sono elevate e sono presenti molti conflitti. Per risolvere i picchi di tentativi simili provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità all'algoritmo o ai criteri di ripetizione. Ciò può migliorare le prestazioni complessive del sistema end-to-end grazie all'aggiunta di casualità nel backoff esponenziale. Permette di diluire i picchi quando si verificano problemi. Quando si usano criteri Polly semplici, il codice per implementare l'instabilità potrebbe somigliare a quello nell'esempio seguente:

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a>Risorse aggiuntive

- **Modello di ripetizione dei tentativi**\
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- **Polly e HttpClientFactory**\
  [https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)

- **Polly (libreria .NET con funzionalità di resilienza e gestione degli errori temporanei)**\
  [https://github.com/App-vNext/Polly](https://github.com/App-vNext/Polly)

- **Marc Brooker. Jitter: Making Things Better With Randomness**\ (Instabilità: come migliorare l'esecuzione con la casualità)
  [https://brooker.co.za/blog/2015/03/21/backoff.html](https://brooker.co.za/blog/2015/03/21/backoff.html)

>[!div class="step-by-step"]
>[Precedente](explore-custom-http-call-retries-exponential-backoff.md)
>[Successivo](implement-circuit-breaker-pattern.md)