---
title: Modelli di dati cloud nativi
description: Architettura di app .NET cloud native per Azure | Modelli di dati nativi cloud
ms.date: 06/30/2019
ms.openlocfilehash: 9e90409b0b633796b452cfcfecb3896e79002d4d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337429"
---
# <a name="cloud-native-data-patterns"></a>Modelli di dati cloud nativi

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Sebbene i dati decentralizzati possano migliorare le prestazioni, la scalabilità e il risparmio sui costi, presentano anche molte problemi. L'esecuzione di query per i dati tra microservizi è complessa. Una transazione che si estende su microservizi deve essere gestita a livello di programmazione perché le transazioni distribuite non sono supportate nelle applicazioni native del cloud. Si passa da un mondo di *coerenza immediata* alla *coerenza finale*.

Questi problemi sono ora discussi.

## <a name="cross-service-queries"></a>Query tra servizi

In che modo un'applicazione esegue query sui dati distribuiti in molti microservizi indipendenti?

Nella figura 5-4 è illustrato questo scenario.

![Esecuzione di query tra microservizi](./media/cross-service-query.png)

**Figura 5-4**. Esecuzione di query tra microservizi

Si noti come nella figura precedente viene visualizzato un microservizio carrello acquisti che aggiunge un elemento al carrello acquisti di un utente. Mentre l'archivio dati del carrello contiene una tabella basket e lineItem, non contiene dati relativi a prodotti o prezzi quando tali elementi si trovano nei microservizi Product e price. Per aggiungere un elemento, il microservizio carrello acquisti richiede i dati del prodotto e i dati sui prezzi. Quali sono le opzioni per ottenere i dati relativi ai prodotti e ai prezzi?

La figura 5-5 Mostra il microservizio carrello acquisti che effettua una chiamata HTTP diretta al catalogo dei prodotti e ai microservizi tariffari.

![Comunicazione HTTP diretta](./media/direct-http-communication.png)

**Figura 5-5**. Comunicazione HTTP diretta

Sebbene sia possibile implementare, nel capitolo 4 è stato illustrato il modo in cui le chiamate HTTP dirette tra i microservizi si abbinano al sistema e non vengono considerate buone procedure.

È possibile implementare un microservizio aggregator illustrato nella figura 5-6.

![Microservizio aggregator](./media/aggregator-microservice.png)

**Figura 5-6.** Microservizio aggregator

Sebbene questo approccio incapsulare il flusso di lavoro dell'operazione di business in un singolo microservizio, aggiunge complessità e restituisce comunque le chiamate HTTP dirette.

Un approccio comune per l'esecuzione di query tra servizi usa il [modello di vista materializzata](https://docs.microsoft.com/azure/architecture/patterns/materialized-view), illustrato nella figura 5-7.

![Modello di vista materializzata](./media/materialized-view-pattern.png)

**Figure5-7**. Modello di vista materializzata

Con questo modello, si inserisce direttamente una tabella locale, nota come *modello di lettura*, nel servizio carrello acquisti che contiene una copia denormalizzata dei dati necessari per i microservizi Product e pricing. Inserendo i dati all'interno del microservizio carrello acquisti si elimina la necessità di richiamare costose chiamate tra servizi. Con i dati locali per il servizio, è possibile migliorare il tempo di risposta e l'affidabilità.

