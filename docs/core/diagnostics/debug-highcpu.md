---
title: Eseguire il debug di un utilizzo elevato della CPU-.NET Core
description: Esercitazione che illustra come eseguire il debug di un utilizzo elevato della CPU in .NET Core.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: e69585d0eb6f04bf37d0c023a1956be62c2a1cf3
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86926403"
---
# <a name="debug-high-cpu-usage-in-net-core"></a><span data-ttu-id="44666-103">Eseguire il debug di un utilizzo elevato della CPU in .NET Core</span><span class="sxs-lookup"><span data-stu-id="44666-103">Debug high CPU usage in .NET Core</span></span>

<span data-ttu-id="44666-104">**Questo articolo si applica a: ✔️** .net core 3,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="44666-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="44666-105">In questa esercitazione si apprenderà come eseguire il debug di uno scenario di utilizzo eccessivo della CPU.</span><span class="sxs-lookup"><span data-stu-id="44666-105">In this tutorial, you'll learn how to debug an excessive CPU usage scenario.</span></span> <span data-ttu-id="44666-106">Usando l'esempio fornito ASP.NET Core repository del codice sorgente dell' [app Web](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) , è possibile causare un deadlock intenzionalmente.</span><span class="sxs-lookup"><span data-stu-id="44666-106">Using the provided example [ASP.NET Core web app](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="44666-107">L'endpoint riscontra un accumulo di blocchi e thread.</span><span class="sxs-lookup"><span data-stu-id="44666-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="44666-108">Si apprenderà come usare diversi strumenti per diagnosticare questo scenario con diversi elementi chiave dei dati di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="44666-108">You'll learn how you can use various tools to diagnose this scenario with several key pieces of diagnostics data.</span></span>

<span data-ttu-id="44666-109">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="44666-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="44666-110">Esaminare l'utilizzo elevato della CPU</span><span class="sxs-lookup"><span data-stu-id="44666-110">Investigate high CPU usage</span></span>
> - <span data-ttu-id="44666-111">Determinare l'utilizzo della CPU con i [contatori DotNet](dotnet-counters.md)</span><span class="sxs-lookup"><span data-stu-id="44666-111">Determine CPU usage with [dotnet-counters](dotnet-counters.md)</span></span>
> - <span data-ttu-id="44666-112">Usare [DotNet-Trace](dotnet-trace.md) per la generazione di tracce</span><span class="sxs-lookup"><span data-stu-id="44666-112">Use [dotnet-trace](dotnet-trace.md) for trace generation</span></span>
> - <span data-ttu-id="44666-113">Prestazioni del profilo in PerfView</span><span class="sxs-lookup"><span data-stu-id="44666-113">Profile performance in PerfView</span></span>
> - <span data-ttu-id="44666-114">Diagnosticare e risolvere un utilizzo eccessivo della CPU</span><span class="sxs-lookup"><span data-stu-id="44666-114">Diagnose and solve excessive CPU usage</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44666-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="44666-115">Prerequisites</span></span>

<span data-ttu-id="44666-116">L'esercitazione usa:</span><span class="sxs-lookup"><span data-stu-id="44666-116">The tutorial uses:</span></span>

