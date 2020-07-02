---
title: Che cos'è .NET per Apache Spark?
description: Informazioni su .NET per Apache Spark, un framework gratuito, open source e multipiattaforma per analisi di Big Data che consente di usare Spark ovunque si scriva codice .NET.
author: mamccrea
ms.topic: overview
ms.date: 06/25/2020
ms.openlocfilehash: 2c04861dabe604b52df583cd5a7eecc5ff8e5481
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621860"
---
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="398a0-103">Che cos'è .NET per Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="398a0-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="398a0-104">[Apache Spark](what-is-spark.md) è un motore di elaborazione distribuito per utilizzo generico per l'analisi su set di dati di grandi dimensioni, in genere terabyte o petabyte di dati.</span><span class="sxs-lookup"><span data-stu-id="398a0-104">[Apache Spark](what-is-spark.md) is a general-purpose distributed processing engine for analytics over large data sets - typically terabytes or petabytes of data.</span></span> <span data-ttu-id="398a0-105">Con .NET per Apache Spark, il supporto .NET gratuito, open source e multipiattaforma per il diffuso Framework open source Big Data Analytics, è ora possibile aggiungere la potenza di Apache Spark alle applicazioni Big Data usando i linguaggi che già conosci.</span><span class="sxs-lookup"><span data-stu-id="398a0-105">With .NET for Apache Spark, the free, open-source, and cross-platform .NET Support for the popular open-source big data analytics framework, you can now add the power of Apache Spark to your big data applications using languages you already know.</span></span>

[!INCLUDE [spark-preview-note](../../includes/spark-preview-note.md)]

## <a name="why-choose-net-for-apache-spark"></a><span data-ttu-id="398a0-106">Perché scegliere .NET per Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="398a0-106">Why choose .NET for Apache Spark?</span></span>

<span data-ttu-id="398a0-107">.NET per Apache Spark consente agli sviluppatori con esperienza .NET o codebase di partecipare al mondo di Big Data Analytics.</span><span class="sxs-lookup"><span data-stu-id="398a0-107">.NET for Apache Spark empowers developers with .NET experience or code bases to participate in the world of big data analytics.</span></span> <span data-ttu-id="398a0-108">.NET per Apache Spark fornisce API ad alte prestazioni per l'uso di Spark da C# e F #.</span><span class="sxs-lookup"><span data-stu-id="398a0-108">.NET for Apache Spark provides high performance APIs for using Spark from C# and F#.</span></span> <span data-ttu-id="398a0-109">Con C# e F# è possibile accedere a:</span><span class="sxs-lookup"><span data-stu-id="398a0-109">With C# and F#, you can access:</span></span>

* <span data-ttu-id="398a0-110">Dataframe e SparkSQL per l'utilizzo di dati strutturati.</span><span class="sxs-lookup"><span data-stu-id="398a0-110">DataFrame and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="398a0-111">Spark Structured Streaming per l'utilizzo di dati di streaming.</span><span class="sxs-lookup"><span data-stu-id="398a0-111">Spark Structured Streaming for working with streaming data.</span></span>
* <span data-ttu-id="398a0-112">Spark SQL per la scrittura di query con la sintassi SQL.</span><span class="sxs-lookup"><span data-stu-id="398a0-112">Spark SQL for writing queries with SQL syntax.</span></span>
* <span data-ttu-id="398a0-113">Integrazione di machine learning per la formazione e la stima più veloci, ovvero l'uso di .NET per Apache Spark insieme a [ml.NET](https://dot.net/ml).</span><span class="sxs-lookup"><span data-stu-id="398a0-113">Machine learning integration for faster training and prediction (that is, use .NET for Apache Spark alongside [ML.NET](https://dot.net/ml)).</span></span>

<span data-ttu-id="398a0-114">.NET per Apache Spark è conforme a .NET Standard, una specifica formale delle API .NET comuni tra le implementazioni di .NET.</span><span class="sxs-lookup"><span data-stu-id="398a0-114">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="398a0-115">Questo significa che è possibile usare .NET per Apache Spark ovunque si scriva codice .NET, potendo così riutilizzare tutte le conoscenze, le competenze, il codice e le librerie già disponibili come sviluppatori .NET.</span><span class="sxs-lookup"><span data-stu-id="398a0-115">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="398a0-116">.NET per Apache Spark viene eseguito in Windows, Linux e macOS con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="398a0-116">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="398a0-117">Viene eseguito anche in Windows con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="398a0-117">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="398a0-118">È possibile distribuire le applicazioni a tutti i principali provider di servizi cloud, tra cui Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks e Databricks su AWS.</span><span class="sxs-lookup"><span data-stu-id="398a0-118">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-for-apache-spark-architecture"></a><span data-ttu-id="398a0-119">.NET per architettura Apache Spark</span><span class="sxs-lookup"><span data-stu-id="398a0-119">.NET for Apache Spark architecture</span></span>

