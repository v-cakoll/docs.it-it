---
title: contatori dotnet-.NET Core
description: Informazioni su come installare e usare lo strumento da riga di comando DotNet-Counter.
ms.date: 10/14/2019
ms.openlocfilehash: 399d5908e8ac52bcd4a20c1a819fc6c99f4de2f4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737702"
---
# <a name="dotnet-counters"></a>dotnet-counters

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

## <a name="install-dotnet-counters"></a>Installare dotnet-Counters

Per installare la versione di rilascio più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-counters)di `dotnet-counters`, usare il comando [DotNet tool install](../tools/dotnet-tool-install.md) :

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a>Riepilogo

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>Descrizione

`dotnet-counters` è uno strumento di monitoraggio delle prestazioni per il monitoraggio dell'integrità ad hoc e l'analisi delle prestazioni di primo livello. Può osservare i valori dei contatori delle prestazioni pubblicati tramite l'API <xref:System.Diagnostics.Tracing.EventCounter>. Ad esempio, è possibile monitorare rapidamente elementi come l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core per verificare se c'è qualcosa di sospetto prima di approfondire le analisi delle prestazioni più gravi usando `PerfView` o `dotnet-trace`.

## <a name="options"></a>Options

- **`--version`**

  Visualizza la versione dell'utilità DotNet-Counters.

- **`-h|--help`**

  Mostra la guida della riga di comando.

## <a name="commands"></a>Comandi

| Comando                                             |
| --------------------------------------------------- |
| [elenco di contatori DotNet](#dotnet-counters-list)       |
| [monitoraggio contatori DotNet](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a>elenco di contatori DotNet

Visualizza un elenco di nomi e descrizioni dei contatori raggruppati per provider.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a>Esempio

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

## <a name="dotnet-counters-monitor"></a>monitoraggio contatori DotNet

Visualizza i valori di aggiornamento periodico dei contatori selezionati.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a>Options

- **`-p|--process-id <PID>`**

  ID del processo da monitorare.

- **`--refresh-interval <SECONDS>`**

  Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati

- **`counter_list <COUNTERS>`**

  Elenco di contatori separato da spazi. È possibile specificare i contatori `provider_name[:counter_name]`. Se il `provider_name` viene usato senza una `counter_name`qualificata, vengono visualizzati tutti i contatori. Per individuare i nomi del provider e del contatore, utilizzare il comando [DotNet-counts list](#dotnet-counters-list) .

### <a name="examples"></a>Esempi

- Monitora tutti i contatori da `System.Runtime` a un intervallo di aggiornamento di 3 secondi:

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

- Monitorare solo l'utilizzo della CPU e le dimensioni dell'heap GC da `System.Runtime`:

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Monitorare `EventCounter` valori da `EventSource`definiti dall'utente. Per altre informazioni, vedere [esercitazione: come misurare le prestazioni per eventi molto frequenti usando EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
