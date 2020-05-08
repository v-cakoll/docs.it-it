---
title: Comunicazione da servizio a servizio
description: Informazioni sul modo in cui i microservizi nativi del cloud back-end comunicano con altri microservizi back-end.
author: robvet
ms.date: 09/09/2019
ms.openlocfilehash: 556617a9e2df5a4d9ff9adb9d19e714ca94930ea
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895501"
---
# <a name="service-to-service-communication"></a>Comunicazione da servizio a servizio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Con il passaggio dal client front-end, ora si affronteranno i microservizi back-end che comunicano tra loro.

Quando si crea un'applicazione nativa del cloud, è opportuno essere sensibili al modo in cui i servizi back-end comunicano tra loro. Idealmente, migliore è la comunicazione tra i servizi. Tuttavia, l'elusione non è sempre possibile perché i servizi back-end si basano spesso su un altro per completare un'operazione.

Esistono diversi approcci ampiamente accettati per l'implementazione della comunicazione tra servizi. Il *tipo di interazione di comunicazione* determinerà spesso l'approccio migliore.

Considerare i tipi di interazione seguenti:

- *Query* : quando un microservizio chiamante richiede una risposta da un microservizio chiamato, ad esempio, "Hey, Give me the buyer Information for an data ID cliente".

- *Comando* : quando il microservizio chiamante necessita di un altro microservizio per eseguire un'azione ma non richiede una risposta, ad esempio, "Hey, è sufficiente spedire questo ordine".

- *Evento* : quando un microservizio, denominato server di pubblicazione, genera un evento che lo stato è stato modificato o si è verificata un'azione. Altri microservizi, detti Sottoscrittori, che sono interessati, possono rispondere all'evento in modo appropriato. Il server di pubblicazione e i Sottoscrittori non sono consapevoli.

I sistemi di microservizi utilizzano in genere una combinazione di questi tipi di interazione durante l'esecuzione di operazioni che richiedono l'interazione tra servizi. Esaminiamo in modo approfondito ciascuno di essi e come è possibile implementarli.

## <a name="queries"></a>Query

Molte volte, un microservizio potrebbe dover *eseguire una query* su un altro, richiedendo una risposta immediata per completare un'operazione. Un microservizio carrello acquisti potrebbe richiedere informazioni sul prodotto e un prezzo per aggiungere un elemento al carrello. Sono disponibili diversi approcci per l'implementazione delle operazioni di query.

### <a name="requestresponse-messaging"></a>Messaggistica di tipo richiesta/risposta

Una delle opzioni per l'implementazione di questo scenario è la chiamata del microservizio back-end per eseguire richieste HTTP dirette ai microservizi necessari per eseguire query, come illustrato nella figura 4-8.

![Comunicazione HTTP diretta](./media/direct-http-communication.png)

**Figura 4-8**. Comunicazione HTTP diretta

Sebbene le chiamate HTTP dirette tra microservizi siano relativamente semplici da implementare, è necessario prestare attenzione per ridurre al minimo questa procedura. Per iniziare, queste chiamate sono sempre *sincrone* e bloccano l'operazione fino a quando non viene restituito un risultato o si verifica il timeout della richiesta. Ciò che era una volta indipendenti, indipendenti, in grado di evolversi in modo indipendente e distribuito di frequente, ora vengono collegati tra loro. Quando l'accoppiamento tra i microservizi aumenta, i vantaggi dell'architettura diminuiscono.

L'esecuzione di una richiesta non frequente che esegue una singola chiamata HTTP diretta a un altro microservizio può essere accettabile per alcuni sistemi. Tuttavia, le chiamate di volumi elevati che richiamano chiamate HTTP dirette a più microservizi non sono consigliate. Possono aumentare la latenza e influire negativamente sulle prestazioni, sulla scalabilità e sulla disponibilità del sistema. Ancora peggio, una serie Prolong di comunicazione HTTP diretta può condurre a catene complete e complesse di chiamate a microservizi sincroni, illustrate nella figura 4-9:

![Concatenamento di query HTTP](./media/chaining-http-queries.png)

**Figura 4-9**. Concatenamento di query HTTP

