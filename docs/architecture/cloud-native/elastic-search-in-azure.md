---
title: Elasticsearch in applicazioni native del cloud
description: Informazioni sull'aggiunta di funzionalità di ricerca elastica alle applicazioni native del cloud.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 6ea237eddc89a8c6843d6b34b05b1b71515a99b6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794877"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="ffa45-103">Elasticsearch in un'app nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="ffa45-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ffa45-104">Elasticsearch è un sistema di ricerca e analisi distribuito che consente funzionalità di ricerca complesse tra tipi diversi di dati.</span><span class="sxs-lookup"><span data-stu-id="ffa45-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="ffa45-105">È open source e molto diffuso.</span><span class="sxs-lookup"><span data-stu-id="ffa45-105">It's open source and widely popular.</span></span> <span data-ttu-id="ffa45-106">Considerare il modo in cui le società seguenti integrano elasticsearch nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="ffa45-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="ffa45-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) per la ricerca full-text e incrementale (ricerca durante la digitazione).</span><span class="sxs-lookup"><span data-stu-id="ffa45-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="ffa45-108">[GitHub](https://www.elastic.co/customers/github) per indicizzare ed esporre oltre 8 milioni repository di codice.</span><span class="sxs-lookup"><span data-stu-id="ffa45-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="ffa45-109">[Docker](https://www.elastic.co/customers/docker) per rendere individuabile la relativa libreria di contenitori.</span><span class="sxs-lookup"><span data-stu-id="ffa45-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="ffa45-110">Elasticsearch si basa sul motore di ricerca full-text di [Apache Lucene](https://lucene.apache.org/core/) .</span><span class="sxs-lookup"><span data-stu-id="ffa45-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="ffa45-111">Lucene fornisce l'indicizzazione e l'esecuzione di query di documenti a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="ffa45-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="ffa45-112">Indicizza i dati con uno schema di indicizzazione invertita, anziché eseguire il mapping delle pagine alle parole chiave, esegue il mapping delle parole chiave alle pagine come un glossario alla fine di un libro.</span><span class="sxs-lookup"><span data-stu-id="ffa45-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="ffa45-113">Lucene dispone di potenti funzionalità di sintassi di query ed è in grado di eseguire query sui dati:</span><span class="sxs-lookup"><span data-stu-id="ffa45-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="ffa45-114">Termine (parola completa)</span><span class="sxs-lookup"><span data-stu-id="ffa45-114">Term (a full word)</span></span> 
- <span data-ttu-id="ffa45-115">Prefix (inizia con Word)</span><span class="sxs-lookup"><span data-stu-id="ffa45-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="ffa45-116">Carattere jolly (usando i filtri "\*" o "?")</span><span class="sxs-lookup"><span data-stu-id="ffa45-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="ffa45-117">Frase (sequenza di testo in un documento)</span><span class="sxs-lookup"><span data-stu-id="ffa45-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="ffa45-118">Valore booleano (ricerche complesse che combinano query)</span><span class="sxs-lookup"><span data-stu-id="ffa45-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="ffa45-119">Anche se Lucene fornisce plumbing di basso livello per la ricerca, elasticsearch fornisce il server che si trova sopra Lucene.</span><span class="sxs-lookup"><span data-stu-id="ffa45-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="ffa45-120">Elasticsearch aggiunge funzionalità di livello superiore per semplificare Lucene di lavoro, tra cui un'API RESTful per accedere alla funzionalità di indicizzazione e ricerca di Lucene.</span><span class="sxs-lookup"><span data-stu-id="ffa45-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene’s indexing and searching functionality.</span></span> <span data-ttu-id="ffa45-121">Fornisce inoltre un'infrastruttura distribuita in grado di ottenere scalabilità elevata, tolleranza di errore e disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="ffa45-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="ffa45-122">Per le più grandi applicazioni native del cloud con requisiti di ricerca complessi, elasticsearch è disponibile come servizio gestito in Azure.</span><span class="sxs-lookup"><span data-stu-id="ffa45-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="ffa45-123">Il Microsoft Azure Marketplace include modelli preconfigurati che gli sviluppatori possono usare per distribuire un cluster elasticsearch in Azure.</span><span class="sxs-lookup"><span data-stu-id="ffa45-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="ffa45-124">Dal Microsoft Azure Marketplace, gli sviluppatori possono usare modelli preconfigurati creati per distribuire rapidamente un cluster elasticsearch in Azure.</span><span class="sxs-lookup"><span data-stu-id="ffa45-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="ffa45-125">Usando l'offerta gestita da Azure, è possibile distribuire fino a 50 nodi dati, 20 nodi di coordinamento e tre nodi master dedicati.</span><span class="sxs-lookup"><span data-stu-id="ffa45-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="ffa45-126">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ffa45-126">Summary</span></span>

<span data-ttu-id="ffa45-127">Questo capitolo presenta una descrizione dettagliata dei dati nei sistemi nativi del cloud.</span><span class="sxs-lookup"><span data-stu-id="ffa45-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="ffa45-128">Abbiamo iniziato a contrastare l'archiviazione dei dati in applicazioni monolitiche con modelli di archiviazione dei dati nei sistemi nativi del cloud.</span><span class="sxs-lookup"><span data-stu-id="ffa45-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="ffa45-129">Sono stati esaminati i modelli di dati implementati nei sistemi nativi del cloud, incluse le query tra servizi, le transazioni distribuite e i modelli per gestire i sistemi con volumi elevati.</span><span class="sxs-lookup"><span data-stu-id="ffa45-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="ffa45-130">Il confronto tra SQL e i dati di NoSQL è stato diverso.</span><span class="sxs-lookup"><span data-stu-id="ffa45-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="ffa45-131">Sono state esaminate le opzioni di archiviazione dei dati disponibili in Azure che includono opzioni sia incentrate su Microsoft che Open Source.</span><span class="sxs-lookup"><span data-stu-id="ffa45-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="ffa45-132">Infine, è stato illustrato come memorizzare nella cache e elasticsearch in un'applicazione nativa del cloud.</span><span class="sxs-lookup"><span data-stu-id="ffa45-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="ffa45-133">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ffa45-133">References</span></span>

- [<span data-ttu-id="ffa45-134">Modello di separazione di responsabilità per query e comandi (CQRS)</span><span class="sxs-lookup"><span data-stu-id="ffa45-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="ffa45-135">Modello di origine eventi</span><span class="sxs-lookup"><span data-stu-id="ffa45-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="ffa45-136">Database RDBMSs vs. NoSQL: Panoramica</span><span class="sxs-lookup"><span data-stu-id="ffa45-136">RDBMSs vs. NoSQL Databases: Overview</span></span>](https://maxivak.com/rdbms-vs-nosql-databases/)

- [<span data-ttu-id="ffa45-137">Perché il teorema della divisione RDBMS non è tollerante nel teorema delle estremità e perché è disponibile?</span><span class="sxs-lookup"><span data-stu-id="ffa45-137">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="ffa45-138">Vista materializzata</span><span class="sxs-lookup"><span data-stu-id="ffa45-138">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="ffa45-139">È sufficiente conoscere i database open source</span><span class="sxs-lookup"><span data-stu-id="ffa45-139">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="ffa45-140">Modello di transazioni di compensazione</span><span class="sxs-lookup"><span data-stu-id="ffa45-140">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="ffa45-141">Modello saga</span><span class="sxs-lookup"><span data-stu-id="ffa45-141">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="ffa45-142">Modelli saga | Come implementare transazioni aziendali con microservizi</span><span class="sxs-lookup"><span data-stu-id="ffa45-142">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="ffa45-143">Modello di transazioni di compensazione</span><span class="sxs-lookup"><span data-stu-id="ffa45-143">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="ffa45-144">Come ottenere dietro la 9-palla: Cosmos DB livelli di coerenza descritti</span><span class="sxs-lookup"><span data-stu-id="ffa45-144">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="ffa45-145">Esplorazione dei diversi tipi di database NoSQL parte II</span><span class="sxs-lookup"><span data-stu-id="ffa45-145">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="ffa45-146">Nei database RDBMS, NoSQL e NewSQL. Intervista con John Ryan</span><span class="sxs-lookup"><span data-stu-id="ffa45-146">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="ffa45-147">SQL vs NoSQL vs NewSQL: confronto completo</span><span class="sxs-lookup"><span data-stu-id="ffa45-147">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="ffa45-148">DASH: quattro proprietà di Kubernetes-database nativi</span><span class="sxs-lookup"><span data-stu-id="ffa45-148">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="ffa45-149">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="ffa45-149">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="ffa45-150">TiDB</span><span class="sxs-lookup"><span data-stu-id="ffa45-150">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="ffa45-151">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="ffa45-151">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="ffa45-152">Vite</span><span class="sxs-lookup"><span data-stu-id="ffa45-152">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="ffa45-153">Elasticsearch: Guida definitiva</span><span class="sxs-lookup"><span data-stu-id="ffa45-153">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="ffa45-154">Introduzione ad Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="ffa45-154">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="ffa45-155">[Precedente](azure-caching.md)
>[Successivo](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="ffa45-155">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
