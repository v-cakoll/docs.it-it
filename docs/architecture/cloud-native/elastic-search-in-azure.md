---
title: Elasticsearch in applicazioni native del cloud
description: Informazioni sull'aggiunta di funzionalità di ricerca elastica alle applicazioni native del cloud.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: e956f28877d88ce5279944964a877efc324918b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614084"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch in un'app nativa del cloud

Elasticsearch è un sistema di ricerca e analisi distribuito che consente funzionalità di ricerca complesse tra tipi diversi di dati. È open source e molto diffuso. Considerare il modo in cui le società seguenti integrano elasticsearch nell'applicazione:

- [Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) per la ricerca full-text e incrementale (ricerca durante la digitazione).
- [GitHub](https://www.elastic.co/customers/github) per indicizzare ed esporre oltre 8 milioni repository di codice.  
- [Docker](https://www.elastic.co/customers/docker) per rendere individuabile la relativa libreria di contenitori.

Elasticsearch si basa sul motore di ricerca full-text di [Apache Lucene](https://lucene.apache.org/core/) . Lucene fornisce l'indicizzazione e l'esecuzione di query di documenti a prestazioni elevate. Indicizza i dati con uno schema di indicizzazione invertita, anziché eseguire il mapping delle pagine alle parole chiave, esegue il mapping delle parole chiave alle pagine come un glossario alla fine di un libro. Lucene dispone di potenti funzionalità di sintassi di query ed è in grado di eseguire query sui dati:

- Termine (parola completa)
- Prefix (inizia con Word)
- Carattere jolly (con i \* filtri "" o "?")
- Frase (sequenza di testo in un documento)
- Valore booleano (ricerche complesse che combinano query)

Anche se Lucene fornisce plumbing di basso livello per la ricerca, elasticsearch fornisce il server che si trova sopra Lucene. Elasticsearch aggiunge funzionalità di livello superiore per semplificare Lucene di lavoro, tra cui un'API RESTful per accedere alla funzionalità di indicizzazione e ricerca di Lucene. Fornisce inoltre un'infrastruttura distribuita in grado di ottenere scalabilità elevata, tolleranza di errore e disponibilità elevata.

Per le più grandi applicazioni native del cloud con requisiti di ricerca complessi, elasticsearch è disponibile come servizio gestito in Azure. Il Microsoft Azure Marketplace include modelli preconfigurati che gli sviluppatori possono usare per distribuire un cluster elasticsearch in Azure.

Dal Microsoft Azure Marketplace, gli sviluppatori possono usare modelli preconfigurati creati per distribuire rapidamente un cluster elasticsearch in Azure. Usando l'offerta gestita da Azure, è possibile distribuire fino a 50 nodi dati, 20 nodi di coordinamento e tre nodi master dedicati.

## <a name="summary"></a>Summary

Questo capitolo presenta una descrizione dettagliata dei dati nei sistemi nativi del cloud. Abbiamo iniziato a contrastare l'archiviazione dei dati in applicazioni monolitiche con modelli di archiviazione dei dati nei sistemi nativi del cloud. Sono stati esaminati i modelli di dati implementati nei sistemi nativi del cloud, incluse le query tra servizi, le transazioni distribuite e i modelli per gestire i sistemi con volumi elevati. Il confronto tra SQL e i dati di NoSQL è stato diverso. Sono state esaminate le opzioni di archiviazione dei dati disponibili in Azure che includono opzioni sia incentrate su Microsoft che Open Source. Infine, è stato illustrato come memorizzare nella cache e elasticsearch in un'applicazione nativa del cloud.

### <a name="references"></a>Riferimenti

- [Modello di separazione di responsabilità per query e comandi (CQRS, Command and Query Responsibility Segregation)](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Modello di origine eventi](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [Perché il teorema della divisione RDBMS non è tollerante nel teorema delle estremità e perché è disponibile?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Vista materializzata](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [È sufficiente conoscere i database open source](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Modello di transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Modello saga](https://microservices.io/patterns/data/saga.html)

- [Modelli saga | Come implementare transazioni aziendali con microservizi](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Modello di transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Come ottenere dietro la 9-palla: Cosmos DB livelli di coerenza descritti](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Esplorazione dei diversi tipi di database NoSQL parte II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [Nei database RDBMS, NoSQL e NewSQL. Intervista con John Ryan](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL vs NewSQL: confronto completo](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: quattro proprietà di Kubernetes-database nativi](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [CockroachDB](https://www.cockroachlabs.com/)

- [TiDB](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Vite](https://vitess.io/)

- [Articolo relativo alla guida completa di Elasticsearch](http://shop.oreilly.com/product/0636920028505.do)
  
- [Introduzione ad Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Precedente](azure-caching.md) 
> [Avanti](resiliency.md) <!-- Next Chapter -->
