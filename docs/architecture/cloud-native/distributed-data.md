---
title: Dati distribuiti
description: Confronto tra l'archiviazione dei dati in applicazioni monolitiche e native del cloud.
author: robvet
ms.date: 04/24/2020
ms.openlocfilehash: 8a9f1478f1a46b2367df9372d4adaa3b4c711782
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82204696"
---
# <a name="distributed-data"></a>Dati distribuiti

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Come è stato illustrato in questo libro, un approccio nativo del cloud cambia la modalità di progettazione, distribuzione e gestione delle applicazioni. Cambia anche la modalità di gestione e archiviazione dei dati.

La figura 5-1 contrasta le differenze.

![Archiviazione dei dati in applicazioni native del cloud](./media/distributed-data.png)

**Figura 5-1**. Gestione dei dati in applicazioni native del cloud

Gli sviluppatori esperti riconoscono facilmente l'architettura sul lato sinistro della figura 5-1. In questa *applicazione monolitica*, i componenti del servizio business si collocano insieme in un livello di servizi condivisi, condividendo i dati da un singolo database relazionale.

In molti casi, un database singolo mantiene la gestione dei dati semplice. L'esecuzione di query sui dati in più tabelle è semplice. Modifiche apportate all'aggiornamento dei dati o a tutti i rollback. [Le transazioni ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) garantiscono coerenza assoluta e immediata.

Progettazione per il cloud nativo, viene adottato un approccio diverso. Sul lato destro della figura 5-1, si noti il modo in cui la funzionalità di business si separa in microservizi piccoli e indipendenti. Ogni microservizio incapsula una funzionalità aziendale specifica e i relativi dati. Il database monolitico viene decomposto in un modello di dati distribuito con molti database più piccoli, ognuno dei quali è allineato a un microservizio. Quando il fumo si cancella, emergiamo con una progettazione che espone un *database per ogni microservizio*.

## <a name="database-per-microservice-why"></a>Database per microservizi, perché?

Questo database per microservizio offre numerosi vantaggi, specialmente per i sistemi che devono evolversi rapidamente e supportano una scalabilità massiccia. Con questo modello...

- I dati del dominio vengono incapsulati all'interno del servizio
- Lo schema dati può evolvere senza influito direttamente sugli altri servizi
- Ogni archivio dati può essere ridimensionato in modo indipendente
- Un errore dell'archivio dati in un servizio non influirà direttamente sugli altri servizi

La separazione dei dati consente anche a ogni microservizio di implementare il tipo di archivio dati ottimizzato in modo ottimale per il carico di lavoro, le esigenze di archiviazione e i modelli di lettura/scrittura. Le scelte includono archivi dati relazionali, documenti, chiave-valore e anche basati su Graph.

La figura 5-2 presenta il principio della persistenza poliglotta in un sistema nativo del cloud.

![Persistenza dei dati poliglotta](./media/polyglot-data-persistence.png)

**Figura 5-2**. Persistenza dei dati poliglotta

Si noti che nella figura precedente il modo in cui ogni microservizio supporta un tipo diverso di archivio dati.

- Il microservizio Catalogo prodotti usa un database relazionale per gestire la struttura relazionale avanzata dei dati sottostanti.
- Il microservizio carrello acquisti utilizza una cache distribuita che supporta il proprio archivio dati semplice e chiave-valore.
- Il microservizio degli ordini usa un database di documenti NoSql per le operazioni di scrittura insieme a un archivio chiave/valore altamente denormalizzato per gestire volumi elevati di operazioni di lettura.
  
Sebbene i database relazionali rimangano rilevanti per i microservizi con dati complessi, i database NoSQL hanno acquisito una notevole popolarità. Forniscono scalabilità e disponibilità elevate. La loro natura senza schema consente agli sviluppatori di uscire da un'architettura di classi di dati tipizzate e ORM che rendono la modifica costosa e dispendiosa in termini di tempo. I database NoSQL vengono coperti più avanti in questo capitolo.

 Sebbene l'incapsulamento dei dati in microservizi distinti possa aumentare l'agilità, le prestazioni e la scalabilità, presenta anche molti problemi. Nella sezione successiva si esamineranno tali problemi insieme ai modelli e alle procedure per risolverli.  

## <a name="cross-service-queries"></a>Query tra servizi

