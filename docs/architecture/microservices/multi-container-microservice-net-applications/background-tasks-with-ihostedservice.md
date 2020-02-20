---
title: Implementare attività in background in microservizi con IHostedService e la classe BackgroundService
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni sulle nuove opzioni per usare IHostedService e BackgroundService per implementare attività in background nei microservizi .NET Core.
ms.date: 01/30/2020
ms.openlocfilehash: fab67c816e90c69a4d593422b4974cb9b8819807
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502297"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a>Implementare attività in background in microservizi con IHostedService e la classe BackgroundService

Le attività in background e i processi pianificati sono elementi che potrebbe essere necessario implementare, prima o poi, in un'applicazione basata su microservizi o in qualsiasi tipo di applicazione. La differenza quando si usa un'architettura di microservizi consiste nella possibilità di implementare un singolo processo/contenitore di microservizi per ospitare queste attività in background così da poterlo ridurre o aumentare in base alle necessità, o persino assicurarsi che venga eseguita una sola istanza di tale processo/contenitore di microservizi.

Da un punto di vista generico, in .NET Core questi tipi di attività vengono chiamati *Servizi ospitati*, perché sono servizi/logica ospitati all'interno di un host, un'applicazione o un microservizio. Si noti che, in questo caso, il servizio ospitato indica semplicemente una classe con la logica di attività in background.

Fin dalla versione .NET Core 2.0, il framework fornisce una nuova interfaccia denominata <xref:Microsoft.Extensions.Hosting.IHostedService> che consente di implementare facilmente i servizi ospitati. L'idea di base è che è possibile registrare più attività in background (servizi ospitati) che vengono eseguite in background mentre l'host o l'host Web è in esecuzione, come illustrato nell'immagine 6-26.

![Diagramma che confronta ASP.NET Core IWebHost e .NET Core IHost.](./media/background-tasks-with-ihostedservice/ihosted-service-webhost-vs-host.png)

**Figura 6-26**. Uso di IHostedService in un WebHost rispetto a un Host

ASP.NET Core 1. x e 2. x supportano `IWebHost` per i processi in background nelle app Web. .NET Core 2,1 e versioni successive supportano `IHost` per i processi in background con app console semplici. Si noti la differenza tra `WebHost` e `Host`.

Un `WebHost` (classe base che implementa `IWebHost`) in ASP.NET Core 2,0 è l'artefatto dell'infrastruttura usato per fornire funzionalità server HTTP al processo, ad esempio quando si implementa un'app Web MVC o un servizio API Web. Fornisce tutta la bontà dell'infrastruttura in ASP.NET Core, consentendo di usare l'inserimento di dipendenze, inserire middleware nella pipeline delle richieste e simili. Il `WebHost` utilizza queste stesse `IHostedServices` per le attività in background.

In .NET Core 2.1 è stato introdotto un `Host` (classe di base che implementa `IHost`). In pratica, un `Host` consente di avere un'infrastruttura simile a quella che si ha con `WebHost` (aggiunta di dipendenze, i servizi ospitati e così via), ma in questo caso si avrà un processo semplice e più snello come host, senza elementi correlati a MVC, API Web o funzionalità del server HTTP.

Pertanto, è possibile scegliere e creare un processo host specializzato con `IHost` per gestire i servizi ospitati e nient'altro, ad esempio un microservizio creato solo per ospitare la `IHostedServices`oppure è possibile estendere un `WebHost`ASP.NET Core esistente, ad esempio un'API Web o un'app MVC esistente ASP.NET Core.

Ogni approccio presenta vantaggi e svantaggi in base alle esigenze aziendali e di scalabilità. In sostanza, se le attività in background non hanno nulla a che fare con HTTP (`IWebHost`), è consigliabile usare `IHost`.

## <a name="registering-hosted-services-in-your-webhost-or-host"></a>Registrazione di servizi ospitati in un Host o WebHost