- <span data-ttu-id="44666-117">[.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="44666-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="44666-118">[Esempio di destinazione di debug](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) per attivare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="44666-118">[Sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario.</span></span>
- <span data-ttu-id="44666-119">[DotNet-Trace](dotnet-trace.md) per elencare i processi e generare un profilo.</span><span class="sxs-lookup"><span data-stu-id="44666-119">[dotnet-trace](dotnet-trace.md) to list processes and generate a profile.</span></span>
- <span data-ttu-id="44666-120">[DotNet-contatori](dotnet-counters.md) per il monitoraggio dell'utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="44666-120">[dotnet-counters](dotnet-counters.md) to monitor cpu usage.</span></span>

## <a name="cpu-counters"></a><span data-ttu-id="44666-121">Contatori CPU</span><span class="sxs-lookup"><span data-stu-id="44666-121">CPU counters</span></span>

<span data-ttu-id="44666-122">Prima di provare a raccogliere i dati di diagnostica, è necessario osservare una condizione di CPU elevata.</span><span class="sxs-lookup"><span data-stu-id="44666-122">Before attempting to collect diagnostics data, you need to observe a high CPU condition.</span></span> <span data-ttu-id="44666-123">Eseguire l' [applicazione di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) usando il comando seguente dalla directory radice del progetto.</span><span class="sxs-lookup"><span data-stu-id="44666-123">Run the [sample application](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) using the following command from the project root directory.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="44666-124">Per trovare l'ID del processo, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="44666-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="44666-125">Prendere nota dell'ID del processo dall'output del comando.</span><span class="sxs-lookup"><span data-stu-id="44666-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="44666-126">Il nostro ID processo era `22884` , ma il tuo sarà diverso.</span><span class="sxs-lookup"><span data-stu-id="44666-126">Our process ID was `22884`, but yours will be different.</span></span> <span data-ttu-id="44666-127">Per controllare l'utilizzo della CPU corrente, usare il comando [DotNet-Counters](dotnet-counters.md) Tool:</span><span class="sxs-lookup"><span data-stu-id="44666-127">To check the current CPU usage, use the [dotnet-counters](dotnet-counters.md) tool command:</span></span>

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

<span data-ttu-id="44666-128">`refresh-interval`È il numero di secondi tra i valori della CPU di polling del contatore.</span><span class="sxs-lookup"><span data-stu-id="44666-128">The `refresh-interval` is the number of seconds between the counter polling CPU values.</span></span> <span data-ttu-id="44666-129">L'output avrà un aspetto analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="44666-129">The output should be similar to the following:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    % Time in GC since last GC (%)                         0
    Allocation Rate / 1 sec (B)                            0
    CPU Usage (%)                                          0
    Exception Count / 1 sec                                0
    GC Heap Size (MB)                                      4
    Gen 0 GC Count / 60 sec                                0
    Gen 0 Size (B)                                         0
    Gen 1 GC Count / 60 sec                                0
    Gen 1 Size (B)                                         0
    Gen 2 GC Count / 60 sec                                0
    Gen 2 Size (B)                                         0
    LOH Size (B)                                           0
    Monitor Lock Contention Count / 1 sec                  0
    Number of Active Timers                                1
    Number of Assemblies Loaded                          140
    ThreadPool Completed Work Item Count / 1 sec           3
    ThreadPool Queue Length                                0
    ThreadPool Thread Count                                7
    Working Set (MB)                                      63
```

<span data-ttu-id="44666-130">Con l'app Web in esecuzione, immediatamente dopo l'avvio, la CPU non viene usata e viene segnalata all'indirizzo `0%` .</span><span class="sxs-lookup"><span data-stu-id="44666-130">With the web app running, immediately after startup, the CPU isn't being consumed at all and is reported at `0%`.</span></span> <span data-ttu-id="44666-131">Passare alla `api/diagscenario/highcpu` Route con `60000` come parametro di route:</span><span class="sxs-lookup"><span data-stu-id="44666-131">Navigate to the `api/diagscenario/highcpu` route with `60000` as the route parameter:</span></span>

[https://localhost:5001/api/diagscenario/highcpu/60000](https://localhost:5001/api/diagscenario/highcpu/60000)

<span data-ttu-id="44666-132">A questo punto, eseguire di nuovo il comando [DotNet-Counters](dotnet-counters.md) .</span><span class="sxs-lookup"><span data-stu-id="44666-132">Now, rerun the [dotnet-counters](dotnet-counters.md) command.</span></span> <span data-ttu-id="44666-133">Per monitorare solo `cpu-usage` , specificare `System.Runtime[cpu-usage]` come parte del comando.</span><span class="sxs-lookup"><span data-stu-id="44666-133">To monitor just the `cpu-usage`, specify `System.Runtime[cpu-usage]` as part of the command.</span></span>

```dotnetcli
dotnet-counters monitor System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

<span data-ttu-id="44666-134">Si noterà un aumento dell'utilizzo della CPU, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="44666-134">You should see an increase in CPU usage as shown below:</span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

<span data-ttu-id="44666-135">Per tutta la durata della richiesta, l'utilizzo della CPU passerà circa il 25%.</span><span class="sxs-lookup"><span data-stu-id="44666-135">Throughout the duration of the request, the CPU usage will hover around 25% .</span></span> <span data-ttu-id="44666-136">A seconda del computer host, è previsto un utilizzo della CPU variabile.</span><span class="sxs-lookup"><span data-stu-id="44666-136">Depending on the host machine, expect varying CPU usage.</span></span>

> [!TIP]
> <span data-ttu-id="44666-137">Per visualizzare un utilizzo della CPU ancora più elevato, è possibile usare questo endpoint in più schede del browser simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="44666-137">To visualize an even higher CPU usage, you can exercise this endpoint in multiple browser tabs simultaneously.</span></span>

<span data-ttu-id="44666-138">A questo punto, è possibile dire che la CPU è in esecuzione in modo più elevato del previsto.</span><span class="sxs-lookup"><span data-stu-id="44666-138">At this point, you can safely say the CPU is running higher than you expect.</span></span>

## <a name="trace-generation"></a><span data-ttu-id="44666-139">Generazione traccia</span><span class="sxs-lookup"><span data-stu-id="44666-139">Trace generation</span></span>

<span data-ttu-id="44666-140">Quando si analizza una richiesta lenta, è necessario uno strumento di diagnostica in grado di fornire informazioni approfondite sulle operazioni del codice.</span><span class="sxs-lookup"><span data-stu-id="44666-140">When analyzing a slow request, you need a diagnostics tool that can provide insights into what the code is doing.</span></span> <span data-ttu-id="44666-141">La scelta consueta è un profiler ed è possibile scegliere tra diverse opzioni del profiler.</span><span class="sxs-lookup"><span data-stu-id="44666-141">The usual choice is a profiler, and there are different profiler options to choose from.</span></span>

### <a name="linux"></a>[<span data-ttu-id="44666-142">Linux</span><span class="sxs-lookup"><span data-stu-id="44666-142">Linux</span></span>](#tab/linux)

<span data-ttu-id="44666-143">Lo `perf` strumento può essere usato per generare profili di app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="44666-143">The `perf` tool can be used to generate .NET Core app profiles.</span></span> <span data-ttu-id="44666-144">Uscire dall'istanza precedente della [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios).</span><span class="sxs-lookup"><span data-stu-id="44666-144">Exit the previous instance of the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios).</span></span>

<span data-ttu-id="44666-145">Impostare la `COMPlus_PerfMapEnabled` variabile di ambiente in modo che l'app .NET Core crei un `map` file nella `/tmp` Directory.</span><span class="sxs-lookup"><span data-stu-id="44666-145">Set the `COMPlus_PerfMapEnabled` environment variable to cause the .NET Core app to create a `map` file in the `/tmp` directory.</span></span> <span data-ttu-id="44666-146">Questo `map` file viene usato da `perf` per eseguire il mapping dell'indirizzo della CPU alle funzioni generate tramite JIT in base al nome.</span><span class="sxs-lookup"><span data-stu-id="44666-146">This `map` file is used by `perf` to map CPU address to JIT-generated functions by name.</span></span> <span data-ttu-id="44666-147">Per altre informazioni, vedere [scrivere la mappa delle prestazioni](../run-time-config/debugging-profiling.md#write-perf-map).</span><span class="sxs-lookup"><span data-stu-id="44666-147">For more information, see [Write perf map](../run-time-config/debugging-profiling.md#write-perf-map).</span></span>

<span data-ttu-id="44666-148">Eseguire la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) nella stessa sessione terminal.</span><span class="sxs-lookup"><span data-stu-id="44666-148">Run the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) in the same terminal session.</span></span>

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

