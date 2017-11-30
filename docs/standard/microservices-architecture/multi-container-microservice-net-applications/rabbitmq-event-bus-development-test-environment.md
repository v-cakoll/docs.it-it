---
title: Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f58d355b6f5fd31a21791d3b072c77f70f90c387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="da637-104">Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test</span><span class="sxs-lookup"><span data-stu-id="da637-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="da637-105">Deve iniziare pronunciando che se si crea il bus di eventi personalizzati in base alle RabbitMQ in esecuzione in un contenitore, come l'applicazione eShopOnContainers, e deve essere utilizzato solo per gli ambienti di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="da637-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="da637-106">È consigliabile non utilizzarlo per l'ambiente di produzione, a meno che non viene creata come parte di un ambiente di produzione service bus.</span><span class="sxs-lookup"><span data-stu-id="da637-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="da637-107">Un bus di eventi personalizzati semplice potrebbe mancare molte funzionalità importanti ambiente di produzione con un bus di servizio esterno.</span><span class="sxs-lookup"><span data-stu-id="da637-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="da637-108">L'implementazione personalizzata di eShopOnContainers del bus di eventi è fondamentalmente una libreria tramite l'API RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="da637-108">The eShopOnContainers custom implementation of an event bus is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="da637-109">L'implementazione consente microservizi sottoscrivere gli eventi, pubblicare eventi e ricevere eventi, come illustrato nella figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="da637-109">The implementation lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="da637-110">**Figura 8-21.**</span><span class="sxs-lookup"><span data-stu-id="da637-110">**Figure 8-21.**</span></span> <span data-ttu-id="da637-111">Implementazione di RabbitMQ del bus di eventi</span><span class="sxs-lookup"><span data-stu-id="da637-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="da637-112">Nel codice, la classe EventBusRabbitMQ implementa l'interfaccia IEventBus generica.</span><span class="sxs-lookup"><span data-stu-id="da637-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="da637-113">Si basa su inserimento di dipendenze in modo che sia possibile passare da questa versione di sviluppo/test a una versione di produzione.</span><span class="sxs-lookup"><span data-stu-id="da637-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="da637-114">L'implementazione di RabbitMQ di un bus di eventi di sviluppo e test di esempio è il codice di boilerplate.</span><span class="sxs-lookup"><span data-stu-id="da637-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="da637-115">Deve gestire la connessione al server RabbitMQ e fornire il codice per la pubblicazione di un evento di messaggio per le code.</span><span class="sxs-lookup"><span data-stu-id="da637-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="da637-116">Dispone anche di implementare un dizionario di raccolte di gestori di eventi di integrazione per ogni tipo di evento. questi tipi di evento possono avere un'istanza diversa e diverse sottoscrizioni per ogni microservizio ricevitore, come illustrato nella figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="da637-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="da637-117">Implementazione di un semplice metodo con RabbitMQ di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="da637-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="da637-118">Il seguente codice è parte dell'implementazione del bus di eventi eShopOnContainers per RabbitMQ, pertanto in genere non è necessario scrivere il codice necessario a meno che non si stanno apportando miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="da637-118">The following code is part of the eShopOnContainers event bus implementation for RabbitMQ, so you usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="da637-119">Il codice ottiene una connessione e il canale RabbitMQ, crea un messaggio e quindi pubblica il messaggio nella coda.</span><span class="sxs-lookup"><span data-stu-id="da637-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

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

<span data-ttu-id="da637-120">Il [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) di pubblicazione è stata migliorata metodo nell'applicazione eShopOnContainers utilizzando un [Polly](https://github.com/App-vNext/Polly) criteri, che tenterà di un determinato numero di volte in cui l'attività nel caso in cui il contenitore RabbitMQ di ripetizione non è pronto.</span><span class="sxs-lookup"><span data-stu-id="da637-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="da637-121">Questa situazione può verificarsi quando comporre docker avvio contenitori; ad esempio, il contenitore RabbitMQ potrebbe avviare più lento rispetto a altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="da637-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="da637-122">Come accennato in precedenza, esistono molte possibili configurazioni di RabbitMQ, quindi questo codice deve essere utilizzato solo per gli ambienti di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="da637-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="da637-123">Implementare il codice di sottoscrizione con l'API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="da637-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="da637-124">Come con il codice di pubblicazione, il codice seguente è una semplificazione della parte dell'implementazione del bus di eventi per RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="da637-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="da637-125">Nuovamente, in genere non occorre modificarlo a meno che non sono migliorarlo.</span><span class="sxs-lookup"><span data-stu-id="da637-125">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...
    public void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent
    {
        var eventName = typeof(T).Name;
        if (_handlers.ContainsKey(eventName))
        {
            _handlers[eventName].Add(handler);
        }
        else
        {
            var channel = GetChannel();
            channel.QueueBind(queue: _queueName,
                exchange: _brokerName,
                routingKey: eventName);
            _handlers.Add(eventName, new List<IIntegrationEventHandler>());
            _handlers[eventName].Add(handler);
            _eventTypes.Add(typeof(T));
        }
    }
}
```

<span data-ttu-id="da637-126">Ogni tipo di evento è un canale per ottenere gli eventi da RabbitMQ correlato.</span><span class="sxs-lookup"><span data-stu-id="da637-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="da637-127">È quindi possibile avere tutti i gestori eventi per ogni tipo di canale e di evento in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="da637-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="da637-128">Il metodo Subscribe accetta un oggetto IIntegrationEventHandler, che è simile a un metodo di callback nel microservizio corrente, e il relativo oggetto IntegrationEvent correlato.</span><span class="sxs-lookup"><span data-stu-id="da637-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="da637-129">Il codice aggiunge quindi il gestore eventi all'elenco di gestori di eventi che può avere ogni tipo di evento di integrazione per ogni client microservizio.</span><span class="sxs-lookup"><span data-stu-id="da637-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="da637-130">Se il codice client non è già stato sottoscritto l'evento, il codice crea un canale per il tipo di evento per la ricezione di eventi in uno stile push da RabbitMQ quando tale evento viene pubblicato da qualsiasi altro servizio.</span><span class="sxs-lookup"><span data-stu-id="da637-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="da637-131">[Precedente] (integrazione-eventi-base-microservizio-communications.md) [Avanti] (events.md sottoscrizione)</span><span class="sxs-lookup"><span data-stu-id="da637-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