Approfondiamo ulteriormente l'interfaccia di `IHostedService` perché il suo utilizzo è abbastanza simile in un `WebHost` o un `Host`.

SignalR è un esempio di un elemento che usa i servizi ospitati, ma è possibile usarlo anche per operazioni molto più semplici, quali:

- Un'attività che esegue in background il polling di un database alla ricerca di modifiche.
- Un'attività pianificata di aggiornamento periodico della cache.
- Un'implementazione di QueueBackgroundWorkItem che consente di eseguire un'attività in un thread in background.
- L'elaborazione di messaggi da una coda di messaggi in background di un'app Web condividendo servizi comuni come `ILogger`.
- Un'attività in background avviata con `Task.Run()`.

In sostanza, è possibile eseguire l'offload di una qualsiasi di queste azioni in un'attività in background che implementa `IHostedService`.

Il modo in cui si aggiungono uno o più `IHostedServices` nel `WebHost` o `Host` consiste nel registrarli tramite il <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>metodo di estensione  in un ASP.NET Core `WebHost` o in un `Host` in .NET Core 2,1 e versioni successive. In pratica, è necessario registrare i servizi ospitati all'interno del noto metodo `ConfigureServices()` della classe `Startup`, come illustrato nel codice seguente da un tipico WebHost ASP.NET.

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddHostedService<GracePeriodManagerService>();
    services.AddHostedService<MyHostedServiceB>();
    services.AddHostedService<MyHostedServiceC>();
    //...
}
```

In questo codice, il servizio ospitato `GracePeriodManagerService` è il codice effettivo del microservizio aziendale Ordering in eShopOnContainers, mentre gli altri due sono solo esempi aggiuntivi.

L'esecuzione dell'attività in background `IHostedService` è coordinata con la durata dell'applicazione (a tal fine, host o microservizio). Si registrano le attività quando viene avviata l'applicazione e si ha la possibilità di eseguire un'azione automatica o di pulizia quando è in corso l'arresto dell'applicazione.

Senza usare `IHostedService`, è sempre possibile avviare un thread in background per eseguire qualsiasi attività. La differenza è precisamente nel tempo di arresto dell'app, quando il thread potrebbe essere semplicemente terminato senza la possibilità di eseguire operazioni di pulizia automatica.

## <a name="the-ihostedservice-interface"></a>Interfaccia IHostedService

Quando si registra un `IHostedService`, .NET Core chiamerà i metodi `StartAsync()` e `StopAsync()` del tipo `IHostedService` rispettivamente durante l'avvio e l'arresto dell'applicazione. In particolare, il metodo start viene chiamato dopo che il server è stato avviato e `IApplicationLifetime.ApplicationStarted` viene attivato.

Il `IHostedService` definito in .NET Core sarà simile al seguente.

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```

Come è facile immaginare, è possibile creare più implementazioni di IHostedService e registrarle nel metodo `ConfigureService()` nel contenitore DI, come illustrato in precedenza. Tutti i servizi ospitati verranno avviati e arrestati con l'applicazione/microservizio.

Lo sviluppatore è responsabile della gestione dell'azione di arresto o dei servizi quando il metodo `StopAsync()` viene attivato dall'host.

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a>Implementazione di IHostedService con una classe personalizzata del servizio ospitato che deriva dalla classe base BackgroundService

È possibile procedere alla creazione da zero di una classe personalizzata del servizio ospitato e implementare l'interfaccia `IHostedService`, come è necessario fare quando si usa .NET Core 2.0.

Tuttavia, poiché la maggior parte delle attività in background avrà esigenze simili per quanto riguarda la gestione dei token di annullamento e altre operazioni tipiche, è disponibile una classe di base astratta molto pratica per la derivazione, denominata `BackgroundService` a partire da .NET Core 2.1.

Tale classe esegue il lavoro principale necessario per configurare l'attività in background.

Il codice successivo è la classe di base astratta BackgroundService nell'implementazione di .NET Core.

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0.
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts =
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it,
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }

    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

