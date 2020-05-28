---
title: Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test
description: Architettura di microservizi .NET per applicazioni .NET nei contenitori | Implementazione della messaggistica di un bus di eventi con RabbitMQ per l'integrazione di eventi per gli ambienti di sviluppo o test.
ms.date: 10/02/2018
ms.openlocfilehash: 32259c76fe81d324ba3ea9b35f7fddc6a0f9cdbc
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144292"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="d2dba-103">Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test</span><span class="sxs-lookup"><span data-stu-id="d2dba-103">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="d2dba-104">È necessario premettere che se si crea un bus di eventi basato su RabbitMQ personalizzato in esecuzione in un contenitore, come l'applicazione eShopOnContainers, tale bus deve essere usato solo per gli ambienti di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="d2dba-104">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="d2dba-105">È consigliabile evitare di usarlo per l'ambiente di produzione, a meno che non venga creato nell'ambito di un bus di servizio per la produzione.</span><span class="sxs-lookup"><span data-stu-id="d2dba-105">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="d2dba-106">In un bus di eventi personalizzato semplice potrebbero mancare molte funzionalità critiche per la produzione, disponibili invece in un bus di servizio disponibile in commercio.</span><span class="sxs-lookup"><span data-stu-id="d2dba-106">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="d2dba-107">Una delle implementazioni personalizzate del bus di eventi in eShopOnContainers è essenzialmente una libreria che usa l'API RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="d2dba-107">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="d2dba-108">(È presente un'altra implementazione basata sul bus di servizio di Azure).</span><span class="sxs-lookup"><span data-stu-id="d2dba-108">(There's another implementation based on Azure Service Bus.)</span></span>

<span data-ttu-id="d2dba-109">L'implementazione del bus di eventi con RabbitMQ consente la pubblicazione e la ricezione di eventi e la sottoscrizione a questi da parte dei microservizi, come illustrato nella figura 6-21.</span><span class="sxs-lookup"><span data-stu-id="d2dba-109">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 6-21.</span></span>

![Diagramma che mostra RabbitMQ tra il mittente del messaggio e il destinatario del messaggio.](./media/rabbitmq-event-bus-development-test-environment/rabbitmq-implementation.png)

<span data-ttu-id="d2dba-111">**Figura 6-21.**</span><span class="sxs-lookup"><span data-stu-id="d2dba-111">**Figure 6-21.**</span></span> <span data-ttu-id="d2dba-112">Implementazione di un bus di eventi in RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="d2dba-112">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="d2dba-113">RabbitMQ svolge il ruolo d'intermediario tra l'autore e i sottoscrittori del messaggio al fine di gestirne la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d2dba-113">RabbitMQ functions as an intermediary between message publisher and subscribers, to handle distribution.</span></span> <span data-ttu-id="d2dba-114">Nel codice, la classe EventBusRabbitMQ implementa l'interfaccia IEventBus generica.</span><span class="sxs-lookup"><span data-stu-id="d2dba-114">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="d2dba-115">Questa si basa su un inserimento di dipendenze, rendendo possibile il passaggio da questa versione sviluppo/test a una versione di produzione.</span><span class="sxs-lookup"><span data-stu-id="d2dba-115">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

<span data-ttu-id="d2dba-116">L'implementazione RabbitMQ di un bus di eventi di sviluppo e test di esempio è codice boilerplate.</span><span class="sxs-lookup"><span data-stu-id="d2dba-116">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="d2dba-117">Tale implementazione deve gestire la connessione al server RabbitMQ e offrire il codice per la pubblicazione di un evento messaggio nelle code.</span><span class="sxs-lookup"><span data-stu-id="d2dba-117">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="d2dba-118">Deve anche implementare un dizionario di raccolte di gestori degli eventi di integrazione per ogni tipo di evento. I tipi di evento possono avere creazioni di istanze e sottoscrizioni diverse per ogni microservizio ricevitore, come illustrato nella figura 6-21.</span><span class="sxs-lookup"><span data-stu-id="d2dba-118">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 6-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="d2dba-119">Implementazione di un metodo di pubblicazione semplice con RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="d2dba-119">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="d2dba-120">Il codice seguente è una versione ***semplificata*** di un'implementazione del bus eventi per RabbitMQ, che illustra lo scenario complessivo.</span><span class="sxs-lookup"><span data-stu-id="d2dba-120">The following code is a ***simplified*** version of an event bus implementation for RabbitMQ, to showcase the whole scenario.</span></span> <span data-ttu-id="d2dba-121">La connessione non viene realmente gestita in questo modo.</span><span class="sxs-lookup"><span data-stu-id="d2dba-121">You don't really handle the connection this way.</span></span> <span data-ttu-id="d2dba-122">Per l'implementazione completa, vedere il codice effettivo nel repository [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs).</span><span class="sxs-lookup"><span data-stu-id="d2dba-122">To see the full implementation, see the actual code in the [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) repository.</span></span>

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

