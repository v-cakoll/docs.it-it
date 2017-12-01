---
title: Comunicazione asincrona basata su messaggi
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Comunicazione asincrona basata su messaggi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df39771295d12e122edbe27e91cd899e3318e301
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="asynchronous-message-based-communication"></a>Comunicazione asincrona basata su messaggi

Messaggistica asincrona e la comunicazione basata su eventi sono fondamentali per la propagazione delle modifiche tra più microservizi e i relativi modelli di dominio correlate. Come accennato in precedenza nella discussione microservizi delimitata contesti (BCs), modelli (utente, cliente, prodotto, Account, e così via) possono avere diversi significati diversi microservizi o BCs. Ciò significa che quando si verificano modifiche, è necessario un modo per risolvere le modifiche tra i diversi modelli. Una soluzione è coerenza finale e la comunicazione basata sugli eventi in base a messaggistica asincrona.

Quando si utilizza la messaggistica, i processi comunicano mediante lo scambio di messaggi in modo asincrono. Un client esegue un comando o una richiesta a un servizio mediante l'invio di un messaggio. Se il servizio deve rispondere, invia un messaggio diverso al client. Poiché si tratta di una comunicazione basata su messaggi, il client si presuppone che la risposta non verrà ricevuta immediatamente, e che non potrebbero essere presenti alcuna risposta affatto.

Un messaggio è composto da un'intestazione (metadati, ad esempio informazioni di identificazione o sicurezza) e un corpo. I messaggi vengono inviati in genere tramite protocolli asincroni come AMQP.

L'infrastruttura preferito per questo tipo di comunicazione della community di microservizi è un broker messaggi leggero, che è diverso da Broker di grandi dimensioni e orchestrators utilizzati in SOA. In un gestore di messaggi semplice, l'infrastruttura è in genere "muto," funge solo da un gestore di messaggi, con implementazioni semplici, ad esempio RabbitMQ o a un bus di servizio scalabile nel cloud come Azure Service Bus. In questo scenario, la maggior parte del concetto di "intelligente" è sempre presente negli endpoint di creazione e utilizzo dei messaggi, vale a dire nel microservizi.

Un'altra regola, che è consigliabile provare a seguire il più possibile consiste nell'utilizzare la messaggistica asincrona solo tra i servizi interni e consente la comunicazione sincrona (ad esempio HTTP) solo dalle App client per i servizi front-end (API gateway e il primo livello di microservizi).

Esistono due tipi di comunicazione di messaggistica asincrona: comunicazione basata su messaggi singolo destinatario e la comunicazione basata su messaggi di più destinatari. Nelle sezioni seguenti si forniscono informazioni dettagliate su tali.

## <a name="single-receiver-message-based-communication"></a>Comunicazione basata su messaggi singolo ricevitore 

Comunicazione asincrona basata su messaggi con un singolo ricevitore pertanto è comunicazione punto a punto che recapita un messaggio a uno e uno solo dei consumatori che sta leggendo il canale e che il messaggio viene elaborato solo una volta. Tuttavia, esistono casi speciali. In un sistema cloud che tenta di recuperare automaticamente da errori, ad esempio, lo stesso messaggio può essere inviato più volte. Problemi di rete o altri errori, il client deve essere in grado di ripetere l'invio di messaggi e il server deve implementare un'operazione per essere idempotenti per elaborare una sola volta un determinato messaggio.

Comunicazione basata su messaggi singolo ricevitore è particolarmente adatto per l'invio di comandi asincroni dal uno microservizio a altro come mostrato nella figura 4-18 che illustra questo approccio.

Una volta avviato l'invio di comunicazione basata su messaggi (sia con i comandi o gli eventi), è consigliabile evitare di combinazione di comunicazioni basate su messaggi con la comunicazione HTTP sincrona.

![](./media/image18.PNG)

**Figura 4-18**. Un singolo microservizio riceve un messaggio asincrono

Si noti che quando i comandi provengono da applicazioni client, possono essere implementate come i comandi sincroni HTTP. Quando è necessaria una maggiore scalabilità o quando si è già in un processo di business basata su messaggi, è necessario utilizzare comandi basata su messaggi.

## <a name="multiple-receivers-message-based-communication"></a>Comunicazione basata su messaggi più destinatari 

