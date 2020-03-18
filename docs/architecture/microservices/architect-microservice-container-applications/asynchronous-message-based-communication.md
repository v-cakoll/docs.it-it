---
title: Comunicazione asincrona basata su messaggi
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | La comunicazione asincrona basata su messaggi è un concetto essenziale nell'architettura dei microservizi, perché è il modo migliore per mantenere i microservizi al contempo indipendenti uno dall'altro e sincronizzati.
ms.date: 09/20/2018
ms.openlocfilehash: 84eaf70178cce91a86dae8a55badb0b4ddd6a7c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73454228"
---
# <a name="asynchronous-message-based-communication"></a>Comunicazione asincrona basata su messaggi

La messaggistica asincrona e la comunicazione basata su eventi sono fondamentali per la propagazione delle modifiche tra più microservizi e i modelli di dominio correlati. Come accennato in precedenza nella sezione relativa a microservizi e contesti delimitati, i modelli (utente, cliente, prodotto, account e così via) possono avere diversi significati per differenti microservizi o contesti delimitati. Ciò significa che, quando si verificano modifiche, è necessario un sistema per riconciliare le modifiche tra i diversi modelli. Una soluzione è coerenza finale e la comunicazione basata su eventi in base alla messaggistica asincrona.

Quando si utilizza la messaggistica, i processi comunicano mediante lo scambio di messaggi in modalità asincrona. Un client esegue un comando o una richiesta a un servizio mediante l'invio di un messaggio al servizio. Se il servizio deve rispondere, invia un messaggio diverso al client. Poiché si tratta di una comunicazione basata su messaggi, il client presuppone che la risposta non verrà ricevuta immediatamente e che potrebbe non essere ricevuta alcuna risposta.

Un messaggio è composto da un'intestazione (metadati come informazioni di identificazione o di sicurezza) e un corpo. I messaggi in genere vengono inviati tramite protocolli asincroni come AMQP.

L'infrastruttura preferita per questo tipo di comunicazione nella community dei microservizi è un broker di messaggi leggero, diverso dai broker e dagli agenti di orchestrazione di grandi dimensioni usati in SOA. In un broker di messaggi leggero, l'infrastruttura in genere opera solo come un broker di messaggi, con implementazioni semplici come RabbitMQ o un bus di servizio scalabile nel cloud come il bus di servizio di Azure. In questo scenario la maggior parte dell'elaborazione "intelligente" viene eseguita negli endpoint che producono e usano i messaggi, ovvero nei microservizi.

Un'altra regola che è consigliabile provare a seguire il più possibile consiste nell'usare solo la messaggistica asincrona tra i servizi interni e impiegare la comunicazione sincrona (ad esempio, HTTP) solo dalle app client ai servizi front-end (gateway API e il primo livello di microservizi).

Esistono due tipi di comunicazione per la messaggistica asincrona: comunicazione basata su messaggi con singolo destinatario e comunicazione basata su messaggi con più destinatari. Nelle sezioni seguenti vengono offerte informazioni dettagliate in proposito.

## <a name="single-receiver-message-based-communication"></a>Comunicazione basata su messaggi con singolo destinatario

La comunicazione basata su messaggi con singolo destinatario implica che sia presente una comunicazione punto a punto che recapita un messaggio a uno e uno solo dei consumer che eseguono la lettura del canale e che il messaggio venga elaborato una sola volta. Esistono tuttavia casi speciali. Ad esempio, in un sistema cloud che tenta di eseguire automaticamente il ripristino dagli errori, lo stesso messaggio potrebbe essere inviato più volte. A causa di problemi di rete o altri errori, il client deve essere in grado di ripetere l'invio dei messaggi e il server deve implementare un'operazione idempotente, in modo da elaborare un particolare messaggio una sola volta.

La comunicazione basata su messaggi con singolo destinatario è particolarmente adatta per l'invio di comandi asincroni da un microservizio all'altro, come mostrato nella figura 4-18 che illustra questo approccio.

Una volta che si iniziano a inviare comunicazioni basate su messaggi (con comandi o eventi), è consigliabile evitare di combinare la comunicazione basata su messaggi con la comunicazione HTTP sincrona.

![Un singolo microservizio che riceve un messaggio asincrono](./media/asynchronous-message-based-communication/single-receiver-message-based-communication.png)

**Figura 4-18**. Un singolo microservizio che riceve un messaggio asincrono

Si noti che quando i comandi provengono da applicazioni client, possono essere implementati come comandi sincroni HTTP. Usare comandi basati su messaggi quando è necessaria una maggiore scalabilità o quando si è già in un processo aziendale basato su messaggi.

