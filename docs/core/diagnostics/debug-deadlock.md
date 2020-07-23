---
title: Deadlock di debug-.NET Core
description: Esercitazione che illustra il debug di un problema di blocco in .NET Core.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 247521176297254180d794d4d4fc850f30e343b0
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86926404"
---
# <a name="debug-a-deadlock-in-net-core"></a><span data-ttu-id="e286b-103">Eseguire il debug di un deadlock in .NET Core</span><span class="sxs-lookup"><span data-stu-id="e286b-103">Debug a deadlock in .NET Core</span></span>

<span data-ttu-id="e286b-104">**Questo articolo si applica a: ✔️** .net core 3,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="e286b-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="e286b-105">In questa esercitazione si apprenderà come eseguire il debug di uno scenario di deadlock.</span><span class="sxs-lookup"><span data-stu-id="e286b-105">In this tutorial, you'll learn how to debug a deadlock scenario.</span></span> <span data-ttu-id="e286b-106">Usando l'esempio fornito ASP.NET Core repository del codice sorgente dell' [app Web](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) , è possibile causare un deadlock intenzionalmente.</span><span class="sxs-lookup"><span data-stu-id="e286b-106">Using the provided example [ASP.NET Core web app](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="e286b-107">L'endpoint riscontra un accumulo di blocchi e thread.</span><span class="sxs-lookup"><span data-stu-id="e286b-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="e286b-108">Si apprenderà come usare diversi strumenti per analizzare il problema, ad esempio i dump di base, l'analisi dei dump di base e la traccia dei processi.</span><span class="sxs-lookup"><span data-stu-id="e286b-108">You'll learn how you can use various tools to analyze the problem, such as core dumps, core dump analysis, and process tracing.</span></span>

<span data-ttu-id="e286b-109">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="e286b-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="e286b-110">Esaminare un blocco dell'app</span><span class="sxs-lookup"><span data-stu-id="e286b-110">Investigate an app hang</span></span>
> - <span data-ttu-id="e286b-111">Genera un file di dump di base</span><span class="sxs-lookup"><span data-stu-id="e286b-111">Generate a core dump file</span></span>
> - <span data-ttu-id="e286b-112">Analizzare i thread del processo nel file dump</span><span class="sxs-lookup"><span data-stu-id="e286b-112">Analyze process threads in the dump file</span></span>
> - <span data-ttu-id="e286b-113">Analizzare i blocchi di sincronizzazione e stack</span><span class="sxs-lookup"><span data-stu-id="e286b-113">Analyze callstacks and sync blocks</span></span>
> - <span data-ttu-id="e286b-114">Diagnosticare e risolvere un deadlock</span><span class="sxs-lookup"><span data-stu-id="e286b-114">Diagnose and solve a deadlock</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e286b-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e286b-115">Prerequisites</span></span>

<span data-ttu-id="e286b-116">L'esercitazione usa:</span><span class="sxs-lookup"><span data-stu-id="e286b-116">The tutorial uses:</span></span>

