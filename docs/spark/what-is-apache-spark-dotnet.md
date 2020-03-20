---
title: Che cos'è .NET per Apache Spark?
description: Informazioni su .NET per Apache Spark, un framework gratuito, open source e multipiattaforma per analisi di Big Data che consente di usare Spark ovunque si scriva codice .NET.
author: mamccrea
ms.topic: overview
ms.date: 10/15/2019
ms.openlocfilehash: 12fccd478cedaccf455043feb3afa7b12221bf0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458197"
---
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="d2786-103">Che cos'è .NET per Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="d2786-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="d2786-104">[Apache Spark](what-is-spark.md) è un motore di elaborazione distribuito generico per l'analisi su set di dati di grandi dimensioni, in genere terabyte o petabyte di dati.</span><span class="sxs-lookup"><span data-stu-id="d2786-104">[Apache Spark](what-is-spark.md) is a general-purpose distributed processing engine for analytics over large data sets - typically terabytes or petabytes of data.</span></span> <span data-ttu-id="d2786-105">Con .NET per Apache Spark, il supporto gratuito, open source e multipiattaforma .NET per il popolare framework di analisi dei Big Data open source, è ora possibile aggiungere la potenza di Apache Spark alle applicazioni Big Data utilizzando linguaggi già conosciuti.</span><span class="sxs-lookup"><span data-stu-id="d2786-105">With .NET for Apache Spark, the free, open-source, and cross-platform .NET Support for the popular open-source big data analytics framework, you can now add the power of Apache Spark to your big data applications using languages you already know.</span></span>

## <a name="why-choose-net-for-apache-spark"></a><span data-ttu-id="d2786-106">Perché scegliere .NET per Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="d2786-106">Why choose .NET for Apache Spark?</span></span>

<span data-ttu-id="d2786-107">.NET per Apache Spark consente agli sviluppatori di esperienza .NET o basi di codice per partecipare al mondo dell'analisi dei Big Data.</span><span class="sxs-lookup"><span data-stu-id="d2786-107">.NET for Apache Spark empowers developers with .NET experience or code bases to participate in the world of big data analytics.</span></span> <span data-ttu-id="d2786-108">.NET per Apache Spark offre API ad alte prestazioni per l'utilizzo di Spark da C e F.</span><span class="sxs-lookup"><span data-stu-id="d2786-108">.NET for Apache Spark provides high performance APIs for using Spark from C# and F#.</span></span> <span data-ttu-id="d2786-109">Con C# e F# è possibile accedere a:</span><span class="sxs-lookup"><span data-stu-id="d2786-109">With C# and F#, you can access:</span></span>

