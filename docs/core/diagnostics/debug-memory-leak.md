---
title: Esercitazione sul debug di una perdita di memoria
description: Informazioni su come eseguire il debug di una perdita di memoria in .NET Core.
author: sdmaclea
ms.author: stmaclea
ms.topic: tutorial
ms.date: 12/17/2019
ms.openlocfilehash: def848b5fe6f08cf32067b833bbf6a97a56edda1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75443512"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a><span data-ttu-id="d81fa-103">Esercitazione: eseguire il debug di una perdita di memoria in .NET Core</span><span class="sxs-lookup"><span data-stu-id="d81fa-103">Tutorial: Debug a memory leak in .NET Core</span></span>

<span data-ttu-id="d81fa-104">**Questo articolo si applica a: ✓** .net core 3,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="d81fa-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="d81fa-105">Questa esercitazione illustra gli strumenti per analizzare una perdita di memoria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d81fa-105">This tutorial demonstrates the tools to analyze a .NET Core memory leak.</span></span>

<span data-ttu-id="d81fa-106">Questa esercitazione usa un'app di esempio progettata per la perdita di memoria intenzionalmente.</span><span class="sxs-lookup"><span data-stu-id="d81fa-106">This tutorial uses a sample app, which is designed to intentionally leak memory.</span></span> <span data-ttu-id="d81fa-107">L'esempio viene fornito come esercizio.</span><span class="sxs-lookup"><span data-stu-id="d81fa-107">The sample is provided as an exercise.</span></span> <span data-ttu-id="d81fa-108">È possibile analizzare un'app che ha inavvertitamente una perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="d81fa-108">You can analyze an app that is unintentionally leaking memory too.</span></span>