- <span data-ttu-id="e286b-117">[.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="e286b-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version</span></span>
- <span data-ttu-id="e286b-118">[Esempio di destinazione di debug-app Web](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) per attivare lo scenario</span><span class="sxs-lookup"><span data-stu-id="e286b-118">[Sample debug target - web app](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario</span></span>
- <span data-ttu-id="e286b-119">[DotNet-Trace](dotnet-trace.md) per elencare i processi</span><span class="sxs-lookup"><span data-stu-id="e286b-119">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="e286b-120">[DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump</span><span class="sxs-lookup"><span data-stu-id="e286b-120">[dotnet-dump](dotnet-dump.md) to collect, and analyze a dump file</span></span>

## <a name="core-dump-generation"></a><span data-ttu-id="e286b-121">Generazione del dump di base</span><span class="sxs-lookup"><span data-stu-id="e286b-121">Core dump generation</span></span>

<span data-ttu-id="e286b-122">Per esaminare la mancata risposta dell'applicazione, un dump principale o un dump della memoria consente di controllare lo stato dei thread e di eventuali blocchi possibili che potrebbero presentare problemi di contesa.</span><span class="sxs-lookup"><span data-stu-id="e286b-122">To investigate application unresponsiveness, a core dump or memory dump allows you to inspect the state of its threads and any possible locks that may have contention issues.</span></span> <span data-ttu-id="e286b-123">Eseguire l'applicazione di [debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) usando il comando seguente dalla directory radice dell'esempio:</span><span class="sxs-lookup"><span data-stu-id="e286b-123">Run the [sample debug](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) application using the following command from the sample root directory:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="e286b-124">Per trovare l'ID del processo, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e286b-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="e286b-125">Prendere nota dell'ID del processo dall'output del comando.</span><span class="sxs-lookup"><span data-stu-id="e286b-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="e286b-126">Il nostro ID processo era `4807` , ma il tuo sarà diverso.</span><span class="sxs-lookup"><span data-stu-id="e286b-126">Our process ID was `4807`, but yours will be different.</span></span> <span data-ttu-id="e286b-127">Passare all'URL seguente, che è un endpoint API nel sito di esempio:</span><span class="sxs-lookup"><span data-stu-id="e286b-127">Navigate to the following URL, which is an API endpoint on the sample site:</span></span>

[https://localhost:5001/api/diagscenario/deadlock](https://localhost:5001/api/diagscenario/deadlock)

<span data-ttu-id="e286b-128">La richiesta dell'API al sito si bloccherà e non risponde.</span><span class="sxs-lookup"><span data-stu-id="e286b-128">The API request to the site will hang and not respond.</span></span> <span data-ttu-id="e286b-129">Consentire l'esecuzione della richiesta per circa 10-15 secondi.</span><span class="sxs-lookup"><span data-stu-id="e286b-129">Let the request run for about 10-15 seconds.</span></span> <span data-ttu-id="e286b-130">Quindi creare il dump di base usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e286b-130">Then create the core dump using the following command:</span></span>

### <a name="linux"></a>[<span data-ttu-id="e286b-131">Linux</span><span class="sxs-lookup"><span data-stu-id="e286b-131">Linux</span></span>](#tab/linux)

```bash
sudo dotnet-dump collect -p 4807
```

### <a name="windows"></a>[<span data-ttu-id="e286b-132">Windows</span><span class="sxs-lookup"><span data-stu-id="e286b-132">Windows</span></span>](#tab/windows)

```console
dotnet-dump collect -p 4807
```

---

## <a name="analyze-the-core-dump"></a><span data-ttu-id="e286b-133">Analizzare il dump di base</span><span class="sxs-lookup"><span data-stu-id="e286b-133">Analyze the core dump</span></span>

<span data-ttu-id="e286b-134">Per avviare l'analisi dei dump di base, aprire il dump principale usando il `dotnet-dump analyze` comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e286b-134">To start the core dump analysis, open the core dump using the following `dotnet-dump analyze` command.</span></span> <span data-ttu-id="e286b-135">L'argomento è il percorso del file di dump principale che è stato raccolto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e286b-135">The argument is the path to the core dump file that was collected earlier.</span></span>

```dotnetcli
dotnet-dump analyze  ~/.dotnet/tools/core_20190513_143916
```

<span data-ttu-id="e286b-136">Poiché si sta esaminando un potenziale blocco, si desidera un'esperienza complessiva per l'attività del thread nel processo.</span><span class="sxs-lookup"><span data-stu-id="e286b-136">Since you're looking at a potential hang, you want an overall feel for the thread activity in the process.</span></span> <span data-ttu-id="e286b-137">È possibile usare il `threads` comando come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e286b-137">You can use the `threads` command as shown below:</span></span>

```console
> threads
*0 0x1DBFF (121855)
 1 0x1DC01 (121857)
 2 0x1DC02 (121858)
 3 0x1DC03 (121859)
 4 0x1DC04 (121860)
 5 0x1DC05 (121861)
 6 0x1DC06 (121862)
 7 0x1DC07 (121863)
 8 0x1DC08 (121864)
 9 0x1DC09 (121865)
 10 0x1DC0A (121866)
 11 0x1DC0D (121869)
 12 0x1DC0E (121870)
 13 0x1DC10 (121872)
 14 0x1DC11 (121873)
 15 0x1DC12 (121874)
 16 0x1DC13 (121875)
 17 0x1DC14 (121876)
 18 0x1DC15 (121877)
 19 0x1DC1C (121884)
 20 0x1DC1D (121885)
 21 0x1DC1E (121886)
 22 0x1DC21 (121889)
 23 0x1DC22 (121890)
 24 0x1DC23 (121891)
 25 0x1DC24 (121892)
 26 0x1DC25 (121893)
...
...
 317 0x1DD48 (122184)
 318 0x1DD49 (122185)
 319 0x1DD4A (122186)
 320 0x1DD4B (122187)
 321 0x1DD4C (122188)
 ```

<span data-ttu-id="e286b-138">L'output Mostra tutti i thread attualmente in esecuzione nel processo con l'ID del thread del debugger e l'ID del thread del sistema operativo associati.</span><span class="sxs-lookup"><span data-stu-id="e286b-138">The output shows all the threads currently running in the process with their associated debugger thread ID and operating system thread ID.</span></span> <span data-ttu-id="e286b-139">In base all'output, sono presenti più di 300 thread.</span><span class="sxs-lookup"><span data-stu-id="e286b-139">Based on the output, there are over 300 threads.</span></span>

<span data-ttu-id="e286b-140">Il passaggio successivo consiste nell'ottenere una migliore comprensione delle operazioni attualmente svolte dai thread ottenendo il stack di ogni thread.</span><span class="sxs-lookup"><span data-stu-id="e286b-140">The next step is to get a better understanding of what the threads are currently doing by getting each thread's callstack.</span></span> <span data-ttu-id="e286b-141">Il `clrstack` comando può essere usato per l'output di stack.</span><span class="sxs-lookup"><span data-stu-id="e286b-141">The `clrstack` command can be used to output callstacks.</span></span> <span data-ttu-id="e286b-142">Può restituire un singolo stack o tutti i stack.</span><span class="sxs-lookup"><span data-stu-id="e286b-142">It can either output a single callstack or all the callstacks.</span></span> <span data-ttu-id="e286b-143">Usare il comando seguente per restituire tutti i stack per tutti i thread nel processo:</span><span class="sxs-lookup"><span data-stu-id="e286b-143">Use the following command to output all the callstacks for all the threads in the process:</span></span>

```console
clrstack -all
```

<span data-ttu-id="e286b-144">Una parte rappresentativa dell'output è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e286b-144">A representative portion of the output looks like:</span></span>

```console
  ...
  ...
  ...
        Child SP               IP Call Site
00007F2AE37B5680 00007f305abc6360 [GCFrame: 00007f2ae37b5680]
00007F2AE37B5770 00007f305abc6360 [GCFrame: 00007f2ae37b5770]
00007F2AE37B57D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae37b57d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE37B5920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE37B5950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE37B5CA0 00007f30593044af [GCFrame: 00007f2ae37b5ca0]
00007F2AE37B5D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae37b5d70]
OS Thread Id: 0x1dc82
        Child SP               IP Call Site
00007F2AE2FB4680 00007f305abc6360 [GCFrame: 00007f2ae2fb4680]
00007F2AE2FB4770 00007f305abc6360 [GCFrame: 00007f2ae2fb4770]
00007F2AE2FB47D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae2fb47d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE2FB4920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE2FB4950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE2FB4CA0 00007f30593044af [GCFrame: 00007f2ae2fb4ca0]
00007F2AE2FB4D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae2fb4d70]
OS Thread Id: 0x1dc83
        Child SP               IP Call Site
00007F2AE27B3680 00007f305abc6360 [GCFrame: 00007f2ae27b3680]
00007F2AE27B3770 00007f305abc6360 [GCFrame: 00007f2ae27b3770]
00007F2AE27B37D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae27b37d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE27B3920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE27B3950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE27B3CA0 00007f30593044af [GCFrame: 00007f2ae27b3ca0]
00007F2AE27B3D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae27b3d70]
OS Thread Id: 0x1dc84
        Child SP               IP Call Site
00007F2AE1FB2680 00007f305abc6360 [GCFrame: 00007f2ae1fb2680]
00007F2AE1FB2770 00007f305abc6360 [GCFrame: 00007f2ae1fb2770]
00007F2AE1FB27D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae1fb27d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE1FB2920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE1FB2950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE1FB2CA0 00007f30593044af [GCFrame: 00007f2ae1fb2ca0]
00007F2AE1FB2D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae1fb2d70]
OS Thread Id: 0x1dc85
        Child SP               IP Call Site
00007F2AE17B1680 00007f305abc6360 [GCFrame: 00007f2ae17b1680]
00007F2AE17B1770 00007f305abc6360 [GCFrame: 00007f2ae17b1770]
00007F2AE17B17D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae17b17d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE17B1920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE17B1950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE17B1CA0 00007f30593044af [GCFrame: 00007f2ae17b1ca0]
00007F2AE17B1D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae17b1d70]
OS Thread Id: 0x1dc86
        Child SP               IP Call Site
00007F2AE0FB0680 00007f305abc6360 [GCFrame: 00007f2ae0fb0680]
00007F2AE0FB0770 00007f305abc6360 [GCFrame: 00007f2ae0fb0770]
00007F2AE0FB07D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae0fb07d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE0FB0920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE0FB0950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE0FB0CA0 00007f30593044af [GCFrame: 00007f2ae0fb0ca0]
00007F2AE0FB0D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae0fb0d70]
OS Thread Id: 0x1dc87
        Child SP               IP Call Site
00007F2AE07AF680 00007f305abc6360 [GCFrame: 00007f2ae07af680]
00007F2AE07AF770 00007f305abc6360 [GCFrame: 00007f2ae07af770]
00007F2AE07AF7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae07af7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE07AF920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE07AF950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE07AFCA0 00007f30593044af [GCFrame: 00007f2ae07afca0]
00007F2AE07AFD70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae07afd70]
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
...
...
```

<span data-ttu-id="e286b-145">Osservando il stack per tutti i 300 thread viene mostrato un modello in cui la maggior parte dei thread condividono un stack comune:</span><span class="sxs-lookup"><span data-stu-id="e286b-145">Observing the callstacks for all 300+ threads shows a pattern where a majority of the threads share a common callstack:</span></span>

```console
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
```

<span data-ttu-id="e286b-146">Stack sembra indicare che la richiesta è arrivata nel metodo deadlock che a sua volta effettua una chiamata a `Monitor.ReliableEnter` .</span><span class="sxs-lookup"><span data-stu-id="e286b-146">The callstack seems to show that the request arrived in our deadlock method that in turn makes a call to `Monitor.ReliableEnter`.</span></span> <span data-ttu-id="e286b-147">Questo metodo indica che i thread tentano di accedere a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e286b-147">This method indicates that the threads are trying to enter a monitor lock.</span></span> <span data-ttu-id="e286b-148">Sono in attesa della disponibilità del blocco.</span><span class="sxs-lookup"><span data-stu-id="e286b-148">They're waiting on the availability of the lock.</span></span> <span data-ttu-id="e286b-149">È probabile che sia bloccato da un thread diverso.</span><span class="sxs-lookup"><span data-stu-id="e286b-149">It's likely locked by a different thread.</span></span>

<span data-ttu-id="e286b-150">Il passaggio successivo consiste nel scoprire quale thread sta effettivamente mantenendo il blocco del monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e286b-150">The next step then is to find out which thread is actually holding the monitor lock.</span></span> <span data-ttu-id="e286b-151">Poiché i monitoraggi in genere archiviano le informazioni di blocco nella tabella dei blocchi di sincronizzazione, è possibile usare il `syncblk` comando per ottenere altre informazioni:</span><span class="sxs-lookup"><span data-stu-id="e286b-151">Since monitors typically store lock information in the sync block table, we can use the `syncblk` command to get more information:</span></span>

```console
> syncblk
Index         SyncBlock MonitorHeld Recursion Owning Thread Info          SyncBlock Owner
   43 00000246E51268B8          603         1 0000024B713F4E30 5634  28   00000249654b14c0 System.Object
   44 00000246E5126908            3         1 0000024B713F47E0 51d4  29   00000249654b14d8 System.Object
-----------------------------
Total           344
CCW             1
RCW             2
ComClassFactory 0
Free            0
```

<span data-ttu-id="e286b-152">Le due colonne interessanti sono **MonitorHeld** e le **informazioni sul thread proprietario**.</span><span class="sxs-lookup"><span data-stu-id="e286b-152">The two interesting columns are **MonitorHeld** and **Owning Thread Info**.</span></span> <span data-ttu-id="e286b-153">La colonna **MonitorHeld** indica se un blocco di monitoraggio viene acquisito da un thread e dal numero di thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="e286b-153">The **MonitorHeld** column shows whether a monitor lock is acquired by a thread and the number of waiting threads.</span></span> <span data-ttu-id="e286b-154">Nella colonna **informazioni thread proprietario** viene visualizzato il thread attualmente proprietario del blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e286b-154">The **Owning Thread Info** column shows which thread currently owns the monitor lock.</span></span> <span data-ttu-id="e286b-155">Le informazioni sul thread hanno tre sottocolonne diverse.</span><span class="sxs-lookup"><span data-stu-id="e286b-155">The thread info has three different subcolumns.</span></span> <span data-ttu-id="e286b-156">La seconda sottocolonna Mostra l'ID del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e286b-156">The second subcolumn shows operating system thread ID.</span></span>

<span data-ttu-id="e286b-157">A questo punto, si conoscono due thread diversi (0x5634 e 0x51d4) che contengono un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e286b-157">At this point, we know two different threads (0x5634 and 0x51d4) hold a monitor lock.</span></span> <span data-ttu-id="e286b-158">Il passaggio successivo consiste nell'esaminare le operazioni svolte da tali thread.</span><span class="sxs-lookup"><span data-stu-id="e286b-158">The next step is to take a look at what those threads are doing.</span></span> <span data-ttu-id="e286b-159">È necessario controllare se sono bloccati in modo indefinito.</span><span class="sxs-lookup"><span data-stu-id="e286b-159">We need to check if they're stuck indefinitely holding the lock.</span></span> <span data-ttu-id="e286b-160">Usare i `setthread` `clrstack` comandi e per passare a ognuno dei thread e visualizzare il stack.</span><span class="sxs-lookup"><span data-stu-id="e286b-160">Let's use the `setthread` and `clrstack` commands to switch to each of the threads and display the callstacks.</span></span>

<span data-ttu-id="e286b-161">Per esaminare il primo thread, eseguire il `setthread` comando e individuare l'indice del thread 0x5634 (l'indice è 28).</span><span class="sxs-lookup"><span data-stu-id="e286b-161">To look at the first thread, run the `setthread` command, and find the index of the 0x5634 thread (our index was 28).</span></span> <span data-ttu-id="e286b-162">La funzione deadlock è in attesa di acquisire un blocco, ma è già proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e286b-162">The deadlock function is waiting to acquire a lock, but it already owns the lock.</span></span> <span data-ttu-id="e286b-163">Si trova in un deadlock in attesa del blocco che possiede già.</span><span class="sxs-lookup"><span data-stu-id="e286b-163">It's in deadlock waiting for the lock it already holds.</span></span>

```console
> setthread 28
> clrstack
OS Thread Id: 0x5634 (28)
        Child SP               IP Call Site
0000004E46AFEAA8 00007fff43a5cbc4 [GCFrame: 0000004e46afeaa8]
0000004E46AFEC18 00007fff43a5cbc4 [GCFrame: 0000004e46afec18]
0000004E46AFEC68 00007fff43a5cbc4 [HelperMethodFrame_1OBJ: 0000004e46afec68] System.Threading.Monitor.Enter(System.Object)
0000004E46AFEDC0 00007FFE5EAF9C80 testwebapi.Controllers.DiagScenarioController.DeadlockFunc() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 58]
0000004E46AFEE30 00007FFE5EAF9B8C testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_0() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 26]
0000004E46AFEE80 00007FFEBB251A5B System.Threading.ThreadHelper.ThreadStart_Context(System.Object) [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 44]
0000004E46AFEEB0 00007FFE5EAEEEEC System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/_/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
0000004E46AFEF20 00007FFEBB234EAB System.Threading.ThreadHelper.ThreadStart() [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 93]
0000004E46AFF138 00007ffebdcc6b63 [GCFrame: 0000004e46aff138]
0000004E46AFF3A0 00007ffebdcc6b63 [DebuggerU2MCatchHandlerFrame: 0000004e46aff3a0]
```

<span data-ttu-id="e286b-164">Il secondo thread è simile.</span><span class="sxs-lookup"><span data-stu-id="e286b-164">The second thread is similar.</span></span> <span data-ttu-id="e286b-165">Tenta anche di acquisire un blocco già proprietario.</span><span class="sxs-lookup"><span data-stu-id="e286b-165">It's also trying to acquire a lock that it already owns.</span></span> <span data-ttu-id="e286b-166">Gli altri 300 thread in attesa sono molto probabilmente in attesa di uno dei blocchi che hanno causato il deadlock.</span><span class="sxs-lookup"><span data-stu-id="e286b-166">The remaining 300+ threads that are all waiting are most likely also waiting on one of the locks that caused the deadlock.</span></span>

## <a name="see-also"></a><span data-ttu-id="e286b-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e286b-167">See also</span></span>

- <span data-ttu-id="e286b-168">[DotNet-Trace](dotnet-trace.md) per elencare i processi</span><span class="sxs-lookup"><span data-stu-id="e286b-168">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="e286b-169">[contatori DotNet](dotnet-counters.md) per controllare l'utilizzo di managed memory</span><span class="sxs-lookup"><span data-stu-id="e286b-169">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="e286b-170">[DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump</span><span class="sxs-lookup"><span data-stu-id="e286b-170">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="e286b-171">DotNet/diagnostica</span><span class="sxs-lookup"><span data-stu-id="e286b-171">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="e286b-172">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e286b-172">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e286b-173">Quali strumenti di diagnostica sono disponibili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="e286b-173">What diagnostic tools are available in .NET Core</span></span>](index.md)
