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
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test

È necessario premettere che se si crea un bus di eventi basato su RabbitMQ personalizzato in esecuzione in un contenitore, come l'applicazione eShopOnContainers, tale bus deve essere usato solo per gli ambienti di sviluppo e test. È consigliabile evitare di usarlo per l'ambiente di produzione, a meno che non venga creato nell'ambito di un bus di servizio per la produzione. In un bus di eventi personalizzato semplice potrebbero mancare molte funzionalità critiche per la produzione, disponibili invece in un bus di servizio disponibile in commercio.

Una delle implementazioni personalizzate di bus di servizio in eShopOnContainers è in pratica una libreria che usa l'API RabbitMQ. È presente un'altra implementazione basata sul bus di servizio di Azure. 

L'implementazione del bus di eventi con RabbitMQ consente la pubblicazione e la ricezione di eventi e la sottoscrizione a questi da parte dei microservizi, come illustrato nella figura 8-21.

![](./media/image22.png)

**Figura 8-21.** Implementazione di un bus di eventi in RabbitMQ

Nel codice, la classe EventBusRabbitMQ implementa l'interfaccia IEventBus generica. Questa si basa su un inserimento di dipendenze, rendendo possibile il passaggio da questa versione sviluppo/test a una versione di produzione.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

L'implementazione RabbitMQ di un bus di eventi di sviluppo e test di esempio è codice boilerplate. Tale implementazione deve gestire la connessione al server RabbitMQ e offrire il codice per la pubblicazione di un evento messaggio nelle code. Deve anche implementare un dizionario di raccolte di gestori degli eventi di integrazione per ogni tipo di evento. I tipi di evento possono avere creazioni di istanze e sottoscrizioni diverse per ogni microservizio ricevitore, come illustrato nella figura 8-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementazione di un metodo di pubblicazione semplice con RabbitMQ

Il codice seguente fa parte dell'implementazione semplificata di un bus di eventi per RabbitMQ, migliorata nel [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) di eShopOnContainers. In genere è necessario scrivere questo codice solo per apportare miglioramenti. Il codice ottiene una connessione e un canale a RabbitMQ,crea un messaggio e quindi pubblica quest'ultimo nella coda.

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

Il [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) del metodo Publish nell'applicazione eShopOnContainers è stato migliorato tramite criteri di ripetizione [Polly](https://github.com/App-vNext/Polly), in base ai quali se il contenitore RabbitMQ non è pronto, l'esecuzione di un'attività viene ritentata un certo numero di volte. Questo può verificarsi se i contenitori vengono avviati tramite docker-compose. In questo caso, ad esempio, il contenitore RabbitMQ può avviarsi più lentamente degli altri contenitori.

Come accennato in precedenza, è possibile configurare RabbitMQ in molti modi diversi. Questo codice deve quindi essere usato solo per ambienti di sviluppo o test.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Implementazione del codice di sottoscrizione con l'API RabbitMQ

Come il codice di pubblicazione, il codice seguente è una semplificazione di una parte dell'implementazione del bus di eventi per RabbitMQ. Anche in questo caso, è necessario modificare questo codice solo per apportare miglioramenti.

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

A ogni tipo di evento è correlato un canale che consente di ottenere gli eventi da RabbitMQ. È quindi possibile avere tanti gestori degli eventi per canale e tipo di evento quanti sono necessari.

Il metodo Subscribe accetta un oggetto IIntegrationEventHandler, che è simile a un metodo di callback nel microservizio corrente, e l'oggetto IntegrationEvent correlato. Il codice aggiunge quindi tale gestore dell'evento all'elenco dei gestori degli eventi che ogni tipo di evento di integrazione può avere per ogni microservizio client. Se la sottoscrizione del codice client all'evento non è ancora stata effettuata, il codice crea un canale per il tipo di evento, in modo da ricevere gli eventi da RabbitMQ in stile push quando gli eventi vengono pubblicati da qualsiasi altro servizio.


>[!div class="step-by-step"]
[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)
