---
title: Implementare attività in background in microservizi con IHostedService e la classe BackgroundService
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Implementare attività in background in microservizi con IHostedService e la classe BackgroundService
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 6ce9e40334e80e8bd17ce2f3d2569a1e3c39d09e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44128873"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="ae3a2-103">Implementare attività in background in microservizi con IHostedService e la classe BackgroundService</span><span class="sxs-lookup"><span data-stu-id="ae3a2-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="ae3a2-104">Le attività in background e i processi pianificati sono elementi che potrebbe essere necessario implementare, prima o poi, in un'applicazione basata su microservizi o in qualsiasi tipo di applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="ae3a2-105">La differenza quando si usa un'architettura di microservizi consiste nella possibilità di implementare un singolo processo/contenitore di microservizi per ospitare queste attività in background così da poterlo ridurre o aumentare in base alle necessità, o persino assicurarsi che venga eseguita una sola istanza di tale processo/contenitore di microservizi.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="ae3a2-106">Da un punto di vista generico, in .NET Core abbiamo chiamato questi tipi di attività Servizi ospitati, perché sono servizi/logica ospitati all'interno dell'host/applicazione/microservizio.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-106">From a generic point of view, in .NET Core we called these type of tasks Hosted Services, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="ae3a2-107">Si noti che, in questo caso, il servizio ospitato indica semplicemente una classe con la logica di attività in background.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="ae3a2-108">Fin dalla versione .NET Core 2.0, il framework fornisce una nuova interfaccia denominata <xref:Microsoft.Extensions.Hosting.IHostedService> che consente di implementare facilmente i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="ae3a2-109">L'idea di base è che è possibile registrare più attività in background (servizi ospitati), che vengono eseguite in background mentre l'host Web o l'host è in esecuzione, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-109">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image below.</span></span>

![](./media/image26.png)

<span data-ttu-id="ae3a2-110">**Figura 8-25.**</span><span class="sxs-lookup"><span data-stu-id="ae3a2-110">**Figure 8-25.**</span></span> <span data-ttu-id="ae3a2-111">Uso di IHostedService in un WebHost rispetto a un Host</span><span class="sxs-lookup"><span data-stu-id="ae3a2-111">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="ae3a2-112">Si noti la differenza tra `WebHost` e `Host`.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-112">Note the difference made between `WebHost` and `Host`.</span></span> <span data-ttu-id="ae3a2-113">Un `WebHost` (classe base che implementa `IWebHost`) in ASP.NET Core 2.0 è l'elemento infrastruttura che si usa per fornire funzionalità di server HTTP al processo, ad esempio durante l'implementazione di un'app Web MVC o un servizio API Web.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-113">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="ae3a2-114">Offre tutta l'efficacia di una nuova infrastruttura in ASP.NET Core, consentendo di usare l'aggiunta di dipendenze, inserire middleware nella pipeline HTTP, ecc. e di usare con precisione questi `IHostedServices` per le attività in background.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-114">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the HTTP pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="ae3a2-115">Un `Host` (classe base che implementa `IHost`), tuttavia, è un elemento del tutto nuovo in .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-115">A `Host` (base class implementing `IHost`), however, is something new in .NET Core 2.1.</span></span> <span data-ttu-id="ae3a2-116">In pratica, un `Host` consente di avere un'infrastruttura simile a quella che si ha con `WebHost` (aggiunta di dipendenze, i servizi ospitati e così via), ma in questo caso si avrà un processo semplice e più snello come host, senza elementi correlati a MVC, API Web o funzionalità del server HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-116">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="ae3a2-117">Di conseguenza, è possibile scegliere e creare un processo host specializzato con IHost per gestire i servizi ospitati e nient'altro, ad esempio un microservizio realizzato solo per l'hosting di `IHostedServices`, oppure è possibile in alternativa estendere un `WebHost` esistente di ASP.NET Core, ad esempio un'API Web di ASP.NET Core o un'app MVC già esistente.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-117">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span> 