<span data-ttu-id="d81fa-109">In questa esercitazione si eseguono le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d81fa-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="d81fa-110">Esaminare managed memory utilizzo con i [contatori DotNet](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d81fa-110">Examine managed memory usage with [dotnet-counters](dotnet-counters.md).</span></span>
> - <span data-ttu-id="d81fa-111">Genera un file dump.</span><span class="sxs-lookup"><span data-stu-id="d81fa-111">Generate a dump file.</span></span>
> - <span data-ttu-id="d81fa-112">Analizzare l'utilizzo della memoria utilizzando il file dump.</span><span class="sxs-lookup"><span data-stu-id="d81fa-112">Analyze the memory usage using the dump file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d81fa-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d81fa-113">Prerequisites</span></span>

<span data-ttu-id="d81fa-114">L'esercitazione usa:</span><span class="sxs-lookup"><span data-stu-id="d81fa-114">The tutorial uses:</span></span>

- <span data-ttu-id="d81fa-115">[.NET Core 3,0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d81fa-115">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="d81fa-116">[DotNet-Trace](dotnet-trace.md) per elencare i processi.</span><span class="sxs-lookup"><span data-stu-id="d81fa-116">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
- <span data-ttu-id="d81fa-117">[DotNet-contatori](dotnet-counters.md) per controllare l'utilizzo del managed memory.</span><span class="sxs-lookup"><span data-stu-id="d81fa-117">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
- <span data-ttu-id="d81fa-118">[DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump.</span><span class="sxs-lookup"><span data-stu-id="d81fa-118">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
- <span data-ttu-id="d81fa-119">App di [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) da diagnosticare.</span><span class="sxs-lookup"><span data-stu-id="d81fa-119">A [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) app to diagnose.</span></span>

<span data-ttu-id="d81fa-120">Nell'esercitazione si presuppone che gli strumenti e gli esempi siano installati e pronti per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d81fa-120">The tutorial assumes the sample and tools are installed and ready to use.</span></span>

## <a name="examine-managed-memory-usage"></a><span data-ttu-id="d81fa-121">Esaminare l'utilizzo di managed memory</span><span class="sxs-lookup"><span data-stu-id="d81fa-121">Examine managed memory usage</span></span>

<span data-ttu-id="d81fa-122">Prima di iniziare a raccogliere i dati di diagnostica per aiutare la radice a causa di questo scenario, è necessario assicurarsi che si stia effettivamente osservando una perdita di memoria (aumento della memoria).</span><span class="sxs-lookup"><span data-stu-id="d81fa-122">Before you start collecting diagnostics data to help us root cause this scenario, you need to make sure you're actually seeing a memory leak (memory growth).</span></span> <span data-ttu-id="d81fa-123">È possibile utilizzare lo strumento [DotNet-Counters](dotnet-counters.md) per verificare che.</span><span class="sxs-lookup"><span data-stu-id="d81fa-123">You can use the [dotnet-counters](dotnet-counters.md) tool to confirm that.</span></span>

<span data-ttu-id="d81fa-124">Aprire una finestra della console e passare alla directory in cui è stata scaricata e decompressa la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span><span class="sxs-lookup"><span data-stu-id="d81fa-124">Open a console window and navigate to the directory where you downloaded and unzipped the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/).</span></span> <span data-ttu-id="d81fa-125">Eseguire la destinazione:</span><span class="sxs-lookup"><span data-stu-id="d81fa-125">Run the target:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="d81fa-126">Da una console separata, trovare l'ID processo usando lo strumento [DotNet-Trace](dotnet-trace.md) :</span><span class="sxs-lookup"><span data-stu-id="d81fa-126">From a separate console, find the process ID using the [dotnet-trace](dotnet-trace.md) tool:</span></span>

```console
dotnet-trace ps
```

<span data-ttu-id="d81fa-127">L'output dovrebbe essere simile a:</span><span class="sxs-lookup"><span data-stu-id="d81fa-127">The output should be similar to:</span></span>

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

<span data-ttu-id="d81fa-128">A questo punto, controllare managed memory utilizzo con lo strumento [DotNet-Counters](dotnet-counters.md) .</span><span class="sxs-lookup"><span data-stu-id="d81fa-128">Now, check managed memory usage with the [dotnet-counters](dotnet-counters.md) tool.</span></span> <span data-ttu-id="d81fa-129">Il `--refresh-interval` specifica il numero di secondi tra gli aggiornamenti:</span><span class="sxs-lookup"><span data-stu-id="d81fa-129">The `--refresh-interval` specifies the number of seconds between refreshes:</span></span>

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

<span data-ttu-id="d81fa-130">L'output Live dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d81fa-130">The live output should be similar to:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

<span data-ttu-id="d81fa-131">Attenzione a questa riga:</span><span class="sxs-lookup"><span data-stu-id="d81fa-131">Focusing on this line:</span></span>

```console
    GC Heap Size (MB)                                  4
```

<span data-ttu-id="d81fa-132">È possibile osservare che la memoria heap gestita è 4 MB subito dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="d81fa-132">You can see that the managed heap memory is 4 MB right after startup.</span></span>

<span data-ttu-id="d81fa-133">A questo punto, fare clic sull'URL `http://localhost:5000/api/diagscenario/memleak/20000`.</span><span class="sxs-lookup"><span data-stu-id="d81fa-133">Now, hit the URL `http://localhost:5000/api/diagscenario/memleak/20000`.</span></span>

<span data-ttu-id="d81fa-134">Osservare che l'utilizzo della memoria è aumentato fino a 30 MB.</span><span class="sxs-lookup"><span data-stu-id="d81fa-134">Observe that the memory usage has grown to 30 MB.</span></span>

```console
    GC Heap Size (MB)                                 30
```

<span data-ttu-id="d81fa-135">Osservando l'utilizzo della memoria, è possibile tranquillamente indicare che la memoria sta crescendo o perdendo.</span><span class="sxs-lookup"><span data-stu-id="d81fa-135">By watching the memory usage, you can safely say that memory is growing or leaking.</span></span> <span data-ttu-id="d81fa-136">Il passaggio successivo consiste nel raccogliere i dati appropriati per l'analisi della memoria.</span><span class="sxs-lookup"><span data-stu-id="d81fa-136">The next step is to collect the right data for memory analysis.</span></span>

### <a name="generate-memory-dump"></a><span data-ttu-id="d81fa-137">Genera dump della memoria</span><span class="sxs-lookup"><span data-stu-id="d81fa-137">Generate memory dump</span></span>

<span data-ttu-id="d81fa-138">Quando si analizzano possibili perdite di memoria, è necessario accedere all'heap di memoria dell'app.</span><span class="sxs-lookup"><span data-stu-id="d81fa-138">When analyzing possible memory leaks, you need access to the app's memory heap.</span></span> <span data-ttu-id="d81fa-139">È quindi possibile analizzare il contenuto della memoria.</span><span class="sxs-lookup"><span data-stu-id="d81fa-139">Then you can analyze the memory contents.</span></span> <span data-ttu-id="d81fa-140">Esaminando le relazioni tra gli oggetti, è possibile creare teorie sui motivi per cui la memoria non viene liberata.</span><span class="sxs-lookup"><span data-stu-id="d81fa-140">Looking at relationships between objects, you create theories on why memory isn't being freed.</span></span> <span data-ttu-id="d81fa-141">Un'origine dati di diagnostica comune è un dump della memoria in Windows o il dump di core equivalente in Linux.</span><span class="sxs-lookup"><span data-stu-id="d81fa-141">A common diagnostics data source is a memory dump on Windows or the equivalent core dump on Linux.</span></span> <span data-ttu-id="d81fa-142">Per generare un dump di un'applicazione .NET Core, è possibile usare lo strumento [DotNet-dump](dotnet-dump.md) .</span><span class="sxs-lookup"><span data-stu-id="d81fa-142">To generate a dump of a .NET Core application, you can use the [dotnet-dump)](dotnet-dump.md) tool.</span></span>

<span data-ttu-id="d81fa-143">Usando la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) precedentemente avviata, eseguire il comando seguente per generare un dump di Linux Core:</span><span class="sxs-lookup"><span data-stu-id="d81fa-143">Using the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) previously started, run the following command to generate a Linux core dump:</span></span>