È certamente possibile immaginare il rischio nella progettazione mostrata nell'immagine precedente. Cosa accade se il \#passaggio 3 ha esito negativo? O il \#passaggio 8 ha esito negativo? Come si esegue il ripristino? Cosa accade se \#il passaggio 6 è lento perché il servizio sottostante è occupato? Come continuare? Anche se tutto funziona correttamente, si può pensare alla latenza utilizzata da questa chiamata, ovvero la somma della latenza di ogni passaggio.

L'elevato livello di accoppiamento nell'immagine precedente suggerisce che i servizi non sono stati modellati in modo ottimale. Behoove al team di rivedere la loro progettazione.

### <a name="materialized-view-pattern"></a>Modello di vista materializzata

Una delle opzioni più diffuse per la rimozione dell'accoppiamento di microservizi è il [modello di vista materializzata](https://docs.microsoft.com/azure/architecture/patterns/materialized-view). Con questo modello, un microservizio archivia la propria copia locale e denormalizzata dei dati di proprietà di altri servizi. Invece del microservizio carrello acquisti che esegue query sul catalogo dei prodotti e sui microservizi tariffari, gestisce la propria copia locale di tali dati. Questo modello Elimina l'accoppiamento non necessario e migliora l'affidabilità e il tempo di risposta. L'intera operazione viene eseguita all'interno di un singolo processo. Questo modello e altri problemi relativi ai dati vengono esaminati nel capitolo 5.

### <a name="service-aggregator-pattern"></a>Modello di Service aggregator

Un'altra opzione per eliminare l'accoppiamento da microservizio a microservizio è un [microservizio aggregatore](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/), illustrato in viola nella figura 4-10.

![Servizio aggregator](./media/aggregator-service.png)

**Figura 4-10**. Microservizio aggregator

Il modello isola un'operazione che effettua chiamate a più microservizi back-end, centralizzando la logica in un microservizio specializzato.  Il microservizio Purple checkout aggregator nella figura precedente Orchestra il flusso di lavoro per l'operazione di estrazione. Include le chiamate a diversi microservizi back-end in ordine sequenziale. I dati del flusso di lavoro vengono aggregati e restituiti al chiamante. Sebbene implementi ancora le chiamate HTTP dirette, il microservizio aggregator riduce le dipendenze dirette tra i microservizi back-end.

### <a name="requestreply-pattern"></a>Modello di richiesta/risposta

Un altro approccio per separare i messaggi HTTP sincroni è un [modello Request/Reply](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html), che usa la comunicazione di Accodamento. La comunicazione con una coda è sempre un canale unidirezionale con un producer che invia il messaggio e il consumer che lo riceve. Con questo modello, vengono implementate sia una coda di richieste che una coda di risposta, illustrate nella figura 4-11.

![Modello Request/Reply](./media/request-reply-pattern.png)

**Figura 4-11**. Modello Request/Reply

In questo caso, il producer di messaggi crea un messaggio basato su query che contiene un ID di correlazione univoco e lo inserisce in una coda di richieste. Il servizio consumer rimuove dalla coda i messaggi, li elabora e inserisce la risposta nella coda di risposta con lo stesso ID di correlazione. Il servizio Producer rimuove il messaggio dalla coda, ne corrisponde l'ID di correlazione e continua l'elaborazione. Le code sono descritte in dettaglio nella sezione successiva.

## <a name="commands"></a>Comandi:

Un altro tipo di interazione di comunicazione è un *comando*. Un microservizio può richiedere un altro microservizio per eseguire un'azione. Il microservizio degli ordini potrebbe richiedere il microservizio shipping per creare una spedizione per un ordine approvato. Nella figura 4-12, un microservizio, denominato Producer, invia un messaggio a un altro microservizio, il consumer, che lo comanda per eseguire un'operazione.

![Interazione del comando con una coda](./media/command-interaction-with-queue.png)

**Figura 4-12**. Interazione del comando con una coda

In genere, il producer non richiede una risposta e può *attivare e dimenticare* il messaggio. Se è necessaria una risposta, il consumer invia un messaggio separato al producer su un altro canale. Un messaggio di comando viene inviato meglio in modo asincrono con una coda di messaggi. supportato da un broker di messaggi Lightweight. Nel diagramma precedente si noti come una coda separa e separa entrambi i servizi.