<span data-ttu-id="ae3a2-118">Ogni approccio presenta vantaggi e svantaggi in base alle esigenze aziendali e di scalabilità.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-118">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="ae3a2-119">In sostanza, se le attività in background non hanno nulla a che fare con HTTP (IWebHost), è consigliabile usare IHost, quando disponibile in .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-119">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use and IHost, when available in .NET Core 2.1.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="ae3a2-120">Registrazione di servizi ospitati in un Host o WebHost</span><span class="sxs-lookup"><span data-stu-id="ae3a2-120">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="ae3a2-121">Approfondiamo ulteriormente l'interfaccia di `IHostedService` perché il suo utilizzo è abbastanza simile in un `WebHost` o un `Host`.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-121">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span> 

<span data-ttu-id="ae3a2-122">SignalR è un esempio di un elemento che usa i servizi ospitati, ma è possibile usarlo anche per operazioni molto più semplici, quali:</span><span class="sxs-lookup"><span data-stu-id="ae3a2-122">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

-   <span data-ttu-id="ae3a2-123">Un'attività che esegue in background il polling di un database alla ricerca di modifiche.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-123">A background task polling a database looking for changes.</span></span>
-   <span data-ttu-id="ae3a2-124">Un'attività pianificata di aggiornamento periodico della cache.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-124">A scheduled task updating some cache periodically.</span></span>
-   <span data-ttu-id="ae3a2-125">Un'implementazione di QueueBackgroundWorkItem che consente di eseguire un'attività in un thread in background.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-125">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
-   <span data-ttu-id="ae3a2-126">L'elaborazione di messaggi da una coda di messaggi in background di un'app Web condividendo servizi comuni come `ILogger`.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-126">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
-   <span data-ttu-id="ae3a2-127">Un'attività in background avviata con `Task.Run()`.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-127">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="ae3a2-128">È praticamente possibile ripartire il carico di lavoro di qualsiasi azione in un'attività in background basata su IHostedService.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-128">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="ae3a2-129">Per aggiungere uno o più `IHostedServices` al proprio `WebHost` o `Host` basta registrarli usando l'aggiunta standard di dipendenze in un `WebHost` di ASP.NET Core (oppure in un `Host` di .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="ae3a2-129">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1).</span></span> <span data-ttu-id="ae3a2-130">In pratica, è necessario registrare i servizi ospitati all'interno del noto metodo `ConfigureServices()` della classe `Startup`, come illustrato nel codice seguente da un tipico WebHost ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-130">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span> 

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{            
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="ae3a2-131">In questo codice, il servizio ospitato `GracePeriodManagerService` è il codice effettivo del microservizio aziendale Ordering in eShopOnContainers, mentre gli altri due sono solo esempi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-131">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="ae3a2-132">L'esecuzione dell'attività in background `IHostedService` è coordinata con la durata dell'applicazione (a tal fine, host o microservizio).</span><span class="sxs-lookup"><span data-stu-id="ae3a2-132">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="ae3a2-133">Si registrano le attività quando viene avviata l'applicazione e si ha la possibilità di eseguire un'azione automatica o di pulizia quando è in corso l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-133">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="ae3a2-134">Senza usare `IHostedService`, è sempre possibile avviare un thread in background per eseguire qualsiasi attività.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-134">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="ae3a2-135">La differenza è precisamente nel tempo di arresto dell'app, quando il thread potrebbe essere semplicemente terminato senza la possibilità di eseguire operazioni di pulizia automatica.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-135">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>


## <a name="the-ihostedservice-interface"></a><span data-ttu-id="ae3a2-136">Interfaccia IHostedService</span><span class="sxs-lookup"><span data-stu-id="ae3a2-136">The IHostedService interface</span></span>

<span data-ttu-id="ae3a2-137">Quando si registra un `IHostedService`, .NET Core chiamerà i metodi `StartAsync()` e `StopAsync()` del tipo `IHostedService` rispettivamente durante l'avvio e l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-137">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="ae3a2-138">In particolare, il metodo start viene chiamato dopo che il server è stato avviato e `IApplicationLifetime.ApplicationStarted` viene attivato.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-138">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="ae3a2-139">Il `IHostedService` definito in .NET Core sarà simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-139">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

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
<span data-ttu-id="ae3a2-140">Come è facile immaginare, è possibile creare più implementazioni di IHostedService e registrarle nel metodo `ConfigureService()` nel contenitore DI, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-140">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="ae3a2-141">Tutti i servizi ospitati verranno avviati e arrestati con l'applicazione/microservizio.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-141">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="ae3a2-142">Lo sviluppatore è responsabile della gestione dell'azione di arresto o dei servizi quando il metodo `StopAsync()` viene attivato dall'host.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-142">As a developer, you are responsible for handling the stopping action or your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="ae3a2-143">Implementazione di IHostedService con una classe personalizzata del servizio ospitato che deriva dalla classe base BackgroundService</span><span class="sxs-lookup"><span data-stu-id="ae3a2-143">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="ae3a2-144">È possibile procedere alla creazione da zero di una classe personalizzata del servizio ospitato e implementare il `IHostedService`, come è necessario fare quando si usa .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-144">You could go ahead and create you custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span> 

<span data-ttu-id="ae3a2-145">Tuttavia, poiché la maggior parte delle attività in background avrà esigenze simili per quanto riguarda la gestione dei token di annullamento e altre operazioni tipiche, .NET Core 2.1 fornirà una classe di base astratta molto pratica per la derivazione, denominata BackgroundService.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-145">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, .NET Core 2.1 will be providing a very convenient abstract base class you can derive from, named BackgroundService.</span></span>

<span data-ttu-id="ae3a2-146">Tale classe esegue il lavoro principale necessario per configurare l'attività in background.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-146">That class provides the main work needed to set up the background task.</span></span> <span data-ttu-id="ae3a2-147">Si noti che questa classe sarà disponibile nella libreria .NET Core 2.1, dunque non è necessario scriverla.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-147">Note that this class will come in the .NET Core 2.1 library so you don’t need to write it.</span></span>

<span data-ttu-id="ae3a2-148">Tuttavia, al momento della redazione del presente documento, .NET Core 2.1 non è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-148">However, as of the time of this writing, .NET Core 2.1 has not been released.</span></span> <span data-ttu-id="ae3a2-149">Perciò, in eShopOnContainers che attualmente usa .Net Core 2.0, stiamo incorporando solo temporaneamente tale classe dal repository open source di .NET Core 2.1 (senza bisogno di alcuna licenza proprietaria diverso dalla licenza open source) perché è compatibile con l'attuale interfaccia IHostedService in .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-149">Therefore, in eShopOnContainers which is currently using .NET Core 2.0, we are just temporally incorporating that class from the .NET Core 2.1 open-source repo (no need of any proprietary license other than the open-source license) because it is compatible with the current IHostedService interface in .NET Core 2.0.</span></span> <span data-ttu-id="ae3a2-150">Quando .NET Core 2.1 verrà rilasciato, sarà necessario solo scegliere il pacchetto NuGet corretto.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-150">When .NET Core 2.1 is released, you’ll just need to point to the right NuGet package.</span></span>

<span data-ttu-id="ae3a2-151">Il codice successivo è la classe base astratta BackgroundService così come implementata in .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-151">The next code is the abstract BackgroundService base class as implemented in .NET Core 2.1.</span></span>

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

<span data-ttu-id="ae3a2-152">Quando si deriva dalla classe base astratta precedente, grazie a tale implementazione ereditata, è sufficiente implementare il metodo `ExecuteAsync()` nella classe personalizzata del servizio ospitato, come illustrato di seguito nel codice semplificato da eShopOnContainers, che esegue il polling di un database e pubblica eventi di integrazione nel Bus di eventi quando necessario.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-152">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

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
                // and publishing events into the Event Bus (RabbitMS / ServiceBus)
                CheckConfirmedGracePeriodOrders();

                await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
            }
            
            _logger.LogDebug($"GracePeriod background task is stopping.");

        }

        protected override async Task StopAsync (CancellationToken stoppingToken)
        {
               // Run your graceful clean-up actions
        }
}
```

<span data-ttu-id="ae3a2-153">In questo caso specifico per eShopOnContainers, viene eseguito un metodo dell'applicazione che cerca in una tabella di database gli ordini con uno stato specifico; quando vengono applicate le modifiche, pubblica eventi di integrazione usando il bus di eventi (al di sotto di questo potrebbe usare RabbitMQ o il bus di servizio di Azure).</span><span class="sxs-lookup"><span data-stu-id="ae3a2-153">In this specific case for eShopOnContainers, it is executing an application method which is querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span> 

<span data-ttu-id="ae3a2-154">Naturalmente, è possibile eseguire in alternativa qualsiasi altra attività di business in background.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-154">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="ae3a2-155">Per impostazione predefinita, il token di annullamento è impostato con un timeout di 5 secondi, nonostante sia possibile modificare tale valore durante la compilazione di `WebHost` usando l'estensione `UseShutdownTimeout` di `IWebHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-155">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="ae3a2-156">Ciò significa che il nostro servizio dovrebbe essere annullato entro 5 secondi; in caso contrario verrà terminato improvvisamente.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-156">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="ae3a2-157">Il codice seguente permette di modificare tale intervallo di tempo in 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-157">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="ae3a2-158">Diagramma classi di riepilogo</span><span class="sxs-lookup"><span data-stu-id="ae3a2-158">Summary class diagram</span></span>

