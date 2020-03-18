---
title: Database per microservizio
description: Contrasto dell'archiviazione dei dati in applicazioni monolitiche e native del cloud.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: c0c5611fa866d70f155e4bdad2eee1181b13c065
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141445"
---
# <a name="database-per-microservice"></a>Database per microservizio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Come abbiamo visto in questo libro, un approccio nativo del cloud cambia il modo in cui progetti, distribuisci e gestisci le applicazioni. Cambia anche il modo in cui gestisci e memorizzi i dati.

Figura 5-1 mette a confronto le differenze.

![Archiviazione dei dati in applicazioni native cloudData storage in cloud-native applications](./media/distributed-data.png)

**Figura 5-1**. Gestione dei dati nelle applicazioni native cloudData management in cloud-native applications

Gli sviluppatori esperti riconosceranno facilmente l'architettura sul lato sinistro della figura 5-1. In questa *applicazione monolitica,* i componenti del servizio aziendale si collocano insieme in un livello servizi condivisi, condividendo i dati da un singolo database relazionale.

In molti modi, un singolo database semplifica la gestione dei dati. L'esecuzione di query sui dati in più tabelle è semplice. Modifiche all'aggiornamento dei dati insieme o tutti ne rilevano il rollback. Le [transazioni ACID](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) garantiscono una coerenza forte e immediata.

Progettare per cloud-native, adottiamo un approccio diverso. Sul lato destro della figura 5-1, si noti come le funzionalità aziendali si segregano in piccoli microservizi indipendenti. Ogni microservizio incapsula una funzionalità aziendale specifica e i propri dati. Il database monolitico si scompone in un modello di dati distribuito con molti database più piccoli, ognuno allineato a un microservizio. Quando il fumo si schiarisce, emerge con un design che espone un *database per microservizio*.

## <a name="why"></a>Perché?

Questo database per microservizio offre molti vantaggi, soprattutto per i sistemi che devono evolversi rapidamente e supportare la scalabilità massiccia. Con questo modello...

- I dati di dominio sono incapsulati all'interno del servizio
- Lo schema dei dati può evolvere senza influire direttamente su altri serviziData schema can evolve without directly impacting other services
- Ogni archivio dati può scalare in modo indipendente
- Un errore dell'archivio dati in un servizio non avrà un impatto diretto sugli altri servizi

La separazione dei dati consente inoltre a ogni microservizio di implementare il tipo di archivio dati che è meglio ottimizzato per il carico di lavoro, le esigenze di archiviazione e i modelli di lettura/scrittura. Le scelte includono archivi dati relazionali, di documenti, chiave-valore e persino basati su grafici.

Figura 5-2 presenta il principio della persistenza poliglotta in un sistema cloud-nativo.

![Persistenza dei dati poliglotta](./media/polyglot-data-persistence.png)

**Figura 5-2**. Persistenza dei dati poliglotta

Si noti nella figura precedente come ogni microservizio supporta un tipo diverso di archivio dati.

- Il microservizio del catalogo prodotti utilizza un database relazionale per supportare la struttura relazionale avanzata dei dati sottostanti.
- Il microservizio del carrello acquisti utilizza una cache distribuita che supporta il suo archivio dati semplice con chiave-valore.
- Il microservizio di ordinazione utilizza sia un database di documenti NoSql per le operazioni di scrittura e un archivio chiave/valore altamente denormalizzato per supportare volumi elevati di operazioni di lettura.
  
Sebbene i database relazionali rimangano rilevanti per i microservizi con dati complessi, i database NoSQL hanno guadagnato una notevole popolarità. Forniscono scalabilità massiccia e disponibilità elevata. La loro natura senza schema consente agli sviluppatori di passare da un'architettura di classi di dati tipizzate e ORM che rendono la modifica costosa e dispendiosa in termini di tempo. I database NoSQL vengono illustrati più avanti in questo capitolo.

 Sebbene l'incapsulamento dei dati in microservizi separati possa aumentare l'agilità, le prestazioni e la scalabilità, presenta anche molte sfide. Nella sezione successiva, discutiamo di queste sfide insieme a modelli e pratiche per aiutarli a superarle.  

## <a name="cross-service-queries"></a>Query tra servizi

