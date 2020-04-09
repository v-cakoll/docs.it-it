---
title: Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test
description: Architettura di microservizi .NET per applicazioni .NET nei contenitori | Implementazione della messaggistica di un bus di eventi con RabbitMQ per l'integrazione di eventi per gli ambienti di sviluppo o test.
ms.date: 10/02/2018
ms.openlocfilehash: 12e37fabfe915b4d2089d27f7852528a9a037d3c
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988297"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test

È necessario premettere che se si crea un bus di eventi basato su RabbitMQ personalizzato in esecuzione in un contenitore, come l'applicazione eShopOnContainers, tale bus deve essere usato solo per gli ambienti di sviluppo e test. È consigliabile evitare di usarlo per l'ambiente di produzione, a meno che non venga creato nell'ambito di un bus di servizio per la produzione. In un bus di eventi personalizzato semplice potrebbero mancare molte funzionalità critiche per la produzione, disponibili invece in un bus di servizio disponibile in commercio.

Una delle implementazioni personalizzate del bus di eventi in eShopOnContainers è fondamentalmente una libreria che usa l'API RabbitMQ. È disponibile un'altra implementazione basata sul bus di servizio di Azure.

L'implementazione del bus di eventi con RabbitMQ consente la pubblicazione e la ricezione di eventi e la sottoscrizione a questi da parte dei microservizi, come illustrato nella figura 6-21.

![Diagramma che mostra RabbitMQ tra il mittente del messaggio e il destinatario del messaggio.](./media/rabbitmq-event-bus-development-test-environment/rabbitmq-implementation.png)

**Figura 6-21.** Implementazione di un bus di eventi in RabbitMQ

RabbitMQ svolge il ruolo d'intermediario tra l'autore e i sottoscrittori del messaggio al fine di gestirne la distribuzione. Nel codice, la classe EventBusRabbitMQ implementa l'interfaccia IEventBus generica. Questa si basa su un inserimento di dipendenze, rendendo possibile il passaggio da questa versione sviluppo/test a una versione di produzione.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

L'implementazione RabbitMQ di un bus di eventi di sviluppo e test di esempio è codice boilerplate. Tale implementazione deve gestire la connessione al server RabbitMQ e offrire il codice per la pubblicazione di un evento messaggio nelle code. Deve anche implementare un dizionario di raccolte di gestori degli eventi di integrazione per ogni tipo di evento. I tipi di evento possono avere creazioni di istanze e sottoscrizioni diverse per ogni microservizio ricevitore, come illustrato nella figura 6-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementazione di un metodo di pubblicazione semplice con RabbitMQ

Il codice seguente è una versione ***semplificata*** di un'implementazione del bus eventi per RabbitMQ, che illustra lo scenario complessivo. La connessione non viene realmente gestita in questo modo. Per l'implementazione completa, vedere il codice effettivo nel repository [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs).

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

Come accennato in precedenza, il bus di eventi implementato in eShopOnContainers ha solo scopo educativo, poiché gestisce solo gli scenari principali, quindi non è pronto per la produzione.

Per gli scenari di produzione, controllare le risorse aggiuntive riportate di seguito, specifiche per RabbitMQ e la sezione Implementazione della [comunicazione basata su eventi tra microservizi.](./integration-event-based-microservice-communications.md#additional-resources)

## <a name="additional-resources"></a>Risorse aggiuntive

Una soluzione pronta per la produzione con supporto per RabbitMQ.

- **EasyNetQ** - Client API .NET open source per RabbitMQ
  <http://easynetq.com/>

- **Transito di Massa** \
  <https://masstransit-project.com/>
  
> [!div class="step-by-step"]
> [Successivo](integration-event-based-microservice-communications.md)
> [precedente](subscribe-events.md)
