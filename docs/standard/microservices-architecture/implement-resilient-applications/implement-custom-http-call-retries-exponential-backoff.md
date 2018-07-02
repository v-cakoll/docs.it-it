---
title: Implementazione dei tentativi per le chiamate HTTP con backoff esponenziale
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dei tentativi per le chiamate HTTP con backoff esponenziale
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 77663f193b5f788ee07eba001306caed764ed253
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104779"
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="56bec-103">Implementazione dei tentativi per le chiamate HTTP con backoff esponenziale</span><span class="sxs-lookup"><span data-stu-id="56bec-103">Implementing custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="56bec-104">Per creare microservizi resilienti, è necessario gestire i possibili scenari di errore HTTP.</span><span class="sxs-lookup"><span data-stu-id="56bec-104">In order to create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="56bec-105">A tale scopo, è possibile creare un'implementazione personalizzata dei tentativi con backoff esponenziale.</span><span class="sxs-lookup"><span data-stu-id="56bec-105">For that purpose, you could create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="56bec-106">Oltre a gestire la mancata disponibilità temporanea della risorsa, il backoff esponenziale deve tenere contro del fatto che il provider di servizi cloud potrebbe limitare la disponibilità delle risorse per impedire un sovraccarico di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="56bec-106">In addition to handling temporal resource unavailability, the exponential backoff also needs to take into account that the cloud provider might throttle availability of resources to prevent usage overload.</span></span> <span data-ttu-id="56bec-107">Ad esempio, la creazione di troppe richieste di connessione in tempi molto rapidi potrebbe essere considerata come un attacco Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) da parte del provider di servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="56bec-107">For example, creating too many connection requests very quickly might be viewed as a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack by the cloud provider.</span></span> <span data-ttu-id="56bec-108">Di conseguenza, è necessario fornire un meccanismo di riduzione delle richieste di connessione quando viene raggiunta una soglia di capacità.</span><span class="sxs-lookup"><span data-stu-id="56bec-108">As a result, you need to provide a mechanism to scale back connection requests when a capacity threshold has been encountered.</span></span>

<span data-ttu-id="56bec-109">Per iniziare, è possibile implementare codice personalizzato con una classe di utilità per il backoff esponenziale come in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) e del codice come quello riportato di seguito (disponibile anche in un [repository in GitHub](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="56bec-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available on a [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

<span data-ttu-id="56bec-110">Usando il codice in un'applicazione client C\# (un altro microservizio client dell'API Web, un'applicazione MVC ASP.NET o anche un'applicazione Xamarin C\#) è semplice.</span><span class="sxs-lookup"><span data-stu-id="56bec-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="56bec-111">L'esempio seguente spiega come procedere usando la classe HttpClient.</span><span class="sxs-lookup"><span data-stu-id="56bec-111">The following example shows how, using the HttpClient class.</span></span>

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

<span data-ttu-id="56bec-112">Tuttavia, questo codice è adatto solo come modello di verifica.</span><span class="sxs-lookup"><span data-stu-id="56bec-112">However, this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="56bec-113">L'argomento successivo spiega come usare librerie più sofisticate e collaudate.</span><span class="sxs-lookup"><span data-stu-id="56bec-113">The next topic explains how to use more sophisticated and proven libraries.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="56bec-114">[Precedente](implement-resilient-entity-framework-core-sql-connections.md)
[Successivo](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="56bec-114">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
