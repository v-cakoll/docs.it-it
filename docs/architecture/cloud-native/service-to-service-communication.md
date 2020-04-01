---
title: Comunicazione da servizio a servizio
description: Scopri come i microservizi back-end nativi cloud comunicano con altri microservizi back-end.
author: robvet
ms.date: 09/09/2019
ms.openlocfilehash: 926be3c2eb4513c89ebcd1f31dceb7d58639dc6f
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523555"
---
# <a name="service-to-service-communication"></a>Comunicazione da servizio a servizio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Passando dal client front-end, ora ci rivoliamo ai microservizi back-end comunicano tra loro.

Quando si costruisce un'applicazione cloud-native, è consigliabile essere sensibili al modo in cui i servizi back-end comunicano tra loro. Idealmente, meno comunicazione tra servizi, meglio è. Tuttavia, evitare non è sempre possibile in quanto i servizi back-end spesso si basano l'uno sull'altro per completare un'operazione.

Esistono diversi approcci ampiamente accettati per l'implementazione della comunicazione tra servizi. Il *tipo di interazione di comunicazione* spesso determinerà l'approccio migliore.

Considerare i seguenti tipi di interazione:

- *Query:* quando un microservizio chiamante richiede una risposta da un microservizio chiamato, ad esempio "Ehi, forniscimi le informazioni sull'acquirente per un determinato ID cliente".

- *Comando:* quando il microservizio chiamante necessita di un altro microservizio per eseguire un'azione ma non richiede una risposta, ad esempio "Ehi, spedisci questo ordine".

- *Evento:* quando un microservizio, denominato editore, genera un evento che lo stato è stato modificato o si è verificata un'azione. Altri microservizi, denominati sottoscrittori, interessati, possono reagire all'evento in modo appropriato. Il server di pubblicazione e gli abbonati non sono a conoscenza l'uno dell'altro.

I sistemi di microservizio usano in genere una combinazione di questi tipi di interazione durante l'esecuzione di operazioni che richiedono l'interazione tra servizi. Diamo un'occhiata da vicino a ciascuno e come si potrebbe implementarli.

## <a name="queries"></a>Query

Molte volte, un microservizio potrebbe essere necessario *eseguire una query* un altro, richiedendo una risposta immediata per completare un'operazione. Un microservizio del carrello della spesa potrebbe aver bisogno di informazioni sui prodotti e di un prezzo per aggiungere un articolo al carrello. Esistono diversi approcci per l'implementazione di operazioni di query.

### <a name="requestresponse-messaging"></a>Messaggistica di tipo richiesta/risposta

Un'opzione per l'implementazione di questo scenario è che il microservizio back-end chiamante effettui richieste HTTP dirette ai microservizi di cui deve eseguire una query, illustrato nella Figura 4-8.

![Comunicazione HTTP diretta](./media/direct-http-communication.png)

**Figura 4-8**. Comunicazione HTTP diretta

Mentre le chiamate HTTP dirette tra microservizi sono relativamente semplici da implementare, è necessario prestare attenzione a ridurre al minimo questa pratica. Per iniziare, queste chiamate sono sempre *sincrone* e bloccheranno l'operazione fino a quando non viene restituito un risultato o si scade la richiesta. Quelli che un tempo erano autonomi, servizi indipendenti, in grado di evolversi in modo indipendente e di distribuirsi frequentemente, ora diventano accoppiati tra loro. Con l'aumento dell'accoppiamento tra i microservizi, i loro benefici architettonici diminuiscono.

L'esecuzione di una richiesta poco frequente che effettua una singola chiamata HTTP diretta a un altro microservizio potrebbe essere accettabile per alcuni sistemi. Tuttavia, le chiamate con volumi elevati che richiamano chiamate HTTP dirette a più microservizi non sono consigliabili. Possono aumentare la latenza e influire negativamente sulle prestazioni, la scalabilità e la disponibilità del sistema. Ancora peggio, una lunga serie di comunicazioni HTTP dirette può portare a catene profonde e complesse di chiamate di microservizi sincroni, illustrato nella figura 4-9:

![Concatenamento di query HTTP](./media/chaining-http-queries.png)

**Figura 4-9**. Concatenamento di query HTTP