* <span data-ttu-id="d2786-110">DataFrame e SparkSQL per l'utilizzo di dati strutturati.</span><span class="sxs-lookup"><span data-stu-id="d2786-110">DataFrame and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="d2786-111">Spark Structured Streaming per l'utilizzo di dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="d2786-111">Spark Structured Streaming for working with streaming data.</span></span>
* <span data-ttu-id="d2786-112">Spark SQL per la scrittura di query con sintassi SQL.</span><span class="sxs-lookup"><span data-stu-id="d2786-112">Spark SQL for writing queries with SQL syntax.</span></span>
* <span data-ttu-id="d2786-113">Integrazione di Machine Learning per una formazione e una stima più veloci, ovvero usare .NET per Apache Spark insieme [a ML.NET](https://dot.net/ml)).</span><span class="sxs-lookup"><span data-stu-id="d2786-113">Machine learning integration for faster training and prediction (that is, use .NET for Apache Spark alongside [ML.NET](https://dot.net/ml)).</span></span>

<span data-ttu-id="d2786-114">.NET per Apache Spark è conforme a .NET Standard, una specifica formale delle API .NET comuni tra le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="d2786-114">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="d2786-115">Questo significa che è possibile usare .NET per Apache Spark ovunque si scriva codice .NET, potendo così riutilizzare tutte le conoscenze, le competenze, il codice e le librerie già disponibili come sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="d2786-115">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="d2786-116">.NET per Apache Spark viene eseguito in Windows, Linux e macOS con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d2786-116">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="d2786-117">Viene eseguito anche in Windows con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2786-117">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="d2786-118">È possibile distribuire le applicazioni a tutti i principali provider di servizi cloud, tra cui Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks e Databricks su AWS.</span><span class="sxs-lookup"><span data-stu-id="d2786-118">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-for-apache-spark-architecture"></a><span data-ttu-id="d2786-119">.NET per l'architettura Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d2786-119">.NET for Apache Spark architecture</span></span>

<span data-ttu-id="d2786-120">L'associazione del linguaggio C / F a Spark viene scritta in un nuovo livello di interoperabilità Spark che offre una maggiore estendibilità.</span><span class="sxs-lookup"><span data-stu-id="d2786-120">The C#/ F# language binding to Spark is written on a new Spark interop layer which offers easier extensibility.</span></span> <span data-ttu-id="d2786-121">Questo nuovo livello di interoperabilità Spark è stato scritto utilizzando le procedure consigliate per l'estensione del linguaggio e ottimizza per l'interoperabilità e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d2786-121">This new layer of Spark interop was written using the best practices for language extension and optimizes for interop and performance.</span></span> <span data-ttu-id="d2786-122">A lungo termine, questa estendibilità può essere utilizzata per aggiungere il supporto per altre lingue in Spark.</span><span class="sxs-lookup"><span data-stu-id="d2786-122">Long term, this extensibility can be used for adding support for other languages in Spark.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d2786-123">![.NET per l'architettura Apache Spark](media/dotnet-spark-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="d2786-123">![.NET for Apache Spark architecture](media/dotnet-spark-architecture.png)</span></span>

<span data-ttu-id="d2786-124">Per informazioni sul supporto dell'interoperabilità per le estensioni del linguaggio [Spark, vedere la proposta](https://issues.apache.org/jira/browse/SPARK-26257).</span><span class="sxs-lookup"><span data-stu-id="d2786-124">You can learn about interop support for Spark language extensions from [the proposal](https://issues.apache.org/jira/browse/SPARK-26257).</span></span>

## <a name="net-for-apache-spark-performance"></a><span data-ttu-id="d2786-125">.NET per prestazioni di Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d2786-125">.NET for Apache Spark performance</span></span>

<span data-ttu-id="d2786-126">Rispetto a Python e Scala che utilizzano il [benchmark TPC-H](http://www.tpc.org/tpch/), .NET per Apache Spark funziona bene nella maggior parte dei casi ed è 2 volte più veloce di Python quando le prestazioni delle funzioni definite dall'utente sono critiche.</span><span class="sxs-lookup"><span data-stu-id="d2786-126">When compared against Python and Scala using the [TPC-H benchmark](http://www.tpc.org/tpch/), .NET for Apache Spark performs well in most cases and is 2x faster than Python when user-defined function performance is critical.</span></span> <span data-ttu-id="d2786-127">C'è uno sforzo continuo per migliorare e valutare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d2786-127">There is an ongoing effort to improve and benchmark performance.</span></span>

<span data-ttu-id="d2786-128">Per eseguire il benchmarking, vedere i benchmark disponibili in [.NET per Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span><span class="sxs-lookup"><span data-stu-id="d2786-128">To do your own benchmarking, see the benchmarks available on the [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span></span>

## <a name="net-for-apache-spark-roadmap"></a><span data-ttu-id="d2786-129">Guida di orientamento a .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d2786-129">.NET for Apache Spark roadmap</span></span>

<span data-ttu-id="d2786-130">Scopri i piani a breve e lungo termine dalla roadmap ufficiale [di .NET for Apache Spark](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span><span class="sxs-lookup"><span data-stu-id="d2786-130">Learn about short term and long term plans from the official [.NET for Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span></span>

## <a name="net-foundation"></a><span data-ttu-id="d2786-131">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="d2786-131">.NET Foundation</span></span>

<span data-ttu-id="d2786-132">Il progetto .NET per Apache Spark fa parte di [.NET Foundation.](https://www.dotnetfoundation.org/)</span><span class="sxs-lookup"><span data-stu-id="d2786-132">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="d2786-133">Contributi</span><span class="sxs-lookup"><span data-stu-id="d2786-133">Contributions</span></span>

<span data-ttu-id="d2786-134">Il team di .NET per Apache Spark incoraggia i contributi, sia sotto forma di registrazione di problemi che di richieste pull in GitHub.</span><span class="sxs-lookup"><span data-stu-id="d2786-134">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="d2786-135">Per prima cosa, cercare un [problema esistente](https://github.com/dotnet/spark/issues).</span><span class="sxs-lookup"><span data-stu-id="d2786-135">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="d2786-136">Se non si riesce a trovare un problema esistente, [aprire un nuovo problema](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span><span class="sxs-lookup"><span data-stu-id="d2786-136">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2786-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d2786-137">Next steps</span></span>

<span data-ttu-id="d2786-138">Prova .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="d2786-138">Try .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d2786-139">Esercitazione: Introduzione a .NET per Apache SparkTutorial: Get started with .NET for Apache Spark</span><span class="sxs-lookup"><span data-stu-id="d2786-139">Tutorial: Get started with .NET for Apache Spark</span></span>](./tutorials/get-started.md)
