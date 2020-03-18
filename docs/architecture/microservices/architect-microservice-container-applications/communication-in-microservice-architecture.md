---
title: Comunicazione in un'architettura di microservizi
description: Esaminare diverse modalità di comunicazione tra i microservizi, comprendere le implicazioni dei metodi sincroni e asincroni.
ms.date: 01/30/2020
ms.openlocfilehash: f2d6e78966bb7d5f481de6db0ab1dcfe2812a1b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401655"
---
# <a name="communication-in-a-microservice-architecture"></a>Comunicazione in un'architettura di microservizi

In un'applicazione monolitica in esecuzione in un singolo processo, i componenti si richiamano a vicenda tramite chiamate a metodi o funzioni a livello di linguaggio. Questi componenti possono essere strettamente accoppiati se si creano oggetti con il codice, ad esempio `new ClassName()`, o possono essere richiamati in modo disaccoppiato se si usa la funzionalità di inserimento delle dipendenze facendo riferimento ad astrazioni anziché a istanze di oggetti concrete. In entrambi i casi, gli oggetti vengono eseguiti all'interno del processo stesso. La sfida maggiore quando si passa da un'applicazione monolitica a un'applicazione basata su microservizi è rappresentata dalla modifica del meccanismo di comunicazione. Una conversione diretta dalle chiamate ai metodi in-process alle chiamate RPC nei servizi produrrà una comunicazione frammentata e non efficiente che non funzionerà correttamente negli ambienti distribuiti. Le problematiche legate alla corretta progettazione di un sistema distribuito sono così ben note che sono state stilate in un articolo relativo ai [luoghi comuni sull'elaborazione distribuita](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing), che elenca i presupposti su cui gli sviluppatori spesso si basano quando passano dalla progettazione monolitica a quella distribuita.

Non c'è un'unica soluzione ma ce ne sono diverse. Una soluzione prevede per quanto possibile l'isolamento dei microservizi aziendali. Viene quindi usata una comunicazione asincrona tra i microservizi interni e si sostituisce la comunicazione con granularità fine tipica della comunicazione tra gli oggetti all'interno di un processo con una comunicazione con granularità grossolana. A tale scopo è possibile raggruppare le chiamate e restituire al client i dati che aggregano i risultati di più chiamate interne.

Un'applicazione basata su microservizi è un sistema distribuito in esecuzione in più processi o servizi, in genere anche in più server o host. Ogni istanza del servizio è in genere un processo. Di conseguenza, i servizi devono interagire usando un protocollo di comunicazione tra più processi, ad esempio HTTP, AMQP o un protocollo binario come TCP, a seconda della natura di ogni servizio.

La community dei microservizi promuove la filosofia "[smart endpoints and dumb pipes](https://simplicable.com/new/smart-endpoints-and-dumb-pipes)", ovvero "endpoint intelligenti e tubi porta-dati", che incoraggia una progettazione che sia quanto più disaccoppiata possibile tra i microservizi e quanto più coesa possibile all'interno di un singolo microservizio. Come spiegato in precedenza, ogni microservizio possiede i propri dati e la propria logica di dominio. Ma i microservizi che compongono un'applicazione end-to-end sono in genere semplicemente coreografati mediante le comunicazioni REST anziché i protocolli complessi come WS-\* e le comunicazioni flessibili basate sugli eventi anziché gli agenti di orchestrazione di processi aziendali centralizzati.

I due protocolli comunemente usati sono richiesta/risposta HTTP con API delle risorse (soprattutto per l'esecuzione di query) e messaggistica asincrona lightweight per l'aggiornamento della comunicazione tra più microservizi. Questi protocolli vengono descritti più dettagliatamente nelle sezioni seguenti.

## <a name="communication-types"></a>Tipi di comunicazione

Il client e i servizi possono comunicare attraverso molti tipi di comunicazione diversi, ciascuno dei quali destinato a uno scenario e obiettivi diversi. Inizialmente, questi tipi di comunicazione possono essere classificati in due assi.

Il primo asse definisce se il protocollo è sincrono o asincrono:

- Protocollo sincrono. HTTP è un protocollo sincrono. Il client invia una richiesta e attende una risposta dal servizio. Tale processo è indipendente dall'esecuzione del codice client che può essere sincrono (thread bloccato) o asincrono (thread non bloccato e la risposta alla fine raggiunge un callback). L'aspetto importante è che il protocollo (HTTP/HTTPS) è sincrono e il codice client può continuare l'attività solo quando riceve la risposta del server HTTP.

- Protocollo asincrono. Altri protocolli quali AMQP (un protocollo supportato da molti sistemi operativi e ambienti cloud) usano messaggi asincroni. Il codice client o il mittente del messaggio in genere non attende una risposta. Invia semplicemente il messaggio analogamente all'invio di un messaggio a una coda RabbitMQ o a un qualsiasi altro broker di messaggi.

Il secondo asse definisce se la comunicazione ha un singolo destinatario o più destinatari:

- Singolo destinatario. Ogni richiesta deve essere elaborata da esattamente un destinatario o servizio. Un esempio di questo tipo di comunicazione è il [Command pattern](https://en.wikipedia.org/wiki/Command_pattern).

- Più destinatari. Ogni richiesta può essere elaborata da zero a più destinatari. Questo tipo di comunicazione deve essere asincrono. Un esempio è il meccanismo di [pubblicazione/sottoscrizione](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) usato in schemi come l'[architettura basata su eventi](https://microservices.io/patterns/data/event-driven-architecture.html). Questo meccanismo si basa su un'interfaccia del bus di eventi o su un broker di messaggi per la propagazione degli aggiornamenti dei dati tra più microservizi attraverso gli eventi. In genere viene implementato con un bus di servizio o un elemento simile, ad esempio il [bus di servizio di Azure](https://azure.microsoft.com/services/service-bus/) usando [argomenti e sottoscrizioni](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).

Un'applicazione basata su microservizi userà spesso una combinazione di questi stili di comunicazione. Il tipo più comune è la comunicazione con singolo destinatario con un protocollo sincrono come HTTP/HTTPS quando si richiama un servizio HTTP API Web normale. I microservizi usano in genere anche i protocolli di messaggistica per la comunicazione asincrona tra microservizi.

È opportuno conoscere questi assi in modo che ci sia chiarezza sui possibili meccanismi di comunicazione, ma non sono aspetti importanti da prendere in considerazione per la creazione di microservizi. Per l'integrazione dei microservizi non serve prendere in considerazione né la natura asincrona dell'esecuzione dei thread del client né la natura asincrona del protocollo selezionato. L'aspetto che *è* importante è la possibilità di integrare in modo asincrono i microservizi mantenendone al contempo l'indipendenza, come illustrato nella sezione seguente.

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>L'integrazione di microservizi asincroni impone l'autonomia del microservizio

Come illustrato in precedenza, l'aspetto importante per la creazione di un'applicazione basata su microservizi è il modo in cui vengono integrati i microservizi. L'ideale sarebbe provare a ridurre al minimo la comunicazione tra i microservizi interni. È preferibile che le comunicazioni tra i microservizi siano minime. Ma in molti casi è necessario integrare in qualche modo i microservizi. In tal caso, la regola essenziale è che la comunicazione tra i microservizi sia asincrona. Ciò non significa che sia necessario usare un protocollo specifico (ad esempio, messaggistica asincrona rispetto a HTTP sincrono). Significa semplicemente che la comunicazione tra i microservizi deve essere eseguita solo propagando i dati in modo asincrono, ma è preferibile non dipendere da altri microservizi interni come parte dell'operazione di richiesta/risposta HTTP del servizio iniziale.

Se possibile, non dipendere mai dalla comunicazione sincrona (richiesta/risposta) tra più microservizi, neanche per le query. L'obiettivo di ogni microservizio è quello di essere autonomo e disponibile per il consumer client, anche se gli altri servizi che fanno parte dell'applicazione end-to-end sono inattivi o non integri. Se si ritiene che sia necessario effettuare una chiamata da un microservizio ad altri microservizi (ad esempio, per eseguire una richiesta HTTP per una query di dati) per inviare una risposta a un'applicazione client, si avrà un'architettura che non sarà resiliente quando alcuni microservizi hanno esito negativo.

Inoltre, se si hanno dipendenze HTTP tra microservizi, come per la creazione di lunghi cicli di richieste/risposte HTTP con catene di richieste HTTP, come illustrato nella prima parte della figura 4-15, non solo si avranno microservizi non autonomi ma si avranno anche ripercussioni sulle prestazioni non appena uno dei servizi della catena non viene eseguito correttamente.

Più si aggiungono dipendenze sincrone tra i microservizi, come per le richieste di query e peggiore sarà il tempo di risposta complessivo necessario per le app client.

![Diagramma che mostra tre tipi di comunicazioni tra microservizi.](./media/communication-in-microservice-architecture/sync-vs-async-patterns-across-microservices.png)

**Figura 4-15**. Schemi e antipattern nella comunicazione tra microservizi

Come illustrato nel diagramma precedente, nella comunicazione sincrona viene creata una "catena" di richieste tra microservizi durante la gestione della richiesta del client. Questo è un anti-pattern. Nella comunicazione asincrona i microservizi usano messaggi asincroni o il polling HTTP per comunicare con altri microservizi, ma la richiesta del client viene gestita immediatamente.

Se un microservizio deve generare un'azione aggiuntiva in un altro microservizio, se possibile non eseguire tale azione in modo sincrono e come parte dell'operazione di richiesta e risposta originale del microservizio. Eseguire invece l'azione in modo asincrono (usando la messaggistica asincrona o eventi di integrazione, code e così via). Tuttavia, per quanto possibile, non richiamare l'azione in modo sincrono come parte dell'operazione di richiesta e risposta sincrona originale.

Infine, e questo è il punto in cui si verifica la maggior parte dei problemi quando si creano i microservizi, se il microservizio iniziale necessita di dati originariamente di proprietà di altri microservizi, evitare di effettuare richieste sincrone per tali dati. Replicare o propagare i dati (solo gli attributi necessari) nel database del servizio iniziale usando la coerenza finale. In genere si usano gli eventi di integrazione, come illustrato nelle sezioni successive.

Come indicato in precedenza nella sezione Identificazione dei limiti del modello di dominio per ogni sezione dei [microservizi,](identify-microservice-domain-model-boundaries.md) la duplicazione di alcuni dati tra diversi microservizi non è una progettazione non corretta, al contrario, in questo modo è possibile tradurre i dati nella lingua o nei termini specifici di tale dominio aggiuntivo o contesto delimitato. Ad esempio, [nell'applicazione eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) si `identity-api` dispone di un microservizio denominato responsabile della maggior `User`parte dei dati dell'utente con un'entità denominata . Tuttavia, quando è necessario archiviare `Ordering` i dati relativi all'utente all'interno del microservizio, archiviarli come entità diversa denominata `Buyer`. L'entità `Buyer` condivide la stessa `User` identità con l'entità originale, `Ordering` ma potrebbe avere solo i pochi attributi necessari per il dominio e non l'intero profilo utente.

È possibile usare qualsiasi protocollo per comunicare e propagare i dati in modo asincrono tra i microservizi per avere la coerenza finale. Come illustrato in precedenza, è possibile usare gli eventi di integrazione mediante un bus di eventi o un broker di messaggi oppure è anche possibile usare HTTP eseguendo il polling degli altri servizi. Non importa. La regola importante consiste nel non creare dipendenze sincrone tra i microservizi.

Le sezioni seguenti illustrano i diversi stili di comunicazione che è possibile usare in un'applicazione basata su microservizi.

## <a name="communication-styles"></a>Stili di comunicazione

Esistono molti protocolli e opzioni che è possibile adottare per la comunicazione, a seconda del tipo di comunicazione che si vuole usare. Se si usa un meccanismo di comunicazione basato su richiesta/risposta sincrona, i protocolli come HTTP e REST sono i più comuni, soprattutto se si pubblicano i servizi all'esterno del cluster del microservizio o dell'host Docker. Se la comunicazione tra i servizi avviene internamente, all'interno del cluster del microservizio o dell'host Docker, è anche possibile usare i meccanismi di comunicazione in formato binario, ad esempio WCF con TCP e formato binario. In alternativa, è possibile usare i meccanismi di comunicazione asincrona basata su messaggi come AMQP.

Esistono inoltre diversi formati di messaggio come JSON o XML o anche formati binari che possono essere più efficienti. Se il formato binario scelto non è un formato standard, probabilmente non è una buona idea pubblicare pubblicamente i servizi usando tale formato. È possibile usare un formato non standard per la comunicazione interna tra microservizi, ad esempio per la comunicazione tra microservizi all'interno del cluster del microservizio o dell'host Docker (ad esempio, agenti di orchestrazione Docker) oppure per le applicazioni client proprietarie che comunicano con i microservizi.

### <a name="requestresponse-communication-with-http-and-rest"></a>Comunicazione di tipo richiesta/risposta con HTTP e REST

Quando un client usa la comunicazione di tipo richiesta/risposta, invia una richiesta a un servizio, quindi il servizio elabora la richiesta e restituisce una risposta. La comunicazione di tipo richiesta/risposta è particolarmente indicata per eseguire query sui dati per un'interfaccia utente in tempo reale dalle app client. Pertanto, in un'architettura di microservizi probabilmente si userà questo meccanismo di comunicazione per la maggior parte delle query, come illustrato nella figura 4-16.

![Diagramma che mostra le comunicazioni richiesta/risposta per le query e gli aggiornamenti in tempo reale.](./media/communication-in-microservice-architecture/request-response-comms-live-queries-updates.png)

**Figura 4-16**. Uso della comunicazione di tipo richiesta/risposta HTTP (sincrona o asincrona)

Quando un client usa la comunicazione di tipo richiesta/risposta, si presuppone che la risposta venga recapitata in breve tempo, in genere meno di un secondo o al massimo alcuni secondi. Per le risposte ritardate, è necessario implementare la comunicazione asincrona in base a [schemi di messaggistica](https://docs.microsoft.com/azure/architecture/patterns/category/messaging) e [tecnologie di messaggistica](https://en.wikipedia.org/wiki/Message-oriented_middleware), che rappresenta un approccio diverso illustrato nella sezione successiva.

Uno stile architetturale diffuso per la comunicazione di tipo richiesta/risposta è [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). Questo approccio è basato sul protocollo [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) a cui è strettamente collegato adottando verbi HTTP come GET, POST e PUT. REST è l'approccio di comunicazione architetturale usato più di frequente quando si creano i servizi. È possibile implementare i servizi REST quando si sviluppano i servizi API Web ASP.NET Core.

L'uso di servizi REST HTTP come linguaggio di definizione dell'interfaccia offre un valore aggiunto. Ad esempio, se si usano i [metadati Swagger](https://swagger.io/) per descrivere l'API del servizio, è possibile usare gli strumenti che generano gli stub client in grado di individuare e usare direttamente i servizi.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Martin Fowler. Richardson Maturity Model** Una descrizione del modello REST. \
  <https://martinfowler.com/articles/richardsonMaturityModel.html>

- **Swagger** Il sito ufficiale. \
  <https://swagger.io/>

### <a name="push-and-real-time-communication-based-on-http"></a>Comunicazione push e in tempo reale basata su HTTP

Un'altra possibilità (in genere per scopi diversi rispetto a REST) è una comunicazione in tempo reale e uno-a-molti con framework di livello superiore quali [ASP.NET SignalR](https://www.asp.net/signalr) e protocolli come [WebSocket](https://en.wikipedia.org/wiki/WebSocket).

Come mostrato nella figura 4-17, la comunicazione HTTP in tempo reale significa che il server può eseguire il push del contenuto ai client connessi man mano che i dati diventano disponibili, anziché dover attendere che un client richieda nuovi dati.

![Diagramma che mostra le comunicazioni push e in tempo reale in base a SignalR.](./media/communication-in-microservice-architecture/one-to-many-communication.png)

**Figura 4-17**. Comunicazione asincrona di messaggi in tempo reale uno-a-uno

SignalR è un buon metodo per ottenere la comunicazione in tempo reale per eseguire il push del contenuto ai client da un server back-end. Poiché la comunicazione è in tempo reale, le app client mostrano le modifiche quasi immediatamente. Questa operazione viene in genere gestita da un protocollo, ad esempio WebSocket, usando molte connessioni WebSocket (una per ogni client). Un esempio tipico è quando un servizio comunica contemporaneamente una modifica del punteggio di un gioco sportivo alle app Web di molti client.

>[!div class="step-by-step"]
>[Successivo](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
>[precedente](asynchronous-message-based-communication.md)