Si può certamente immaginare il rischio nel disegno mostrato nell'immagine precedente. Cosa succede \#se il passaggio 3 non riesce? O \#il passaggio 8 non riesce? Come si fa a recuperare? Cosa succede \#se il passaggio 6 è lento perché il servizio sottostante è occupato? Come si continua? Anche se tutto funziona correttamente, pensare alla latenza che questa chiamata comporterebbe, che è la somma della latenza di ogni passaggio.

Il grande grado di accoppiamento nell'immagine precedente suggerisce che i servizi non sono stati modellati in modo ottimale. Sarebbe doveroso che il team rivisiti il loro design.

### <a name="materialized-view-pattern"></a>Modello di vista materializzata

Un'opzione popolare per la rimozione dell'accoppiamento dei microservizi è il [modello Vista materializzata.](https://docs.microsoft.com/azure/architecture/patterns/materialized-view) Con questo modello, un microservizio archivia la propria copia locale denormalizzata dei dati di proprietà di altri servizi. Invece del microservizio Shopping Basket che esegue query sui microservizi Product Catalog e Pricing, mantiene la propria copia locale di tali dati. Questo modello elimina l'accoppiamento non necessario e migliora l'affidabilità e il tempo di risposta. L'intera operazione viene eseguita all'interno di un singolo processo. Esaminiamo questo modello e altre preoccupazioni relative ai dati nel capitolo 5.

### <a name="service-aggregator-pattern"></a>Modello di aggregatore di serviziService Aggregator Pattern

Un'altra opzione per eliminare l'accoppiamento microservizio-microservizio è un [microservizio Aggregator](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/), mostrato in viola nella figura 4-10.

![Servizio Aggregatore](./media/aggregator-service.png)

**Figura 4-10**. Microservizio aggregatore

Il modello isola un'operazione che effettua chiamate a più microservizi back-end, centralizzando la logica in un microservizio specializzato.  Il microservizio dell'aggregatore di estrazione viola nella figura precedente orchestra il flusso di lavoro per l'operazione di estrazione. Include chiamate a diversi microservizi back-end in un ordine in sequenza. I dati del flusso di lavoro vengono aggregati e restituiti al chiamante. Sebbene implementi ancora chiamate HTTP dirette, il microservizio aggregatore riduce le dipendenze dirette tra i microservizi back-end.

### <a name="requestreply-pattern"></a>Modello di richiesta/risposta

Un altro approccio per la disaccoppiamento dei messaggi HTTP sincroni è un modello [di richiesta-risposta](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html), che utilizza la comunicazione di accodamento. La comunicazione tramite una coda è sempre un canale unidirezionale, con un producer che invia il messaggio e il consumer che lo riceve. Con questo modello, vengono implementate sia una coda di richieste che una coda di risposta, illustrata nella Figura 4-11.With this pattern, both a request queue are implemented, both a request queue are implemented, shown in Figure 4-11.

![Modello di richiesta-risposta](./media/request-reply-pattern.png)

**Figura 4-11**. Modello di richiesta-risposta

In questo caso, il produttore di messaggi crea un messaggio basato su query che contiene un ID di correlazione univoco e lo inserisce in una coda di richieste. Il servizio consumer deaccoda i messaggi, li elabora e inserisce la risposta nella coda di risposta con lo stesso ID di correlazione. Il servizio producer deaccoda il messaggio, lo associa all'ID di correlazione e continua l'elaborazione. Copriamo le code in dettaglio nella prossima sezione.

## <a name="commands"></a>Comandi:

Un altro tipo di interazione di comunicazione è un *comando*. Un microservizio potrebbe avere bisogno di un altro microservizio per eseguire un'azione. Il microservizio Ordering potrebbe richiedere il microservizio Shipping per creare una spedizione per un ordine approvato. Nella figura 4-12, un microservizio, denominato Producer, invia un messaggio a un altro microservizio, il consumer, comandandolo a eseguire un'operazione.

![Interazione dei comandi con una codaCommand interaction with a queue](./media/command-interaction-with-queue.png)

**Figura 4-12**. Interazione dei comandi con una codaCommand interaction with a queue

Molto spesso, il Produttore non richiede una risposta e può *sparare e dimenticare* il messaggio. Se è necessaria una risposta, il Consumatore invia un messaggio separato a Producer su un altro canale. Un messaggio di comando viene inviato in modo asincrono con una coda di messaggi. supportato da un broker di messaggi leggeri. Nel diagramma precedente, notare come una coda separa e separa entrambi i servizi.

Una coda di messaggi è un costrutto intermedio tramite il quale un producer e un consumer passano un messaggio. Le code implementano un modello di messaggistica punto-punto asincrono. Il Produttore sa dove un comando deve essere inviato e instrada in modo appropriato. La coda garantisce che un messaggio venga elaborato esattamente da una delle istanze consumer che stanno leggendo dal canale. In questo scenario, il producer o il servizio consumer può aumentare la scalabilità orizzontale senza influire sull'altro. Inoltre, le tecnologie possono essere disparate su ogni lato, il che significa che potremmo avere un microservizio Java che chiama un microservizio [Golang.](https://golang.org)

Nel capitolo 1, abbiamo parlato di servizi di *sostegno*. I servizi di supporto sono risorse ausiliarie da cui dipendono i sistemi nativi del cloud. Le code di messaggi supportano i servizi di backup. Il cloud di Azure supporta due tipi di code di messaggi che i sistemi nativi cloud possono usare per implementare la messaggistica dei comandi: Code di archiviazione di Azure e Code del bus di servizio di Azure.The Azure cloud supports two types of message queues that your cloud-native systems can consume to implement command messaging: Azure Storage Queues and Azure Service Bus Queues.

### <a name="azure-storage-queues"></a>Code di Archiviazione di Azure

Le code di archiviazione di Azure offrono una semplice infrastruttura di accodamento veloce, conveniente e supportata da account di archiviazione di Azure.Azure storage queues offer a simple queueing infrastructure that is fast, affordable, and backed by Azure storage accounts.

Le code di archiviazione di [Azure dispongono](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction) di un meccanismo di accodamento basato su REST con messaggistica affidabile e persistente. Forniscono un set di funzionalità minimo, ma sono poco costosi e archiviano milioni di messaggi. La loro capacità varia fino a 500 TB. Un singolo messaggio può avere una dimensione massima di 64 KB.

È possibile accedere ai messaggi da qualsiasi parte del mondo tramite chiamate autenticate tramite HTTP o HTTPS. Le code di archiviazione possono scalare orizzontalmente a un numero elevato di client simultanei per gestire i picchi di traffico.

Detto questo, ci sono limitazioni con il servizio:

- L'ordine dei messaggi non è garantito.

- Un messaggio può essere mantenuto solo per sette giorni prima che venga rimosso automaticamente.

- Il supporto per la gestione dello stato, il rilevamento duplicati o le transazioni non è disponibile.

Nella figura 4-13 viene illustrata la gerarchia di una coda di Archiviazione di Azure.Figure 4-13 shows the hierarchy of an Azure Storage Queue.

![Gerarchia delle code di archiviazione](./media/storage-queue-hierarchy.png)

**Figura 4-13**. Gerarchia delle code di archiviazione

Nella figura precedente, prendere nota di come le code di archiviazione archiviano i messaggi nell'account di archiviazione di Azure sottostante.

Per gli sviluppatori, Microsoft fornisce diverse librerie client e lato server per l'elaborazione della coda di archiviazione. La maggior parte delle piattaforme principali sono supportate tra cui .NET, Java, JavaScript, Ruby, Python e Go. Gli sviluppatori non devono mai comunicare direttamente con queste librerie. In questo modo, il codice del microservizio verrà associato al servizio di coda di Archiviazione di Azure.Doing so will tightly couple your microservice code to the Azure Storage Queue service. È consigliabile isolare i dettagli di implementazione dell'API. Introdurre un livello di intermediazione, o API intermedia, che espone operazioni generiche e incapsula la libreria concreta. Questo accoppiamento libero consente di scambiare un servizio di accodamento con un altro senza dover apportare modifiche al codice del servizio principale.

Le code di Archiviazione di Azure sono un'opzione economica per implementare la messaggistica dei comandi nelle applicazioni native cloud. Soprattutto quando una dimensione della coda supererà gli 80 GB o un semplice set di funzionalità è accettabile. Si paga solo per l'archiviazione dei messaggi; non ci sono costi orari fissi.

### <a name="azure-service-bus-queues"></a>Code del bus di servizio di Azure

Per requisiti di messaggistica più complessi, prendere in considerazione le code del bus di servizio di Azure.For more complex messaging requirements, consider Azure Service Bus queues.

Seduti in cima a una solida infrastruttura dei messaggi, [il bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) di servizio di Azure supporta un modello di *messaggistica negoziato.* I messaggi vengono archiviati in modo affidabile in un broker (la coda) fino alla ricezione dal consumer. La coda garantisce il recapito dei messaggi FIFO (First-In/First-Out), rispettando l'ordine in cui i messaggi sono stati aggiunti alla coda.

La dimensione di un messaggio può essere molto più grande, fino a 256 KB. I messaggi vengono mantenuti nella coda per un periodo di tempo illimitato. Il bus di servizio supporta non solo le chiamate basate su HTTP, ma fornisce anche il supporto completo per il [protocollo AMPQ.](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-amqp-overview) AMPQ è uno standard aperto tra i fornitori che supporta un protocollo binario e livelli di affidabilità più elevati.

Il bus di servizio offre un set completo di funzionalità, tra cui il supporto delle [transazioni](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions) e una funzionalità di [rilevamento duplicati.](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) La coda garantisce "al massimo il recapito" per messaggio. Elimina automaticamente un messaggio già inviato. Se un producer è in dubbio, può inviare nuovamente lo stesso messaggio e il bus di servizio garantisce che verrà elaborata una sola copia. Il rilevamento duplicati ti evita di dover creare ulteriori impianti idraulici dell'infrastruttura.

Altre due funzionalità aziendali sono il partizionamento e le sessioni. Una coda del bus di servizio convenzionale viene gestita da un singolo broker di messaggi e archiviata in un singolo archivio messaggi. Tuttavia, [il partizionamento](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) del bus di servizio distribuisce la coda tra più broker di messaggi e archivi messaggi. La velocità effettiva complessiva non è più limitata dalle prestazioni di un singolo broker di messaggi o di un archivio di messaggistica. Un'interruzione temporanea di un archivio di messaggistica non rende non disponibile una coda partizionata.

[Le sessioni del bus](https://codingcanvas.com/azure-service-bus-sessions/) di servizio consentono di raggruppare i messaggi relativi ai gruppi. Si immagini uno scenario di flusso di lavoro in cui i messaggi devono essere elaborati insieme e l'operazione completata alla fine. Per sfruttare i vantaggi, le sessioni devono essere abilitate in modo esplicito per la coda e ogni messaggio correlato deve contenere lo stesso ID di sessione.

Tuttavia, ci sono alcuni avvertimenti importanti: le code del bus di servizio sono limitate a 80 GB, che è molto più piccolo di quello disponibile dalle code dell'archivio. Inoltre, le code del bus di servizio comportano un costo di base e un addebito per operazione.

Nella figura 4-14 viene descritta l'architettura di alto livello di una coda del bus di servizio.

![Coda del bus di servizio](./media/service-bus-queue.png)

**Figura 4-14**. Coda del bus di servizio

Nella figura precedente, prendere nota della relazione punto-punto. Due istanze dello stesso provider stanno accodando messaggi in una singola coda del bus di servizio. Ogni messaggio viene utilizzato da una sola delle tre istanze consumer a destra. Successivamente, viene illustrato come implementare la messaggistica in cui utenti diversi possono essere tutti interessati allo stesso messaggio.

## <a name="events"></a>Eventi

Accodamento messaggi è un modo efficace per implementare la comunicazione in cui un producer può inviare un messaggio a un consumer in modo asincrono. Tuttavia, cosa succede quando *molti consumatori diversi* sono interessati allo stesso messaggio? Una coda di messaggi dedicata per ogni consumer non verrebbe ridimensionata bene e diventerebbe difficile da gestire.

Per risolvere questo scenario, si passa al terzo tipo di interazione di messaggio, *l'evento*. Un microservizio annuncia che si è verificata un'azione. Altri microservizi, se interessati, reagiscono all'azione o all'evento.

L'evento è un processo in due fasi. Per una determinata modifica dello stato, un microservizio pubblica un evento in un broker di messaggi, rendendolo disponibile per qualsiasi altro microservizio interessato. Il microservizio interessato riceve una notifica sottoscrivendo l'evento nel broker di messaggi. Utilizzare il modello [Publish/Subscribe](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) per implementare la [comunicazione basata su eventi](https://docs.microsoft.com/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications).

Nella figura 4-15 viene illustrato un microservizio del carrello acquisti che pubblica un evento con altri due microservizi che vi si iscrivono.

![Messaggistica basata su eventi](./media/event-driven-messaging.png)

**Figura 4-15**. Messaggistica basata su eventi

Si noti il componente *bus di eventi* che si trova al centro del canale di comunicazione. Si tratta di una classe personalizzata che incapsula il broker di messaggi e lo separa dall'applicazione sottostante. I microservizi di ordinazione e inventario gestiscono in modo indipendente l'evento senza alcuna conoscenza l'uno dell'altro, né il microservizio del carrello acquisti. Quando l'evento registrato viene pubblicato nel bus di eventi, agiscono su di esso.

Con gli eventi, passiamo dalla tecnologia di accodamento agli *argomenti.* Un [argomento](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) è simile a una coda, ma supporta un modello di messaggistica uno-a-molti. Un microservizio pubblica un messaggio. Più microservizi di sottoscrizione possono scegliere di ricevere e agire in base a tale messaggio. Nella figura 4-16 viene illustrata un'architettura di argomenti.

![Architettura dell'argomento](./media/topic-architecture.png)

**Figura 4-16**. Architettura dell'argomento

Nella figura precedente, gli editori inviano messaggi all'argomento. Alla fine, i sottoscrittori ricevono messaggi dalle sottoscrizioni. Al centro, l'argomento inoltra i messaggi alle sottoscrizioni in base a un set di *regole,* visualizzate in riquadri blu scuro. Le regole fungono da filtro che inoltrano messaggi specifici a una sottoscrizione. In questo caso, un evento "CreateOrder" verrà inviato alla sottoscrizione \#1 e alla sottoscrizione \#3, ma non alla sottoscrizione \#2. Un evento "OrderCompleted" viene \#inviato alla \#sottoscrizione 2 e alla sottoscrizione 3.

Il cloud di Azure supporta due diversi servizi di argomento: Argomenti del bus di servizio di Azure e EventGrid di Azure.The Azure cloud supports two different topic services: Azure Service Bus Topics and Azure EventGrid.

### <a name="azure-service-bus-topics"></a>Argomenti del bus di servizio di Azure

In cima allo stesso modello di messaggi negoziato robusto delle code del bus di servizio di Azure sono Argomenti del bus di servizio di [Azure.](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) Un argomento può ricevere messaggi da più server di pubblicazione indipendenti e inviare messaggi a un massimo di 2.000 sottoscrittori. Le sottoscrizioni possono essere aggiunte o rimosse dinamicamente in fase di esecuzione senza arrestare il sistema o ricreare l'argomento.

Molte funzionalità avanzate delle code del bus di servizio di Azure sono disponibili anche per gli argomenti, tra cui [Il rilevamento duplicati](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) e [il supporto delle transazioni](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions). Per impostazione predefinita, gli argomenti del bus di servizio vengono gestiti da un singolo broker di messaggi e archiviati in un singolo archivio messaggi. Tuttavia, [il partizionamento](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) del bus di servizio ridimensiona un argomento distesa su molti broker di messaggi e archivi messaggi.

[Il recapito dei messaggi pianificato contrassegna](https://docs.microsoft.com/azure/service-bus-messaging/message-sequencing) un messaggio con un orario specifico per l'elaborazione. Il messaggio non verrà visualizzato nell'argomento prima di tale ora. [Il rinvio](https://docs.microsoft.com/azure/service-bus-messaging/message-deferral) dei messaggi consente di rinviare il recupero di un messaggio a un momento successivo. Entrambi vengono comunemente utilizzati negli scenari di elaborazione del flusso di lavoro in cui le operazioni vengono elaborate in un ordine specifico. È possibile posticipare l'elaborazione dei messaggi ricevuti fino al completamento del lavoro precedente.

Gli argomenti del bus di servizio sono una tecnologia robusta e collaudata per abilitare la comunicazione di pubblicazione/sottoscrizione nei sistemi nativi del cloud.

### <a name="azure-event-grid"></a>Griglia di eventi di Azure

Mentre il bus di servizio di Azure è un broker di messaggistica testato in battaglia con un set completo di funzionalità aziendali, [Griglia di](https://docs.microsoft.com/azure/event-grid/overview) eventi di Azure è il nuovo capretto nel blocco.

A prima vista, Griglia di eventi può apparire come solo un altro sistema di messaggistica basato su argomenti. Tuttavia, è diverso in molti modi. Incentrato sui carichi di lavoro basati su eventi, consente l'elaborazione degli eventi in tempo reale, l'integrazione completa di Azure e una piattaforma aperta, il tutto sull'infrastruttura senza server. È progettato per applicazioni contemporanee native per il cloud e senza server

Come *backplane centralizzato*degli eventi, o pipe, Griglia di eventi reagisce agli eventi all'interno delle risorse di Azure e dai propri servizi.

Le notifiche degli eventi vengono pubblicate in un argomento Griglia di eventi che, a sua volta, indirizza ogni evento a una sottoscrizione. I sottoscrittori eseguono il mapping alle sottoscrizioni e utilizzano gli eventi. Come il bus di servizio, Griglia di eventi supporta un modello di *sottoscrittore filtrato* in cui una regola di set di sottoscrizioni per gli eventi che desidera ricevere. Griglia di eventi offre una velocità effettiva rapida con una garanzia di 10 milioni di eventi al secondo, consentendo il recapito quasi in tempo reale, molto più di quanto può generare il bus di servizio di Azure.Event Grid provides fast throughput with a guarantee of 10 million events per second enabling near real-time delivery - molto more than what Azure Service Bus can generate.

Un punto debole per Griglia di eventi è la sua profonda integrazione nell'infrastruttura dell'infrastruttura di Azure.A sweet spot for Event Grid is its deep integration into the fabric of Azure infrastructure. Una risorsa di Azure, ad esempio Cosmos DB, può pubblicare eventi predefiniti direttamente in altre risorse di Azure interessate, senza la necessità di codice personalizzato. Griglia di eventi può pubblicare eventi da una sottoscrizione di Azure, un gruppo di risorse o un servizio, offrendo agli sviluppatori un controllo granulare sul ciclo di vita delle risorse cloud. Tuttavia, Griglia di eventi non è limitata ad Azure.However, Event Grid isn't limited to Azure. Si tratta di una piattaforma aperta che può utilizzare eventi HTTP personalizzati pubblicati da applicazioni o servizi di terze parti e indirizzare gli eventi ai sottoscrittori esterni.

Quando si pubblica noe e si sottoscrive eventi nativi dalle risorse di Azure, non è necessaria alcuna codifica. Con la configurazione semplice, è possibile integrare gli eventi da una risorsa di Azure a un'altra sfruttando l'impianto idraulico incorporato per Argomenti e sottoscrizioni. La figura 4-17 mostra l'anatomia della griglia di eventi.

![Anatomia della griglia di eventi](./media/event-grid-anatomy.png)

**Figura 4-17**. Anatomia della griglia di eventi

Una differenza importante tra EventGrid e Service Bus è il modello di *scambio*dei messaggi sottostante.

Il bus di servizio implementa un *modello pull* di stile precedente in cui il sottoscrittore downstream esegue attivamente il polling della sottoscrizione dell'argomento per i nuovi messaggi. Al rialzo, questo approccio offre all'abbonato il pieno controllo del ritmo con cui elabora i messaggi. Controlla quando e quanti messaggi elaborare in un determinato momento. I messaggi non letti rimangono nella sottoscrizione fino all'elaborazione. Una carenza significativa è la latenza tra il momento in cui viene generato l'evento e l'operazione di polling che esegue il pull del messaggio al server di sottoscrizione per l'elaborazione. Inoltre, l'overhead del polling costante per l'evento successivo consuma risorse e denaro.

EventGrid, tuttavia, è diverso. Implementa un *modello push* in cui gli eventi vengono inviati a EventHandlers come ricevuti, con recapito quasi in tempo reale degli eventi. Riduce inoltre i costi in quanto il servizio viene attivato solo quando è necessario per utilizzare un evento, non continuamente come con il polling. Detto questo, un gestore eventi deve gestire il carico in ingresso e fornire meccanismi di limitazione per proteggersi da essere sopraffatto. Molti servizi di Azure che utilizzano questi eventi, ad esempio Funzioni di Azure e App per la logica, offrono funzionalità di scalabilità automatica automatica automatica per gestire carichi aumentati.  

Griglia di eventi è un servizio cloud completamente gestito senza server. Si ridimensiona dinamicamente in base al traffico e ti addebita solo l'utilizzo effettivo, non la capacità preacquistata. Le prime 100.000 operazioni al mese sono gratuite: le operazioni vengono definite come ingresso eventi (notifiche di eventi in ingresso), tentativi di recapito delle sottoscrizioni, chiamate di gestione e filtraggio in base all'oggetto. Con una disponibilità del 99,99%, EventGrid garantisce la distribuzione di un evento entro un periodo di 24 ore, con funzionalità di ripetizione dei tentativi incorporate per la consegna non riuscita. I messaggi non consegnati possono essere spostati in una coda "lettera morta" per la risoluzione.  A differenza del bus di servizio di Azure, Griglia di eventi è sintonizzata per ottenere prestazioni veloci e non supporta funzionalità come messaggistica ordinata, transazioni e sessioni.

### <a name="streaming-messages-in-the-azure-cloud"></a>Streaming di messaggi nel cloud di AzureStreaming messages in the Azure cloud

Il bus di servizio di Azure e Griglia di eventi forniscono un ottimo supporto per le applicazioni che espongono singoli eventi discreti come un nuovo documento è stato inserito in un cosmos DB. Ma cosa succede se il sistema nativo del cloud deve elaborare un *flusso di eventi correlati?* [I flussi di eventi](https://docs.microsoft.com/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems) sono più complessi. Sono in genere ordinati nel tempo, sono correlati e devono essere elaborati come gruppo.

[Hub eventi di Azure](https://azure.microsoft.com/services/event-hubs/) è una piattaforma di streaming dati e un servizio di inserimento eventi che raccoglie, trasforma e archivia eventi. È stata messa a chiave per acquisire i dati di streaming, ad esempio le notifiche di eventi continue generate da un contesto di telemetria. Il servizio è altamente scalabile e può archiviare ed [elaborare milioni di eventi al secondo.](https://docs.microsoft.com/azure/event-hubs/event-hubs-about) Nella figura 4-18, è spesso una porta iniziale per una pipeline di eventi, disaccoppiamento flusso di inserimento dall'utilizzo dell'evento.

![Hub eventi di Azure](./media/azure-event-hub.png)

**Figura 4-18**. Hub eventi di Azure

L'Hub eventi supporta una bassa latenza e una conservazione del tempo configurabile. A differenza delle code e degli argomenti, gli hub eventi mantengono i dati degli eventi dopo che sono stati letti da un consumer. Questa funzionalità consente ad altri servizi di analisi dei dati, sia interni che esterni, di riprodurre i dati per un'ulteriore analisi. Gli eventi archiviati nell'hub eventi vengono eliminati solo alla scadenza del periodo di conservazione, che è un giorno per impostazione predefinita, ma configurabile.

Event Hub supporta protocolli comuni di pubblicazione degli eventi, tra cui HTTPS e AMQP. Supporta anche Kafka 1.0. [Le applicazioni Kafka esistenti possono comunicare con Event Hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview) utilizzando il protocollo Kafka che offre un'alternativa alla gestione di cluster Kafka di grandi dimensioni. Molti sistemi cloud-nativi open-source adottano Kafka.

Gli hub eventi implementano lo streaming dei messaggi tramite un [modello consumer partizionato](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) in cui ogni consumer legge solo un subset specifico, o partizione, del flusso di messaggi. Questo modello consente notevole scalabilità orizzontale per l'elaborazione di eventi e fornisce altre funzionalità incentrate sui flussi che non sono disponibili in code e argomenti. Una partizione è una sequenza ordinata di eventi contenuta in un hub eventi. Quando arrivano gli eventi più recenti, vengono aggiunti alla fine di questa sequenza.Figura 4-19 Mostra il partizionamento in un hub eventi.

![Partizionamento dell'hub eventi](./media/event-hub-partitioning.png)

**Figura 4-19**. Partizionamento dell'hub eventi

Anziché leggere dalla stessa risorsa, ogni gruppo di consumer legge in un subset, o partizione, il flusso di messaggi.

Per le applicazioni native cloud che devono eseguire lo streaming di un numero elevato di eventi, l'hub eventi di Azure può essere una soluzione affidabile e conveniente.

>[!div class="step-by-step"]
>[Successivo](front-end-communication.md)
>[precedente](grpc.md)