Mentre i microservizi sono indipendenti e si concentrano su funzionalità specifiche, come l'inventario, la spedizione o l'ordinazione, spesso richiedono l'integrazione con altri microservizi. Spesso l'integrazione coinvolge un microservizio che *esegue query* su un altro per i dati. Nella figura 5-3 viene illustrato lo scenario.

![Esecuzione di query tra microservizi](./media/cross-service-query.png)

**Figura 5-3**. Esecuzione di query tra microservizi

Nella figura precedente viene visualizzato un microservizio del carrello acquisti che aggiunge un elemento al carrello acquisti di un utente. Sebbene l'archivio dati per questo microservizio contenga dati relativi a carrelli e elementi pubblicitari, non gestisce i dati relativi ai prodotti o ai prezzi. Al contrario, tali elementi di dati sono di proprietà dei microservizi di catalogo e determinazione dei prezzi. Questo rappresenta un problema. In che modo il microservizio del carrello acquisti può aggiungere un prodotto al carrello dell'utente quando non dispone di dati sui prodotti o sui prezzi nel suo database?

Un'opzione descritta nel capitolo 4 è una [chiamata HTTP diretta](service-to-service-communication.md#queries) dal carrello al catalogo e ai microservizi dei prezzi. Tuttavia, nel capitolo 4, abbiamo detto che le chiamate HTTP sincrone *accoppiano* i microservizi, riducendone l'autonomia e diminuendo ne i vantaggi architetturali.

È anche possibile implementare un modello di richiesta-risposta con code in ingresso e in uscita separate per ogni servizio. Tuttavia, questo modello è complicato e richiede l'impianto idraulico per correlare i messaggi di richiesta e risposta.
Mentre viene disaccoppiata le chiamate di microservizio back-end, il servizio chiamante deve comunque attendere in modo sincrono il completamento della chiamata. Congestione della rete, errori temporanei o un microservizio sovraccarico e può causare operazioni a esecuzione prolungata e persino non riuscite.

Al contrario, un modello ampiamente accettato per la rimozione delle dipendenze tra servizi è il modello di [visualizzazione materializzato](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), illustrato nella Figura 5-4.

![Modello di vista materializzata](./media/materialized-view-pattern.png)

**Figura 5-4**. Modello vista materializzata

Con questo modello, si inserisce una tabella di dati locale (noto come modello di *lettura)* nel servizio carrello acquisti. Questa tabella contiene una copia denormalizzata dei dati necessari dai microservizi dei prodotti e dei prezzi. La copia dei dati direttamente nel microservizio del carrello acquisti elimina la necessità di costose chiamate tra servizi. Con i dati locali per il servizio, è possibile migliorare il tempo di risposta e l'affidabilità del servizio. Inoltre, avere una propria copia dei dati rende il servizio del carrello acquisti più resiliente. Se il servizio di catalogo non è più disponibile, non avrebbe un impatto diretto sul servizio carrello acquisti. Il carrello può continuare a operare con i dati dal proprio negozio.

Il problema con questo approccio è che ora si dispone di dati duplicati nel sistema. Tuttavia, la duplicazione *strategica* dei dati nei sistemi nativi cloud è una pratica consolidata e non è considerata un anti-modello o una cattiva pratica. Tenere presente che *un solo servizio* può essere proprietario di un set di dati e disporre dell'autorità su di esso. È necessario sincronizzare i modelli di lettura quando il sistema di registrazione viene aggiornato. La sincronizzazione viene in genere implementata tramite messaggistica asincrona con un modello di [pubblicazione/sottoscrizione](service-to-service-communication.md#events), come illustrato nella Figura 5.4.

## <a name="distributed-transactions"></a>Transazioni distribuite

Sebbene l'esecuzione di query sui dati tra microservizi sia difficile, l'implementazione di una transazione tra diversi microservizi è ancora più complessa. La sfida intrinseca di mantenere la coerenza dei dati tra origini dati indipendenti in diversi microservizi non può essere sottovalutata. La mancanza di transazioni distribuite nelle applicazioni native cloud significa che è necessario gestire le transazioni distribuite a livello di codice. Si passa da un mondo di *coerenza immediata* a quello di *coerenza finale*.

Figura 5-5 mostra il problema.

![Transazione nel modello sagaTransaction in saga pattern](./media/saga-transaction-operation.png)

**Figura 5-5**. Implementazione di una transazione tra microserviziImplementing a transaction across microservices

