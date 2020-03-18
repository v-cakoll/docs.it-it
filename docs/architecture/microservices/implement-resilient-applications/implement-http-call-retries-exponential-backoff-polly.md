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
# <a name="implement-http-call-retries-with-exponential-backoff-with-ihttpclientfactory-and-polly-policies"></a><span data-ttu-id="f40c7-103">Implementare tentativi di chiamata HTTP con backoff esponenziale con criteri IClientClientFactory e PollyImplement HTTP call retries with exponential backoff with IClientClientFactory and Polly policies</span><span class="sxs-lookup"><span data-stu-id="f40c7-103">Implement HTTP call retries with exponential backoff with IHttpClientFactory and Polly policies</span></span>

<span data-ttu-id="f40c7-104">L'approccio consigliato per i tentativi con backoff esponenziale prevede l'uso di librerie .NET più avanzate, ad esempio la [libreria open source Polly](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="f40c7-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="f40c7-105">Polly è una libreria .NET che fornisce funzionalità di resilienza e di gestione degli errori temporanei.</span><span class="sxs-lookup"><span data-stu-id="f40c7-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="f40c7-106">È possibile implementare queste funzionalità applicando i criteri di Polly, ad esempio Retry, Circuit Breaker, Bulkhead Isolation, Timeout e Fallback.</span><span class="sxs-lookup"><span data-stu-id="f40c7-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="f40c7-107">Polly è destinato a .NET Framework 4.x e .NET Standard 1.0, 1.1 e 2.0 (che supporta .NET Core).</span><span class="sxs-lookup"><span data-stu-id="f40c7-107">Polly targets .NET Framework 4.x and .NET Standard 1.0, 1.1, and 2.0 (which supports .NET Core).</span></span>

<span data-ttu-id="f40c7-108">I passaggi seguenti illustrano come utilizzare i tentativi Http con Polly integrato in `IHttpClientFactory`, come illustrato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f40c7-108">The following steps show how you can use Http retries with Polly integrated into `IHttpClientFactory`, which is explained in the previous section.</span></span>

<span data-ttu-id="f40c7-109">**Fare riferimento ai pacchetti ASP.NET Core 3.1Reference the ASP.NET Core 3.1 packages**</span><span class="sxs-lookup"><span data-stu-id="f40c7-109">**Reference the ASP.NET Core 3.1 packages**</span></span>

<span data-ttu-id="f40c7-110">`IHttpClientFactory`è disponibile poiché .NET Core 2.1 è consigliabile usare i pacchetti ASP.NET Core 3.1 più recenti da NuGet nel progetto.</span><span class="sxs-lookup"><span data-stu-id="f40c7-110">`IHttpClientFactory` is available since .NET Core 2.1 however we recommend you to use the latest ASP.NET Core 3.1 packages from NuGet in your project.</span></span> <span data-ttu-id="f40c7-111">In genere è inoltre necessario `Microsoft.Extensions.Http.Polly`fare riferimento al pacchetto di estensione .</span><span class="sxs-lookup"><span data-stu-id="f40c7-111">You typically also need to reference the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="f40c7-112">**Configurare un client con i criteri di ripetizione dei tentativi di Polly, in Avvio**</span><span class="sxs-lookup"><span data-stu-id="f40c7-112">**Configure a client with Polly's Retry policy, in Startup**</span></span>

<span data-ttu-id="f40c7-113">Come illustrato nelle sezioni precedenti, è necessario definire una configurazione HttpClient client denominata o tipizzata nel metodo Startup.ConfigureServices(...) standard, ma ora si aggiunge il codice incrementale che specifica i criteri dei tentativi HTTP con backoff esponenziale, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f40c7-113">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="f40c7-114">Il metodo **AddPolicyHandler()** aggiunge i criteri agli oggetti `HttpClient` che verranno usati.</span><span class="sxs-lookup"><span data-stu-id="f40c7-114">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="f40c7-115">In questo caso, viene aggiunto un criterio di Polly per i tentativi Http con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="f40c7-115">In this case, it's adding a Polly's policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="f40c7-116">Per avere un approccio più modulare, i criteri di ripetizione HTTP possono essere definiti in un metodo separato nel file `Startup.cs`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f40c7-116">To have a more modular approach, the Http Retry Policy can be defined in a separate method within the `Startup.cs` file, as shown in the following code:</span></span>

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

<span data-ttu-id="f40c7-117">Con Polly è possibile definire i criteri di ripetizione con il numero di tentativi, la configurazione del backoff esponenziale e le azioni da eseguire quando si verifica un'eccezione HTTP, ad esempio la registrazione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="f40c7-117">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there's an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="f40c7-118">In questo caso, i criteri vengono configurati per provare sei volte con un tentativo esponenziale, a partire da due secondi.</span><span class="sxs-lookup"><span data-stu-id="f40c7-118">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span>

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="f40c7-119">Aggiungere una strategia di instabilità ai criteri di ripetizione</span><span class="sxs-lookup"><span data-stu-id="f40c7-119">Add a jitter strategy to the retry policy</span></span>

<span data-ttu-id="f40c7-120">I normali criteri di ripetizione possono influire sul sistema quando scalabilità e concorrenza sono elevate e sono presenti molti conflitti.</span><span class="sxs-lookup"><span data-stu-id="f40c7-120">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="f40c7-121">Per risolvere i picchi di tentativi simili provenienti da molti client in caso di interruzioni parziali, una soluzione alternativa efficace consiste nell'aggiungere una strategia di instabilità all'algoritmo o ai criteri di ripetizione.</span><span class="sxs-lookup"><span data-stu-id="f40c7-121">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="f40c7-122">Ciò può migliorare le prestazioni complessive del sistema end-to-end grazie all'aggiunta di casualità nel backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="f40c7-122">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="f40c7-123">Permette di diluire i picchi quando si verificano problemi.</span><span class="sxs-lookup"><span data-stu-id="f40c7-123">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="f40c7-124">Il principio è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="f40c7-124">The principle is illustrated by the following example:</span></span>

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

<span data-ttu-id="f40c7-125">Polly fornisce algoritmi di jitter pronti per la produzione tramite il sito web del progetto.</span><span class="sxs-lookup"><span data-stu-id="f40c7-125">Polly provides production-ready jitter algorithms via the project website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f40c7-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f40c7-126">Additional resources</span></span>

- <span data-ttu-id="f40c7-127">**Modello di ripetizione dei tentativi**</span><span class="sxs-lookup"><span data-stu-id="f40c7-127">**Retry pattern**</span></span>  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- <span data-ttu-id="f40c7-128">**Polly e IHttpClientFactory**</span><span class="sxs-lookup"><span data-stu-id="f40c7-128">**Polly and IHttpClientFactory**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- <span data-ttu-id="f40c7-129">**Polly (libreria .NET con funzionalità di resilienza e gestione degli errori temporanei)**</span><span class="sxs-lookup"><span data-stu-id="f40c7-129">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <https://github.com/App-vNext/Polly>

- <span data-ttu-id="f40c7-130">**Polly: Riprova con Jitter**</span><span class="sxs-lookup"><span data-stu-id="f40c7-130">**Polly: Retry with Jitter**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- <span data-ttu-id="f40c7-131">**Marc Brooker. Jitter: Migliorare le cose con la casualità**</span><span class="sxs-lookup"><span data-stu-id="f40c7-131">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
><span data-ttu-id="f40c7-132">[Successivo](use-httpclientfactory-to-implement-resilient-http-requests.md)
>[precedente](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="f40c7-132">[Previous](use-httpclientfactory-to-implement-resilient-http-requests.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
