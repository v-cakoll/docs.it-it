---
title: Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test
description: Architettura di microservizi .NET per applicazioni .NET nei contenitori | Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3505cb993c736165d4aff4ce8fad38cfa14ed417
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="b7a30-104">Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test</span><span class="sxs-lookup"><span data-stu-id="b7a30-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="b7a30-105">È necessario premettere che se si crea un bus di eventi basato su RabbitMQ personalizzato in esecuzione in un contenitore, come l'applicazione eShopOnContainers, tale bus deve essere usato solo per gli ambienti di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="b7a30-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="b7a30-106">È consigliabile evitare di usarlo per l'ambiente di produzione, a meno che non venga creato nell'ambito di un bus di servizio per la produzione.</span><span class="sxs-lookup"><span data-stu-id="b7a30-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="b7a30-107">In un bus di eventi personalizzato semplice potrebbero mancare molte funzionalità critiche per la produzione, disponibili invece in un bus di servizio disponibile in commercio.</span><span class="sxs-lookup"><span data-stu-id="b7a30-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="b7a30-108">Una delle implementazioni personalizzate di bus di servizio in eShopOnContainers è in pratica una libreria che usa l'API RabbitMQ. È presente un'altra implementazione basata sul bus di servizio di Azure.</span><span class="sxs-lookup"><span data-stu-id="b7a30-108">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span> 

<span data-ttu-id="b7a30-109">L'implementazione del bus di eventi con RabbitMQ consente la pubblicazione e la ricezione di eventi e la sottoscrizione a questi da parte dei microservizi, come illustrato nella figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="b7a30-109">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="b7a30-110">**Figura 8-21.**</span><span class="sxs-lookup"><span data-stu-id="b7a30-110">**Figure 8-21.**</span></span> <span data-ttu-id="b7a30-111">Implementazione di un bus di eventi in RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="b7a30-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="b7a30-112">Nel codice, la classe EventBusRabbitMQ implementa l'interfaccia IEventBus generica.</span><span class="sxs-lookup"><span data-stu-id="b7a30-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="b7a30-113">Questa si basa su un inserimento di dipendenze, rendendo possibile il passaggio da questa versione sviluppo/test a una versione di produzione.</span><span class="sxs-lookup"><span data-stu-id="b7a30-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="b7a30-114">L'implementazione RabbitMQ di un bus di eventi di sviluppo e test di esempio è codice boilerplate.</span><span class="sxs-lookup"><span data-stu-id="b7a30-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="b7a30-115">Tale implementazione deve gestire la connessione al server RabbitMQ e offrire il codice per la pubblicazione di un evento messaggio nelle code.</span><span class="sxs-lookup"><span data-stu-id="b7a30-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="b7a30-116">Deve anche implementare un dizionario di raccolte di gestori degli eventi di integrazione per ogni tipo di evento. I tipi di evento possono avere creazioni di istanze e sottoscrizioni diverse per ogni microservizio ricevitore, come illustrato nella figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="b7a30-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="b7a30-117">Implementazione di un metodo di pubblicazione semplice con RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="b7a30-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="b7a30-118">Il codice seguente fa parte dell'implementazione semplificata di un bus di eventi per RabbitMQ, migliorata nel [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="b7a30-118">The following code is part is a simplified event bus implementation for RabbitMQ, improved in the [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of eShopOnContainers.</span></span> <span data-ttu-id="b7a30-119">In genere è necessario scrivere questo codice solo per apportare miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="b7a30-119">You usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="b7a30-120">Il codice ottiene una connessione e un canale a RabbitMQ,crea un messaggio e quindi pubblica quest'ultimo nella coda.</span><span class="sxs-lookup"><span data-stu-id="b7a30-120">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="b7a30-121">Il [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) del metodo Publish nell'applicazione eShopOnContainers è stato migliorato tramite criteri di ripetizione [Polly](https://github.com/App-vNext/Polly), in base ai quali se il contenitore RabbitMQ non è pronto, l'esecuzione di un'attività viene ritentata un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="b7a30-121">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="b7a30-122">Questo può verificarsi se i contenitori vengono avviati tramite docker-compose. In questo caso, ad esempio, il contenitore RabbitMQ può avviarsi più lentamente degli altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="b7a30-122">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="b7a30-123">Come accennato in precedenza, è possibile configurare RabbitMQ in molti modi diversi. Questo codice deve quindi essere usato solo per ambienti di sviluppo o test.</span><span class="sxs-lookup"><span data-stu-id="b7a30-123">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="b7a30-124">Implementazione del codice di sottoscrizione con l'API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="b7a30-124">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="b7a30-125">Come il codice di pubblicazione, il codice seguente è una semplificazione di una parte dell'implementazione del bus di eventi per RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="b7a30-125">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="b7a30-126">Anche in questo caso, è necessario modificare questo codice solo per apportare miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="b7a30-126">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();
        
        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

<span data-ttu-id="b7a30-127">A ogni tipo di evento è correlato un canale che consente di ottenere gli eventi da RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="b7a30-127">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="b7a30-128">È quindi possibile avere tanti gestori degli eventi per canale e tipo di evento quanti sono necessari.</span><span class="sxs-lookup"><span data-stu-id="b7a30-128">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="b7a30-129">Il metodo Subscribe accetta un oggetto IIntegrationEventHandler, che è simile a un metodo di callback nel microservizio corrente, e l'oggetto IntegrationEvent correlato.</span><span class="sxs-lookup"><span data-stu-id="b7a30-129">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="b7a30-130">Il codice aggiunge quindi tale gestore dell'evento all'elenco dei gestori degli eventi che ogni tipo di evento di integrazione può avere per ogni microservizio client.</span><span class="sxs-lookup"><span data-stu-id="b7a30-130">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="b7a30-131">Se la sottoscrizione del codice client all'evento non è ancora stata effettuata, il codice crea un canale per il tipo di evento, in modo da ricevere gli eventi da RabbitMQ in stile push quando gli eventi vengono pubblicati da qualsiasi altro servizio.</span><span class="sxs-lookup"><span data-stu-id="b7a30-131">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b7a30-132">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="b7a30-132">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
