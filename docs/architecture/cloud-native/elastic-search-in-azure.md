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
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="7d036-103">Elasticsearch in un'app nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="7d036-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7d036-104">Elasticsearch è un sistema di ricerca e analisi distribuito che consente funzionalità di ricerca complesse tra diversi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="7d036-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="7d036-105">È open source e ampiamente popolare.</span><span class="sxs-lookup"><span data-stu-id="7d036-105">It's open source and widely popular.</span></span> <span data-ttu-id="7d036-106">Considerare come le seguenti aziende integrano Elasticsearch nella propria applicazione:</span><span class="sxs-lookup"><span data-stu-id="7d036-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="7d036-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) per la ricerca full-text e incrementale (ricerca durante la digitazione).</span><span class="sxs-lookup"><span data-stu-id="7d036-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="7d036-108">[GitHub](https://www.elastic.co/customers/github) per indicizzare ed esporre oltre 8 milioni di repository di codice.</span><span class="sxs-lookup"><span data-stu-id="7d036-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="7d036-109">[Docker](https://www.elastic.co/customers/docker) per rendere la libreria contenitore individuabile.</span><span class="sxs-lookup"><span data-stu-id="7d036-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="7d036-110">Elasticsearch è costruito sulla cima del motore di ricerca full-text [Apache Lucene.](https://lucene.apache.org/core/)</span><span class="sxs-lookup"><span data-stu-id="7d036-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="7d036-111">Lucene fornisce l'indicizzazione e l'esecuzione di query di documenti ad alte prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7d036-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="7d036-112">Indicizza i dati con uno schema di indicizzazione invertito: invece di mappare le pagine a parole chiave, esegue il mapping delle parole chiave alle pagine come un glossario alla fine di un libro.</span><span class="sxs-lookup"><span data-stu-id="7d036-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="7d036-113">Lucene dispone di potenti funzionalità di sintassi delle query e può eseguire query sui dati in base a:Lucene has powerful query syntax capabilities and can query data by:</span><span class="sxs-lookup"><span data-stu-id="7d036-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="7d036-114">Termine (una parola completa)</span><span class="sxs-lookup"><span data-stu-id="7d036-114">Term (a full word)</span></span>
- <span data-ttu-id="7d036-115">Prefisso (inizia-con parola)</span><span class="sxs-lookup"><span data-stu-id="7d036-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="7d036-116">Carattere jolly\*(utilizzando i filtri " " o "?")</span><span class="sxs-lookup"><span data-stu-id="7d036-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="7d036-117">Frase (una sequenza di testo in un documento)</span><span class="sxs-lookup"><span data-stu-id="7d036-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="7d036-118">Valore booleano (ricerche complesse che combinano query)</span><span class="sxs-lookup"><span data-stu-id="7d036-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="7d036-119">Mentre Lucene fornisce idraulico di basso livello per la ricerca, Elasticsearch fornisce il server che si trova sulla parte superiore di Lucene.</span><span class="sxs-lookup"><span data-stu-id="7d036-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="7d036-120">Elasticsearch aggiunge funzionalità di livello superiore per semplificare l'utilizzo di Lucene, inclusa un'API RESTful per accedere alle funzionalità di indicizzazione e ricerca di Lucene.</span><span class="sxs-lookup"><span data-stu-id="7d036-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene’s indexing and searching functionality.</span></span> <span data-ttu-id="7d036-121">Fornisce inoltre un'infrastruttura distribuita in grado di eseguire scalabilità massiccia, tolleranza di errore e disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="7d036-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="7d036-122">Per applicazioni native cloud di grandi dimensioni con requisiti di ricerca complessi, Elasticsearch è disponibile come servizio gestito in Azure.For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span><span class="sxs-lookup"><span data-stu-id="7d036-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="7d036-123">Le caratteristiche di Microsoft Azure Marketplace modelli preconfigurati che gli sviluppatori possono usare per distribuire un cluster Elasticsearch in Azure.The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span><span class="sxs-lookup"><span data-stu-id="7d036-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="7d036-124">Da Microsoft Azure Marketplace, gli sviluppatori possono usare modelli preconfigurati creati per distribuire rapidamente un cluster Elasticsearch in Azure.From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span><span class="sxs-lookup"><span data-stu-id="7d036-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="7d036-125">Usando l'offerta gestita da Azure, è possibile distribuire fino a 50 nodi di dati, 20 nodi di coordinamento e tre nodi master dedicati.</span><span class="sxs-lookup"><span data-stu-id="7d036-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="7d036-126">Summary</span><span class="sxs-lookup"><span data-stu-id="7d036-126">Summary</span></span>

<span data-ttu-id="7d036-127">Questo capitolo ha presentato un'analisi dettagliata dei dati nei sistemi nativi del cloud.</span><span class="sxs-lookup"><span data-stu-id="7d036-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="7d036-128">Abbiamo iniziato confrontando l'archiviazione dei dati nelle applicazioni monolitiche con i modelli di archiviazione dei dati nei sistemi nativi al cloud.</span><span class="sxs-lookup"><span data-stu-id="7d036-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="7d036-129">Abbiamo esaminato i modelli di dati implementati nei sistemi nativi cloud, tra cui query tra servizi, transazioni distribuite e modelli per gestire sistemi con volumi elevati.</span><span class="sxs-lookup"><span data-stu-id="7d036-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="7d036-130">Abbiamo confrontato SQL con i dati NoSQL.</span><span class="sxs-lookup"><span data-stu-id="7d036-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="7d036-131">Sono state esaminate le opzioni di archiviazione dei dati disponibili in Azure che includono opzioni sia incentrate su Microsoft che open source.</span><span class="sxs-lookup"><span data-stu-id="7d036-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="7d036-132">Infine, abbiamo discusso la memorizzazione nella cache e Elasticsearch in un'applicazione cloud-native.</span><span class="sxs-lookup"><span data-stu-id="7d036-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="7d036-133">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="7d036-133">References</span></span>

- [<span data-ttu-id="7d036-134">Modello di separazione di responsabilità per query e comandi (CQRS, Command and Query Responsibility Segregation)</span><span class="sxs-lookup"><span data-stu-id="7d036-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="7d036-135">Modello di approvvigionamento di eventi</span><span class="sxs-lookup"><span data-stu-id="7d036-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="7d036-136">Database RDBMSs e NoSQL: panoramica</span><span class="sxs-lookup"><span data-stu-id="7d036-136">RDBMSs vs. NoSQL Databases: Overview</span></span>](https://maxivak.com/rdbms-vs-nosql-databases/)

- [<span data-ttu-id="7d036-137">Perché RDBMS Partition Tolerant non è tollerante nel teorema CAP e perché è disponibile?</span><span class="sxs-lookup"><span data-stu-id="7d036-137">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="7d036-138">Vista materializzata</span><span class="sxs-lookup"><span data-stu-id="7d036-138">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="7d036-139">Tutto quello che dovete sapere sui database open source</span><span class="sxs-lookup"><span data-stu-id="7d036-139">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="7d036-140">Modello di transazioni di compensazione</span><span class="sxs-lookup"><span data-stu-id="7d036-140">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="7d036-141">Modello Saga</span><span class="sxs-lookup"><span data-stu-id="7d036-141">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="7d036-142">Modelli Saga Come implementare le transazioni aziendali utilizzando i microservizi</span><span class="sxs-lookup"><span data-stu-id="7d036-142">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="7d036-143">Modello di transazioni di compensazione</span><span class="sxs-lookup"><span data-stu-id="7d036-143">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="7d036-144">Dietro la 9-Ball: cosmos DB livelli di coerenza spiegato</span><span class="sxs-lookup"><span data-stu-id="7d036-144">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="7d036-145">Esplorazione dei diversi tipi di database NoSQL Parte II</span><span class="sxs-lookup"><span data-stu-id="7d036-145">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="7d036-146">Nei database RDBMS, NoSQL e NewSQL. Intervista a John Ryan</span><span class="sxs-lookup"><span data-stu-id="7d036-146">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="7d036-147">SQL vs NoSQL e NewSQL: il confronto completo</span><span class="sxs-lookup"><span data-stu-id="7d036-147">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="7d036-148">DASH: quattro proprietà di Kubernetes-Native Databases</span><span class="sxs-lookup"><span data-stu-id="7d036-148">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="7d036-149">Scarafaggidb</span><span class="sxs-lookup"><span data-stu-id="7d036-149">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="7d036-150">Ordinatore di cose da parte</span><span class="sxs-lookup"><span data-stu-id="7d036-150">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="7d036-151">JuribyteDB</span><span class="sxs-lookup"><span data-stu-id="7d036-151">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="7d036-152">Vitess</span><span class="sxs-lookup"><span data-stu-id="7d036-152">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="7d036-153">Articolo relativo alla guida completa di Elasticsearch</span><span class="sxs-lookup"><span data-stu-id="7d036-153">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="7d036-154">Introduzione ad Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="7d036-154">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="7d036-155">[Successivo](azure-caching.md)
>[precedente](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="7d036-155">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