Una coda di messaggi è un costrutto intermediario attraverso il quale un producer e un consumer passano un messaggio. Le code implementano un modello di messaggistica Point-to-Point asincrono. Il produttore sa dove deve essere inviato un comando e viene indirizzato in modo appropriato. La coda garantisce che un messaggio venga elaborato esattamente da una delle istanze del consumer che eseguono la lettura dal canale. In questo scenario, il servizio Producer o consumer può essere scalato in orizzontale senza influire sull'altro. Inoltre, le tecnologie possono essere diversi su ogni lato, ovvero potrebbe essere presente un microservizio Java che chiama un microservizio [Golang](https://golang.org) .

Nel capitolo 1, abbiamo parlato dei *servizi di supporto*. I servizi di supporto sono risorse ausiliarie su cui dipendono i sistemi nativi del cloud. Le code di messaggi sono servizi di supporto. Il cloud di Azure supporta due tipi di code di messaggi che possono essere utilizzati dai sistemi nativi del cloud per implementare la messaggistica dei comandi: le code di archiviazione di Azure e le code del bus di servizio di Azure.

### <a name="azure-storage-queues"></a>Code di Archiviazione di Azure

Le code di archiviazione di Azure offrono una semplice infrastruttura di Accodamento, veloce, conveniente e supportata dagli account di archiviazione di Azure.

Le [code di archiviazione di Azure](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction) includono un meccanismo di accodamento basato su REST con messaggistica affidabile e persistente. Forniscono un set di funzionalità minime, ma sono convenienti e archiviano milioni di messaggi. La capacità varia fino a 500 TB. Un singolo messaggio può avere dimensioni massime di 64 KB.

È possibile accedere ai messaggi da qualsiasi parte del mondo mediante chiamate autenticate tramite HTTP o HTTPS. Le code di archiviazione possono essere scalate in un numero elevato di client simultanei per gestire i picchi di traffico.

Detto ciò, esistono alcune limitazioni al servizio:

- L'ordine del messaggio non è garantito.

- Un messaggio può essere mantenuto solo per sette giorni prima di essere rimosso automaticamente.

- Il supporto per la gestione dello stato, il rilevamento di duplicati o le transazioni non è disponibile.

La figura 4-13 Mostra la gerarchia di una coda di archiviazione di Azure.

![Gerarchia della coda di archiviazione](./media/storage-queue-hierarchy.png)

**Figura 4-13**. Gerarchia della coda di archiviazione

Nella figura precedente si noti come le code di archiviazione archiviano i messaggi nell'account di archiviazione di Azure sottostante.

Per gli sviluppatori, Microsoft fornisce diverse librerie lato client e lato server per l'elaborazione delle code di archiviazione. Sono supportate la maggior parte delle piattaforme principali, tra cui .NET, Java, JavaScript, Ruby, Python e go. Gli sviluppatori non devono mai comunicare direttamente con queste librerie. In questo modo il codice del microservizio viene abbinato al Servizio di accodamento di archiviazione di Azure. È consigliabile isolare i dettagli di implementazione dell'API. Introduce un livello di intermediazione, o un'API intermedia, che espone operazioni generiche e incapsula la libreria concreta. Questo accoppiamento libero consente di scambiare un servizio di Accodamento per un altro senza dover apportare modifiche al codice del servizio principale.

Le code di archiviazione di Azure rappresentano un'opzione economica per implementare la messaggistica dei comandi nelle applicazioni native del cloud. In particolare, se le dimensioni della coda superano 80 GB o un set di funzionalità semplice è accettabile. Paghi solo per l'archiviazione dei messaggi; non sono previsti addebiti orari fissi.

### <a name="azure-service-bus-queues"></a>Code del bus di servizio di Azure

Per i requisiti di messaggistica più complessi, prendere in considerazione le code del bus di servizio di Azure.

