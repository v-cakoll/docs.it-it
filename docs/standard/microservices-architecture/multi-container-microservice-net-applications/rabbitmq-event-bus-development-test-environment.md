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
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test

Deve iniziare pronunciando che se si crea il bus di eventi personalizzati in base alle RabbitMQ in esecuzione in un contenitore, come l'applicazione eShopOnContainers, e deve essere utilizzato solo per gli ambienti di sviluppo e test. È consigliabile non utilizzarlo per l'ambiente di produzione, a meno che non viene creata come parte di un ambiente di produzione service bus. Un bus di eventi personalizzati semplice potrebbe mancare molte funzionalità importanti ambiente di produzione con un bus di servizio esterno.

L'implementazione personalizzata di eShopOnContainers del bus di eventi è fondamentalmente una libreria tramite l'API RabbitMQ. L'implementazione consente microservizi sottoscrivere gli eventi, pubblicare eventi e ricevere eventi, come illustrato nella figura 8-21.

![](./media/image22.png)

**Figura 8-21.** Implementazione di RabbitMQ del bus di eventi

Nel codice, la classe EventBusRabbitMQ implementa l'interfaccia IEventBus generica. Si basa su inserimento di dipendenze in modo che sia possibile passare da questa versione di sviluppo/test a una versione di produzione.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

L'implementazione di RabbitMQ di un bus di eventi di sviluppo e test di esempio è il codice di boilerplate. Deve gestire la connessione al server RabbitMQ e fornire il codice per la pubblicazione di un evento di messaggio per le code. Dispone anche di implementare un dizionario di raccolte di gestori di eventi di integrazione per ogni tipo di evento. questi tipi di evento possono avere un'istanza diversa e diverse sottoscrizioni per ogni microservizio ricevitore, come illustrato nella figura 8-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementazione di un semplice metodo con RabbitMQ di pubblicazione

Il seguente codice è parte dell'implementazione del bus di eventi eShopOnContainers per RabbitMQ, pertanto in genere non è necessario scrivere il codice necessario a meno che non si stanno apportando miglioramenti. Il codice ottiene una connessione e il canale RabbitMQ, crea un messaggio e quindi pubblica il messaggio nella coda.

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

Il [codice effettivo](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) di pubblicazione è stata migliorata metodo nell'applicazione eShopOnContainers utilizzando un [Polly](https://github.com/App-vNext/Polly) criteri, che tenterà di un determinato numero di volte in cui l'attività nel caso in cui il contenitore RabbitMQ di ripetizione non è pronto. Questa situazione può verificarsi quando comporre docker avvio contenitori; ad esempio, il contenitore RabbitMQ potrebbe avviare più lento rispetto a altri contenitori.

Come accennato in precedenza, esistono molte possibili configurazioni di RabbitMQ, quindi questo codice deve essere utilizzato solo per gli ambienti di sviluppo e test.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Implementare il codice di sottoscrizione con l'API RabbitMQ

Come con il codice di pubblicazione, il codice seguente è una semplificazione della parte dell'implementazione del bus di eventi per RabbitMQ. Nuovamente, in genere non occorre modificarlo a meno che non sono migliorarlo.

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

Ogni tipo di evento è un canale per ottenere gli eventi da RabbitMQ correlato. È quindi possibile avere tutti i gestori eventi per ogni tipo di canale e di evento in base alle esigenze.

Il metodo Subscribe accetta un oggetto IIntegrationEventHandler, che è simile a un metodo di callback nel microservizio corrente, e il relativo oggetto IntegrationEvent correlato. Il codice aggiunge quindi il gestore eventi all'elenco di gestori di eventi che può avere ogni tipo di evento di integrazione per ogni client microservizio. Se il codice client non è già stato sottoscritto l'evento, il codice crea un canale per il tipo di evento per la ricezione di eventi in uno stile push da RabbitMQ quando tale evento viene pubblicato da qualsiasi altro servizio.


>[!div class="step-by-step"]
[Precedente] (integrazione-eventi-base-microservizio-communications.md) [Avanti] (events.md sottoscrizione)