<span data-ttu-id="44666-149">Eseguire di nuovo l'endpoint API CPU ( <https://localhost:5001/api/diagscenario/highcpu/60000> ) elevato.</span><span class="sxs-lookup"><span data-stu-id="44666-149">Exercise the high CPU API (<https://localhost:5001/api/diagscenario/highcpu/60000>) endpoint again.</span></span> <span data-ttu-id="44666-150">Mentre è in esecuzione entro la richiesta di 1 minuto, eseguire il `perf` comando con l'ID del processo:</span><span class="sxs-lookup"><span data-stu-id="44666-150">While it's running within the 1-minute request, run the `perf` command with your process ID:</span></span>

```bash
sudo perf record -p 2266 -g
```

<span data-ttu-id="44666-151">Il `perf` comando avvia il processo di raccolta delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="44666-151">The `perf` command starts the performance collection process.</span></span> <span data-ttu-id="44666-152">Consente di eseguire circa 20-30 secondi, quindi premere <kbd>CTRL + C</kbd> per uscire dal processo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="44666-152">Let it run for about 20-30 seconds, then press <kbd>Ctrl+C</kbd> to exit the collection process.</span></span> <span data-ttu-id="44666-153">È possibile usare lo stesso `perf` comando per visualizzare l'output della traccia.</span><span class="sxs-lookup"><span data-stu-id="44666-153">You can use the same `perf` command to see the output of the trace.</span></span>