Il [bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) supporta un modello di *messaggistica negoziata*che si trova in cima a un'infrastruttura di messaggi affidabile. I messaggi vengono archiviati in modo affidabile in un broker, ovvero la coda, fino alla ricezione da parte del consumer. La coda garantisce il recapito dei messaggi FIFO (First-in/First-out), rispettando l'ordine in cui i messaggi sono stati aggiunti alla coda.

Le dimensioni di un messaggio possono essere molto più grandi, fino a 256 KB. I messaggi vengono mantenuti nella coda per un periodo di tempo illimitato. Il bus di servizio supporta non solo le chiamate basate su HTTP, ma offre anche il supporto completo per il [protocollo AMQP](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-amqp-overview). AMQP è uno standard aperto tra più fornitori che supporta un protocollo binario e livelli più elevati di affidabilità.

Il bus di servizio offre un set completo di funzionalità, tra cui il [supporto delle transazioni](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions) e una [funzionalità di rilevamento dei duplicati](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection). La coda garantisce il recapito "al massimo" per messaggio. Elimina automaticamente un messaggio che è già stato inviato. Se un Producer è in dubbio, può inviare nuovamente lo stesso messaggio e il bus di servizio garantisce che venga elaborata una sola copia. Il rilevamento dei duplicati evita di dover creare un impianto aggiuntivo di infrastruttura.

Altre due funzionalità aziendali sono il partizionamento e le sessioni. Una coda del bus di servizio convenzionale viene gestita da un singolo broker di messaggi e archiviato in un singolo archivio di messaggi. Tuttavia, il [partizionamento del bus di servizio](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) suddivide la coda tra più broker di messaggi e archivi di messaggi. La velocità effettiva complessiva non è più limitata dalle prestazioni di un singolo broker messaggi o archivio di messaggistica. Un'interruzione temporanea di un archivio di messaggistica non esegue il rendering di una coda partizionata non disponibile.

