---
title: Panoramica degli strumenti di diagnostica -.NET Core
description: Panoramica degli strumenti e delle tecniche disponibili per la diagnosi delle applicazioni .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.date: 12/17/2019
ms.topic: overview
ms.openlocfilehash: 20374c53769bf19901b042e0909175718665b523
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341485"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="281bc-103">Quali strumenti di diagnostica sono disponibili in .NET Core?</span><span class="sxs-lookup"><span data-stu-id="281bc-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="281bc-104">Il software non sempre si comporta come previsto, ma .NET Core offre strumenti e API utili per diagnosticare questi problemi in modo rapido ed efficace.</span><span class="sxs-lookup"><span data-stu-id="281bc-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="281bc-105">Questo articolo consente di trovare i vari strumenti necessari.</span><span class="sxs-lookup"><span data-stu-id="281bc-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="281bc-106">Debugger gestiti</span><span class="sxs-lookup"><span data-stu-id="281bc-106">Managed debuggers</span></span>

<span data-ttu-id="281bc-107">I [debugger gestiti](managed-debuggers.md) consentono di interagire con il programma.</span><span class="sxs-lookup"><span data-stu-id="281bc-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="281bc-108">La sospensione, l'esecuzione incrementale, l'analisi e la ripresa forniscono informazioni approfondite sul comportamento del codice.</span><span class="sxs-lookup"><span data-stu-id="281bc-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="281bc-109">Un debugger è la prima scelta per la diagnosi dei problemi funzionali che possono essere facilmente riprodotti.</span><span class="sxs-lookup"><span data-stu-id="281bc-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="281bc-110">Registrazione e traccia</span><span class="sxs-lookup"><span data-stu-id="281bc-110">Logging and tracing</span></span>

<span data-ttu-id="281bc-111">La [registrazione e la traccia](logging-tracing.md) sono tecniche correlate.</span><span class="sxs-lookup"><span data-stu-id="281bc-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="281bc-112">Si riferiscono all'instrumentazione del codice per creare file di log.</span><span class="sxs-lookup"><span data-stu-id="281bc-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="281bc-113">I file registrano i dettagli delle operazioni eseguite da un programma.</span><span class="sxs-lookup"><span data-stu-id="281bc-113">The files record the details of what a program does.</span></span> <span data-ttu-id="281bc-114">Questi dettagli possono essere usati per diagnosticare i problemi più complessi.</span><span class="sxs-lookup"><span data-stu-id="281bc-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="281bc-115">In combinazione con i timestamp, queste tecniche sono utili anche per le analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="281bc-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="281bc-116">Unit test</span><span class="sxs-lookup"><span data-stu-id="281bc-116">Unit testing</span></span>

<span data-ttu-id="281bc-117">[Unit test](../testing/index.md) è un componente chiave dell'integrazione continua e della distribuzione di software di alta qualità.</span><span class="sxs-lookup"><span data-stu-id="281bc-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="281bc-118">Gli unit test sono progettati per offrire avvisi in anticipo in caso di problemi funzionali.</span><span class="sxs-lookup"><span data-stu-id="281bc-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="281bc-119">Strumenti globali di diagnostica DotNet di .NET Core</span><span class="sxs-lookup"><span data-stu-id="281bc-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="281bc-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="281bc-120">dotnet-counters</span></span>

<span data-ttu-id="281bc-121">[DotNet-Counters](dotnet-counters.md) è uno strumento di monitoraggio delle prestazioni per il monitoraggio dell'integrità di primo livello e l'analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="281bc-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="281bc-122">Osserva i valori dei contatori delle prestazioni pubblicati tramite l'API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="281bc-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="281bc-123">Ad esempio, è possibile monitorare rapidamente elementi come l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="281bc-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="281bc-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="281bc-124">dotnet-dump</span></span>

<span data-ttu-id="281bc-125">Lo strumento [DotNet-dump](dotnet-dump.md) consente di raccogliere e analizzare i dump di base di Windows e Linux senza un debugger nativo.</span><span class="sxs-lookup"><span data-stu-id="281bc-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="281bc-126">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="281bc-126">dotnet-trace</span></span>

<span data-ttu-id="281bc-127">.NET Core include il cosiddetto `EventPipe` tramite cui vengono esposti i dati di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="281bc-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="281bc-128">Lo strumento [DotNet-Trace](dotnet-trace.md) consente di usare i dati di profilatura interessanti dall'app che possono risultare utili negli scenari in cui è necessario causare la lentezza delle app.</span><span class="sxs-lookup"><span data-stu-id="281bc-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="281bc-129">Esercitazioni di diagnostica .NET Core</span><span class="sxs-lookup"><span data-stu-id="281bc-129">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="281bc-130">Debug di una perdita di memoria</span><span class="sxs-lookup"><span data-stu-id="281bc-130">Debug a memory leak</span></span>

<span data-ttu-id="281bc-131">[Esercitazione: eseguire il debug di una perdita di memoria](debug-memory-leak.md) per trovare una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="281bc-131">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="281bc-132">Lo strumento [DotNet-counts](dotnet-counters.md) viene usato per confermare la perdita e lo strumento [DotNet-dump](dotnet-dump.md) viene usato per diagnosticare la perdita.</span><span class="sxs-lookup"><span data-stu-id="281bc-132">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>