```bash
sudo perf report -f
```

<span data-ttu-id="44666-154">È anche possibile generare un _grafico Flame_ usando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="44666-154">You can also generate a _flame-graph_ by using the following commands:</span></span>

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

<span data-ttu-id="44666-155">Questo comando genera un oggetto `flamegraph.svg` che è possibile visualizzare nel browser per esaminare il problema relativo alle prestazioni:</span><span class="sxs-lookup"><span data-stu-id="44666-155">This command generates a `flamegraph.svg` that you can view in the browser to investigate the performance problem:</span></span>

<span data-ttu-id="44666-156">[![Immagine di Flame Graph SVG](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="44666-156">[![Flame graph SVG image](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)</span></span>

### <a name="windows"></a>[<span data-ttu-id="44666-157">Windows</span><span class="sxs-lookup"><span data-stu-id="44666-157">Windows</span></span>](#tab/windows)

<span data-ttu-id="44666-158">In Windows è possibile usare lo strumento [DotNet-Trace](dotnet-trace.md) come profiler.</span><span class="sxs-lookup"><span data-stu-id="44666-158">On Windows, you can use the [dotnet-trace](dotnet-trace.md) tool as a profiler.</span></span> <span data-ttu-id="44666-159">Utilizzando la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios)precedente, verificare di nuovo l'endpoint CPU () elevato <https://localhost:5001/api/diagscenario/highcpu/60000> .</span><span class="sxs-lookup"><span data-stu-id="44666-159">Using the previous [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios), exercise the high CPU (<https://localhost:5001/api/diagscenario/highcpu/60000>) endpoint again.</span></span> <span data-ttu-id="44666-160">Mentre è in esecuzione entro la richiesta di 1 minuto, utilizzare il `collect` comando come segue:</span><span class="sxs-lookup"><span data-stu-id="44666-160">While it's running within the 1-minute request, use the `collect` command as follows:</span></span>

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

<span data-ttu-id="44666-161">Consentire l'esecuzione di [DotNet-Trace](dotnet-trace.md) per circa 20-30 secondi, quindi premere <kbd>invio</kbd> per uscire dalla raccolta.</span><span class="sxs-lookup"><span data-stu-id="44666-161">Let [dotnet-trace](dotnet-trace.md) run for about 20-30 seconds, and then press the <kbd>Enter</kbd> to exit the collection.</span></span> <span data-ttu-id="44666-162">Il risultato è un `nettrace` file che si trova nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="44666-162">The result is a `nettrace` file located in the same folder.</span></span> <span data-ttu-id="44666-163">I `nettrace` file sono un ottimo modo per usare gli strumenti di analisi esistenti in Windows.</span><span class="sxs-lookup"><span data-stu-id="44666-163">The `nettrace` files are a great way to use existing analysis tools on Windows.</span></span>

<span data-ttu-id="44666-164">Aprire `nettrace` con [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="44666-164">Open the `nettrace` with [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) as shown below.</span></span>

<span data-ttu-id="44666-165">[![Immagine di PerfView](media/perfview.jpg)](media/perfview.jpg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="44666-165">[![PerfView image](media/perfview.jpg)](media/perfview.jpg#lightbox)</span></span>

---

## <a name="see-also"></a><span data-ttu-id="44666-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44666-166">See also</span></span>

- <span data-ttu-id="44666-167">[DotNet-Trace](dotnet-trace.md) per elencare i processi</span><span class="sxs-lookup"><span data-stu-id="44666-167">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="44666-168">[contatori DotNet](dotnet-counters.md) per controllare l'utilizzo di managed memory</span><span class="sxs-lookup"><span data-stu-id="44666-168">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="44666-169">[DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump</span><span class="sxs-lookup"><span data-stu-id="44666-169">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="44666-170">DotNet/diagnostica</span><span class="sxs-lookup"><span data-stu-id="44666-170">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="44666-171">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="44666-171">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="44666-172">Eseguire il debug di un deadlock in .NET Core</span><span class="sxs-lookup"><span data-stu-id="44666-172">Debug a deadlock in .NET Core</span></span>](debug-deadlock.md)
