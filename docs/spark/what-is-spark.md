---
title: Che cos'è Apache Spark?
description: Scopri di più sugli scenari di Apache Spark e Big Data.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458171"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="798b5-103">Che cos'è Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="798b5-103">What is Apache Spark?</span></span>

<span data-ttu-id="798b5-104">[Apache Spark](https://spark.apache.org/) è un framework di elaborazione parallela open source che supporta l'elaborazione in memoria per migliorare le prestazioni delle applicazioni che analizzano i Big Data.</span><span class="sxs-lookup"><span data-stu-id="798b5-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="798b5-105">Le soluzioni Big Data sono progettate per gestire dati troppo grandi o complessi per i database tradizionali.</span><span class="sxs-lookup"><span data-stu-id="798b5-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="798b5-106">Spark elabora grandi quantità di dati in memoria, il che è molto più veloce rispetto alle alternative basate su disco.</span><span class="sxs-lookup"><span data-stu-id="798b5-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span>

## <a name="common-big-data-scenarios"></a><span data-ttu-id="798b5-107">Scenari comuni di Big Data</span><span class="sxs-lookup"><span data-stu-id="798b5-107">Common big data scenarios</span></span>

<span data-ttu-id="798b5-108">È possibile prendere in considerazione un'architettura Big Data se è necessario archiviare ed elaborare grandi volumi di dati, trasformare dati non strutturati o elaborare i dati in streaming.</span><span class="sxs-lookup"><span data-stu-id="798b5-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="798b5-109">Spark è un motore di elaborazione distribuito generico che può essere utilizzato per diversi scenari di Big Data.Spark is a general-purpose distributed processing engine that can be used for several Big Data scenarios.</span><span class="sxs-lookup"><span data-stu-id="798b5-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span>

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="798b5-110">ETL (Extract, Transform, and Load)</span><span class="sxs-lookup"><span data-stu-id="798b5-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="798b5-111">[Estrai, trasforma e carica (ETL)](/azure/architecture/data-guide/relational-data/etl) è il processo di raccolta di dati da una o più origini, la modifica dei dati e lo spostamento dei dati in un nuovo archivio dati.</span><span class="sxs-lookup"><span data-stu-id="798b5-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="798b5-112">Esistono diversi modi per trasformare i dati, tra cui:There are several ways to transform data, including:</span><span class="sxs-lookup"><span data-stu-id="798b5-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="798b5-113">Filtri</span><span class="sxs-lookup"><span data-stu-id="798b5-113">Filtering</span></span>
* <span data-ttu-id="798b5-114">Ordinamento</span><span class="sxs-lookup"><span data-stu-id="798b5-114">Sorting</span></span>
* <span data-ttu-id="798b5-115">Aggregazione</span><span class="sxs-lookup"><span data-stu-id="798b5-115">Aggregating</span></span>
* <span data-ttu-id="798b5-116">Aggiunta</span><span class="sxs-lookup"><span data-stu-id="798b5-116">Joining</span></span>
* <span data-ttu-id="798b5-117">Pulizia</span><span class="sxs-lookup"><span data-stu-id="798b5-117">Cleaning</span></span>
* <span data-ttu-id="798b5-118">Deduplicazione</span><span class="sxs-lookup"><span data-stu-id="798b5-118">Deduplicating</span></span>
* <span data-ttu-id="798b5-119">Convalida in corso.</span><span class="sxs-lookup"><span data-stu-id="798b5-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="798b5-120">Elaborazione del flusso di dati in tempo reale</span><span class="sxs-lookup"><span data-stu-id="798b5-120">Real-time data stream processing</span></span>

<span data-ttu-id="798b5-121">Lo streaming, o dati in tempo reale, sono dati in movimento.</span><span class="sxs-lookup"><span data-stu-id="798b5-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="798b5-122">La telemetria da dispositivi IoT, weblog e clickstream sono tutti esempi di dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="798b5-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="798b5-123">I dati in tempo reale possono essere elaborati per fornire informazioni utili, come l'analisi geospaziale, il monitoraggio remoto e il rilevamento delle anomalie.</span><span class="sxs-lookup"><span data-stu-id="798b5-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="798b5-124">Analogamente ai dati relazionali, è possibile filtrare, aggregare e preparare i dati in streaming prima di spostare i dati in un sink di output.</span><span class="sxs-lookup"><span data-stu-id="798b5-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="798b5-125">Apache Spark supporta [l'elaborazione](/azure/architecture/data-guide/big-data/real-time-processing) del flusso di dati in tempo reale tramite [Spark Streaming](https://spark.apache.org/streaming/).</span><span class="sxs-lookup"><span data-stu-id="798b5-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span>

### <a name="batch-processing"></a><span data-ttu-id="798b5-126">Elaborazione batch</span><span class="sxs-lookup"><span data-stu-id="798b5-126">Batch processing</span></span>

<span data-ttu-id="798b5-127">[L'elaborazione batch](/azure/architecture/data-guide/big-data/batch-processing) è l'elaborazione dei Big Data inattivi.</span><span class="sxs-lookup"><span data-stu-id="798b5-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="798b5-128">È possibile filtrare, aggregare e preparare set di dati di grandi dimensioni usando processi a esecuzione prolungata in parallelo.</span><span class="sxs-lookup"><span data-stu-id="798b5-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="798b5-129">Apprendimento automatico tramite MLlib</span><span class="sxs-lookup"><span data-stu-id="798b5-129">Machine learning through MLlib</span></span>

<span data-ttu-id="798b5-130">L'apprendimento automatico viene utilizzato per problemi analitici avanzati.</span><span class="sxs-lookup"><span data-stu-id="798b5-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="798b5-131">Il computer può utilizzare i dati esistenti per prevedere o prevedere comportamenti, risultati e tendenze futuri.</span><span class="sxs-lookup"><span data-stu-id="798b5-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="798b5-132">La libreria di apprendimento automatico di Apache Spark, [MLlib](https://spark.apache.org/mllib/), contiene diversi algoritmi e utilità di apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="798b5-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="798b5-133">Elaborazione grafica tramite GraphX</span><span class="sxs-lookup"><span data-stu-id="798b5-133">Graph processing through GraphX</span></span>

<span data-ttu-id="798b5-134">Un grafico è una raccolta di nodi collegati da bordi.</span><span class="sxs-lookup"><span data-stu-id="798b5-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="798b5-135">È possibile utilizzare un database grafico se si dispone di dati gerarchici o di dati con relazioni interconnesse.</span><span class="sxs-lookup"><span data-stu-id="798b5-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="798b5-136">È possibile elaborare questi dati utilizzando l'API GraphX di Apache Spark.You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span><span class="sxs-lookup"><span data-stu-id="798b5-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="798b5-137">Elaborazione di dati SQL e strutturati con Spark SQL</span><span class="sxs-lookup"><span data-stu-id="798b5-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="798b5-138">Se si utilizzano dati strutturati (formattati), è possibile utilizzare query SQL nell'applicazione Spark utilizzando [Spark SQL](https://spark.apache.org/sql/).</span><span class="sxs-lookup"><span data-stu-id="798b5-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="798b5-139">Architettura Apache Spark</span><span class="sxs-lookup"><span data-stu-id="798b5-139">Apache Spark architecture</span></span>

<span data-ttu-id="798b5-140">Apache Spark, che utilizza l'architettura master/worker, include tre componenti principali: il driver, gli esecutori e il gestore cluster.</span><span class="sxs-lookup"><span data-stu-id="798b5-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Architettura Apache Spark](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="798b5-142">Driver</span><span class="sxs-lookup"><span data-stu-id="798b5-142">Driver</span></span>

<span data-ttu-id="798b5-143">Il driver è costituito da un programma, ad esempio un'app console di C, e una sessione Spark.The driver consists of your program, like a C' console app, and a Spark session.</span><span class="sxs-lookup"><span data-stu-id="798b5-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="798b5-144">La sessione Spark prende il programma e lo divide in attività più piccole gestite dagli esecutori.</span><span class="sxs-lookup"><span data-stu-id="798b5-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="798b5-145">Executors</span><span class="sxs-lookup"><span data-stu-id="798b5-145">Executors</span></span>

<span data-ttu-id="798b5-146">Ogni esecutore, o nodo di lavoro, riceve un'attività dal driver ed esegue tale attività.</span><span class="sxs-lookup"><span data-stu-id="798b5-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="798b5-147">Gli esecutori risiedono in un'entità nota come cluster.</span><span class="sxs-lookup"><span data-stu-id="798b5-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="798b5-148">Gestione cluster</span><span class="sxs-lookup"><span data-stu-id="798b5-148">Cluster manager</span></span>

<span data-ttu-id="798b5-149">Il gestore cluster comunica con il driver e gli esecutori per:</span><span class="sxs-lookup"><span data-stu-id="798b5-149">The cluster manager communicates with both the driver and the executors to:</span></span>

* <span data-ttu-id="798b5-150">Gestire l'allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="798b5-150">Manage resource allocation</span></span>
* <span data-ttu-id="798b5-151">Gestire la divisione dei programmi</span><span class="sxs-lookup"><span data-stu-id="798b5-151">Manage program division</span></span>
* <span data-ttu-id="798b5-152">Gestire l'esecuzione del programma</span><span class="sxs-lookup"><span data-stu-id="798b5-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="798b5-153">Lingue supportate</span><span class="sxs-lookup"><span data-stu-id="798b5-153">Language support</span></span>

<span data-ttu-id="798b5-154">Apache Spark supporta i seguenti linguaggi di programmazione:</span><span class="sxs-lookup"><span data-stu-id="798b5-154">Apache Spark supports the following programming languages:</span></span>

* <span data-ttu-id="798b5-155">Scala</span><span class="sxs-lookup"><span data-stu-id="798b5-155">Scala</span></span>
* <span data-ttu-id="798b5-156">Python</span><span class="sxs-lookup"><span data-stu-id="798b5-156">Python</span></span>
* <span data-ttu-id="798b5-157">Java</span><span class="sxs-lookup"><span data-stu-id="798b5-157">Java</span></span>
* <span data-ttu-id="798b5-158">SQL</span><span class="sxs-lookup"><span data-stu-id="798b5-158">SQL</span></span>
* <span data-ttu-id="798b5-159">R</span><span class="sxs-lookup"><span data-stu-id="798b5-159">R</span></span>
* <span data-ttu-id="798b5-160">.NET</span><span class="sxs-lookup"><span data-stu-id="798b5-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="798b5-161">API Spark</span><span class="sxs-lookup"><span data-stu-id="798b5-161">Spark APIs</span></span>

<span data-ttu-id="798b5-162">Apache Spark supporta le seguenti API:</span><span class="sxs-lookup"><span data-stu-id="798b5-162">Apache Spark supports the following APIs:</span></span>

* [<span data-ttu-id="798b5-163">Spark Scala API</span><span class="sxs-lookup"><span data-stu-id="798b5-163">Spark Scala API</span></span>](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [<span data-ttu-id="798b5-164">Spark Java API</span><span class="sxs-lookup"><span data-stu-id="798b5-164">Spark Java API</span></span>](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [<span data-ttu-id="798b5-165">Spark Python API</span><span class="sxs-lookup"><span data-stu-id="798b5-165">Spark Python API</span></span>](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [<span data-ttu-id="798b5-166">Spark R API</span><span class="sxs-lookup"><span data-stu-id="798b5-166">Spark R API</span></span>](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* <span data-ttu-id="798b5-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), funzioni incorporate</span><span class="sxs-lookup"><span data-stu-id="798b5-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="798b5-168">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="798b5-168">Next steps</span></span>

<span data-ttu-id="798b5-169">Informazioni su come usare Apache Spark nell'applicazione .NET.</span><span class="sxs-lookup"><span data-stu-id="798b5-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="798b5-170">Con .NET per Apache Spark, gli sviluppatori con esperienza .NET e logica di business possono scrivere query Di Big Data in C e F.</span><span class="sxs-lookup"><span data-stu-id="798b5-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="798b5-171">Che cos'è .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="798b5-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)