Anche se i microservizi sono indipendenti e si concentrano su funzionalità funzionali specifiche, ad esempio inventario, spedizione o ordinamento, spesso richiedono l'integrazione con altri microservizi. Spesso l'integrazione prevede un microservizio che *esegue query* su un altro per i dati. La figura 5-3 illustra lo scenario.

![Esecuzione di query tra microservizi](./media/cross-service-query.png)

**Figura 5-3**. Esecuzione di query tra microservizi

Nella figura precedente viene visualizzato un microservizio carrello acquisti che aggiunge un elemento al carrello acquisti di un utente. Mentre l'archivio dati per questo microservizio contiene i dati relativi a basket e voce, non mantiene i dati relativi ai prodotti o ai prezzi. Gli elementi di dati sono invece di proprietà dei microservizi Catalog e pricing. Questa operazione presenta un problema. In che modo il microservizio carrello acquisti aggiunge un prodotto al carrello acquisti dell'utente quando non contiene prodotti o dati sui prezzi nel database?

Una delle opzioni descritte nel capitolo 4 è una [chiamata http diretta](service-to-service-communication.md#queries) dal carrello acquisti ai microservizi del catalogo e dei prezzi. Tuttavia, nel capitolo 4, abbiamo detto che l'HTTP sincrono chiama *due* microservizi insieme, riducendo la loro autonomia e diminuendo i vantaggi architettonici.

È anche possibile implementare un modello Request/Reply con code separate in ingresso e in uscita per ogni servizio. Tuttavia, questo modello è complesso e richiede un plumbing per correlare i messaggi di richiesta e risposta.
Mentre separa le chiamate del microservizio back-end, il servizio chiamante deve comunque attendere in modo sincrono il completamento della chiamata. Congestione della rete, errori temporanei o un microservizio di overload e possono comportare operazioni a esecuzione prolungata e anche non riuscite.

Al contrario, un modello ampiamente accettato per la rimozione delle dipendenze tra i servizi è il [modello di vista materializzata](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), illustrato nella figura 5-4.

![Modello di vista materializzata](./media/materialized-view-pattern.png)

**Figura 5-4**. Modello di vista materializzata

Con questo modello, si inserisce una tabella di dati locale (nota come *modello di lettura*) nel servizio carrello acquisti. Questa tabella contiene una copia denormalizzata dei dati necessari per i microservizi Product e pricing. La copia dei dati direttamente nel microservizio carrello acquisti Elimina la necessità di costosi chiamate tra servizi. Con i dati locali per il servizio, è possibile migliorare il tempo di risposta e l'affidabilità del servizio. Inoltre, la presenza di una propria copia dei dati rende più resiliente il servizio carrello acquisti. Se il servizio catalogo non è più disponibile, non avrà alcun effetto direttamente sul servizio carrello acquisti. Il carrello acquisti può continuare a funzionare con i dati provenienti dal proprio negozio.

Il problema con questo approccio è che ora si hanno dati duplicati nel sistema. Tuttavia, la duplicazione *strategica* dei dati nei sistemi nativi del cloud è una prassi stabilita e non è considerata un anti-modello o una procedura non valida. Tenere presente che un *solo servizio* può essere proprietario di un set di dati e avere un'autorità. È necessario sincronizzare i modelli di lettura quando il sistema di registrazione viene aggiornato. La sincronizzazione viene in genere implementata tramite messaggistica asincrona con un [modello di pubblicazione/sottoscrizione](service-to-service-communication.md#events), come illustrato nella figura 5,4.

## <a name="distributed-transactions"></a>Transazioni distribuite

Quando si eseguono query sui dati tra microservizi è difficile, l'implementazione di una transazione tra più microservizi è ancora più complessa. La sfida inerente alla gestione della coerenza dei dati tra origini dati indipendenti in microservizi diversi non può essere sottostata. La mancanza di transazioni distribuite nelle applicazioni native del cloud significa che è necessario gestire le transazioni distribuite a livello di programmazione. Si passa da un mondo di *coerenza immediata* a quello di *coerenza finale*.

La figura 5-5 illustra il problema.

![Transazione nel modello saga](./media/saga-transaction-operation.png)

**Figura 5-5**. Implementazione di una transazione tra microservizi

Nella figura precedente cinque microservizi indipendenti partecipano a una transazione distribuita che crea un ordine. Ogni microservizio mantiene il proprio archivio dati e implementa una transazione locale per il relativo archivio. Per creare l'ordine, la transazione locale per *ogni* singolo microservizio deve avere esito *positivo oppure è* necessario interrompere ed eseguire il rollback dell'operazione. Sebbene il supporto transazionale predefinito sia disponibile all'interno di ogni microservizio, non esiste alcun supporto per una transazione distribuita che si estenderebbe su tutti i cinque servizi per mantenere coerenti i dati.

È invece necessario costruire questa transazione distribuita *a livello di codice*.

Uno dei modelli più diffusi per l'aggiunta del supporto transazionale distribuito è il modello saga. Viene implementata raggruppando le transazioni locali a livello di codice e richiamando in modo sequenziale ciascuna di esse. Se alcune transazioni locali hanno esito negativo, la saga interrompe l'operazione e richiama un set di [transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction). Le transazioni di compensazione annullano le modifiche apportate dalle transazioni locali precedenti e ripristinano la coerenza dei dati. La figura 5-6 Mostra una transazione non riuscita con il modello saga.

![Eseguire il rollback nel modello saga](./media/saga-rollback-operation.png)

**Figura 5-6**. Rollback di una transazione

Nella figura precedente, l'operazione di *aggiornamento dell'inventario* non è riuscita nel microservizio di inventario. La saga richiama un set di transazioni di compensazione (in rosso) per modificare i conteggi dell'inventario, annullare il pagamento e l'ordine e restituire i dati per ogni microservizio a uno stato coerente.

I modelli di Saga vengono in genere sottoposti a coreografia come una serie di eventi correlati o orchestrati come un set di comandi correlati. Nel capitolo 4 è stato illustrato il modello Service aggregator che costituisce la base per un'implementazione di Saga orchestrata. Sono stati anche discussi gli eventi con il bus di servizio di Azure e gli argomenti di griglia di eventi di Azure che sarebbero una base per un'implementazione della saga con coreografia.

## <a name="high-volume-data"></a>Dati con volumi elevati

Le grandi applicazioni native del cloud supportano spesso requisiti di volumi elevati di dati. In questi scenari, le tecniche tradizionali di archiviazione dei dati possono causare colli di bottiglia. Per i sistemi complessi distribuiti su larga scala, sia separazione di responsabilità per query e comandi (CQRS) che l'origine eventi possono migliorare le prestazioni dell'applicazione.  

### <a name="cqrs"></a>CQRS

[CQRS](https://docs.microsoft.com/azure/architecture/patterns/cqrs)è uno schema architettonico che consente di ottimizzare le prestazioni, la scalabilità e la sicurezza. Il criterio separa le operazioni di lettura dei dati dalle operazioni che scrivono i dati.

Per gli scenari normali, lo stesso modello di entità e l'oggetto archivio dati vengono utilizzati per le operazioni *di lettura e* scrittura.

Uno scenario di dati con volumi elevati può tuttavia trarre vantaggio da modelli e tabelle di dati separati per operazioni di lettura e scrittura. Per migliorare le prestazioni, l'operazione di lettura può eseguire una query su una rappresentazione altamente denormalizzata dei dati per evitare costosi join di tabella ripetitivi e blocchi di tabella. L'operazione di *scrittura* , nota come *comando*, verrebbe aggiornata rispetto a una rappresentazione completamente normalizzata dei dati che garantirebbe la coerenza. È quindi necessario implementare un meccanismo per mantenendo sincronizzate entrambe le rappresentazioni. In genere, ogni volta che la tabella di scrittura viene modificata, pubblica un evento che replica la modifica nella tabella Read.

La figura 5-7 illustra un'implementazione del modello CQRS.

![separazione di responsabilità per query e comandi](./media/cqrs-implementation.png)

**Figura 5-7**. Implementazione di CQRS

Nella figura precedente sono implementati i modelli di query e di comando separati. Ogni operazione di scrittura dei dati viene salvata nell'archivio di scrittura e quindi propagata nell'archivio di lettura. Prestare particolare attenzione al modo in cui il processo di propagazione dei dati opera sul principio della [coerenza finale](http://www.cloudcomputingpatterns.org/eventual_consistency/). Il modello di lettura viene sincronizzato con il modello di scrittura, ma è possibile che si verifichi un ritardo nel processo. Nella sezione successiva verrà illustrata la coerenza finale.

Questa separazione consente la scalabilità delle letture e scritture in modo indipendente. Le operazioni di lettura utilizzano uno schema ottimizzato per le query, mentre le Scritture utilizzano uno schema ottimizzato per gli aggiornamenti. Le query di lettura vengono eseguite su dati denormalizzati, mentre la logica di business complessa può essere applicata al modello di scrittura. È anche possibile imporre una sicurezza più stretta sulle operazioni di scrittura rispetto a quelle che espongono le letture.

L'implementazione di CQRS può migliorare le prestazioni dell'applicazione per i servizi nativi del cloud. Tuttavia, si ottiene un progetto più complesso. Applicare questo principio in modo accurato e strategico a tali sezioni dell'applicazione nativa del cloud che ne trarranno vantaggio. Per altre informazioni su CQRS, vedere la documentazione Microsoft relativa ai [microservizi .NET: architettura per le applicazioni .NET in contenitori](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns).

### <a name="event-sourcing"></a>Origine eventi

Un altro approccio per l'ottimizzazione degli scenari con volumi elevati di dati riguarda l'origine di [eventi](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

In genere, un sistema archivia lo stato corrente di un'entità di dati. Se un utente modifica il numero di telefono, ad esempio, il record del cliente viene aggiornato con il nuovo numero. Si conosce sempre lo stato corrente di un'entità di dati, ma ogni aggiornamento sovrascrive lo stato precedente.

Nella maggior parte dei casi, questo modello funziona correttamente. Nei sistemi con volumi elevati, tuttavia, l'overhead del blocco transazionale e delle frequenti operazioni di aggiornamento può influisca sulle prestazioni del database, sulla velocità di risposta e sul limite di scalabilità.

L'origine eventi adotta un approccio diverso per l'acquisizione dei dati. Ogni operazione che influiscono sui dati viene salvata in modo permanente in un archivio eventi. Anziché aggiornare lo stato di un record di dati, ogni modifica viene accodata a un elenco sequenziale di eventi passati, simile al Ledger di un revisore. L'archivio eventi diventa il sistema di registrazione per i dati. Viene usato per propagare varie viste materializzate all'interno del contesto delimitato di un microservizio. Nella figura 5,8 è illustrato il modello.

![Origine eventi](./media/event-sourcing.png)

**Figura 5-8**. Origine eventi

Nella figura precedente si noti come ogni voce (in blu) per il carrello acquisti di un utente viene aggiunta a un archivio eventi sottostante. Nella vista materializzata adiacente, il sistema proietta lo stato corrente riproducendo tutti gli eventi associati a ogni carrello acquisti. Questa vista, o lettura modello, viene quindi esposta all'interfaccia utente. Gli eventi possono inoltre essere integrati con applicazioni e sistemi esterni o sottoposti a query per determinare lo stato corrente di un'entità. Con questo approccio si mantiene la cronologia. Non solo si conosce lo stato corrente di un'entità, ma anche il modo in cui è stato raggiunto questo stato.

In termini meccanici, l'origine eventi semplifica il modello di scrittura. Non sono presenti aggiornamenti o eliminazioni. L'aggiunta di ogni voce di dati come evento non modificabile riduce al minimo i conflitti di contesa, di blocco e di concorrenza associati a database relazionali. La compilazione di modelli di lettura con il modello di vista materializzata consente di separare la visualizzazione dal modello di scrittura e scegliere l'archivio dati migliore per ottimizzare le esigenze dell'interfaccia utente dell'applicazione.

Per questo modello, si consideri un archivio dati che supporta direttamente il sourcing degli eventi. Azure Cosmos DB, MongoDB, Cassandra, CouchDB e RavenDB sono candidati validi.

Come per tutti i modelli e le tecnologie, implementare in modo strategico e quando necessario. Sebbene l'origine di eventi possa fornire prestazioni e scalabilità migliorate, si tratta di una riduzione della complessità e di una curva di apprendimento.

>[!div class="step-by-step"]
>[Precedente](service-mesh-communication-infrastructure.md)
>[successivo](relational-vs-nosql-data.md)
