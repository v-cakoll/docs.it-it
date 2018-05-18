---
title: Implementazione dei tentativi per le chiamate HTTP con backoff esponenziale
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione dei tentativi per le chiamate HTTP con backoff esponenziale
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 10751bb74ed648839fabec67ff7a71e458fb2a44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a>Implementazione dei tentativi per le chiamate HTTP con backoff esponenziale

Per creare microservizi resilienti, è necessario gestire i possibili scenari di errore HTTP. A tale scopo, è possibile creare un'implementazione personalizzata dei tentativi con backoff esponenziale.

Oltre a gestire la mancata disponibilità temporanea della risorsa, il backoff esponenziale deve tenere contro del fatto che il provider di servizi cloud potrebbe limitare la disponibilità delle risorse per impedire un sovraccarico di utilizzo. Ad esempio, la creazione di troppe richieste di connessione in tempi molto rapidi potrebbe essere considerata come un attacco Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) da parte del provider di servizi cloud. Di conseguenza, è necessario fornire un meccanismo di riduzione delle richieste di connessione quando viene raggiunta una soglia di capacità.

Per iniziare, è possibile implementare codice personalizzato con una classe di utilità per il backoff esponenziale come in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260) e del codice come quello riportato di seguito (disponibile anche in un [repository in GitHub](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).

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

Usando il codice in un'applicazione client C\# (un altro microservizio client dell'API Web, un'applicazione MVC ASP.NET o anche un'applicazione Xamarin C\#) è semplice. L'esempio seguente spiega come procedere usando la classe HttpClient.

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

Tuttavia, questo codice è adatto solo come modello di verifica. L'argomento successivo spiega come usare librerie più sofisticate e collaudate.


>[!div class="step-by-step"]
[Indietro] (implement-resilient-entity-framework-core-sql-connections.md) [Avanti] (implement-http-call-retries-exponential-backoff-polly.md)
