---
title: Implementazione di tentativi di chiamata HTTP con backoff esponenziale con Polly
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di tentativi di chiamata HTTP con backoff esponenziale con Polly
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1ed48142546403ea710f4c132e038521232c20ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-http-call-retries-with-exponential-backoff-with-polly"></a>Implementazione di tentativi di chiamata HTTP con backoff esponenziale con Polly

È l'approccio consigliato per i tentativi con backoff esponenziale per sfruttare le librerie .NET più avanzate come open source [Polly](https://github.com/App-vNext/Polly) libreria.

Polly è una libreria .NET che offre resilienza e funzionalità di gestione degli errori di temporaneo. È possibile implementare tali funzionalità facilmente applicando criteri di Polly, ad esempio i tentativi, l'interruttore, ponte isolamento, Timeout e Fallback. Polly destinata a .NET 4. x e Standard .NET versione 1.0 (che supporta .NET Core).

I criteri di ripetizione in Polly sono l'approccio adottato in eShopOnContainers quando si implementa tentativi HTTP. È possibile implementare un'interfaccia in modo è possibile inserire le funzionalità HttpClient standard o una versione resiliente di HttpClient utilizzando Polly, a seconda di quale configurazione di criteri di tentativi che si desidera utilizzare.

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

È possibile utilizzare l'implementazione standard se non si desidera utilizzare un meccanismo flessibile, come durante lo sviluppo o test più semplici approcci. Il codice seguente illustra il standard HttpClient implementazione per consentire le richieste con i token di autenticazione come un case facoltativo.

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

L'implementazione interessano è codice simile, un'altra classe, ma utilizzando Polly per implementare i meccanismi resilienti si desidera utilizzare, nell'esempio seguente, i tentativi con backoff esponenziale.

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

Con Polly, definire un criterio di ripetizione con un numero di tentativi, la configurazione di backoff esponenziale e le azioni da intraprendere quando si verifica un'eccezione HTTP, ad esempio la registrazione dell'errore. In questo caso, il criterio è configurato in modo che tenterà il numero di volte specificato durante la registrazione di tipi nel contenitore IoC. A causa della configurazione di backoff esponenziale, ogni volta che il codice rileva un'eccezione di HttpRequest, riprovare a eseguire la richiesta Http dopo un'attesa di un periodo di tempo che aumenta in misura esponenziale, a seconda della configurazione di criteri.

Il metodo importante è HttpInvoker, che è ciò che rende le richieste HTTP in tutta questa classe di utilità. Che metodo viene eseguito internamente la richiesta HTTP con \_policyWrapper.ExecuteAsync, che prende in considerazione i criteri di ripetizione.

In eShopOnContainers specificare criteri Polly quando si registra i tipi di contenitore IoC, come illustrato nel codice seguente dal [app web MVC nel startup.cs](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Web/WebMVC/Startup.cs) classe.

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

Si noti che i IHttpClient vengono create istanze degli oggetti come singleton anziché come oggetto temporaneo in modo che le connessioni TCP vengono utilizzate in modo efficiente dal servizio e [un problema con i socket](https://aspnetmonsters.com/2016/08/2016-08-27-httpclientwrong/) non verrà eseguita.

Ma l'aspetto importante sulla resilienza è applicare il criterio di Polly WaitAndRetryAsync all'interno di ResilientHttpClientFactory nel metodo CreateResilientHttpClient, come illustrato nel codice seguente:

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
[Precedente] [Avanti] (implementare circuito-breaker pattern.md) (implement-custom-http-call-retries-exponential-backoff.md)
