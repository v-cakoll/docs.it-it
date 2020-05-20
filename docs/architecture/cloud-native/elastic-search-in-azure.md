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
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="648f2-103">Elasticsearch in un'app nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="648f2-103">Elasticsearch in a cloud-native app</span></span>

<span data-ttu-id="648f2-104">Elasticsearch è un sistema di ricerca e analisi distribuito che consente funzionalità di ricerca complesse tra tipi diversi di dati.</span><span class="sxs-lookup"><span data-stu-id="648f2-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="648f2-105">È open source e molto diffuso.</span><span class="sxs-lookup"><span data-stu-id="648f2-105">It's open source and widely popular.</span></span> <span data-ttu-id="648f2-106">Considerare il modo in cui le società seguenti integrano elasticsearch nell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="648f2-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="648f2-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) per la ricerca full-text e incrementale (ricerca durante la digitazione).</span><span class="sxs-lookup"><span data-stu-id="648f2-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="648f2-108">[GitHub](https://www.elastic.co/customers/github) per indicizzare ed esporre oltre 8 milioni repository di codice.</span><span class="sxs-lookup"><span data-stu-id="648f2-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="648f2-109">[Docker](https://www.elastic.co/customers/docker) per rendere individuabile la relativa libreria di contenitori.</span><span class="sxs-lookup"><span data-stu-id="648f2-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="648f2-110">Elasticsearch si basa sul motore di ricerca full-text di [Apache Lucene](https://lucene.apache.org/core/) .</span><span class="sxs-lookup"><span data-stu-id="648f2-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="648f2-111">Lucene fornisce l'indicizzazione e l'esecuzione di query di documenti a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="648f2-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="648f2-112">Indicizza i dati con uno schema di indicizzazione invertita, anziché eseguire il mapping delle pagine alle parole chiave, esegue il mapping delle parole chiave alle pagine come un glossario alla fine di un libro.</span><span class="sxs-lookup"><span data-stu-id="648f2-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="648f2-113">Lucene dispone di potenti funzionalità di sintassi di query ed è in grado di eseguire query sui dati:</span><span class="sxs-lookup"><span data-stu-id="648f2-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="648f2-114">Termine (parola completa)</span><span class="sxs-lookup"><span data-stu-id="648f2-114">Term (a full word)</span></span>
- <span data-ttu-id="648f2-115">Prefix (inizia con Word)</span><span class="sxs-lookup"><span data-stu-id="648f2-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="648f2-116">Carattere jolly (con i \* filtri "" o "?")</span><span class="sxs-lookup"><span data-stu-id="648f2-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="648f2-117">Frase (sequenza di testo in un documento)</span><span class="sxs-lookup"><span data-stu-id="648f2-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="648f2-118">Valore booleano (ricerche complesse che combinano query)</span><span class="sxs-lookup"><span data-stu-id="648f2-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="648f2-119">Anche se Lucene fornisce plumbing di basso livello per la ricerca, elasticsearch fornisce il server che si trova sopra Lucene.</span><span class="sxs-lookup"><span data-stu-id="648f2-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="648f2-120">Elasticsearch aggiunge funzionalità di livello superiore per semplificare Lucene di lavoro, tra cui un'API RESTful per accedere alla funzionalità di indicizzazione e ricerca di Lucene.</span><span class="sxs-lookup"><span data-stu-id="648f2-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="648f2-121">Fornisce inoltre un'infrastruttura distribuita in grado di ottenere scalabilità elevata, tolleranza di errore e disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="648f2-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="648f2-122">Per le più grandi applicazioni native del cloud con requisiti di ricerca complessi, elasticsearch è disponibile come servizio gestito in Azure.</span><span class="sxs-lookup"><span data-stu-id="648f2-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="648f2-123">Il Microsoft Azure Marketplace include modelli preconfigurati che gli sviluppatori possono usare per distribuire un cluster elasticsearch in Azure.</span><span class="sxs-lookup"><span data-stu-id="648f2-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="648f2-124">Dal Microsoft Azure Marketplace, gli sviluppatori possono usare modelli preconfigurati creati per distribuire rapidamente un cluster elasticsearch in Azure.</span><span class="sxs-lookup"><span data-stu-id="648f2-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="648f2-125">Usando l'offerta gestita da Azure, è possibile distribuire fino a 50 nodi dati, 20 nodi di coordinamento e tre nodi master dedicati.</span><span class="sxs-lookup"><span data-stu-id="648f2-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="648f2-126">Summary</span><span class="sxs-lookup"><span data-stu-id="648f2-126">Summary</span></span>

<span data-ttu-id="648f2-127">Questo capitolo presenta una descrizione dettagliata dei dati nei sistemi nativi del cloud.</span><span class="sxs-lookup"><span data-stu-id="648f2-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="648f2-128">Abbiamo iniziato a contrastare l'archiviazione dei dati in applicazioni monolitiche con modelli di archiviazione dei dati nei sistemi nativi del cloud.</span><span class="sxs-lookup"><span data-stu-id="648f2-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="648f2-129">Sono stati esaminati i modelli di dati implementati nei sistemi nativi del cloud, incluse le query tra servizi, le transazioni distribuite e i modelli per gestire i sistemi con volumi elevati.</span><span class="sxs-lookup"><span data-stu-id="648f2-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="648f2-130">Il confronto tra SQL e i dati di NoSQL è stato diverso.</span><span class="sxs-lookup"><span data-stu-id="648f2-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="648f2-131">Sono state esaminate le opzioni di archiviazione dei dati disponibili in Azure che includono opzioni sia incentrate su Microsoft che Open Source.</span><span class="sxs-lookup"><span data-stu-id="648f2-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="648f2-132">Infine, è stato illustrato come memorizzare nella cache e elasticsearch in un'applicazione nativa del cloud.</span><span class="sxs-lookup"><span data-stu-id="648f2-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="648f2-133">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="648f2-133">References</span></span>

- [<span data-ttu-id="648f2-134">Modello di separazione di responsabilità per query e comandi (CQRS, Command and Query Responsibility Segregation)</span><span class="sxs-lookup"><span data-stu-id="648f2-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="648f2-135">Modello di origine eventi</span><span class="sxs-lookup"><span data-stu-id="648f2-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="648f2-136">Perché il teorema della divisione RDBMS non è tollerante nel teorema delle estremità e perché è disponibile?</span><span class="sxs-lookup"><span data-stu-id="648f2-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="648f2-137">Vista materializzata</span><span class="sxs-lookup"><span data-stu-id="648f2-137">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="648f2-138">È sufficiente conoscere i database open source</span><span class="sxs-lookup"><span data-stu-id="648f2-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="648f2-139">Modello di transazioni di compensazione</span><span class="sxs-lookup"><span data-stu-id="648f2-139">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="648f2-140">Modello saga</span><span class="sxs-lookup"><span data-stu-id="648f2-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="648f2-141">Modelli saga | Come implementare transazioni aziendali con microservizi</span><span class="sxs-lookup"><span data-stu-id="648f2-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="648f2-142">Modello di transazioni di compensazione</span><span class="sxs-lookup"><span data-stu-id="648f2-142">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="648f2-143">Come ottenere dietro la 9-palla: Cosmos DB livelli di coerenza descritti</span><span class="sxs-lookup"><span data-stu-id="648f2-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="648f2-144">Esplorazione dei diversi tipi di database NoSQL parte II</span><span class="sxs-lookup"><span data-stu-id="648f2-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="648f2-145">Nei database RDBMS, NoSQL e NewSQL. Intervista con John Ryan</span><span class="sxs-lookup"><span data-stu-id="648f2-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="648f2-146">SQL vs NoSQL vs NewSQL: confronto completo</span><span class="sxs-lookup"><span data-stu-id="648f2-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="648f2-147">DASH: quattro proprietà di Kubernetes-database nativi</span><span class="sxs-lookup"><span data-stu-id="648f2-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="648f2-148">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="648f2-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="648f2-149">TiDB</span><span class="sxs-lookup"><span data-stu-id="648f2-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="648f2-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="648f2-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="648f2-151">Vite</span><span class="sxs-lookup"><span data-stu-id="648f2-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="648f2-152">Articolo relativo alla guida completa di Elasticsearch</span><span class="sxs-lookup"><span data-stu-id="648f2-152">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="648f2-153">Introduzione ad Apache Lucene</span><span class="sxs-lookup"><span data-stu-id="648f2-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="648f2-154">[Precedente](azure-caching.md) 
> [Avanti](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="648f2-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