```dotnetcli
dotnet-dump collect -p 4807
```

<span data-ttu-id="d81fa-144">Il risultato è un dump di base che si trova nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="d81fa-144">The result is a core dump located in the same folder.</span></span>

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a><span data-ttu-id="d81fa-145">Riavvia il processo non riuscito</span><span class="sxs-lookup"><span data-stu-id="d81fa-145">Restart the failed process</span></span>

<span data-ttu-id="d81fa-146">Una volta raccolto il dump, è necessario disporre di informazioni sufficienti per diagnosticare il processo non riuscito.</span><span class="sxs-lookup"><span data-stu-id="d81fa-146">Once the dump is collected, you should have sufficient information to diagnose the failed process.</span></span> <span data-ttu-id="d81fa-147">Se il processo non riuscito viene eseguito in un server di produzione, è ora ideale per la correzione a breve termine riavviando il processo.</span><span class="sxs-lookup"><span data-stu-id="d81fa-147">If the failed process is running on a production server, now it's the ideal time for short-term remediation by restarting the process.</span></span>

<span data-ttu-id="d81fa-148">In questa esercitazione viene ora eseguita la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) , che può essere chiusa.</span><span class="sxs-lookup"><span data-stu-id="d81fa-148">In this tutorial, you're now done with the [Sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) and you can close it.</span></span> <span data-ttu-id="d81fa-149">Passare al terminale che ha avviato il server e premere `Control-C`.</span><span class="sxs-lookup"><span data-stu-id="d81fa-149">Navigate to the terminal that started the server and press `Control-C`.</span></span>

### <a name="analyze-the-core-dump"></a><span data-ttu-id="d81fa-150">Analizzare il dump di base</span><span class="sxs-lookup"><span data-stu-id="d81fa-150">Analyze the core dump</span></span>

<span data-ttu-id="d81fa-151">Ora che è stato generato un dump di base, usare lo strumento [DotNet-dump)](dotnet-dump.md) per analizzare il dump:</span><span class="sxs-lookup"><span data-stu-id="d81fa-151">Now that you have a core dump generated, use the [dotnet-dump)](dotnet-dump.md) tool to analyze the dump:</span></span>

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

<span data-ttu-id="d81fa-152">Dove `core_20190430_185145` è il nome del dump di base che si vuole analizzare.</span><span class="sxs-lookup"><span data-stu-id="d81fa-152">Where `core_20190430_185145` is the name of the core dump you want to analyze.</span></span>

