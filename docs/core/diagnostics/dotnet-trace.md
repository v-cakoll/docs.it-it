---
title: strumento dotnet-trace - .NET Core
description: Installazione e utilizzo dello strumento da riga di comando dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: 6880c3721e4cab12677bd02c82ca944cc9812670
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888085"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="dca17-103">utilità di analisi delle prestazioni dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="dca17-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="dca17-104">**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="dca17-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="dca17-105">Installare dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="dca17-105">Install dotnet-trace</span></span>

<span data-ttu-id="dca17-106">Installare `dotnet-trace` il [pacchetto NuGet](https://www.nuget.org/packages/dotnet-trace) con il comando [dotnet tool install:](../tools/dotnet-tool-install.md)</span><span class="sxs-lookup"><span data-stu-id="dca17-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="dca17-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="dca17-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="dca17-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dca17-108">Description</span></span>

<span data-ttu-id="dca17-109">Lo `dotnet-trace` strumento:</span><span class="sxs-lookup"><span data-stu-id="dca17-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="dca17-110">È uno strumento .NET Core multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="dca17-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="dca17-111">Abilita la raccolta di tracce .NET Core di un processo in esecuzione senza un profiler nativo.</span><span class="sxs-lookup"><span data-stu-id="dca17-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="dca17-112">Si basa sulla tecnologia `EventPipe` multipiattaforma del runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="dca17-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="dca17-113">Offre la stessa esperienza su Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="dca17-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="dca17-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dca17-114">Options</span></span>

- **`--version`**

  <span data-ttu-id="dca17-115">Visualizza la versione dell'utilità dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="dca17-115">Displays the version of the dotnet-trace utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="dca17-116">Mostra la Guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dca17-116">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="dca17-117">Comandi:</span><span class="sxs-lookup"><span data-stu-id="dca17-117">Commands</span></span>

| <span data-ttu-id="dca17-118">Comando</span><span class="sxs-lookup"><span data-stu-id="dca17-118">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="dca17-119">dotnet-trace raccogliere</span><span class="sxs-lookup"><span data-stu-id="dca17-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="dca17-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="dca17-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="dca17-121">dotnet-traccia ps</span><span class="sxs-lookup"><span data-stu-id="dca17-121">dotnet-trace ps</span></span>](#dotnet-trace-ps) |
| [<span data-ttu-id="dca17-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="dca17-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="dca17-123">dotnet-trace raccogliere</span><span class="sxs-lookup"><span data-stu-id="dca17-123">dotnet-trace collect</span></span>

<span data-ttu-id="dca17-124">Raccoglie una traccia diagnostica da un processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dca17-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="dca17-125">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="dca17-125">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="dca17-126">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dca17-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="dca17-127">Processo da cui raccogliere la traccia.</span><span class="sxs-lookup"><span data-stu-id="dca17-127">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="dca17-128">Imposta la dimensione del buffer circolare in memoria, in megabyte.</span><span class="sxs-lookup"><span data-stu-id="dca17-128">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="dca17-129">Valore predefinito 256 MB.</span><span class="sxs-lookup"><span data-stu-id="dca17-129">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="dca17-130">Percorso di output per i dati di traccia raccolti.</span><span class="sxs-lookup"><span data-stu-id="dca17-130">The output path for the collected trace data.</span></span> <span data-ttu-id="dca17-131">Se non specificato, `trace.nettrace`il valore predefinito è .</span><span class="sxs-lookup"><span data-stu-id="dca17-131">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="dca17-132">Elenco delimitato da `EventPipe` virgole di provider da abilitare.</span><span class="sxs-lookup"><span data-stu-id="dca17-132">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="dca17-133">Questi fornitori integrano `--profile <profile-name>`tutti i fornitori impliciti da .</span><span class="sxs-lookup"><span data-stu-id="dca17-133">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="dca17-134">In caso di incoerenza per un determinato provider, questa configurazione ha la precedenza sulla configurazione implicita dal profilo.</span><span class="sxs-lookup"><span data-stu-id="dca17-134">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="dca17-135">Questo elenco di provider è nel formato:</span><span class="sxs-lookup"><span data-stu-id="dca17-135">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="dca17-136">`Provider`è nella forma: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="dca17-136">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="dca17-137">`KeyValueArgs`è nella forma: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="dca17-137">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="dca17-138">Set predefinito denominato di configurazioni del provider che consente di specificare in modo conciso scenari di traccia comuni.</span><span class="sxs-lookup"><span data-stu-id="dca17-138">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format {NetTrace|Speedscope}`**

  <span data-ttu-id="dca17-139">Imposta il formato di output per la conversione del file di traccia.</span><span class="sxs-lookup"><span data-stu-id="dca17-139">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="dca17-140">Il valore predefinito è `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="dca17-140">The default is `NetTrace`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="dca17-141">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="dca17-141">dotnet-trace convert</span></span>

<span data-ttu-id="dca17-142">Converte `nettrace` le tracce in formati alternativi da utilizzare con strumenti di analisi traccia alternativi.</span><span class="sxs-lookup"><span data-stu-id="dca17-142">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="dca17-143">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="dca17-143">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="dca17-144">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dca17-144">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="dca17-145">File di traccia di input da convertire.</span><span class="sxs-lookup"><span data-stu-id="dca17-145">Input trace file to be converted.</span></span> <span data-ttu-id="dca17-146">Il valore predefinito è *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="dca17-146">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="dca17-147">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dca17-147">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="dca17-148">Imposta il formato di output per la conversione del file di traccia.</span><span class="sxs-lookup"><span data-stu-id="dca17-148">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="dca17-149">Nome file di output.</span><span class="sxs-lookup"><span data-stu-id="dca17-149">Output filename.</span></span> <span data-ttu-id="dca17-150">Verrà aggiunta l'estensione del formato di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dca17-150">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="dca17-151">dotnet-traccia ps</span><span class="sxs-lookup"><span data-stu-id="dca17-151">dotnet-trace ps</span></span>

<span data-ttu-id="dca17-152">Elenca i processi dotnet a cui è possibile collegarsi.</span><span class="sxs-lookup"><span data-stu-id="dca17-152">Lists dotnet processes that can be attached to.</span></span>

### <a name="synopsis"></a><span data-ttu-id="dca17-153">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="dca17-153">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="dca17-154">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="dca17-154">dotnet-trace list-profiles</span></span>

<span data-ttu-id="dca17-155">Elenca i profili di traccia predefiniti con una descrizione dei provider e dei filtri presenti in ogni profilo.</span><span class="sxs-lookup"><span data-stu-id="dca17-155">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="dca17-156">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="dca17-156">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="dca17-157">Raccogliere una traccia con dotnet-traceCollect a trace with dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="dca17-157">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="dca17-158">Per raccogliere tracce `dotnet-trace`utilizzando :</span><span class="sxs-lookup"><span data-stu-id="dca17-158">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="dca17-159">Ottenere l'identificatore di processo (PID) dell'applicazione .NET Core da cui raccogliere le tracce.</span><span class="sxs-lookup"><span data-stu-id="dca17-159">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="dca17-160">In Windows, è possibile utilizzare `tasklist` Task Manager o il comando, ad esempio.</span><span class="sxs-lookup"><span data-stu-id="dca17-160">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="dca17-161">Su Linux, ad `ps` esempio, il comando.</span><span class="sxs-lookup"><span data-stu-id="dca17-161">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="dca17-162">dotnet-traccia ps</span><span class="sxs-lookup"><span data-stu-id="dca17-162">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="dca17-163">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dca17-163">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="dca17-164">Il comando precedente genera un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="dca17-164">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="dca17-165">Interrompere la raccolta `<Enter>` premendo il tasto .</span><span class="sxs-lookup"><span data-stu-id="dca17-165">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="dca17-166">`dotnet-trace`terminerà la registrazione degli eventi nel file *trace.nettrace.*</span><span class="sxs-lookup"><span data-stu-id="dca17-166">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="dca17-167">Visualizzare la traccia acquisita da dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="dca17-167">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="dca17-168">In Windows, i file *.nettrace* possono essere visualizzati su [PerfView](https://github.com/microsoft/perfview) per l'analisi: per le tracce raccolte su altre piattaforme, il file di traccia può essere spostato in un computer Windows per essere visualizzato su PerfView.</span><span class="sxs-lookup"><span data-stu-id="dca17-168">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="dca17-169">In Linux, la traccia può essere visualizzata modificando il formato di output di `dotnet-trace` in `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="dca17-169">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="dca17-170">Il formato del file di `-f|--format` output `-f speedscope` può `dotnet-trace` essere `speedscope` modificato utilizzando l'opzione - produrrà un file.</span><span class="sxs-lookup"><span data-stu-id="dca17-170">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="dca17-171">È possibile `nettrace` scegliere tra (opzione `speedscope`predefinita) e .</span><span class="sxs-lookup"><span data-stu-id="dca17-171">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="dca17-172">`Speedscope`i file possono <https://www.speedscope.app>essere aperti all'indirizzo .</span><span class="sxs-lookup"><span data-stu-id="dca17-172">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="dca17-173">Il runtime di .NET Core `nettrace` genera tracce nel formato.</span><span class="sxs-lookup"><span data-stu-id="dca17-173">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="dca17-174">Le tracce vengono convertite in speedscope (se specificato) al termine della traccia.</span><span class="sxs-lookup"><span data-stu-id="dca17-174">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="dca17-175">Poiché alcune conversioni possono comportare `nettrace` la perdita di dati, il file originale viene mantenuto accanto al file convertito.</span><span class="sxs-lookup"><span data-stu-id="dca17-175">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="dca17-176">Usare dotnet-trace per raccogliere i valori dei contatori nel tempoUse dotnet-trace to collect counter values over time</span><span class="sxs-lookup"><span data-stu-id="dca17-176">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="dca17-177">`dotnet-trace`potere:</span><span class="sxs-lookup"><span data-stu-id="dca17-177">`dotnet-trace` can:</span></span>

* <span data-ttu-id="dca17-178">Utilizzare `EventCounter` per il monitoraggio dell'integrità di base in ambienti sensibili alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="dca17-178">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="dca17-179">Ad esempio, in produzione.</span><span class="sxs-lookup"><span data-stu-id="dca17-179">For example, in production.</span></span>
* <span data-ttu-id="dca17-180">Raccogliere le tracce in modo che non hanno bisogno di essere visualizzati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="dca17-180">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="dca17-181">Ad esempio, per raccogliere i valori dei contatori delle prestazioni di runtime, utilizzare il comando seguente:For example, to collect runtime performance counter values, use the following command:</span><span class="sxs-lookup"><span data-stu-id="dca17-181">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="dca17-182">Il comando precedente indica ai contatori di runtime di segnalare una volta ogni secondo per il monitoraggio dello stato leggero.</span><span class="sxs-lookup"><span data-stu-id="dca17-182">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="dca17-183">La `EventCounterIntervalSec=1` sostituzione con un valore più alto (ad esempio, 60) consente la raccolta di una traccia più piccola con minore granularità nei dati del contatore.</span><span class="sxs-lookup"><span data-stu-id="dca17-183">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="dca17-184">Il comando seguente riduce l'overhead e le dimensioni di traccia più di quello precedente:The following command reduces overhead and trace size more than the preceding one:</span><span class="sxs-lookup"><span data-stu-id="dca17-184">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="dca17-185">Il comando precedente disabilita gli eventi di runtime e il profiler dello stack gestito.</span><span class="sxs-lookup"><span data-stu-id="dca17-185">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="dca17-186">Provider .NET</span><span class="sxs-lookup"><span data-stu-id="dca17-186">.NET Providers</span></span>

<span data-ttu-id="dca17-187">Il runtime di .NET Core supporta i provider .NET seguenti.</span><span class="sxs-lookup"><span data-stu-id="dca17-187">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="dca17-188">.NET Core usa le stesse `Event Tracing for Windows (ETW)` `EventPipe` parole chiave per abilitare entrambe le tracce.</span><span class="sxs-lookup"><span data-stu-id="dca17-188">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="dca17-189">Nome provider</span><span class="sxs-lookup"><span data-stu-id="dca17-189">Provider name</span></span>                            | <span data-ttu-id="dca17-190">Informazioni</span><span class="sxs-lookup"><span data-stu-id="dca17-190">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="dca17-191">Provider di runtime</span><span class="sxs-lookup"><span data-stu-id="dca17-191">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="dca17-192">Parole chiave di runtime CLRCLR Runtime Keywords</span><span class="sxs-lookup"><span data-stu-id="dca17-192">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="dca17-193">Provider di rundown</span><span class="sxs-lookup"><span data-stu-id="dca17-193">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="dca17-194">Parole chiave run-down CLRCLR Rundown Keywords</span><span class="sxs-lookup"><span data-stu-id="dca17-194">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="dca17-195">Abilita il profiler di esempio.</span><span class="sxs-lookup"><span data-stu-id="dca17-195">Enables the sample profiler.</span></span> |
