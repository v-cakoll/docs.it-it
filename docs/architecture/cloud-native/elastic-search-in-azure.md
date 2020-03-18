---
title: Elasticsearch nelle applicazioni native cloud
description: Informazioni sull'aggiunta di funzionalità di ricerca elastica alle applicazioni native del cloud.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141289"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch in un'app nativa del cloud

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch è un sistema di ricerca e analisi distribuito che consente funzionalità di ricerca complesse tra diversi tipi di dati. È open source e ampiamente popolare. Considerare come le seguenti aziende integrano Elasticsearch nella propria applicazione:

- [Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) per la ricerca full-text e incrementale (ricerca durante la digitazione).
- [GitHub](https://www.elastic.co/customers/github) per indicizzare ed esporre oltre 8 milioni di repository di codice.  
- [Docker](https://www.elastic.co/customers/docker) per rendere la libreria contenitore individuabile.

Elasticsearch è costruito sulla cima del motore di ricerca full-text [Apache Lucene.](https://lucene.apache.org/core/) Lucene fornisce l'indicizzazione e l'esecuzione di query di documenti ad alte prestazioni. Indicizza i dati con uno schema di indicizzazione invertito: invece di mappare le pagine a parole chiave, esegue il mapping delle parole chiave alle pagine come un glossario alla fine di un libro. Lucene dispone di potenti funzionalità di sintassi delle query e può eseguire query sui dati in base a:Lucene has powerful query syntax capabilities and can query data by:

- Termine (una parola completa)
- Prefisso (inizia-con parola)
- Carattere jolly\*(utilizzando i filtri " " o "?")
- Frase (una sequenza di testo in un documento)
- Valore booleano (ricerche complesse che combinano query)

Mentre Lucene fornisce idraulico di basso livello per la ricerca, Elasticsearch fornisce il server che si trova sulla parte superiore di Lucene. Elasticsearch aggiunge funzionalità di livello superiore per semplificare l'utilizzo di Lucene, inclusa un'API RESTful per accedere alle funzionalità di indicizzazione e ricerca di Lucene. Fornisce inoltre un'infrastruttura distribuita in grado di eseguire scalabilità massiccia, tolleranza di errore e disponibilità elevata.

Per applicazioni native cloud di grandi dimensioni con requisiti di ricerca complessi, Elasticsearch è disponibile come servizio gestito in Azure.For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure. Le caratteristiche di Microsoft Azure Marketplace modelli preconfigurati che gli sviluppatori possono usare per distribuire un cluster Elasticsearch in Azure.The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.

Da Microsoft Azure Marketplace, gli sviluppatori possono usare modelli preconfigurati creati per distribuire rapidamente un cluster Elasticsearch in Azure.From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure. Usando l'offerta gestita da Azure, è possibile distribuire fino a 50 nodi di dati, 20 nodi di coordinamento e tre nodi master dedicati.

## <a name="summary"></a>Summary

Questo capitolo ha presentato un'analisi dettagliata dei dati nei sistemi nativi del cloud. Abbiamo iniziato confrontando l'archiviazione dei dati nelle applicazioni monolitiche con i modelli di archiviazione dei dati nei sistemi nativi al cloud. Abbiamo esaminato i modelli di dati implementati nei sistemi nativi cloud, tra cui query tra servizi, transazioni distribuite e modelli per gestire sistemi con volumi elevati. Abbiamo confrontato SQL con i dati NoSQL. Sono state esaminate le opzioni di archiviazione dei dati disponibili in Azure che includono opzioni sia incentrate su Microsoft che open source. Infine, abbiamo discusso la memorizzazione nella cache e Elasticsearch in un'applicazione cloud-native.

### <a name="references"></a>Riferimenti

- [Modello di separazione di responsabilità per query e comandi (CQRS, Command and Query Responsibility Segregation)](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Modello di approvvigionamento di eventi](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [Database RDBMSs e NoSQL: panoramica](https://maxivak.com/rdbms-vs-nosql-databases/)

- [Perché RDBMS Partition Tolerant non è tollerante nel teorema CAP e perché è disponibile?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Vista materializzata](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [Tutto quello che dovete sapere sui database open source](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Modello di transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Modello Saga](https://microservices.io/patterns/data/saga.html)

- [Modelli Saga Come implementare le transazioni aziendali utilizzando i microservizi](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Modello di transazioni di compensazione](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Dietro la 9-Ball: cosmos DB livelli di coerenza spiegato](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Esplorazione dei diversi tipi di database NoSQL Parte II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [Nei database RDBMS, NoSQL e NewSQL. Intervista a John Ryan](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL e NewSQL: il confronto completo](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: quattro proprietà di Kubernetes-Native Databases](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [Scarafaggidb](https://www.cockroachlabs.com/)

- [Ordinatore di cose da parte](https://pingcap.com/en/)

- [JuribyteDB](https://www.yugabyte.com/)

- [Vitess](https://vitess.io/)

- [Articolo relativo alla guida completa di Elasticsearch](http://shop.oreilly.com/product/0636920028505.do)
  
- [Introduzione ad Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Successivo](azure-caching.md)
>[precedente](resiliency.md) <!-- Next Chapter -->