Quando si deriva dalla classe base astratta precedente, grazie a tale implementazione ereditata, è sufficiente implementare il metodo `ExecuteAsync()` nella classe personalizzata del servizio ospitato, come illustrato di seguito nel codice semplificato da eShopOnContainers, che esegue il polling di un database e pubblica eventi di integrazione nel Bus di eventi quando necessario.

```csharp
public class GracePeriodManagerService : BackgroundService
{
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        //Constructor’s parameters validations...
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() =>
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table
            // and publishing events into the Event Bus (RabbitMQ / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

In questo caso specifico per eShopOnContainers, viene eseguito un metodo dell'applicazione che cerca in una tabella di database gli ordini con uno stato specifico; quando vengono applicate le modifiche, pubblica eventi di integrazione usando il bus di eventi (al di sotto di questo potrebbe usare RabbitMQ o il bus di servizio di Azure).

Naturalmente, è possibile eseguire in alternativa qualsiasi altra attività di business in background.

Per impostazione predefinita, il token di annullamento è impostato con un timeout di 5 secondi, nonostante sia possibile modificare tale valore durante la compilazione di `WebHost` usando l'estensione `UseShutdownTimeout` di `IWebHostBuilder`. Ciò significa che il nostro servizio dovrebbe essere annullato entro 5 secondi; in caso contrario verrà terminato improvvisamente.

Il codice seguente permette di modificare tale intervallo di tempo in 10 secondi.

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a>Diagramma classi di riepilogo

Nell'immagine seguente viene illustrato un riepilogo visivo delle classi e delle interfacce necessarie per l'implementazione di IHostedServices.

![Diagramma che mostra che IWebHost e IHost possono ospitare molti servizi.](./media/background-tasks-with-ihostedservice/class-diagram-custom-ihostedservice.png)

**Figura 6-27**. Diagramma classi che mostra più classi e interfacce correlate a IHostedService

Diagramma classi: IWebHost e IHost possono ospitare molti servizi, che ereditano da BackgroundService, che implementa IHostedService.

### <a name="deployment-considerations-and-takeaways"></a>Considerazioni finali sulla distribuzione

È importante notare che la modalità di distribuzione del `WebHost` di ASP.NET Core o del `Host` di .NET Core può incidere negativamente sulla soluzione finale. Ad esempio, se si distribuisce il `WebHost` in IIS o in un normale Servizio App di Azure, l'host può essere arrestato a causa di ricicli del pool di app. Tuttavia, se si distribuisce l'host come contenitore in un agente di orchestrazione come Kubernetes, è possibile controllare il numero di istanze attive dell'host. In più, è possibile considerare altri approcci nel cloud fatti apposta per questi scenari, ad esempio le Funzioni di Azure. Infine, se è necessario che il servizio sia sempre in esecuzione e si esegue la distribuzione in un'istanza di Windows Server, è possibile usare un servizio di Windows.

Tuttavia, anche per una `WebHost` distribuita in un pool di applicazioni, esistono scenari come il ripopolamento o lo scaricamento della cache in memoria dell'applicazione che sarebbe ancora applicabile.

L'interfaccia `IHostedService` offre un modo pratico per avviare attività in background in un'applicazione Web ASP.NET Core (in .NET Core 2,0 e versioni successive) o in qualsiasi processo/host (a partire da .NET Core 2,1 con `IHost`). Il vantaggio principale è la possibilità che si ottiene con l'annullamento automatico di pulire il codice delle attività in background quando è in corso la chiusura dell'host stesso.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Compilazione di un'attività pianificata in ASP.NET Core/Standard 2,0** \
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- **Implementazione di IHostedService in ASP.NET Core 2,0** \
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- **Esempio di GenericHost con ASP.NET Core 2,1** \
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

>[!div class="step-by-step"]
>[Precedente](test-aspnet-core-services-web-apps.md)
>[Successivo](implement-api-gateways-with-ocelot.md)