Nella figura precedente, cinque microservizi indipendenti partecipano a una transazione distribuita che crea un ordine. Ogni microservizio gestisce il proprio archivio dati e implementa una transazione locale per il proprio archivio. Per creare l'ordine, la transazione locale per *ogni* singolo microservizio deve avere esito positivo oppure *tutti* devono interrompersi ed eseguire il rollback dell'operazione. Sebbene il supporto transazionale incorporato sia disponibile all'interno di ciascuno dei microservizi, non è disponibile alcun supporto per una transazione distribuita che si estenderebbe su tutti e cinque i servizi per mantenere coerenti i dati.

È invece necessario costruire questa transazione distribuita a livello di *codice.*

Un modello popolare per l'aggiunta di supporto transazionale distribuito è il modello Saga. Viene implementato raggruppando le transazioni locali a livello di codice e richiamando ciascuna di esse in sequenza. Se una delle transazioni locali ha esito negativo, la Saga interrompe l'operazione e richiama un set di [transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction). Le transazioni di compensazione annullano le modifiche apportate dalle transazioni locali precedenti e ripristinano la coerenza dei dati. Figura 5-6 Mostra una transazione non riuscita con il modello Saga.

![Torna indietro nel modello saga](./media/saga-rollback-operation.png)

**Figura 5-6**. Rollback di una transazione

Nella figura precedente, l'operazione *aggiorna inventario* non è riuscita nel microservizio Di magazzino. La Saga richiama un set di transazioni di compensazione (in rosso) per rettificare i conteggi scorte, annullare il pagamento e l'ordine e riportare i dati per ogni microservizio a uno stato coerente.

I modelli saga sono in genere coreografati come una serie di eventi correlati o orchestrati come un insieme di comandi correlati. Nel capitolo 4, abbiamo discusso il modello di aggregatore di servizi che sarebbe la base per l'implementazione di una saga orchestrata. Sono stati inoltre illustrati gli eventi insieme agli argomenti del bus di servizio di Azure e della griglia di eventi di Azure che sarebbero alla base di un'implementazione della saga coreografata.

## <a name="high-volume-data"></a>Dati ad alto volume

Le applicazioni native cloud di grandi dimensioni spesso supportano requisiti di dati di grandi volumi. In questi scenari, le tecniche di archiviazione dei dati tradizionali possono causare colli di bottiglia. Per i sistemi complessi distribuiti su larga scala, sia La topologia di comando che di query (CQRS) e la separazione degli eventi possono migliorare le prestazioni dell'applicazione.  

### <a name="cqrs"></a>CQRS

