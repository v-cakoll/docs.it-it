---
title: Implementazione della ripetizione dei tentativi per le chiamate HTTP con backoff esponenziale con Polly
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementazione della ripetizione dei tentativi per le chiamate HTTP con backoff esponenziale con Polly
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: cce1392bb381859e7cad89c9f2518113241ae724
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106931"
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Implementazione della ripetizione dei tentativi per le chiamate HTTP con backoff esponenziale con Polly

L'approccio consigliato per la ripetizione dei tentativi con backoff esponenziale prevede l'uso di librerie .NET più avanzate, ad esempio la libreria open source [Polly](https://github.com/App-vNext/Polly).

Polly è una libreria .NET che fornisce funzionalità di resilienza e di gestione degli errori temporanei. È possibile implementare facilmente queste funzionalità applicando i criteri di Polly, ad esempio Retry, Circuit Breaker, Bulkhead Isolation, Timeout e Fallback. La libreria Polly è compatibile con .NET 4.x e .NET Standard versione 1.0, che supporta .NET Core.

I criteri di ripetizione (Retry) in Polly costituiscono l'approccio usato nell'app eShopOnContainers per l'implementazione dei tentativi HTTP. È possibile implementare un'interfaccia per inserire la funzionalità HttpClient standard o una versione resiliente di HttpClient tramite Polly, a seconda della configurazione dei criteri di ripetizione che si vuole usare.

L'esempio seguente mostra l'interfaccia implementata in eShopOnContainers.

```csharp
public interface IHttpClient
{
    Task<string> GetStringAsync(string uri, string authorizationToken = null,
        string authorizationMethod = "Bearer");
        Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    Task<HttpResponseMessage> DeleteAsync(string uri,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer");

    // Other methods ...
}
```

È possibile usare l'implementazione standard se non si vuole usare un meccanismo resiliente, in particolare per lo sviluppo o il test di approcci più semplici. Il codice seguente mostra l'implementazione della funzionalità HttpClient standard che consente le richieste con token di autenticazione come scenario facoltativo.

```csharp
public class StandardHttpClient : IHttpClient
{
    private HttpClient _client;
    private ILogger<StandardHttpClient> _logger;

    public StandardHttpClient(ILogger<StandardHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
    }

    public async Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
        if (authorizationToken != null)
        {
            requestMessage.Headers.Authorization =
                new AuthenticationHeaderValue(authorizationMethod, authorizationToken);
        }
        var response = await _client.SendAsync(requestMessage);
        return await response.Content.ReadAsStringAsync();
    }

    public async Task<HttpResponseMessage> PostAsync<T>(string uri, T item,
        string authorizationToken = null, string requestId = null,
        string authorizationMethod = "Bearer")
    {
        // Rest of the code and other Http methods ...
```

L'aspetto interessante consiste nella scrittura di codice di un'altra classe simile usando Polly per implementare i meccanismi di resilienza desiderati, nell'esempio seguente i tentativi con backoff esponenziale.

```csharp
public class ResilientHttpClient : IHttpClient
{
    private HttpClient _client;
    private PolicyWrap _policyWrapper;
    private ILogger<ResilientHttpClient> _logger;

    public ResilientHttpClient(Policy[] policies,
        ILogger<ResilientHttpClient> logger)
    {
        _client = new HttpClient();
        _logger = logger;
        // Add Policies to be applied
        _policyWrapper = Policy.WrapAsync(policies);
    }

    private Task<T> HttpInvoker<T>(Func<Task<T>> action)
    {
        // Executes the action applying all
        // the policies defined in the wrapper
        return _policyWrapper.ExecuteAsync(() => action());
    }

    public Task<string> GetStringAsync(string uri,
        string authorizationToken = null,
        string authorizationMethod = "Bearer")
    {
        return HttpInvoker(async () =>
        {
            var requestMessage = new HttpRequestMessage(HttpMethod.Get, uri);
            // The Token's related code eliminated for clarity in code snippet
            var response = await _client.SendAsync(requestMessage);
            return await response.Content.ReadAsStringAsync();
        });
    }
    // Other Http methods executed through HttpInvoker so it applies Polly policies
    // ...
}
```

Con Polly, si definiscono criteri di ripetizione con il numero di tentativi, la configurazione del backoff esponenziale e le azioni da eseguire quando si verifica un'eccezione HTTP, ad esempio la registrazione dell'errore. In questo caso, i criteri sono configurati, quindi verrà eseguito il numero di tentativi specificato durante la registrazione dei tipi nel contenitore IoC. Poiché è presente una configurazione di backoff esponenziale, ogni volta che il codice rileva un'eccezione HttpRequest, effettua un nuovo tentativo di richiesta HTTP dopo aver atteso un periodo di tempo che aumenta esponenzialmente a seconda di come sono stati configurati i criteri.

Il metodo importante in questo scenario è HttpInvoker, che elabora le richieste tramite questa classe di utilità. Questo metodo esegue internamente la richiesta HTTP con \_policyWrapper.ExecuteAsync, che tiene conto dei criteri di ripetizione.

In eShopOnContainers si specificano i criteri di Polly durante la registrazione dei tipi nel contenitore IoC, come nel codice seguente della [classe startup.cs dell'app Web MVC](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs).

```csharp
// Startup.cs class
if (Configuration.GetValue<string>("UseResilientHttp") == bool.TrueString)
{
    services.AddTransient<IResilientHttpClientFactory,
        ResilientHttpClientFactory>();
    services.AddSingleton<IHttpClient,
        ResilientHttpClient>(sp =>
            sp.GetService<IResilientHttpClientFactory>().
            CreateResilientHttpClient());
}
else
{
    services.AddSingleton<IHttpClient, StandardHttpClient>();
}
```

Si noti che per gli oggetti IHttpClient le istanze vengono create come singleton anziché come temporanee per garantire l'uso efficiente delle connessioni TCP da parte del servizio ed evitare che si verifichino [problemi con i socket](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/).

Il punto importante circa la resilienza sta nel fatto che si applicano i criteri di Polly WaitAndRetryAsync in ResilientHttpClientFactory nel metodo CreateResilientHttpClient, come mostrato nel codice seguente:

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

// Other code
private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
        // number of retries
        6,
        // exponential backoff
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
        // on retry
        (exception, timeSpan, retryCount, context) =>
        {
            var msg = $"Retry {retryCount} implemented with Pollys RetryPolicy " +
            $"of {context.PolicyKey} " +
            $"at {context.ExecutionKey}, " +
            $"due to: {exception}.";
            _logger.LogWarning(msg);
            _logger.LogDebug(msg);
        }),
    }
```


>[!div class="step-by-step"]
[Precedente](implement-custom-http-call-retries-exponential-backoff.md)
[Successivo](implement-circuit-breaker-pattern.md)
