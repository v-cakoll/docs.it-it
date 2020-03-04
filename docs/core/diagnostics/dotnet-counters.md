---
title: contatori dotnet-.NET Core
description: Informazioni su come installare e usare lo strumento da riga di comando DotNet-Counter.
ms.date: 02/26/2020
ms.openlocfilehash: 88f701a60d0ee03dd0236ae54c57679943e14939
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157882"
---
# <a name="dotnet-counters"></a><span data-ttu-id="3f210-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="3f210-103">dotnet-counters</span></span>

<span data-ttu-id="3f210-104">**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="3f210-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="3f210-105">Installare dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="3f210-105">Install dotnet-counters</span></span>

<span data-ttu-id="3f210-106">Per installare la versione di rilascio più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-counters)di `dotnet-counters`, usare il comando [DotNet tool install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="3f210-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="3f210-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3f210-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="3f210-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f210-108">Description</span></span>

<span data-ttu-id="3f210-109">`dotnet-counters` è uno strumento di monitoraggio delle prestazioni per il monitoraggio dell'integrità ad hoc e l'analisi delle prestazioni di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3f210-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="3f210-110">Può osservare i valori dei contatori delle prestazioni pubblicati tramite l'API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="3f210-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="3f210-111">Ad esempio, è possibile monitorare rapidamente elementi come l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core per verificare se c'è qualcosa di sospetto prima di approfondire le analisi delle prestazioni più gravi usando `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="3f210-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="3f210-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3f210-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="3f210-113">Visualizza la versione dell'utilità DotNet-Counters.</span><span class="sxs-lookup"><span data-stu-id="3f210-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3f210-114">Mostra la guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3f210-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="3f210-115">Comandi:</span><span class="sxs-lookup"><span data-stu-id="3f210-115">Commands</span></span>

| <span data-ttu-id="3f210-116">Comando</span><span class="sxs-lookup"><span data-stu-id="3f210-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="3f210-117">DotNet-contatori Collect</span><span class="sxs-lookup"><span data-stu-id="3f210-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="3f210-118">elenco di contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="3f210-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="3f210-119">monitoraggio contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="3f210-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="3f210-120">PS dei contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="3f210-120">dotnet-counters ps</span></span>](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="3f210-121">DotNet-contatori Collect</span><span class="sxs-lookup"><span data-stu-id="3f210-121">dotnet-counters collect</span></span>

<span data-ttu-id="3f210-122">Raccogliere periodicamente i valori dei contatori selezionati ed esportarli in un formato di file specificato per la post-elaborazione.</span><span class="sxs-lookup"><span data-stu-id="3f210-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3f210-123">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3f210-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="3f210-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3f210-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="3f210-125">ID del processo da monitorare.</span><span class="sxs-lookup"><span data-stu-id="3f210-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="3f210-126">Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati</span><span class="sxs-lookup"><span data-stu-id="3f210-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="3f210-127">Elenco di contatori separato da spazi.</span><span class="sxs-lookup"><span data-stu-id="3f210-127">A space separated list of counters.</span></span> <span data-ttu-id="3f210-128">È possibile specificare i contatori `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="3f210-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="3f210-129">Se il `provider_name` viene usato senza una `counter_name`qualificata, vengono visualizzati tutti i contatori.</span><span class="sxs-lookup"><span data-stu-id="3f210-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="3f210-130">Per individuare i nomi del provider e del contatore, utilizzare il comando [DotNet-counts list](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="3f210-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="3f210-131">Formato TImpossibile da esportare.</span><span class="sxs-lookup"><span data-stu-id="3f210-131">TThe format to be exported.</span></span> <span data-ttu-id="3f210-132">Attualmente disponibile: CSV, JSON.</span><span class="sxs-lookup"><span data-stu-id="3f210-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="3f210-133">Nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="3f210-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="3f210-134">Esempi</span><span class="sxs-lookup"><span data-stu-id="3f210-134">Examples</span></span>

- <span data-ttu-id="3f210-135">Raccogliere tutti i contatori in un intervallo di aggiornamento di 3 secondi e generare un volume CSV come output:</span><span class="sxs-lookup"><span data-stu-id="3f210-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="3f210-136">elenco di contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="3f210-136">dotnet-counters list</span></span>

<span data-ttu-id="3f210-137">Visualizza un elenco di nomi e descrizioni dei contatori raggruppati per provider.</span><span class="sxs-lookup"><span data-stu-id="3f210-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3f210-138">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3f210-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="3f210-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f210-139">Example</span></span>

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

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="3f210-140">monitoraggio contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="3f210-140">dotnet-counters monitor</span></span>

<span data-ttu-id="3f210-141">Visualizza i valori di aggiornamento periodico dei contatori selezionati.</span><span class="sxs-lookup"><span data-stu-id="3f210-141">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3f210-142">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3f210-142">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="3f210-143">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3f210-143">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="3f210-144">ID del processo da monitorare.</span><span class="sxs-lookup"><span data-stu-id="3f210-144">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="3f210-145">Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati</span><span class="sxs-lookup"><span data-stu-id="3f210-145">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="3f210-146">Elenco di contatori separato da spazi.</span><span class="sxs-lookup"><span data-stu-id="3f210-146">A space separated list of counters.</span></span> <span data-ttu-id="3f210-147">È possibile specificare i contatori `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="3f210-147">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="3f210-148">Se il `provider_name` viene usato senza una `counter_name`qualificata, vengono visualizzati tutti i contatori.</span><span class="sxs-lookup"><span data-stu-id="3f210-148">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="3f210-149">Per individuare i nomi del provider e del contatore, utilizzare il comando [DotNet-counts list](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="3f210-149">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="3f210-150">Esempi</span><span class="sxs-lookup"><span data-stu-id="3f210-150">Examples</span></span>

- <span data-ttu-id="3f210-151">Monitora tutti i contatori da `System.Runtime` a un intervallo di aggiornamento di 3 secondi:</span><span class="sxs-lookup"><span data-stu-id="3f210-151">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="3f210-152">Monitorare solo l'utilizzo della CPU e le dimensioni dell'heap GC da `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="3f210-152">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="3f210-153">Monitorare `EventCounter` valori da `EventSource`definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3f210-153">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="3f210-154">Per altre informazioni, vedere [esercitazione: come misurare le prestazioni per eventi molto frequenti usando EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span><span class="sxs-lookup"><span data-stu-id="3f210-154">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="3f210-155">PS dei contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="3f210-155">dotnet-counters ps</span></span> 

<span data-ttu-id="3f210-156">Visualizza un elenco di processi DotNet che è possibile monitorare.</span><span class="sxs-lookup"><span data-stu-id="3f210-156">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="3f210-157">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3f210-157">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="3f210-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f210-158">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
