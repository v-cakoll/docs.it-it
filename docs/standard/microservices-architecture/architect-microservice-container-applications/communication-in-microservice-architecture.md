---
title: Comunicazione in un'architettura microservizio
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Comunicazione in un'architettura di architettura microservizio
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8d38095a151b7568619b17340d768eff684d3271
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="communication-in-a-microservice-architecture"></a>Comunicazione in un'architettura microservizio

In un'applicazione monolitica in esecuzione in un unico processo, i componenti richiamano tra loro tramite chiamate di funzione o metodo a livello di linguaggio. Questi può essere fortemente accoppiati se si siano creando oggetti con il codice (ad esempio, `new ClassName()`), o può essere richiamato in modo separato, se si utilizza Dependency Injection facendo riferimento astrazioni anziché a istanze di un oggetto concreto. In entrambi i casi, gli oggetti sono in esecuzione all'interno del processo stesso. L'aspetto più impegnativo durante la modifica di un'applicazione monolitica a un'applicazione basata su microservizi risiede nel modificare il meccanismo di comunicazione. Una conversione diretta dalle chiamate ai metodi in-process in chiamate RPC ai servizi provocherà un "frammentate" e la comunicazione non efficiente che non verrà eseguite anche in ambienti distribuiti. Le problematiche di progettazione di un sistema distribuito correttamente sono sufficientemente noti che è anche un canon noto come il [il fallacies delle applicazioni distribuite](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) che elenca i presupposti che gli sviluppatori spesso durante lo spostamento da monolitico alle progettazioni distribuite.

È una soluzione non, ma diversi. Una soluzione prevede l'isolamento di microservizi business quanto possibile. Quindi, usano la comunicazione asincrona tra il microservizi interno e sostituire le comunicazioni con granularità fine sono tipica delle comunicazioni interne del processo tra gli oggetti con granularità grossolana comunicazione. È possibile farlo mediante il raggruppamento di chiamate e restituendo i dati che aggrega i risultati di più chiamate interne, al client.

Un'applicazione basata su microservizi è un sistema distribuito in esecuzione in più processi o servizi, in genere anche in più server o host. Ogni istanza del servizio è in genere un processo. Di conseguenza, i servizi devono interagire usando un protocollo di comunicazione tra processi, ad esempio HTTP, AMQP o un protocollo binario come TCP, a seconda della natura di ogni servizio.

La Comunità microservizio Alza di livello la filosofia di "[smart endpoint e pipe dumb](http://simplicable.com/new/smart-endpoints-and-dumb-pipes)." Questo slogan incoraggia progettato come disaccoppiati possibile tra microservizi e come coesiva come possibili all'interno di un singolo microservizio. Come spiegato in precedenza, ogni microservizio possiede i propri dati e la propria logica di dominio. Ma la composizione di un'applicazione end-to-end di microservizi sono in genere semplicemente concertate utilizzando le comunicazioni REST anziché un protocolli complessi, ad esempio WS -\* e le comunicazioni flessibile basato su eventi invece di centralizzata orchestrators di processo di business.