Come un approccio più flessibile, è inoltre possibile utilizzare un meccanismo di pubblicazione/sottoscrizione in modo che la comunicazione tra il mittente sarà disponibile al sottoscrittore aggiuntive microservizi o alle applicazioni esterne. Pertanto, consente di seguire il [principio di apertura/chiusura](https://en.wikipedia.org/wiki/Open/closed_principle) nel servizio di invio. In questo modo, è possibile aggiungere ulteriori server di sottoscrizione in futuro senza dover modificare il servizio del mittente.

Quando si utilizza una comunicazione di pubblicazione/sottoscrizione, è possibile utilizzare un'interfaccia del bus di eventi agli eventi di pubblicazione a qualsiasi sottoscrittore.

## <a name="asynchronous-event-driven-communication"></a>Comunicazione asincrona basata su eventi

Quando si usa la comunicazione asincrona basata sugli eventi, un microservizio pubblica un evento di integrazione quando si verifica un evento all'interno del dominio e un altro microservizio deve da considerare, ad esempio una variazione di prezzo di un microservizio catalogo prodotti. Ulteriori microservizi sottoscrivono gli eventi in modo che possano ricevere di in modo asincrono. In questo caso, i destinatari potrebbero aggiornare le proprie entità di dominio, causando ulteriori eventi di integrazione da pubblicare. Questo sistema di pubblicazione/sottoscrizione viene in genere eseguito tramite un'implementazione di un bus di eventi. Il bus di eventi può essere progettato come astrazione o un'interfaccia, con l'API necessarie per la sottoscrizione o annullare la sottoscrizione a eventi e per pubblicare eventi. Il bus di eventi può avere anche uno o più implementazioni in base a qualsiasi broker tra i processi e messaggistica, ad esempio una coda di messaggi o il bus di servizio che supporta la comunicazione asincrona e un modello di pubblicazione/sottoscrizione.

Se un sistema utilizza la coerenza eventuale definita dagli eventi di integrazione, è consigliabile che questo approccio precisare completamente per l'utente finale. Il sistema non deve utilizzare un approccio in grado di simulare eventi di integrazione, ad esempio SignalR o sistemi di polling dal client. L'utente finale e il titolare dell'organizzazione è necessario adottare la coerenza finale nel sistema e tenere presente che in molti casi l'azienda non disporre di qualsiasi problema con questo approccio, purché esplicita in modo esplicito.

Come accennato in precedenza il [sfide e soluzioni per la gestione di dati distribuite](#challenges-and-solutions-for-distributed-data-management) sezione, è possibile utilizzare gli eventi di integrazione per implementare le attività di business che si estendono su più microservizi. In questo modo si avrà la coerenza eventuale tra tali servizi. Una transazione alla fine coerente è costituita da una raccolta di azioni distribuite. In ogni azione, il microservizio correlato aggiorna un'entità di dominio e pubblica un altro evento di integrazione che genera l'azione successiva all'interno della stessa attività di business-to-end.

Un aspetto importante è che si desidera comunicare a più microservizi sottoscritti all'evento stesso. A tale scopo, è possibile usare pubblicazione/sottoscrizione messaggistica basato sulla comunicazione basata sugli eventi, come illustrato nella figura 4-19. Questo meccanismo di pubblicazione/sottoscrizione non è esclusivo per l'architettura del microservizio. È simile a quello [delimitata contesti](http://martinfowler.com/bliki/BoundedContext.html) in DDD deve comunicare, o al modo in cui si distribuire gli aggiornamenti dal database di scrittura al database di lettura nel [comando e Query Responsibility Segregation (CQRS)](http://martinfowler.com/bliki/CQRS.html)modello di architettura. L'obiettivo consiste nell'ottenere la coerenza eventuale tra più origini dei dati tra i sistemi distribuiti.

![](./media/image19.png)

**Figura 4-19**. Comunicazione asincrona dei messaggi basato su eventi

Determina l'implementazione del protocollo da utilizzare per le comunicazioni basate su eventi, basata su messaggi. [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) possono aiutare a realizzare una comunicazione affidabile in coda.

Quando si utilizza un bus di eventi, si desidera utilizzare un livello di astrazione (ad esempio, un'interfaccia di bus di eventi) basato su un'implementazione correlata nelle classi con codice usando l'API da un gestore di messaggi come [RabbitMQ](https://www.rabbitmq.com/) o a un bus di servizio come [Azure Service Bus con argomenti](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). In alternativa, è possibile utilizzare un bus di servizio di livello superiore come NServiceBus, MassTransit o Brighter per esprimere il bus di eventi e sistema di pubblicazione/sottoscrizione.

## <a name="a-note-about-messaging-technologies-for-production-systems"></a>Una nota sulle tecnologie per i sistemi di produzione di messaggistica

Le tecnologie di messaggistica disponibili per l'implementazione del bus di eventi astratti sono a livelli diversi. Prodotti come RabbitMQ (trasporto di Service broker messaggistica) e Azure Service Bus, ad esempio, si trovano a un livello inferiore di altri prodotti come, NServiceBus, MassTransit o Brighter, che può essere utilizzata su RabbitMQ e Azure Service Bus. La scelta dipende da quanti funzionalità avanzate a livello di applicazione e la scalabilità della casella che è necessario per l'applicazione. Per implementare solo un bus di eventi di prova per l'ambiente di sviluppo, come nell'esempio eShopOnContainers, potrebbe essere una semplice implementazione sopra RabbitMQ in esecuzione in un contenitore Docker sufficiente.

Tuttavia, di importanza critica e sistemi di produzione che richiedono la scalabilità di hyper, si consiglia di valutare Azure Service Bus. Astrazioni di alto livello e le funzionalità che consentono di semplificare lo sviluppo di applicazioni distribuite, è consigliabile valutare altri bus di servizio commerciale e open source, quali NServiceBus, MassTransit e Brighter. Naturalmente, è possibile creare funzionalità personalizzate bus di servizio su tecnologie di livello inferiore come RabbitMQ e Docker. Ma tale lavoro plumbing potrebbe essere costo troppo elevato per un'applicazione personalizzati dell'organizzazione.

## <a name="resiliently-publishing-to-the-event-bus"></a>Modo resiliente pubblicazione per il bus di eventi

Un problema durante l'implementazione di un'architettura basata sugli eventi in più microservizi viene illustrato come aggiornare in modo atomico stato il microservizio originale durante la pubblicazione modo resiliente l'evento di integrazione correlata nel bus di eventi, in qualche modo, in base a transazioni. Ecco alcuni modi per eseguire questa operazione, anche se è possibile che anche altri approcci.

-   Utilizzo di una coda transazionale (basato su DTC) come MSMQ. (Tuttavia, questo è un approccio legacy).

-   Utilizzando [data mining del log delle transazioni](http://www.scoop.it/t/sql-server-transaction-log-mining).

-   Utilizzo completo [di determinazione dell'origine evento](https://msdn.microsoft.com/en-us/library/dn589792.aspx) modello.

-   Utilizzo di [modello posta in uscita](http://gistlabs.com/2014/05/the-outbox/): una tabella di database transazionale come una coda di messaggi che sarà la base per un componente creatore di eventi che è necessario creare l'evento e pubblicarlo.

Argomenti aggiuntivi da considerare quando si usa la comunicazione asincrona sono idempotenza messaggio e la deduplicazione di messaggio. Questi argomenti vengono trattati nella sezione [implementazione basato su eventi di comunicazione tra microservizi (eventi di integrazione)](#implementing_event_based_comms_microserv) più avanti in questa Guida.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Basato su messaggistica degli eventi**
    [*http://soapatterns.org/design\_modelli/evento\_driven\_messaggistica*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Canale di pubblicazione/sottoscrizione**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **udi Dahan. È stato chiarito CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **Comando ed eseguire Query responsabilità Segregation (CQRS)**
    [*https://docs.microsoft.com/azure/architecture/patterns/cqrs*](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

-   **La comunicazione tra contesti di delimitata**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)

-   **La coerenza eventuale**
    [*https://en.wikipedia.org/wiki/Eventual\_coerenza*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Jimmy Bogard. Refactoring verso resilienza: Valutazione accoppiamento**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)


>[!div class="step-by-step"]
[Precedente] (comunicazione-in-microservizio-architecture.md) [Avanti] (mantenere-microservizio-apis.md)
