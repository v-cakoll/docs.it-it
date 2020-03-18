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
# <a name="dotnet-counters"></a>dotnet-counters

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

## <a name="install-dotnet-counters"></a>Installare dotnet-counters

Per installare la versione `dotnet-counters` più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-counters), utilizzare il comando [dotnet tool install:](../tools/dotnet-tool-install.md)

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a>Riepilogo

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a>Descrizione

`dotnet-counters`è uno strumento di monitoraggio delle prestazioni per il monitoraggio dello stato ad hoc e l'analisi delle prestazioni di primo livello. Può osservare i valori dei <xref:System.Diagnostics.Tracing.EventCounter> contatori delle prestazioni pubblicati tramite l'API. Ad esempio, è possibile monitorare rapidamente elementi quali l'utilizzo della CPU o la frequenza delle eccezioni generate nell'applicazione .NET Core per verificare se è presente qualcosa di sospetto prima di approfondire l'analisi delle prestazioni più grave utilizzando `PerfView` o `dotnet-trace`.

## <a name="options"></a>Opzioni

- **`--version`**

  Visualizza la versione dell'utilità dotnet-counters.

- **`-h|--help`**

  Mostra la Guida della riga di comando.

## <a name="commands"></a>Comandi:

| Comando                                             |
| --------------------------------------------------- |
| [dotnet-counters raccogliere](#dotnet-counters-collect) |
| [elenco dei contatori di dotnet](#dotnet-counters-list)       |
| [monitor dotnet-counters](#dotnet-counters-monitor) |
| [dotnet-counters ps](#dotnet-counters-ps) |

## <a name="dotnet-counters-collect"></a>dotnet-counters raccogliere

Raccogliere periodicamente i valori dei contatori selezionati ed esportarli in un formato di file specificato per la post-elaborazione.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a>Opzioni

- **`-p|--process-id <PID>`**

  ID del processo da monitorare.

- **`--refresh-interval <SECONDS>`**

  Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati

- **`counter_list <COUNTERS>`**

  Elenco di contatori separati da spazi. È possibile specificare i contatori `provider_name[:counter_name]`. Se `provider_name` l'oggetto viene `counter_name`utilizzato senza una qualifica, vengono visualizzati tutti i contatori. Per individuare i nomi di provider e contatori, utilizzare il comando [dotnet-counters list.](#dotnet-counters-list)

- **`--format <csv|json>`**

  TIl formato da esportare. Attualmente disponibile: csv, json.

- **`-o|--output <output>`**

  Nome del file di output.

### <a name="examples"></a>Esempi

- Raccogliere tutti i contatori con un intervallo di aggiornamento di 3 secondi e generare un file csv come output:Collect all counters at a refresh interval of 3 seconds and generate a csv as output:

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a>elenco dei contatori di dotnet

Visualizza un elenco di nomi e descrizioni dei contatori, raggruppati per provider.

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

## <a name="dotnet-counters-monitor"></a>monitor dotnet-counters

Visualizza i valori di aggiornamento periodico dei contatori selezionati.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a>Opzioni

- **`-p|--process-id <PID>`**

  ID del processo da monitorare.

- **`--refresh-interval <SECONDS>`**

  Numero di secondi di ritardo tra l'aggiornamento dei contatori visualizzati

- **`counter_list <COUNTERS>`**

  Elenco di contatori separati da spazi. È possibile specificare i contatori `provider_name[:counter_name]`. Se `provider_name` l'oggetto viene `counter_name`utilizzato senza una qualifica, vengono visualizzati tutti i contatori. Per individuare i nomi di provider e contatori, utilizzare il comando [dotnet-counters list.](#dotnet-counters-list)

### <a name="examples"></a>Esempi

- Monitorare tutti `System.Runtime` i contatori da un intervallo di aggiornamento di 3 secondi:

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

- Monitorare solo l'utilizzo `System.Runtime`della CPU e la dimensione dell'heap GC da :

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- Monitorare i `EventCounter` valori `EventSource`da . Per ulteriori informazioni, vedere [Esercitazione: come misurare le prestazioni per eventi molto frequenti utilizzando EventCounters](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a>dotnet-counters ps

Visualizzare un elenco di processi dotnet che possono essere monitorati.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a>Esempio

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
