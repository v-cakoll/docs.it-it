---
title: Che cos'è Apache Spark?
description: Informazioni sugli scenari Apache Spark e Big Data.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: ccf41f08df3c68a039210320f14219e6b6229a64
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72396236"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="28496-103">Che cos'è Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="28496-103">What is Apache Spark?</span></span>

<span data-ttu-id="28496-104">[Apache Spark](https://spark.apache.org/) è un Framework di elaborazione parallela open source che supporta l'elaborazione in memoria per migliorare le prestazioni delle applicazioni che analizzano Big Data.</span><span class="sxs-lookup"><span data-stu-id="28496-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="28496-105">Le soluzioni per Big data sono progettate per gestire dati troppo grandi o complessi per i database tradizionali.</span><span class="sxs-lookup"><span data-stu-id="28496-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="28496-106">Spark elabora grandi quantità di dati in memoria, il che è molto più veloce rispetto alle alternative basate su disco.</span><span class="sxs-lookup"><span data-stu-id="28496-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span> 

## <a name="common-big-data-scenarios"></a><span data-ttu-id="28496-107">Scenari comuni di Big Data</span><span class="sxs-lookup"><span data-stu-id="28496-107">Common big data scenarios</span></span>

<span data-ttu-id="28496-108">È possibile prendere in considerazione un'architettura Big Data se è necessario archiviare ed elaborare grandi volumi di dati, trasformare i dati non strutturati o elaborare dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="28496-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="28496-109">Spark è un motore di elaborazione distribuito per utilizzo generico che può essere usato per diversi scenari di Big Data.</span><span class="sxs-lookup"><span data-stu-id="28496-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span> 

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="28496-110">Estrarre, trasformare e caricare (ETL)</span><span class="sxs-lookup"><span data-stu-id="28496-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="28496-111">L' [estrazione, la trasformazione e il caricamento (ETL)](/azure/architecture/data-guide/relational-data/etl) è il processo di raccolta dei dati da una o più origini, modifica dei dati e trasferimento dei dati in un nuovo archivio dati.</span><span class="sxs-lookup"><span data-stu-id="28496-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="28496-112">Esistono diversi modi per trasformare i dati, tra cui:</span><span class="sxs-lookup"><span data-stu-id="28496-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="28496-113">Filtro</span><span class="sxs-lookup"><span data-stu-id="28496-113">Filtering</span></span>
* <span data-ttu-id="28496-114">Ordinamento</span><span class="sxs-lookup"><span data-stu-id="28496-114">Sorting</span></span>
* <span data-ttu-id="28496-115">Aggregazione</span><span class="sxs-lookup"><span data-stu-id="28496-115">Aggregating</span></span>
* <span data-ttu-id="28496-116">Uso di join</span><span class="sxs-lookup"><span data-stu-id="28496-116">Joining</span></span>
* <span data-ttu-id="28496-117">Pulizia</span><span class="sxs-lookup"><span data-stu-id="28496-117">Cleaning</span></span>
* <span data-ttu-id="28496-118">Deduplicazione</span><span class="sxs-lookup"><span data-stu-id="28496-118">Deduplicating</span></span>
* <span data-ttu-id="28496-119">Convalida</span><span class="sxs-lookup"><span data-stu-id="28496-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="28496-120">Elaborazione del flusso di dati in tempo reale</span><span class="sxs-lookup"><span data-stu-id="28496-120">Real-time data stream processing</span></span>

<span data-ttu-id="28496-121">I dati in streaming o in tempo reale sono dati in movimento.</span><span class="sxs-lookup"><span data-stu-id="28496-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="28496-122">I dati di telemetria dei dispositivi, i log e i clickstream sono tutti esempi di dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="28496-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="28496-123">I dati in tempo reale possono essere elaborati per fornire informazioni utili, ad esempio l'analisi geospaziale, il monitoraggio remoto e il rilevamento delle anomalie.</span><span class="sxs-lookup"><span data-stu-id="28496-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="28496-124">Analogamente ai dati relazionali, è possibile filtrare, aggregare e preparare i dati di streaming prima di trasferire i dati in un sink di output.</span><span class="sxs-lookup"><span data-stu-id="28496-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="28496-125">Apache Spark supporta l' [elaborazione di flussi di dati in tempo reale](/azure/architecture/data-guide/big-data/real-time-processing) tramite [Spark streaming](https://spark.apache.org/streaming/).</span><span class="sxs-lookup"><span data-stu-id="28496-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span> 

### <a name="batch-processing"></a><span data-ttu-id="28496-126">Elaborazione batch</span><span class="sxs-lookup"><span data-stu-id="28496-126">Batch processing</span></span>

<span data-ttu-id="28496-127">L' [elaborazione batch](/azure/architecture/data-guide/big-data/batch-processing) è l'elaborazione di Big Data inattivi.</span><span class="sxs-lookup"><span data-stu-id="28496-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="28496-128">È possibile filtrare, aggregare e preparare set di impostazioni di grandi dimensioni utilizzando processi con esecuzione prolungata in parallelo.</span><span class="sxs-lookup"><span data-stu-id="28496-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="28496-129">Apprendimento automatico tramite MLlib</span><span class="sxs-lookup"><span data-stu-id="28496-129">Machine learning through MLlib</span></span>

<span data-ttu-id="28496-130">Machine Learning viene usato per i problemi analitici avanzati.</span><span class="sxs-lookup"><span data-stu-id="28496-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="28496-131">Il computer può usare i dati esistenti per prevedere o prevedere comportamenti, risultati e tendenze futuri.</span><span class="sxs-lookup"><span data-stu-id="28496-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="28496-132">La libreria di Machine Learning di Apache Spark, [MLlib](https://spark.apache.org/mllib/), contiene diverse utilità e algoritmi di machine learning.</span><span class="sxs-lookup"><span data-stu-id="28496-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="28496-133">Elaborazione di grafi tramite GraphX</span><span class="sxs-lookup"><span data-stu-id="28496-133">Graph processing through GraphX</span></span>

<span data-ttu-id="28496-134">Un grafico è una raccolta di nodi collegati da bordi.</span><span class="sxs-lookup"><span data-stu-id="28496-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="28496-135">È possibile utilizzare un database Graph se si dispone di dati gerarchica o di dati con relazioni interconnesse.</span><span class="sxs-lookup"><span data-stu-id="28496-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="28496-136">È possibile elaborare questi dati usando l'API [graphx](https://spark.apache.org/graphx/) di Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="28496-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="28496-137">Elaborazione di dati strutturati e SQL con Spark SQL</span><span class="sxs-lookup"><span data-stu-id="28496-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="28496-138">Se si lavora con dati strutturati (formattati), è possibile usare le query SQL nell'applicazione Spark usando [Spark SQL](https://spark.apache.org/sql/).</span><span class="sxs-lookup"><span data-stu-id="28496-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="28496-139">Architettura Apache Spark</span><span class="sxs-lookup"><span data-stu-id="28496-139">Apache Spark architecture</span></span>

<span data-ttu-id="28496-140">Apache Spark, che utilizza l'architettura master/di lavoro, dispone di tre componenti principali: driver, Executor e gestione cluster.</span><span class="sxs-lookup"><span data-stu-id="28496-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Architettura Apache Spark](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="28496-142">Driver</span><span class="sxs-lookup"><span data-stu-id="28496-142">Driver</span></span>

<span data-ttu-id="28496-143">Il driver è costituito dal programma, ad C# esempio un'app console e una sessione di Spark.</span><span class="sxs-lookup"><span data-stu-id="28496-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="28496-144">La sessione Spark prende il programma e lo divide in attività più piccole gestite dagli esecutori.</span><span class="sxs-lookup"><span data-stu-id="28496-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="28496-145">Esecutori</span><span class="sxs-lookup"><span data-stu-id="28496-145">Executors</span></span>

<span data-ttu-id="28496-146">Ogni Executor, o nodo di lavoro, riceve un'attività dal driver ed esegue tale attività.</span><span class="sxs-lookup"><span data-stu-id="28496-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="28496-147">Gli executor si trovano in un'entità nota come cluster.</span><span class="sxs-lookup"><span data-stu-id="28496-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="28496-148">Gestione cluster</span><span class="sxs-lookup"><span data-stu-id="28496-148">Cluster manager</span></span>

<span data-ttu-id="28496-149">Gestione cluster comunica con il driver e gli Executor per:</span><span class="sxs-lookup"><span data-stu-id="28496-149">The cluster manager communicates with both the driver and the executors to:</span></span>

- <span data-ttu-id="28496-150">Gestisci allocazione risorse</span><span class="sxs-lookup"><span data-stu-id="28496-150">Manage resource allocation</span></span>
- <span data-ttu-id="28496-151">Gestisci divisione programmi</span><span class="sxs-lookup"><span data-stu-id="28496-151">Manage program division</span></span>
- <span data-ttu-id="28496-152">Gestire l'esecuzione del programma</span><span class="sxs-lookup"><span data-stu-id="28496-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="28496-153">Supporto delle lingue</span><span class="sxs-lookup"><span data-stu-id="28496-153">Language support</span></span>

<span data-ttu-id="28496-154">Apache Spark supporta i linguaggi di programmazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="28496-154">Apache Spark supports the following programming languages:</span></span>

- <span data-ttu-id="28496-155">Scala</span><span class="sxs-lookup"><span data-stu-id="28496-155">Scala</span></span>
- <span data-ttu-id="28496-156">Python</span><span class="sxs-lookup"><span data-stu-id="28496-156">Python</span></span>
- <span data-ttu-id="28496-157">Java</span><span class="sxs-lookup"><span data-stu-id="28496-157">Java</span></span>
- <span data-ttu-id="28496-158">SQL</span><span class="sxs-lookup"><span data-stu-id="28496-158">SQL</span></span>
- <span data-ttu-id="28496-159">V</span><span class="sxs-lookup"><span data-stu-id="28496-159">R</span></span>
- <span data-ttu-id="28496-160">.NET</span><span class="sxs-lookup"><span data-stu-id="28496-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="28496-161">API Spark</span><span class="sxs-lookup"><span data-stu-id="28496-161">Spark APIs</span></span>

<span data-ttu-id="28496-162">Apache Spark supporta le API seguenti:</span><span class="sxs-lookup"><span data-stu-id="28496-162">Apache Spark supports the following APIs:</span></span>

- [<span data-ttu-id="28496-163">API Spark scala</span><span class="sxs-lookup"><span data-stu-id="28496-163">Spark Scala API</span></span>](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
- [<span data-ttu-id="28496-164">API Java Spark</span><span class="sxs-lookup"><span data-stu-id="28496-164">Spark Java API</span></span>](https://spark.apache.org/docs/2.2.0/api/java/index.html)
- [<span data-ttu-id="28496-165">API Python Spark</span><span class="sxs-lookup"><span data-stu-id="28496-165">Spark Python API</span></span>](https://spark.apache.org/docs/2.2.0/api/python/index.html)
- [<span data-ttu-id="28496-166">API R Spark</span><span class="sxs-lookup"><span data-stu-id="28496-166">Spark R API</span></span>](https://spark.apache.org/docs/2.2.0/api/R/index.html)
- <span data-ttu-id="28496-167">Funzioni predefinite di [Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html)</span><span class="sxs-lookup"><span data-stu-id="28496-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="28496-168">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="28496-168">Next steps</span></span>

<span data-ttu-id="28496-169">Informazioni su come usare Apache Spark nell'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="28496-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="28496-170">Con .NET per Apache Spark, gli sviluppatori con esperienza .NET e la logica di business possono scrivere C# Big data F#query in e.</span><span class="sxs-lookup"><span data-stu-id="28496-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="28496-171">Informazioni su .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="28496-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)