> [!NOTE]
> <span data-ttu-id="d81fa-153">Se viene visualizzato un errore che segnala che non è possibile trovare *libdl.so* , potrebbe essere necessario installare il pacchetto *libc6-dev* .</span><span class="sxs-lookup"><span data-stu-id="d81fa-153">If you see an error complaining that *libdl.so* cannot be found, you may have to install the *libc6-dev* package.</span></span> <span data-ttu-id="d81fa-154">Per altre informazioni, vedere [Prerequisiti per .NET Core in Linux](../linux-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d81fa-154">For more information, see [Prerequisites for .NET Core on Linux](../linux-prerequisites.md).</span></span>

<span data-ttu-id="d81fa-155">Verrà visualizzato un prompt in cui è possibile immettere i comandi SOS.</span><span class="sxs-lookup"><span data-stu-id="d81fa-155">You'll be presented with a prompt where you can enter SOS commands.</span></span> <span data-ttu-id="d81fa-156">In genere, la prima cosa che si vuole esaminare è lo stato complessivo dell'heap gestito:</span><span class="sxs-lookup"><span data-stu-id="d81fa-156">Commonly, the first thing you want to look at is the overall state of the managed heap:</span></span>

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

<span data-ttu-id="d81fa-157">Qui è possibile notare che la maggior parte degli oggetti è `String` o `Customer` oggetti.</span><span class="sxs-lookup"><span data-stu-id="d81fa-157">Here you can see that most objects are either `String` or `Customer` objects.</span></span>

<span data-ttu-id="d81fa-158">È possibile usare di nuovo il comando `dumpheap` con la tabella dei metodi (MT) per ottenere un elenco di tutte le istanze di `String`:</span><span class="sxs-lookup"><span data-stu-id="d81fa-158">You can use the `dumpheap` command again with the method table (MT) to get a list of all the `String` instances:</span></span>

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

<span data-ttu-id="d81fa-159">È ora possibile usare il comando `gcroot` in un'istanza di `System.String` per vedere come e perché l'oggetto è radicato.</span><span class="sxs-lookup"><span data-stu-id="d81fa-159">You can now use the `gcroot` command on a `System.String` instance to see how and why the object is rooted.</span></span> <span data-ttu-id="d81fa-160">Essere paziente perché questo comando richiede diversi minuti con un heap di 30 MB:</span><span class="sxs-lookup"><span data-stu-id="d81fa-160">Be patient because this command takes several minutes with a 30-MB heap:</span></span>

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

<span data-ttu-id="d81fa-161">È possibile osservare che l'`String` viene mantenuta direttamente dall'oggetto `Customer` e che è indirettamente utilizzata da un oggetto `CustomerCache`.</span><span class="sxs-lookup"><span data-stu-id="d81fa-161">You can see that the `String` is directly held by the `Customer` object and indirectly held by a `CustomerCache` object.</span></span>

<span data-ttu-id="d81fa-162">È possibile continuare a eseguire il dump degli oggetti per vedere che la maggior parte degli oggetti `String` segue un modello simile.</span><span class="sxs-lookup"><span data-stu-id="d81fa-162">You can continue dumping out objects to see that most `String` objects follow a similar pattern.</span></span> <span data-ttu-id="d81fa-163">A questo punto, l'indagine forniva informazioni sufficienti per identificare la causa radice nel codice.</span><span class="sxs-lookup"><span data-stu-id="d81fa-163">At this point, the investigation provided sufficient information to identify the root cause in your code.</span></span>

<span data-ttu-id="d81fa-164">Questa procedura generale consente di identificare l'origine delle perdite di memoria principali.</span><span class="sxs-lookup"><span data-stu-id="d81fa-164">This general procedure allows you to identify the source of major memory leaks.</span></span>

## <a name="clean-up-resources"></a><span data-ttu-id="d81fa-165">Pulire le risorse</span><span class="sxs-lookup"><span data-stu-id="d81fa-165">Clean up resources</span></span>

<span data-ttu-id="d81fa-166">In questa esercitazione è stato avviato un server Web di esempio.</span><span class="sxs-lookup"><span data-stu-id="d81fa-166">In this tutorial, you started a sample web server.</span></span> <span data-ttu-id="d81fa-167">Questo server dovrebbe essere stato arrestato come illustrato nella sezione [riavviare il processo non riuscito](#restart-the-failed-process) .</span><span class="sxs-lookup"><span data-stu-id="d81fa-167">This server should have been shut down as explained in the [Restart the failed process](#restart-the-failed-process) section.</span></span>

<span data-ttu-id="d81fa-168">È anche possibile eliminare il file di dump creato.</span><span class="sxs-lookup"><span data-stu-id="d81fa-168">You can also delete the dump file that was created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d81fa-169">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d81fa-169">Next steps</span></span>

<span data-ttu-id="d81fa-170">Congratulazioni per aver completato questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="d81fa-170">Congratulations on completing this tutorial.</span></span>

<span data-ttu-id="d81fa-171">Stiamo ancora pubblicando altre esercitazioni diagnostiche.</span><span class="sxs-lookup"><span data-stu-id="d81fa-171">We're still publishing more diagnostic tutorials.</span></span> <span data-ttu-id="d81fa-172">È possibile leggere le versioni bozza nel repository [DotNet/Diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) .</span><span class="sxs-lookup"><span data-stu-id="d81fa-172">You can read the draft versions on the [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) repository.</span></span>

<span data-ttu-id="d81fa-173">Questa esercitazione ha trattato le nozioni di base degli strumenti di diagnostica .NET principali.</span><span class="sxs-lookup"><span data-stu-id="d81fa-173">This tutorial covered the basics of key .NET diagnostic tools.</span></span> <span data-ttu-id="d81fa-174">Per informazioni sull'utilizzo avanzato, vedere la documentazione di riferimento seguente:</span><span class="sxs-lookup"><span data-stu-id="d81fa-174">For advanced usage, see the following reference documentation:</span></span>

* <span data-ttu-id="d81fa-175">[DotNet-Trace](dotnet-trace.md) per elencare i processi.</span><span class="sxs-lookup"><span data-stu-id="d81fa-175">[dotnet-trace](dotnet-trace.md) to list processes.</span></span>
* <span data-ttu-id="d81fa-176">[DotNet-contatori](dotnet-counters.md) per controllare l'utilizzo del managed memory.</span><span class="sxs-lookup"><span data-stu-id="d81fa-176">[dotnet-counters](dotnet-counters.md) to check managed memory usage.</span></span>
* <span data-ttu-id="d81fa-177">[DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump.</span><span class="sxs-lookup"><span data-stu-id="d81fa-177">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file.</span></span>