Le [sessioni del bus di servizio](https://codingcanvas.com/azure-service-bus-sessions/) forniscono un modo per raggruppare i messaggi correlati. Si immagini uno scenario del flusso di lavoro in cui i messaggi devono essere elaborati insieme e l'operazione è stata completata alla fine. Per sfruttare i vantaggi, le sessioni devono essere abilitate in modo esplicito per la coda e ogni messaggio correlato deve contenere lo stesso ID di sessione.

Tuttavia, esistono alcuni aspetti importanti: le dimensioni delle code del bus di servizio sono limitate a 80 GB, il che è molto più piccolo rispetto a quello disponibile dalle code di archiviazione. Inoltre, le code del bus di servizio incorrono un costo di base e un addebito per ogni operazione.

La figura 4-14 illustra l'architettura di alto livello di una coda del bus di servizio.

![Coda del bus di servizio](./media/service-bus-queue.png)

**Figura 4-14**. Coda del bus di servizio

Nella figura precedente si noti la relazione Point-to-Point. Due istanze dello stesso provider accodano i messaggi in una singola coda del bus di servizio. Ogni messaggio viene utilizzato da una sola delle tre istanze di consumer a destra. Viene quindi illustrato come implementare la messaggistica in cui i diversi consumer possono essere tutti interessati allo stesso messaggio.

## <a name="events"></a>Eventi

Accodamento messaggi è un modo efficace per implementare la comunicazione in cui un producer può inviare un messaggio in modo asincrono a un consumer. Tuttavia, cosa accade quando *molti utenti diversi* sono interessati allo stesso messaggio? Una coda di messaggi dedicata per ogni consumer non avrebbe scalato bene e sarebbe diventato difficile da gestire.

Per risolvere questo scenario, si passa al terzo tipo di interazione dei messaggi, ovvero l' *evento*. Un microservizio annuncia che si è verificata un'azione. Altri microservizi, se interessati, reagiscono all'azione o all'evento.

L'evento è un processo in due passaggi. Per una modifica dello stato, un microservizio pubblica un evento in un broker di messaggi, rendendolo disponibile per qualsiasi altro microservizio interessato. Il microservizio interessato viene informato sottoscrivendo l'evento nel broker di messaggi. Usare il modello di [pubblicazione/sottoscrizione](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) per implementare la [comunicazione basata su eventi](https://docs.microsoft.com/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications).

La figura 4-15 Mostra un microservizio carrello acquisti che pubblica un evento con altri due microservizi che li sottoscrivono.

![Messaggistica basata sugli eventi](./media/event-driven-messaging.png)

**Figura 4-15**. Messaggistica basata sugli eventi

Si noti il componente *bus di eventi* che si trova al centro del canale di comunicazione. Si tratta di una classe personalizzata che incapsula il broker di messaggi e lo separa dall'applicazione sottostante. I microservizi di ordinamento e inventario operano in modo indipendente sull'evento senza alcuna conoscenza dell'altro, né nel microservizio acquisti. Quando l'evento registrato viene pubblicato nel bus di eventi, agisce su di esso.

Con la gestione degli eventi, la tecnologia di Accodamento viene spostata *negli argomenti*. Un [argomento](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) è simile a una coda, ma supporta un modello di messaggistica uno-a-molti. Un microservizio pubblica un messaggio. Più microservizi di sottoscrizione possono scegliere di ricevere e agire sul messaggio. La figura 4-16 illustra l'architettura di un argomento.

![Architettura degli argomenti](./media/topic-architecture.png)

**Figura 4-16**. Architettura degli argomenti

Nella figura precedente, i Publisher inviano messaggi all'argomento. Al termine, i sottoscrittori ricevono messaggi dalle sottoscrizioni. Al centro, l'argomento invia messaggi alle sottoscrizioni in base a un set di *regole*, visualizzate in caselle blu scuro. Le regole fungono da filtro che trasmette messaggi specifici a una sottoscrizione. Qui viene inviato un evento "CreateOrder" alla sottoscrizione \#1 e alla sottoscrizione \#3, ma non alla sottoscrizione \#2. Un evento "OrderCompleted" verrebbe inviato alla sottoscrizione \#2 e alla sottoscrizione \#3.

Il cloud di Azure supporta due servizi di argomento diversi: gli argomenti del bus di servizio di Azure e Azure EventGrid.

### <a name="azure-service-bus-topics"></a>Argomenti del bus di servizio di Azure

Gli [argomenti del bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions)di servizio di Azure si trovano sopra lo stesso modello di messaggio negoziato affidabile delle code del bus di servizio di Azure. Un argomento può ricevere messaggi da più autori indipendenti e inviare messaggi a un massimo di 2.000 sottoscrittori. Le sottoscrizioni possono essere aggiunte o rimosse dinamicamente in fase di esecuzione senza arrestare il sistema o ricreare l'argomento.

Per gli argomenti sono disponibili anche molte funzionalità avanzate delle code del bus di servizio di Azure, tra cui il [rilevamento dei duplicati](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) e il [supporto delle transazioni](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions). Per impostazione predefinita, gli argomenti del bus di servizio vengono gestiti da un singolo broker di messaggi e archiviati in un singolo archivio di messaggi. Il [partizionamento del bus di servizio](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) , tuttavia, consente di ridimensionare un argomento distribuendo questo argomento tra molti broker di messaggi e archivi di messaggi.

Il [recapito dei messaggi pianificato](https://docs.microsoft.com/azure/service-bus-messaging/message-sequencing) contrassegna un messaggio con una data e un'ora specifiche per l'elaborazione. Il messaggio non verrà visualizzato nell'argomento prima di tale ora. Il [rinvio dei messaggi](https://docs.microsoft.com/azure/service-bus-messaging/message-deferral) consente di rinviare un recupero di un messaggio a un momento successivo. Entrambi sono comunemente usati negli scenari di elaborazione del flusso di lavoro in cui le operazioni vengono elaborate in un ordine particolare. È possibile posticipare l'elaborazione dei messaggi ricevuti fino al completamento del lavoro precedente.

Gli argomenti del bus di servizio sono una tecnologia solida e collaudata per l'abilitazione della comunicazione di pubblicazione/sottoscrizione nei sistemi nativi del cloud.

### <a name="azure-event-grid"></a>Griglia di eventi di Azure

Mentre il bus di servizio di Azure è un broker di messaggistica collaudato con un set completo di funzionalità aziendali, [griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview) è il nuovo bambino nel blocco.

A prima vista, griglia di eventi può essere simile a un altro sistema di messaggistica basato su argomenti. Tuttavia, è diverso in molti modi. Con particolare attenzione ai carichi di lavoro basati su eventi, consente l'elaborazione di eventi in tempo reale, l'integrazione con Azure approfondita e una piattaforma open-all su un'infrastruttura senza server. È progettato per applicazioni moderne native del cloud e senza server

Come backplane centralizzato degli *eventi*, o pipe, griglia di eventi reagisce agli eventi all'interno delle risorse di Azure e dai propri servizi.

Le notifiche degli eventi vengono pubblicate in un argomento di griglia di eventi, che, a sua volta, instrada ogni evento a una sottoscrizione. I sottoscrittori vengono mappati alle sottoscrizioni e utilizzano gli eventi. Analogamente al bus di servizio, griglia di eventi supporta un *modello di Sottoscrittore filtrato* in cui una sottoscrizione imposta la regola per gli eventi che si desidera ricevere. Griglia di eventi offre una velocità effettiva rapida con una garanzia di 10 milioni eventi al secondo che consentono il recapito quasi in tempo reale, molto più di quanto può generare il bus di servizio di Azure.

Una soluzione ideale per griglia di eventi è l'integrazione completa nell'infrastruttura di Azure. Una risorsa di Azure, ad esempio Cosmos DB, può pubblicare eventi predefiniti direttamente in altre risorse di Azure interessate, senza la necessità di codice personalizzato. Griglia di eventi può pubblicare eventi da una sottoscrizione, un gruppo di risorse o un servizio di Azure, offrendo agli sviluppatori un controllo granulare del ciclo di vita delle risorse cloud. Tuttavia, griglia di eventi non è limitata ad Azure. Si tratta di una piattaforma aperta che può utilizzare eventi HTTP personalizzati pubblicati da applicazioni o servizi di terze parti e indirizzare gli eventi a sottoscrittori esterni.

Quando si pubblicano e sottoscrivono eventi nativi dalle risorse di Azure, non è necessaria alcuna codifica. Con la semplice configurazione è possibile integrare gli eventi da una risorsa di Azure a un'altra sfruttando il plumbing integrato per gli argomenti e le sottoscrizioni. La figura 4-17 illustra l'anatomia di griglia di eventi.

![Anatomia griglia di eventi](./media/event-grid-anatomy.png)

**Figura 4-17**. Anatomia griglia di eventi

Una differenza principale tra EventGrid e il bus di servizio è il *modello di scambio dei messaggi*sottostante.

Il bus di servizio implementa un *modello pull* di tipo obsoleto in cui il Sottoscrittore downstream esegue attivamente il polling della sottoscrizione dell'argomento per i nuovi messaggi. Questo approccio offre al Sottoscrittore il controllo completo della velocità di elaborazione dei messaggi. Consente di controllare il momento e il numero di messaggi da elaborare in un determinato momento. I messaggi non letti rimangono nella sottoscrizione fino a quando non vengono elaborati. Un difetto significativo è la latenza tra il momento in cui viene generato l'evento e l'operazione di polling che effettua il pull del messaggio nel Sottoscrittore per l'elaborazione. Inoltre, l'overhead del polling costante per l'evento successivo utilizza risorse e denaro.

EventGrid, tuttavia, è diverso. Implementa un *modello push* in cui gli eventi vengono inviati agli EventHandler come ricevuti, offrendo il recapito di eventi quasi in tempo reale. Riduce inoltre i costi quando il servizio viene attivato solo quando è necessario per l'utilizzo di un evento, non sempre come per il polling. Detto questo, un gestore eventi deve gestire il carico in ingresso e fornire meccanismi di limitazione delle richieste per proteggersi dal sovraccarico. Molti servizi di Azure che usano questi eventi, ad esempio funzioni di Azure e app per la logica, offrono funzionalità di scalabilità automatica automatica per gestire carichi maggiori.  

Griglia di eventi è un servizio cloud senza server completamente gestito. Viene scalato dinamicamente in base al traffico e viene addebitato solo per l'utilizzo effettivo, non per la capacità preacquistata. Le prime 100.000 operazioni al mese sono gratuite, ovvero le operazioni definite come ingresso di eventi (notifiche degli eventi in ingresso), i tentativi di recapito delle sottoscrizioni, le chiamate di gestione e il filtraggio in base all'oggetto. Con la disponibilità del 99,99%, EventGrid garantisce la consegna di un evento entro un periodo di 24 ore, con funzionalità di ripetizione dei tentativi predefinite per il recapito non riuscito. I messaggi non recapitati possono essere spostati in una coda di "Dead-Letter" per la risoluzione.  A differenza del bus di servizio di Azure, griglia di eventi è ottimizzata per prestazioni rapide e non supporta funzionalità quali messaggistica ordinata, transazioni e sessioni.

### <a name="streaming-messages-in-the-azure-cloud"></a>Streaming di messaggi nel cloud di Azure

Il bus di servizio e griglia di eventi di Azure offrono un supporto eccezionale per le applicazioni che espongono singoli eventi discreti, ad esempio un nuovo documento inserito in un Cosmos DB. Tuttavia, cosa accade se il sistema nativo del cloud deve elaborare un *flusso di eventi correlati*? I [flussi di eventi](https://docs.microsoft.com/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems) sono più complessi. In genere sono ordinati in termini di tempo, intercorrelati e devono essere elaborati come un gruppo.

[Hub eventi di Azure](https://azure.microsoft.com/services/event-hubs/) è una piattaforma di streaming di dati e un servizio di inserimento di eventi che raccoglie, trasforma e archivia gli eventi. È ottimizzato per acquisire i dati di streaming, ad esempio le notifiche di eventi continui emesse da un contesto di telemetria. Il servizio è altamente scalabile e può archiviare ed [elaborare milioni di eventi al secondo](https://docs.microsoft.com/azure/event-hubs/event-hubs-about). Come illustrato nella figura 4-18, spesso si tratta di una porta anteriore per una pipeline di eventi, disaccoppiando il flusso di inserimento dal consumo di eventi.

![Hub eventi di Azure](./media/azure-event-hub.png)

**Figura 4-18**. Hub eventi di Azure

Hub eventi supporta la bassa latenza e la conservazione dell'ora configurabile. A differenza delle code e degli argomenti, Hub eventi mantiene i dati degli eventi dopo che è stato letto da un consumer. Questa funzionalità consente ad altri servizi di analisi dei dati, sia interni che esterni, di riprodurre i dati per un'ulteriore analisi. Gli eventi archiviati nell'hub eventi vengono eliminati solo dopo la scadenza del periodo di memorizzazione, che è un giorno per impostazione predefinita, ma configurabile.

Hub eventi supporta i protocolli comuni di pubblicazione degli eventi, inclusi HTTPS e AMQP. Supporta anche Kafka 1,0. Le [applicazioni Kafka esistenti possono comunicare con l'hub eventi](https://docs.microsoft.com/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview) usando il protocollo Kafka offrendo un'alternativa alla gestione di cluster Kafka di grandi dimensioni. Molti sistemi open source Cloud nativi adottano Kafka.

Hub eventi implementa lo streaming di messaggi tramite un [modello consumer partizionato](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) in cui ogni consumer legge solo uno specifico subset, o partizione, del flusso di messaggi. Questo modello consente notevole scalabilità orizzontale per l'elaborazione di eventi e fornisce altre funzionalità incentrate sui flussi che non sono disponibili in code e argomenti. Una partizione è una sequenza ordinata di eventi contenuta in un hub eventi. Man mano che arrivano gli eventi più recenti, vengono aggiunti alla fine di questa sequenza.La figura 4-19 illustra il partizionamento in un hub eventi.

![Partizionamento dell'hub eventi](./media/event-hub-partitioning.png)

**Figura 4-19**. Partizionamento dell'hub eventi

Anziché leggere dalla stessa risorsa, ogni gruppo di consumer viene letto in un subset, o partizione, del flusso di messaggi.

Per le applicazioni native del cloud che devono trasmettere un numero elevato di eventi, Hub eventi di Azure può essere una soluzione affidabile e conveniente.

>[!div class="step-by-step"]
>[Precedente](front-end-communication.md)
>[successivo](grpc.md)