I due protocolli comunemente usati sono HTTP richiesta/risposta con la risorsa API (quando l'esecuzione di query la maggior parte di tutti) e aggiorna il lightweight messaggistica asincrona durante la comunicazione tra più microservizi. Questi sono spiegati in dettaglio nelle sezioni seguenti.

## <a name="communication-types"></a>Tipi di comunicazione

Servizi e client possono comunicare attraverso molti tipi diversi di comunicazione, ciascuno di essi destinata a uno scenario diverso e obiettivi. Inizialmente, i tipi di comunicazione possono essere classificati in due assi.

Se il protocollo è sincrono o asincrono consiste nel definire il primo asse:

-   Protocollo sincrono. HTTP è un protocollo sincrono. Il client invia una richiesta e attende una risposta dal servizio. Che è indipendente dell'esecuzione del codice client che può essere sincrono (thread bloccato) o asincrono (thread non è bloccato e la risposta raggiungerà un callback alla fine). Ecco l'aspetto importante è che il protocollo (HTTP/HTTPS) è sincrono e il codice client può continuare solo la propria attività quando riceve la risposta del server HTTP.

-   Protocollo asincrono. Altri protocolli quali AMQP (un protocollo supportato da molti sistemi operativi e ambienti cloud) utilizzano messaggi asincroni. Il mittente del messaggio o del codice di client in genere non attendere una risposta. Invia solo il messaggio come quando si invia un messaggio a una coda RabbitMQ o qualsiasi altro broker di messaggi.

Il secondo asse consiste nel definire se la comunicazione con un singolo ricevitore o più destinatari:

-   Singolo destinatario. Ogni richiesta deve essere elaborata esattamente un ricevitore o un servizio. Un esempio di questo tipo di comunicazione è la [pattern comandi](https://en.wikipedia.org/wiki/Command_pattern).

-   Più ricevitori. Ogni richiesta può essere elaborato da zero a più ricevitori. Questo tipo di comunicazione deve essere asincrono. Un esempio è la [pubblicazione/sottoscrizione](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) meccanismo utilizzato per modelli come [architettura basata su evento](http://microservices.io/patterns/data/event-driven-architecture.html). Si basa su un'interfaccia o messaggio Service broker di bus di eventi durante la propagazione degli aggiornamenti di dati tra più microservizi tramite eventi; viene in genere implementato tramite un bus di servizio o un elemento simile come [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) utilizzando [argomenti e sottoscrizioni](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).

Un'applicazione basata su microservizio utilizzerà spesso una combinazione di questi stili di comunicazione. Il tipo più comune è singolo ricevitore comunicazione con un protocollo sincrono come HTTP/HTTPS quando si richiama un servizio Web API HTTP regolare. Microservizi inoltre in genere utilizzano i protocolli di messaggistica per la comunicazione asincrona tra microservizi.

Questi assi sono efficaci per conoscere, pertanto è necessario maggiore chiarezza sui meccanismi di comunicazione possibili, ma non sono importanti problemi da affrontare quando si compila microservizi. La natura asincrona dell'esecuzione del thread client nemmeno la natura asincrona del protocollo selezionato sono le considerazioni per l'integrazione di microservizi. Cosa *è* importante è la possibilità di integrare in modo asincrono il microservizi mantenendo l'indipendenza di microservizi, come illustrato nella sezione seguente.

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>Integrazione microservizio asincrona impone l'autonomia del microservizio.

Come accennato, l'aspetto importante quando si compila un'applicazione basata su microservizi è il modo in cui si integrano il microservizi. Idealmente, è consigliabile provare a ridurre al minimo la comunicazione tra il microservizi interno. Il minore le comunicazioni tra microservizi, l'approccio migliore. Ma ovviamente, in molti casi è necessario integrare in qualche modo la microservizi. Quando è necessario eseguire questa operazione, la regola di critici è che la comunicazione tra il microservizi deve essere asincrona. Ciò non significa che è necessario utilizzare un protocollo specifico (ad esempio messaggistica asincrona e sincrona HTTP). Significa semplicemente che la comunicazione tra microservizi deve essere eseguito solo la propagazione dei dati in modo asincrono, ma è preferibile non dipendono da altri microservizi interno come parte dell'operazione di richiesta/risposta HTTP del servizio iniziale.

Se possibile, mai dipendono comunicazione sincrona (richiesta/risposta) tra più microservizi, nonché per le query. L'obiettivo di ogni microservizio è essere autonomi e disponibili per l'utente del client, anche se gli altri servizi che fanno parte dell'applicazione end-to-end inattivo o non integro. Se si ritiene che si desidera effettuare una chiamata da un microservizio a altri microservizi (ad esempio l'esecuzione di una richiesta HTTP per una query di dati) in ordine per essere in grado di fornire una risposta a un'applicazione client, si dispone di un'architettura che non potrà essere resiliente quando alcuni microservizi esito negativo.

Inoltre, con dipendenze HTTP tra microservizi, come durante la creazione di lunghi cicli di richiesta/risposta HTTP richiedono catene, come illustrato nella prima parte della figura 4-15, non solo rende il microservizi non autonomo ma anche le prestazioni è interessati non appena uno dei servizi della catena non viene eseguito correttamente. 

Più si aggiungono le dipendenze sincrona tra microservizi, ad esempio le richieste di query, il tempo di risposta complessivo di peggiore Ottiene per le applicazioni client.

![](./media/image15.png)

**Figura 4-15**. Anti-pattern e modelli di comunicazione tra microservizi

Se deve generare un'azione aggiuntiva in un altro microservizio del microservizio, se possibile, non eseguire tale operazione in modo sincrono e come parte dell'operazione di richiesta e risposta microservizio originale. In alternativa, eseguire questa operazione in modo asincrono (tramite la messaggistica asincrona o eventi di integrazione, code, ecc.). Tuttavia, per quanto possibile, non richiamare l'azione in modo sincrono come parte dell'operazione di richiesta e risposta sincrona originale.

E infine (si tratta di in cui la maggior parte dei problemi si verificano durante la compilazione di microservizi), se del microservizio iniziale necessita di dati di origine sono di proprietà di altri microservizi, non fare affidamento su effettua richieste sincrone per tali dati. Invece, la replica o propagare tali dati (solo gli attributi è necessario) nel database del servizio iniziale usando la coerenza eventuale (in genere con gli eventi di integrazione, come illustrato nelle sezioni successive).

Come notato in precedenza nella sezione [che identifica i limiti di modello di dominio per ogni microservizio](#identifying-domain-model-boundaries-for-each-microservice), la duplicazione di alcuni dei dati tra diversi microservizi non è una progettazione non corretta, al contrario, quando tale che si possono tradurre i dati nella lingua specifica o condizioni di tale dominio aggiuntivo o contesto limitato. Ad esempio, il [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) applicazione si dispone di un microservizio denominato identity.api che è responsabile della maggior parte dei dati dell'utente con un'entità denominata utente. Tuttavia, quando è necessario archiviare i dati relativi all'utente all'interno di microservizio l'ordinamento, è archiviarlo come un'entità diversa denominata acquirente. L'entità Buyer condivide la stessa identità con l'entità utente originale, ma potrebbe contenere alcuni attributi che è necessari per il dominio di ordinamento e non l'intero profilo utente.

È possibile utilizzare qualsiasi protocollo di comunicazione e i dati vengono propagati in modo asincrono tra microservizi per avere la coerenza eventuale. Come accennato, è possibile utilizzare gli eventi di integrazione con un messaggio di Service broker o è anche possibile usare HTTP tramite il polling invece di altri servizi o il bus di eventi. Non è importante. La regola importante consiste nel creare non sincrone dipendenze tra i microservizi.

Le sezioni seguenti illustrano i diversi stili di comunicazione, che è possibile utilizzare in un'applicazione basata su microservizio.

## <a name="communication-styles"></a>Stili di comunicazione

Esistono molti protocolli e opzioni che è possibile utilizzare per la comunicazione, a seconda del tipo di comunicazione che si desidera utilizzare. Se si utilizza un meccanismo di comunicazione basata su richiesta/risposta sincrona, protocolli, ad esempio HTTP e altri approcci sono più comuni, specialmente se si desidera pubblicare i servizi all'esterno del cluster di host o microservizio Docker. Se la comunicazione tra i servizi (all'interno del cluster di host o microservizi Docker) è inoltre possibile utilizzare i meccanismi di comunicazione formato binario (ad esempio, comunicazione remota di Service Fabric o WCF utilizzando TCP e formato binario). In alternativa, è possibile utilizzare i meccanismi di comunicazione asincrona e basata su messaggi, ad esempio AMQP.

Sono inoltre più formati di messaggio come JSON o XML o binari anche formati, che possono essere più efficienti. Se il formato binario scelto non è uno standard, probabilmente non è una buona idea pubblicamente pubblicare i servizi utilizzando tale formato. È possibile utilizzare un formato non standard per le comunicazioni interne tra il microservizi. È possibile farlo durante la comunicazione tra microservizi all'interno del cluster di host o microservizio del Docker (orchestrators Docker o Azure Service Fabric) o per le applicazioni client proprietarie che comunicano con il microservizi.

### <a name="requestresponse-communication-with-http-and-rest"></a>Comunicazione richiesta/risposta HTTP e REST 

Quando un client usa la comunicazione richiesta/risposta, invia una richiesta a un servizio, quindi il servizio elabora la richiesta e restituisce una risposta. Comunicazione richiesta/risposta è particolarmente adatto per eseguire query sui dati per un'interfaccia utente in tempo reale (un'interfaccia utente in tempo reale) dalle applicazioni client. Pertanto, in un'architettura microservizio è probabilmente utilizzerà questo meccanismo di comunicazione per la maggior parte delle query, come illustrato nella figura 4-16.

![](./media/image16.png)

**Figura 4-16**. Utilizzo di comunicazione richiesta/risposta HTTP (sincrona o asincrona)

Quando un client usa la comunicazione richiesta/risposta, si presuppone che la risposta verrà recapitato in un breve periodo di tempo, in genere meno di un secondo o pochi secondi al massimo. Per le risposte ritardate, è necessario implementare la comunicazione asincrona in base a [modelli di messaggistica](https://docs.microsoft.com/azure/architecture/patterns/category/messaging) e [tecnologie di messaggistica](https://en.wikipedia.org/wiki/Message-oriented_middleware), che è un approccio diverso che viene descritto nella sezione successiva.

È uno stile architettura comune per la comunicazione richiesta/risposta [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). Questo approccio è basato su e strettamente associata, il [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) del protocollo, l'adozione di verbi HTTP come GET, POST e inserire. REST è l'approccio dell'architettura di comunicazione utilizzate più di frequente quando si creano servizi. È possibile implementare i servizi REST quando si sviluppano servizi API Web di ASP.NET Core.

È il valore di aggiuntivo quando si utilizzano i servizi REST di HTTP come linguaggio di definizione di interfaccia. Ad esempio, se si utilizza [metadati Swagger](http://swagger.io/) per descrivere l'API del servizio, è possibile utilizzare gli strumenti che generano gli stub di client che è possano direttamente individuare e utilizzare i servizi.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Martin Fowler. Richardson Maturity Model.** Descrizione del modello REST.
    [*http://martinfowler.com/articles/richardsonMaturityModel.HTML*](http://martinfowler.com/articles/richardsonMaturityModel.html)

-   **Swagger.** Il sito ufficiale.
    [*http://swagger.IO/*](http://swagger.io/)

### <a name="push-and-real-time-communication-based-on-http"></a>Comunicazione in tempo reale basate su HTTP e push

Un'altra possibilità (in genere per scopi diversi rispetto a REST) è una comunicazione in tempo reale e uno-a-molti con Framework di livello superiore quali [ASP.NET SignalR](https://www.asp.net/signalr) e protocolli, ad esempio [WebSocket](https://en.wikipedia.org/wiki/WebSocket).

Come mostrato nella figura 4-17, la comunicazione HTTP in tempo reale significa che è possibile avere codice server pubblicato il contenuto ai client connessi, come i dati diventano disponibili, anziché il server di attendere che un client di richiedere nuovi dati.

![](./media/image17.png)

**Figura 4-17**. Comunicazione uno a uno dei messaggi asincroni in tempo reale

Poiché la comunicazione in tempo reale, le app client mostrano le modifiche quasi istantaneamente. Questa operazione viene in genere gestita da un protocollo, ad esempio WebSocket, utilizzando un numero di connessioni WebSocket (uno per ogni client). Un esempio tipico è quando un servizio comunica una modifica il punteggio di un gioco sportivi nelle App web di numerosi client contemporaneamente.


>[!div class="step-by-step"]
[Precedente] [Avanti] (asincrono-messaggio-base-communication.md) (direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