<span data-ttu-id="ae3a2-159">La figura 8-26 seguente mostra un riepilogo visivo delle classi e delle interfacce visibili durante l'implementazione di IHostedServices.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-159">The following image 8-26 shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>
 
![](./media/image27.png)

<span data-ttu-id="ae3a2-160">**Figura 8-26.**</span><span class="sxs-lookup"><span data-stu-id="ae3a2-160">**Figure 8-26.**</span></span> <span data-ttu-id="ae3a2-161">Diagramma classi che mostra più classi e interfacce correlate a IHostedService</span><span class="sxs-lookup"><span data-stu-id="ae3a2-161">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="ae3a2-162">Considerazioni finali sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="ae3a2-162">Deployment considerations and takeaways</span></span>

<span data-ttu-id="ae3a2-163">È importante notare che la modalità di distribuzione del `WebHost` di ASP.NET Core o del `Host` di .NET Core può incidere negativamente sulla soluzione finale.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-163">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="ae3a2-164">Ad esempio, se si distribuisce il `WebHost` in IIS o in un normale Servizio App di Azure, l'host può essere arrestato a causa di ricicli del pool di app.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-164">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="ae3a2-165">Se invece si distribuisce l'host come contenitore in un agente di orchestrazione come Kubernetes o Service Fabric, è possibile controllare il numero garantito di istanze attive dell'host.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-165">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="ae3a2-166">In più, è possibile considerare altri approcci nel cloud fatti apposta per questi scenari, ad esempio le Funzioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-166">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> 

