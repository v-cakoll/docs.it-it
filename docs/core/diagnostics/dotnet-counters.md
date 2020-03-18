---
title: dotnet-counters - .NET Core
description: Informazioni su come installare e utilizzare lo strumento da riga di comando dotnet-counter.
ms.date: 02/26/2020
ms.openlocfilehash: dc95297478784ca06fe442a939f8489a40b29da7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147178"
---
# <a name="dotnet-counters"></a><span data-ttu-id="5e543-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="5e543-103">dotnet-counters</span></span>

<span data-ttu-id="5e543-104">**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="5e543-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="5e543-105">Installare dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="5e543-105">Install dotnet-counters</span></span>

<span data-ttu-id="5e543-106">Per installare la versione `dotnet-counters` più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-counters), utilizzare il comando [dotnet tool install:](../tools/dotnet-tool-install.md)</span><span class="sxs-lookup"><span data-stu-id="5e543-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="5e543-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5e543-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="5e543-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e543-108">Description</span></span>

<span data-ttu-id="5e543-109">`dotnet-counters`è uno strumento di monitoraggio delle prestazioni per il monitoraggio dello stato ad hoc e l'analisi delle prestazioni di primo livello.</span><span class="sxs-lookup"><span data-stu-id="5e543-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="5e543-110">Può osservare i valori dei <xref:System.Diagnostics.Tracing.EventCounter> contatori delle prestazioni pubblicati tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="5e543-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="5e543-111">Ad esempio, è possibile monitorare rapidamente elementi quali l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core per verificare se è presente qualcosa di sospetto prima di approfondire l'analisi delle prestazioni più grave utilizzando `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="5e543-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="5e543-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5e543-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="5e543-113">Visualizza la versione dell'utilità dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="5e543-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5e543-114">Mostra la Guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5e543-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="5e543-115">Comandi:</span><span class="sxs-lookup"><span data-stu-id="5e543-115">Commands</span></span>

| <span data-ttu-id="5e543-116">Comando</span><span class="sxs-lookup"><span data-stu-id="5e543-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="5e543-117">dotnet-counters raccogliere</span><span class="sxs-lookup"><span data-stu-id="5e543-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="5e543-118">elenco dei contatori di dotnet</span><span class="sxs-lookup"><span data-stu-id="5e543-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="5e543-119">monitor dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="5e543-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="5e543-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="5e543-120">dotnet-counters ps</span></span>](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="5e543-121">dotnet-counters raccogliere</span><span class="sxs-lookup"><span data-stu-id="5e543-121">dotnet-counters collect</span></span>

<span data-ttu-id="5e543-122">Raccogliere periodicamente i valori dei contatori selezionati ed esportarli in un formato di file specificato per la post-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="5e543-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5e543-123">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5e543-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="5e543-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5e543-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="5e543-125">ID del processo da monitorare.</span><span class="sxs-lookup"><span data-stu-id="5e543-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="5e543-126">Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati</span><span class="sxs-lookup"><span data-stu-id="5e543-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="5e543-127">Elenco di contatori separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="5e543-127">A space separated list of counters.</span></span> <span data-ttu-id="5e543-128">È possibile specificare i contatori `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="5e543-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="5e543-129">Se `provider_name` l'oggetto viene `counter_name`utilizzato senza una qualifica, vengono visualizzati tutti i contatori.</span><span class="sxs-lookup"><span data-stu-id="5e543-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="5e543-130">Per individuare i nomi di provider e contatori, utilizzare il comando [dotnet-counters list.](#dotnet-counters-list)</span><span class="sxs-lookup"><span data-stu-id="5e543-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="5e543-131">TIl formato da esportare.</span><span class="sxs-lookup"><span data-stu-id="5e543-131">TThe format to be exported.</span></span> <span data-ttu-id="5e543-132">Attualmente disponibile: csv, json.</span><span class="sxs-lookup"><span data-stu-id="5e543-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="5e543-133">Nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="5e543-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="5e543-134">Esempi</span><span class="sxs-lookup"><span data-stu-id="5e543-134">Examples</span></span>

- <span data-ttu-id="5e543-135">Raccogliere tutti i contatori con un intervallo di aggiornamento di 3 secondi e generare un file csv come output:Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span><span class="sxs-lookup"><span data-stu-id="5e543-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="5e543-136">elenco dei contatori di dotnet</span><span class="sxs-lookup"><span data-stu-id="5e543-136">dotnet-counters list</span></span>

<span data-ttu-id="5e543-137">Visualizza un elenco di nomi e descrizioni dei contatori, raggruppati per provider.</span><span class="sxs-lookup"><span data-stu-id="5e543-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5e543-138">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5e543-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="5e543-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e543-139">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="5e543-140">monitor dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="5e543-140">dotnet-counters monitor</span></span>

<span data-ttu-id="5e543-141">Visualizza i valori di aggiornamento periodico dei contatori selezionati.</span><span class="sxs-lookup"><span data-stu-id="5e543-141">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5e543-142">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5e543-142">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="5e543-143">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5e543-143">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="5e543-144">ID del processo da monitorare.</span><span class="sxs-lookup"><span data-stu-id="5e543-144">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="5e543-145">Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati</span><span class="sxs-lookup"><span data-stu-id="5e543-145">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="5e543-146">Elenco di contatori separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="5e543-146">A space separated list of counters.</span></span> <span data-ttu-id="5e543-147">È possibile specificare i contatori `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="5e543-147">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="5e543-148">Se `provider_name` l'oggetto viene `counter_name`utilizzato senza una qualifica, vengono visualizzati tutti i contatori.</span><span class="sxs-lookup"><span data-stu-id="5e543-148">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="5e543-149">Per individuare i nomi di provider e contatori, utilizzare il comando [dotnet-counters list.](#dotnet-counters-list)</span><span class="sxs-lookup"><span data-stu-id="5e543-149">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="5e543-150">Esempi</span><span class="sxs-lookup"><span data-stu-id="5e543-150">Examples</span></span>

- <span data-ttu-id="5e543-151">Monitorare tutti `System.Runtime` i contatori da un intervallo di aggiornamento di 3 secondi:</span><span class="sxs-lookup"><span data-stu-id="5e543-151">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="5e543-152">Monitorare solo l'utilizzo `System.Runtime`della CPU e la dimensione dell'heap GC da :</span><span class="sxs-lookup"><span data-stu-id="5e543-152">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="5e543-153">Monitorare i `EventCounter` valori `EventSource`da .</span><span class="sxs-lookup"><span data-stu-id="5e543-153">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="5e543-154">Per ulteriori informazioni, vedere [Esercitazione: come misurare le prestazioni per eventi molto frequenti utilizzando EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span><span class="sxs-lookup"><span data-stu-id="5e543-154">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="5e543-155">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="5e543-155">dotnet-counters ps</span></span>

<span data-ttu-id="5e543-156">Visualizzare un elenco di processi dotnet che possono essere monitorati.</span><span class="sxs-lookup"><span data-stu-id="5e543-156">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5e543-157">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5e543-157">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="5e543-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e543-158">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