[CQRS](https://docs.microsoft.com/azure/architecture/patterns/cqrs), è un modello architetturale che consente di ottimizzare le prestazioni, la scalabilità e la sicurezza. Il modello separa le operazioni che leggono i dati dalle operazioni che scrivono dati.

Per gli scenari normali, lo stesso modello di entità e lo stesso oggetto repository di dati vengono utilizzati sia per le operazioni di lettura *che* di scrittura.

Tuttavia, uno scenario di dati con volumi elevati può trarre vantaggio da modelli e tabelle di dati separati per operazioni di lettura e scrittura. Per migliorare le prestazioni, l'operazione di lettura potrebbe eseguire query su una rappresentazione altamente denormalizzata dei dati per evitare costosi join di tabella ripetitivi e blocchi di tabella. L'operazione di *scrittura,* nota come *comando*, verrebbe aggiornata in base a una rappresentazione completamente normalizzata dei dati che garantisce la coerenza. È quindi necessario implementare un meccanismo per mantenere sincronizzate entrambe le rappresentazioni. In genere, ogni volta che la tabella di scrittura viene modificata, pubblica un evento che replica la modifica alla tabella di lettura.

Figura 5-7 viene illustrata un'implementazione del modello CQRS.

![Separazione responsabilità di comando e queryCommand and Query Responsibility Segregation](./media/cqrs-implementation.png)

**Figura 5-7**. Implementazione di CQRS

Nella figura precedente vengono implementati modelli di comando e query separati. Ogni operazione di scrittura dei dati viene salvata nell'archivio di scrittura e quindi propagata all'archivio di lettura. Prestare particolare attenzione a come il processo di propagazione dei dati opera sul principio della [coerenza finale](http://www.cloudcomputingpatterns.org/eventual_consistency/). Il modello di lettura alla fine si sincronizza con il modello di scrittura, ma potrebbe esserci un certo ritardo nel processo. Discutiamo della coerenza finale nella sezione successiva.

Questa separazione consente alle letture e alle scritture di scalare in modo indipendente. Le operazioni di lettura utilizzano uno schema ottimizzato per le query, mentre le scritture usano uno schema ottimizzato per gli aggiornamenti. Le query di lettura vengono eseguite sui dati denormalizzati, mentre la logica di business complessa può essere applicata al modello di scrittura. Inoltre, è possibile imporre una sicurezza più snella nelle operazioni di scrittura rispetto a quelle che espongono letture.

L'implementazione di CQRS può migliorare le prestazioni delle applicazioni per i servizi nativi cloud. Tuttavia, si traducono in una progettazione più complessa. Applicare questo principio con attenzione e strategicamente a quelle sezioni dell'applicazione cloud-native che ne trarranno vantaggio. Per altre informazioni su CQRS, vedere il libro Microsoft [.NET Microservices: Architecture for Containerized Applications .](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns)

### <a name="event-sourcing"></a>Origine evento

Un altro approccio per ottimizzare scenari di dati con volumi elevati prevede l'utilizzo di [Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

Un sistema archivia in genere lo stato corrente di un'entità di dati. Se un utente modifica il proprio numero di telefono, ad esempio, il record cliente viene aggiornato con il nuovo numero. Conosciamo sempre lo stato corrente di un'entità di dati, ma ogni aggiornamento sovrascrive lo stato precedente.

Nella maggior parte dei casi, questo modello funziona correttamente. Nei sistemi con volumi elevati, tuttavia, l'overhead del blocco transazionale e le operazioni di aggiornamento frequenti possono influire sulle prestazioni del database, sulla velocità di risposta e sulla scalabilità limite.

Event Sourcing adotta un approccio diverso per l'acquisizione dei dati. Ogni operazione che interessa i dati viene resa persistente in un archivio eventi. Anziché aggiornare lo stato di un record di dati, aggiungiamo ogni modifica a un elenco sequenziale di eventi passati, simile al libro mastro di un contabile. L'archivio eventi diventa il sistema di record per i dati. Viene utilizzato per propagare varie viste materializzate all'interno del contesto limitato di un microservizio. Figura 5.8 Mostra il modello.

![Origine eventi](./media/event-sourcing.png)

**Figura 5-8**. Origine eventi

Nella figura precedente, si noti come ogni voce (in blu) per il carrello della spesa di un utente viene aggiunta a un archivio eventi sottostante. Nella vista materializzata adiacente, il sistema proietta lo stato corrente riproducendo tutti gli eventi associati a ogni carrello. Questa visualizzazione, o modello di lettura, viene quindi esposta nuovamente all'interfaccia utente. Gli eventi possono anche essere integrati con sistemi e applicazioni esterni o sottoposti a query per determinare lo stato corrente di un'entità. Con questo approccio, si mantiene la storia. Si conosce non solo lo stato corrente di un'entità, ma anche come è stato raggiunto questo stato.

Meccanicamente parlando, l'origine eventi semplifica il modello di scrittura. Non ci sono aggiornamenti o eliminazioni. L'aggiunta di ogni immissione di dati come evento non modificabile riduce al minimo i conflitti di contesa, blocco e concorrenza associati ai database relazionali. La compilazione di modelli di lettura con il modello di visualizzazione materializzato consente di separare la visualizzazione dal modello di scrittura e di scegliere l'archivio dati migliore per ottimizzare le esigenze dell'interfaccia utente dell'applicazione.

Per questo modello, si consideri un archivio dati che supporta direttamente l'origine eventi. Azure Cosmos DB, MongoDB, Cassandra, CouchDB e RavenDB sono buoni candidati.

Come per tutti i modelli e le tecnologie, implementare strategicamente e quando necessario. Sebbene l'approvvigionamento di eventi possa fornire prestazioni e scalabilità migliori, ciò va a scapito della complessità e di una curva di apprendimento.

>[!div class="step-by-step"]
>[Successivo](service-mesh-communication-infrastructure.md)
>[precedente](relational-vs-nosql-data.md)