<span data-ttu-id="ae3a2-167">Ma anche per un `WebHost` distribuito in un pool di applicazioni, esistono scenari come il ripopolamento o lo scaricamento della cache in memoria dell'applicazione che sarebbero comunque applicabili.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-167">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="ae3a2-168">L'interfaccia di `IHostedService` fornisce un modo pratico per avviare le attività in background in un'applicazione Web di ASP.NET Core (in .NET Core 2.0 ) o in qualsiasi processo/host (a partire da .NET Core 2.1 con `IHost`).</span><span class="sxs-lookup"><span data-stu-id="ae3a2-168">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="ae3a2-169">Il vantaggio principale è la possibilità che si ottiene con l'annullamento automatico di pulire il codice delle attività in background quando è in corso la chiusura dell'host stesso.</span><span class="sxs-lookup"><span data-stu-id="ae3a2-169">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>


#### <a name="additional-resources"></a><span data-ttu-id="ae3a2-170">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ae3a2-170">Additional resources</span></span>

-   <span data-ttu-id="ae3a2-171">**Creare un'attività pianificata in ASP.NET Core/Standard 2.0**</span><span class="sxs-lookup"><span data-stu-id="ae3a2-171">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span> 

    [*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*](https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html)

-   <span data-ttu-id="ae3a2-172">**Implementazione di IHostedService in ASP.NET Core 2.0**</span><span class="sxs-lookup"><span data-stu-id="ae3a2-172">**Implementing IHostedService in ASP.NET Core 2.0**</span></span> 

    [*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*](https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice)

-   <span data-ttu-id="ae3a2-173">**Esempi di hosting di ASP.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="ae3a2-173">**ASP.NET Core 2.1 Hosting samples**</span></span> 

    [*https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample*](https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample)

>[!div class="step-by-step"]
<span data-ttu-id="ae3a2-174">[Precedente](test-aspnet-core-services-web-apps.md)
[Successivo](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="ae3a2-174">[Previous](test-aspnet-core-services-web-apps.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