<span data-ttu-id="d2dba-123">Il [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) del metodo Publish nell'applicazione eShopOnContainers è stato migliorato tramite criteri di ripetizione [Polly](https://github.com/App-vNext/Polly), in base ai quali se il contenitore RabbitMQ non è pronto, l'esecuzione di un'attività viene ritentata un certo numero di volte.</span><span class="sxs-lookup"><span data-stu-id="d2dba-123">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="d2dba-124">Questo può verificarsi se i contenitori vengono avviati tramite docker-compose. In questo caso, ad esempio, il contenitore RabbitMQ può avviarsi più lentamente degli altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="d2dba-124">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="d2dba-125">Come accennato in precedenza, è possibile configurare RabbitMQ in molti modi diversi. Questo codice deve quindi essere usato solo per ambienti di sviluppo o test.</span><span class="sxs-lookup"><span data-stu-id="d2dba-125">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="d2dba-126">Implementazione del codice di sottoscrizione con l'API RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="d2dba-126">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="d2dba-127">Come il codice di pubblicazione, il codice seguente è una semplificazione di una parte dell'implementazione del bus di eventi per RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="d2dba-127">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="d2dba-128">Anche in questo caso, è necessario modificare questo codice solo per apportare miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="d2dba-128">Again, you usually do not need to change it unless you are improving it.</span></span>

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

<span data-ttu-id="d2dba-129">A ogni tipo di evento è correlato un canale che consente di ottenere gli eventi da RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="d2dba-129">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="d2dba-130">È quindi possibile avere tanti gestori degli eventi per canale e tipo di evento quanti sono necessari.</span><span class="sxs-lookup"><span data-stu-id="d2dba-130">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="d2dba-131">Il metodo Subscribe accetta un oggetto IIntegrationEventHandler, che è simile a un metodo di callback nel microservizio corrente, e l'oggetto IntegrationEvent correlato.</span><span class="sxs-lookup"><span data-stu-id="d2dba-131">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="d2dba-132">Il codice aggiunge quindi tale gestore dell'evento all'elenco dei gestori degli eventi che ogni tipo di evento di integrazione può avere per ogni microservizio client.</span><span class="sxs-lookup"><span data-stu-id="d2dba-132">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="d2dba-133">Se la sottoscrizione del codice client all'evento non è ancora stata effettuata, il codice crea un canale per il tipo di evento, in modo da ricevere gli eventi da RabbitMQ in stile push quando gli eventi vengono pubblicati da qualsiasi altro servizio.</span><span class="sxs-lookup"><span data-stu-id="d2dba-133">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>

<span data-ttu-id="d2dba-134">Come indicato in precedenza, il bus di eventi implementato in eShopOnContainers ha solo uno scopo pedagogico, perché gestisce solo gli scenari principali, quindi non è pronto per la produzione.</span><span class="sxs-lookup"><span data-stu-id="d2dba-134">As mentioned above, the event bus implemented in eShopOnContainers has only and educational purpose, since it only handles the main scenarios, so it's not ready for production.</span></span>

<span data-ttu-id="d2dba-135">Per gli scenari di produzione, controllare le risorse aggiuntive seguenti, specifiche per RabbitMQ, e la sezione [implementazione della comunicazione basata su eventi tra microservizi](./integration-event-based-microservice-communications.md#additional-resources) .</span><span class="sxs-lookup"><span data-stu-id="d2dba-135">For production scenarios check the additional resources below, specific for RabbitMQ, and the [Implementing event-based communication between microservices](./integration-event-based-microservice-communications.md#additional-resources) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2dba-136">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d2dba-136">Additional resources</span></span>

<span data-ttu-id="d2dba-137">Soluzioni pronte per l'ambiente di produzione con supporto per RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="d2dba-137">A production-ready solutions with support for RabbitMQ.</span></span>

- <span data-ttu-id="d2dba-138">**EasyNetQ** -client API .NET open source per RabbitMQ </span><span class="sxs-lookup"><span data-stu-id="d2dba-138">**EasyNetQ** - Open Source .NET API client for RabbitMQ </span></span>\
  <https://easynetq.com/>

- <span data-ttu-id="d2dba-139">**MassTransit** </span><span class="sxs-lookup"><span data-stu-id="d2dba-139">**MassTransit** </span></span>\
  <https://masstransit-project.com/>
  
> [!div class="step-by-step"]
> <span data-ttu-id="d2dba-140">[Precedente](integration-event-based-microservice-communications.md) 
>  [Avanti](subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="d2dba-140">[Previous](integration-event-based-microservice-communications.md)
[Next](subscribe-events.md)</span></span>