Il problema con questo approccio è che ora sono presenti dati duplicati nel sistema. Nei sistemi nativi del cloud, i dati duplicati non sono considerati un [anti-modello](https://en.wikipedia.org/wiki/Anti-pattern) ed è comunemente implementato nei sistemi nativi del cloud. Tuttavia, un solo sistema può essere il proprietario di un set di dati ed è necessario implementare un meccanismo di sincronizzazione affinché il sistema di registrazione aggiorni tutti i modelli di lettura associati, ogni volta che viene apportata una modifica ai dati sottostanti.

## <a name="transactional-support"></a>Supporto delle transazioni

Sebbene le query tra microservizi siano complesse, l'implementazione di una transazione tra microservizi può essere complessa. La sfida inerente alla gestione della coerenza dei dati tra le origini dati che si trovano in microservizi diversi non può essere sottostata. La figura 5-8 illustra il problema.

![Transazione nel modello saga](./media/saga-transaction-operation.png)

**Figura 5-8**. Implementazione di una transazione tra microservizi

Si noti che nella figura precedente cinque microservizi indipendenti partecipano tutti a una transazione di *creazione ordine* distribuita. Tuttavia, la transazione per ognuno dei cinque singoli microservizi deve avere esito positivo oppure tutti devono interrompere ed eseguire il rollback dell'operazione. Sebbene il supporto transazionale predefinito sia disponibile all'interno di ogni microservizio, non esiste alcun supporto per una transazione distribuita in tutti i cinque servizi.

Poiché il supporto transazionale è essenziale per questa operazione per mantenere i dati coerenti in ogni microservizio, è necessario creare una transazione distribuita a livello di codice.

Uno dei modelli più diffusi per l'aggiunta a livello di codice del supporto transazionale è il [modello saga](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/). Viene implementato raggruppando le transazioni locali e richiamando in modo sequenziale ciascuna di esse. Se una transazione locale ha esito negativo, la saga interrompe l'operazione e richiama un set di [transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction) per annullare le modifiche apportate dalle transazioni locali precedenti. La figura 5-9 Mostra una transazione non riuscita con il modello saga.

![Eseguire il rollback nel modello saga](./media/saga-rollback-operation.png)

**Figura 5-9**. Esecuzione del rollback di una transazione

Si noti come nella figura precedente l'operazione *GenerateContent* non è riuscita nel microservizio Music. La saga richiama le transazioni di compensazione (in rosso) per rimuovere il contenuto, annullare il pagamento e annullare l'ordine, restituendo di nuovo i dati per ogni microservizio a uno stato coerente.

I modelli di Saga vengono in genere sottoposti a coreografia come una serie di eventi correlati o orchestrati come un set di comandi correlati.

## <a name="cqrs-pattern"></a>Modello CQRS

CQRS, o [separazione di responsabilità per query e comandi](https://docs.microsoft.com/azure/architecture/patterns/cqrs), è uno schema architettonico che separa le operazioni di lettura dei dati da quelle che scrivono i dati. Questo modello consente di ottimizzare le prestazioni, la scalabilità e la sicurezza.

Negli scenari di accesso ai dati normali si implementa un singolo modello (oggetto entità e repository) che eseguono operazioni *di lettura e* scrittura dei dati.

Uno scenario di accesso ai dati più avanzato può tuttavia trarre vantaggio da modelli e tabelle di dati separati per operazioni di lettura e scrittura. Per migliorare le prestazioni, l'operazione di lettura, nota come *query*, potrebbe eseguire query su una rappresentazione altamente denormalizzata dei dati per evitare costosi join di tabella ripetitivi. Mentre l'operazione di *scrittura* , nota come *comando*, potrebbe essere aggiornata rispetto a una rappresentazione completamente normalizzata dei dati. Sarà quindi necessario implementare un meccanismo per mantenendo sincronizzate entrambe le rappresentazioni. In genere, ogni volta che la tabella di scrittura viene modificata, genera un evento che replica la modifica dei dati nella tabella Read.

La figura 5-10 illustra un'implementazione del modello CQRS.

![Implementazione di CQRS](./media/cqrs-implementation.png)

**Figura 5-10**. Implementazione di CQRS

Si noti che nella figura precedente sono implementati i modelli di query e di comando separati. Ogni operazione di scrittura dei dati viene inoltre salvata nell'archivio di scrittura e quindi propagata nell'archivio di lettura. Prestare particolare attenzione al modo in cui il processo di propagazione opera sul principio della [coerenza finale](https://www.cloudcomputingpatterns.org/eventual_consistency/), mentre il modello di lettura viene sincronizzato con il modello di scrittura, ma potrebbe verificarsi un certo ritardo nel processo.

Implementando la separazione, è possibile ridimensionare le letture e le Scritture separatamente. È anche possibile imporre una sicurezza più stretta sulle operazioni di scrittura rispetto a quelle relative alle letture.

In genere, i modelli CQRS vengono applicati a sezioni limitate del sistema in base a specifiche esigenze.

## <a name="relational-vs-nosql"></a>Confronto tra NoSQL e relazionali

L'effetto delle tecnologie [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) non può essere sovrastato, specialmente per i sistemi distribuiti nativi del cloud. La proliferazione di nuove tecnologie dati in questo spazio ha comportato soluzioni che una volta si basavano esclusivamente sui database relazionali.

Da un lato, i database relazionali sono stati una tecnologia prevalente per decenni. Sono maturi, collaudati e ampiamente implementati. I prodotti di database, le competenze e gli strumenti in competizione sono molto ricchi. I database relazionali forniscono un archivio di tabelle di dati correlate. Queste tabelle hanno uno schema fisso, usano SQL (Structured Query Language) per gestire i dati e hanno garanzie [acid](https://www.geeksforgeeks.org/acid-properties-in-dbms/) (noti anche come atomicità, coerenza, isolamento e durabilità).

I database no-SQL, dall'altro lato, fanno riferimento a archivi dati non relazionali a prestazioni elevate. Si distinguono per la facilità d'uso, la scalabilità, la resilienza e le caratteristiche di disponibilità. Anziché riunire le tabelle di dati normalizzati, NoSQL archivia i dati autodescrittivi (senza schema) in genere nei documenti JSON. Non offrono garanzie [acid](https://www.geeksforgeeks.org/acid-properties-in-dbms/) .

Un modo per comprendere le differenze tra questi tipi di database è disponibile nel [teorema Cap](https://towardsdatascience.com/cap-theorem-and-distributed-database-management-systems-5c2be977950e), un set di principi che è possibile applicare ai sistemi distribuiti che archiviano lo stato. La figura 5-11 illustra le tre proprietà del teorema CAP.

![Teorema CAP](./media/cap-theorem.png)

**Figura 5-11**. Teorema CAP

Il teorema indica che qualsiasi sistema di dati distribuito offrirà un compromesso tra coerenza, disponibilità e tolleranza di partizione e che qualsiasi database può garantire solo due delle tre proprietà:

- *Coerenza*: ogni nodo del cluster risponderà con i dati più recenti, anche se è necessario bloccare una richiesta fino a quando tutte le repliche non vengono aggiornate correttamente.

- *Disponibilità*: ogni nodo restituirà una risposta in un periodo di tempo ragionevole, anche se tale risposta non è i dati più recenti.

- *Tolleranza di partizione*: garantisce che il sistema continuerà a funzionare in caso di errore di un nodo o di perdita della connettività con un'altra.

I database relazionali presentano coerenza e disponibilità, ma non la tolleranza della partizione. Il partizionamento di un database relazionale, ad esempio il partizionamento orizzontale, è difficile e può influisca sulle prestazioni.

D'altra parte, i database NoSQL in genere presentano tolleranza di partizione, nota come scalabilità orizzontale e disponibilità elevata. Come specificato dal teorema CAP, è possibile avere solo due dei tre principi e si perde la proprietà di coerenza.

I database NoSQL vengono distribuiti e generalmente scalati orizzontalmente nei server di prodotti. Questa operazione può offrire una disponibilità straordinaria, sia all'interno che tra aree geografiche a un costo ridotto. I dati possono essere partizionati e replicati in questi computer, o nodi, garantendo ridondanza e tolleranza di errore. Il lato negativo è la coerenza. Una modifica ai dati in un nodo NoSQL può richiedere del tempo per la propagazione ad altri nodi. In genere, un nodo del database NoSQL fornirà una risposta immediata a una query, anche se i dati che presenta sono obsoleti e non sono stati ancora aggiornati.

Si tratta di una [coerenza finale](https://www.cloudcomputingpatterns.org/eventual_consistency/)nota, una caratteristica dei sistemi dati distribuiti in cui non sono supportate le transazioni ACID. Si tratta di un breve ritardo tra l'aggiornamento di un elemento di dati e il tempo necessario per propagare tale aggiornamento a ogni nodo di replica. Se si aggiorna un elemento prodotto in un database NoSQL nel Stati Uniti, ma allo stesso tempo si esegue una query sullo stesso elemento di dati da un nodo di replica in Europa, è possibile recuperare le informazioni precedenti sul prodotto, fino a quando il nodo europeo non è stato aggiornato con la modifica del prodotto. Il compromesso è che, grazie alla [coerenza](https://en.wikipedia.org/wiki/Strong_consistency)assoluta, in attesa dell'aggiornamento di tutti i nodi di replica prima della restituzione di un risultato della query, è possibile supportare volumi di traffico e scalabilità enormi, ma con la possibilità di presentare dati meno recenti.

I database NoSQL possono essere suddivisi in categorie in base ai quattro modelli seguenti:

- *Archivio documenti* (MongoDB, CouchDB, Couchbase): i dati (e i metadati corrispondenti) vengono archiviati in un formato non relazionale in documenti denormalizzati basati su JSON all'interno del database.

- *Archivio chiave/valore* (Redis, Riak, Memcached): i dati vengono archiviati in semplici coppie chiave-valore con operazioni di sistema eseguite su una chiave di accesso univoca mappata a un valore di dati utente.

- *Archivio a colonne Wide* (HBASE, Cassandra): i dati correlati vengono archiviati in un formato a colonne come un set di coppie chiave/valore annidate all'interno di una singola colonna con dati recuperati in genere come una singola unità senza dover unire più tabelle.

- *Archivi Graph* (Neo4j, Titan): i dati vengono archiviati come rappresentazione grafica all'interno di un nodo insieme ai bordi che specificano la relazione tra i nodi.

I database NoSQL possono essere ottimizzati per gestire i dati su larga scala, soprattutto quando i dati sono relativamente semplici. Si consideri un database NoSQL nei casi seguenti:

- Il carico di lavoro richiede una grande scala e una concorrenza elevata.
- Si dispone di un numero elevato di utenti.
- I dati possono essere espressi semplicemente senza relazioni.
- È necessario distribuire geograficamente i dati.
- Non sono necessarie le garanzie ACID.
- Verranno distribuiti nell'hardware di un prodotto.

Quindi, si consideri un database relazionale nei casi seguenti:

- I carichi di lavoro richiedono una scala media-large.
- La concorrenza non è un problema importante.
- Sono necessarie le garanzie ACID.
- I dati sono espressi in modo ottimale in modo relazionale.
- L'applicazione verrà distribuita nell'hardware di fascia alta di grandi dimensioni.

Viene quindi esaminata l'archiviazione dei dati nel cloud di Azure.

>[!div class="step-by-step"]
>[Precedente](distributed-data.md)
>[Successivo](azure-data-storage.md)