<span data-ttu-id="398a0-120">L'associazione di linguaggio C#/F # a Spark è scritta in un nuovo livello di interoperabilità Spark che offre un'estensibilità più semplice.</span><span class="sxs-lookup"><span data-stu-id="398a0-120">The C#/ F# language binding to Spark is written on a new Spark interop layer which offers easier extensibility.</span></span> <span data-ttu-id="398a0-121">Questo nuovo livello di interoperabilità Spark è stato scritto usando le procedure consigliate per l'estensione del linguaggio e ottimizza per l'interoperabilità e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="398a0-121">This new layer of Spark interop was written using the best practices for language extension and optimizes for interop and performance.</span></span> <span data-ttu-id="398a0-122">A lungo termine, questa estensibilità può essere usata per aggiungere il supporto per altri linguaggi in Spark.</span><span class="sxs-lookup"><span data-stu-id="398a0-122">Long term, this extensibility can be used for adding support for other languages in Spark.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="398a0-123">![.NET per architettura Apache Spark](media/dotnet-spark-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="398a0-123">![.NET for Apache Spark architecture](media/dotnet-spark-architecture.png)</span></span>

<span data-ttu-id="398a0-124">È possibile ottenere informazioni sul supporto di interoperabilità per [le estensioni del](https://issues.apache.org/jira/browse/SPARK-26257)linguaggio Spark dalla proposta.</span><span class="sxs-lookup"><span data-stu-id="398a0-124">You can learn about interop support for Spark language extensions from [the proposal](https://issues.apache.org/jira/browse/SPARK-26257).</span></span>

## <a name="net-for-apache-spark-performance"></a><span data-ttu-id="398a0-125">.NET per prestazioni Apache Spark</span><span class="sxs-lookup"><span data-stu-id="398a0-125">.NET for Apache Spark performance</span></span>

<span data-ttu-id="398a0-126">Quando viene confrontato con Python e scala usando il [benchmark TPC-H](http://www.tpc.org/tpch/), .net for Apache Spark viene eseguito correttamente nella maggior parte dei casi e 2x è più veloce di Python quando le prestazioni delle funzioni definite dall'utente sono critiche.</span><span class="sxs-lookup"><span data-stu-id="398a0-126">When compared against Python and Scala using the [TPC-H benchmark](http://www.tpc.org/tpch/), .NET for Apache Spark performs well in most cases and is 2x faster than Python when user-defined function performance is critical.</span></span> <span data-ttu-id="398a0-127">È possibile migliorare le prestazioni e migliorare le prestazioni del benchmark.</span><span class="sxs-lookup"><span data-stu-id="398a0-127">There is an ongoing effort to improve and benchmark performance.</span></span>

<span data-ttu-id="398a0-128">Per eseguire il benchmarking, vedere i benchmark disponibili in [.NET per Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span><span class="sxs-lookup"><span data-stu-id="398a0-128">To do your own benchmarking, see the benchmarks available on the [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span></span>

## <a name="net-for-apache-spark-roadmap"></a><span data-ttu-id="398a0-129">Guida di orientamento a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="398a0-129">.NET for Apache Spark roadmap</span></span>

<span data-ttu-id="398a0-130">Per informazioni sui piani a breve e a lungo termine, vedere la pagina [relativa a .NET ufficiale per Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span><span class="sxs-lookup"><span data-stu-id="398a0-130">Learn about short term and long term plans from the official [.NET for Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span></span>

## <a name="net-foundation"></a><span data-ttu-id="398a0-131">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="398a0-131">.NET Foundation</span></span>

<span data-ttu-id="398a0-132">Il progetto .NET per Apache Spark fa parte di [.NET Foundation.](https://www.dotnetfoundation.org/)</span><span class="sxs-lookup"><span data-stu-id="398a0-132">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="398a0-133">Contributi</span><span class="sxs-lookup"><span data-stu-id="398a0-133">Contributions</span></span>

<span data-ttu-id="398a0-134">Il team di .NET per Apache Spark incoraggia i contributi, sia sotto forma di registrazione di problemi che di richieste pull in GitHub.</span><span class="sxs-lookup"><span data-stu-id="398a0-134">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="398a0-135">Per prima cosa, cercare un [problema esistente](https://github.com/dotnet/spark/issues).</span><span class="sxs-lookup"><span data-stu-id="398a0-135">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="398a0-136">Se non si riesce a trovare un problema esistente, [aprire un nuovo problema](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span><span class="sxs-lookup"><span data-stu-id="398a0-136">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>

## <a name="next-steps"></a><span data-ttu-id="398a0-137">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="398a0-137">Next steps</span></span>

<span data-ttu-id="398a0-138">Provare .NET per Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="398a0-138">Try .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="398a0-139">Esercitazione: Introduzione a .NET per Apache Spark</span><span class="sxs-lookup"><span data-stu-id="398a0-139">Tutorial: Get started with .NET for Apache Spark</span></span>](./tutorials/get-started.md)