## <a name="multiple-receivers-message-based-communication"></a>Comunicazione basata su messaggi con più destinatari

Come approccio più flessibile, è anche possibile usare un meccanismo di pubblicazione/sottoscrizione, in modo da rendere disponibile la comunicazione dal mittente per microservizi sottoscrittori aggiuntivi o applicazioni esterne. Questo pertanto consente di seguire il [principio aperto/chiuso](https://en.wikipedia.org/wiki/Open/closed_principle) nel servizio di invio. In questo modo, sarà possibile aggiungere ulteriori sottoscrittori in futuro senza dover modificare il servizio del mittente.

Quando si usa una comunicazione basata su pubblicazione/sottoscrizione, è possibile usare un'interfaccia di bus di eventi per pubblicare gli eventi per qualsiasi sottoscrittore.

## <a name="asynchronous-event-driven-communication"></a>Comunicazione asincrona basata su eventi

Quando si usa la comunicazione asincrona basata su eventi, un microservizio pubblica un evento di integrazione quando accade qualcosa all'interno del proprio dominio e un altro microservizio deve rilevare tale evento, ad esempio una variazione di prezzo in un microservizio per un catalogo prodotti. Ulteriori microservizi eseguono la sottoscrizione agli eventi in modo da poterli ricevere in modo asincrono. In questo caso, i destinatari potrebbero aggiornare le proprie entità di dominio, causando la pubblicazione di altri eventi di integrazione. Questo sistema di pubblicazione/sottoscrizione viene in genere eseguito usando un'implementazione di un bus di eventi. Il bus di eventi può essere progettato come un'astrazione o un'interfaccia, con l'API necessaria per sottoscrivere o annullare la sottoscrizione a eventi e per pubblicare eventi. Il bus di eventi può anche avere uno o più implementazioni basate su qualsiasi broker tra processi e di messaggistica, ad esempio una coda di messaggi o un bus di servizio che supporta la comunicazione asincrona e un modello di pubblicazione/sottoscrizione.

Se un sistema usa la coerenza finale definita dagli eventi di integrazione, è consigliabile rendere questo approccio completamente chiaro per l'utente finale. Il sistema non deve usare un approccio che simula gli eventi di integrazione, come ad esempio SignalR o il polling dei sistemi dal client. L'utente finale e il titolare dell'azienda devono prevedere esplicitamente la coerenza finale nel sistema e tenere presente che in molti casi l'azienda non ha alcun problema con questo approccio, purché venga esplicitato. Questo è importante perché gli utenti potrebbero aspettarsi di visualizzare alcuni risultati immediatamente e ciò potrebbe non avvenire con la coerenza finale.

Come accennato in precedenza nella sezione [Problemi e soluzioni per la gestione dei dati distribuiti](distributed-data-management.md), è possibile usare gli eventi di integrazione per implementare attività aziendali che interessano più microservizi. In questo modo, si otterrà la coerenza finale tra tali servizi. Una transazione con coerenza finale è costituita da un insieme di azioni distribuite. A ogni azione, il microservizio correlato aggiorna un'entità di dominio e pubblica un altro evento di integrazione che genera l'azione successiva all'interno della stessa attività aziendale end-to-end.

Un aspetto importante è che potrebbe essere necessario comunicare con più microservizi sottoscritti allo stesso evento. A tale scopo, è possibile usare la messaggistica con pubblicazione/sottoscrizione in base alla comunicazione basata su eventi, come illustrato nella figura 4-19. Questo meccanismo di pubblicazione/sottoscrizione non è esclusivo per l'architettura dei microservizi. È simile al modo in cui devono comunicare i [contesti delimitati](https://martinfowler.com/bliki/BoundedContext.html) in DDD o al modo in cui si propagano gli aggiornamenti dal database di scrittura al database di lettura nello schema di architettura [separazione di responsabilità per query e comandi (CQRS, Command and Query Responsibility Segregation)](https://martinfowler.com/bliki/CQRS.html). L'obiettivo è ottenere la coerenza finale tra più origini dati in tutto il sistema distribuito.

![Diagramma che mostra le comunicazioni asincrone basate su eventi.](./media/asynchronous-message-based-communication/asynchronous-event-driven-communication.png)

**Figura 4-19**. Comunicazione di messaggi asincrona basata su eventi

Nella comunicazione asincrona basata su evento un microservizio pubblica eventi in un bus di eventi a cui più microservizi possono eseguire la sottoscrizione per ricevere notifiche ed eseguire operazioni. L'implementazione determina il protocollo da usare per le comunicazioni di messaggi basate su eventi. [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) può consentire di realizzare comunicazioni in coda affidabili.

Quando si usa un bus di eventi, è possibile usare un livello di astrazione (ad esempio, un'interfaccia di bus di eventi) basato su un'implementazione correlata nelle classi con codice che usa l'API da un broker di messaggi come [RabbitMQ](https://www.rabbitmq.com/) o un bus di servizio come il [bus di servizio di Azure con argomenti](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). In alternativa, è possibile usare un bus di servizio di livello superiore come NServiceBus, MassTransit o Brighter per articolare il bus di eventi e il sistema di pubblicazione/sottoscrizione.

## <a name="a-note-about-messaging-technologies-for-production-systems"></a>Nota sulle tecnologie di messaggistica per i sistemi di produzione

Le tecnologie di messaggistica disponibili per l'implementazione del bus di eventi astratto sono a livelli diversi. Ad esempio, prodotti come RabbitMQ (un trasporto di broker di messaggi) e il bus di servizio di Azure sono a un livello inferiore rispetto ad altri prodotti come NServiceBus, MassTransit o Brighter, che possono essere usati in aggiunta a RabbitMQ e al bus di servizio di Azure. La scelta dipende dal numero di funzionalità a livello di applicazione e dalla quantità di scalabilità predefinita necessaria per l'applicazione. Per implementare solo un modello di prova del bus di eventi per l'ambiente di sviluppo, come nell'esempio eShopOnContainers, potrebbe essere sufficiente una semplice implementazione su RabbitMQ eseguito in un contenitore Docker.

Tuttavia, per i sistemi di produzione e mission-critical che necessitano di una scalabilità molto elevata, può essere opportuno valutare il bus di servizio di Azure. Per astrazioni e funzionalità di alto livello che semplificano lo sviluppo di applicazioni distribuite, è consigliabile valutare altri bus di servizio commerciali e open source, come NServiceBus, MassTransit e Brighter. Naturalmente, è possibile creare funzionalità personalizzate per il bus di servizio su tecnologie di livello inferiore come RabbitMQ e Docker. Un'attività tanto complessa potrebbe tuttavia avere dei costi troppo elevati per un'applicazione aziendale personalizzata.

## <a name="resiliently-publishing-to-the-event-bus"></a>Pubblicazione resiliente per il bus di eventi

Un problema durante l'implementazione di un'architettura basata su eventi per più microservizi è come aggiornare in modo atomico lo stato nel microservizio originale, pubblicando al tempo stesso in modo resiliente l'evento di integrazione correlato nel bus di eventi, in qualche modo basato sulle transazioni. Ecco alcuni modi per eseguire questa operazione, anche se potrebbero essere adottati anche altri approcci.

- Uso di una coda transazionale (basata su DTC) come MSMQ. Questo, tuttavia, è un approccio di tipo legacy.

- Uso dell'[estrazione del log delle transazioni](https://www.scoop.it/t/sql-server-transaction-log-mining).

- Uso dello schema [Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing) completo.

- Uso dello [schema Outbox](https://www.kamilgrzybek.com/design/the-outbox-pattern/): una tabella di database transazionale come una coda di messaggi che sarà la base per un componente per la creazione di eventi, che crea l'evento e lo pubblica.

Altri aspetti da considerare quando si usa la comunicazione asincrona sono l'idempotenza dei messaggi e la deduplicazione dei messaggi. Questi argomenti sono trattati nella sezione [Implementazione della comunicazione basata su eventi tra microservizi (eventi di integrazione)](../multi-container-microservice-net-applications/integration-event-based-microservice-communications.md) più avanti in questa guida.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Messaggi guidati da eventi** \
  <https://soapatterns.org/design_patterns/event_driven_messaging>

- **Pubblica/Sottoscrivi canale** \
  <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- **Udi Dahan. Chiarito CQRS** \
  <http://udidahan.com/2009/12/09/clarified-cqrs/>

- **Separazione responsabilità di comando e query (CQRS)Command and Query Responsibility Segregation (CQRS)** \
  <https://docs.microsoft.com/azure/architecture/patterns/cqrs>

- **Comunicazione tra contesti delimitati** \
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- **Coerenza finale** \
  <https://en.wikipedia.org/wiki/Eventual_consistency>

- **Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling** \
  <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

> [!div class="step-by-step"]
> [Successivo](communication-in-microservice-architecture.md)
> [precedente](maintain-microservice-apis.md)
