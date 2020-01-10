---
title: contatori dotnet-.NET Core
description: Informazioni su come installare e usare lo strumento da riga di comando DotNet-Counter.
ms.date: 10/14/2019
ms.openlocfilehash: 10af451a8b1b4d8b27da1490b99b19a4359c860f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740799"
---
# <a name="dotnet-counters"></a><span data-ttu-id="9b658-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="9b658-103">dotnet-counters</span></span>

<span data-ttu-id="9b658-104">**Questo articolo si applica a: ✓** .net core 3,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="9b658-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="9b658-105">Installare dotnet-Counters</span><span class="sxs-lookup"><span data-stu-id="9b658-105">Install dotnet-counters</span></span>

<span data-ttu-id="9b658-106">Per installare la versione di rilascio più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-counters)di `dotnet-counters`, usare il comando [DotNet tool install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="9b658-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="9b658-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9b658-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="9b658-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b658-108">Description</span></span>

<span data-ttu-id="9b658-109">`dotnet-counters` è uno strumento di monitoraggio delle prestazioni per il monitoraggio dell'integrità ad hoc e l'analisi delle prestazioni di primo livello.</span><span class="sxs-lookup"><span data-stu-id="9b658-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="9b658-110">Può osservare i valori dei contatori delle prestazioni pubblicati tramite l'API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="9b658-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="9b658-111">Ad esempio, è possibile monitorare rapidamente elementi come l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core per verificare se c'è qualcosa di sospetto prima di approfondire le analisi delle prestazioni più gravi usando `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="9b658-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="9b658-112">Options</span><span class="sxs-lookup"><span data-stu-id="9b658-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="9b658-113">Visualizza la versione dell'utilità DotNet-Counters.</span><span class="sxs-lookup"><span data-stu-id="9b658-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9b658-114">Mostra la guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="9b658-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="9b658-115">Comandi</span><span class="sxs-lookup"><span data-stu-id="9b658-115">Commands</span></span>

| <span data-ttu-id="9b658-116">Comando</span><span class="sxs-lookup"><span data-stu-id="9b658-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="9b658-117">elenco di contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="9b658-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="9b658-118">monitoraggio contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="9b658-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="9b658-119">elenco di contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="9b658-119">dotnet-counters list</span></span>

<span data-ttu-id="9b658-120">Visualizza un elenco di nomi e descrizioni dei contatori raggruppati per provider.</span><span class="sxs-lookup"><span data-stu-id="9b658-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9b658-121">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9b658-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="9b658-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b658-122">Example</span></span>

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

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="9b658-123">monitoraggio contatori DotNet</span><span class="sxs-lookup"><span data-stu-id="9b658-123">dotnet-counters monitor</span></span>

<span data-ttu-id="9b658-124">Visualizza i valori di aggiornamento periodico dei contatori selezionati.</span><span class="sxs-lookup"><span data-stu-id="9b658-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9b658-125">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9b658-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="9b658-126">Options</span><span class="sxs-lookup"><span data-stu-id="9b658-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="9b658-127">ID del processo da monitorare.</span><span class="sxs-lookup"><span data-stu-id="9b658-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="9b658-128">Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati</span><span class="sxs-lookup"><span data-stu-id="9b658-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="9b658-129">Elenco di contatori separato da spazi.</span><span class="sxs-lookup"><span data-stu-id="9b658-129">A space separated list of counters.</span></span> <span data-ttu-id="9b658-130">È possibile specificare i contatori `provider_name[:counter_name]`.</span><span class="sxs-lookup"><span data-stu-id="9b658-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="9b658-131">Se il `provider_name` viene usato senza una `counter_name`qualificata, vengono visualizzati tutti i contatori.</span><span class="sxs-lookup"><span data-stu-id="9b658-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="9b658-132">Per individuare i nomi del provider e del contatore, utilizzare il comando [DotNet-counts list](#dotnet-counters-list) .</span><span class="sxs-lookup"><span data-stu-id="9b658-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="9b658-133">Esempi</span><span class="sxs-lookup"><span data-stu-id="9b658-133">Examples</span></span>

- <span data-ttu-id="9b658-134">Monitora tutti i contatori da `System.Runtime` a un intervallo di aggiornamento di 3 secondi:</span><span class="sxs-lookup"><span data-stu-id="9b658-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="9b658-135">Monitorare solo l'utilizzo della CPU e le dimensioni dell'heap GC da `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="9b658-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="9b658-136">Monitorare `EventCounter` valori da `EventSource`definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9b658-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="9b658-137">Per altre informazioni, vedere [esercitazione: come misurare le prestazioni per eventi molto frequenti usando EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9b658-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
