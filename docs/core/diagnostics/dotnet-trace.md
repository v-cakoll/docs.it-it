---
title: strumento dotnet-trace - .NET Core
description: Installazione e utilizzo dello strumento da riga di comando dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: b19b159636fbf57fa2d461b398fcf9234aab491c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76737657"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>utilità di analisi delle prestazioni dotnet-trace

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

## <a name="install-dotnet-trace"></a>Installare dotnet-trace

Installare `dotnet-trace` il [pacchetto NuGet](https://www.nuget.org/packages/dotnet-trace) con il comando [dotnet tool install:](../tools/dotnet-tool-install.md)

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Riepilogo

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Descrizione

Lo `dotnet-trace` strumento:

* È uno strumento .NET Core multipiattaforma.
* Abilita la raccolta di tracce .NET Core di un processo in esecuzione senza un profiler nativo.
* Si basa sulla tecnologia `EventPipe` multipiattaforma del runtime di .NET Core.
* Offre la stessa esperienza su Windows, Linux o macOS.

## <a name="options"></a>Opzioni

- **`--version`**

  Visualizza la versione dell'utilità dotnet-counters.

- **`-h|--help`**

  Mostra la Guida della riga di comando.

## <a name="commands"></a>Comandi:

| Comando                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace raccogliere](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-traccia ps](#dotnet-trace-ps) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace raccogliere

Raccoglie una traccia diagnostica da un processo in esecuzione.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>Opzioni

- **`-p|--process-id <PID>`**

  Processo da cui raccogliere la traccia.

- **`--buffersize <size>`**

  Imposta la dimensione del buffer circolare in memoria, in megabyte. Valore predefinito 256 MB.

- **`-o|--output <trace-file-path>`**

  Percorso di output per i dati di traccia raccolti. Se non specificato, `trace.nettrace`il valore predefinito è .

- **`--providers <list-of-comma-separated-providers>`**

  Elenco delimitato da `EventPipe` virgole di provider da abilitare. Questi fornitori integrano `--profile <profile-name>`tutti i fornitori impliciti da . In caso di incoerenza per un determinato provider, questa configurazione ha la precedenza sulla configurazione implicita dal profilo.

  Questo elenco di provider è nel formato:

  - `Provider[,Provider]`
  - `Provider`è nella forma: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs`è nella forma: `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Set predefinito denominato di configurazioni del provider che consente di specificare in modo conciso scenari di traccia comuni.

- **`--format {NetTrace|Speedscope}`**

  Imposta il formato di output per la conversione del file di traccia. Il valore predefinito è `NetTrace`.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Converte `nettrace` le tracce in formati alternativi da utilizzare con strumenti di analisi traccia alternativi.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>Argomenti

- **`<input-filename>`**

  File di traccia di input da convertire. Il valore predefinito è *trace.nettrace*.

### <a name="options"></a>Opzioni

- **`--format <NetTrace|Speedscope>`**

  Imposta il formato di output per la conversione del file di traccia.

- **`-o|--output <output-filename>`**

  Nome file di output. Verrà aggiunta l'estensione del formato di destinazione.

## <a name="dotnet-trace-ps"></a>dotnet-traccia ps

Elenca i processi dotnet a cui è possibile collegarsi.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Elenca i profili di traccia predefiniti con una descrizione dei provider e dei filtri presenti in ogni profilo.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Raccogliere una traccia con dotnet-traceCollect a trace with dotnet-trace

Per raccogliere tracce `dotnet-trace`utilizzando :

- Ottenere l'identificatore di processo (PID) dell'applicazione .NET Core da cui raccogliere le tracce.

  - In Windows, è possibile utilizzare `tasklist` Task Manager o il comando, ad esempio.
  - Su Linux, ad `ps` esempio, il comando.
  - [dotnet-traccia ps](#dotnet-trace-ps)

- Eseguire il comando seguente:

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  Il comando precedente genera un output simile al seguente:

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- Interrompere la raccolta `<Enter>` premendo il tasto . `dotnet-trace`terminerà la registrazione degli eventi nel file *trace.nettrace.*

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Visualizzare la traccia acquisita da dotnet-trace

In Windows, i file *.nettrace* possono essere visualizzati su [PerfView](https://github.com/microsoft/perfview) per l'analisi: per le tracce raccolte su altre piattaforme, il file di traccia può essere spostato in un computer Windows per essere visualizzato su PerfView.

In Linux, la traccia può essere visualizzata modificando il formato di output di `dotnet-trace` in `speedscope`. Il formato del file di `-f|--format` output `-f speedscope` può `dotnet-trace` essere `speedscope` modificato utilizzando l'opzione - produrrà un file. È possibile `nettrace` scegliere tra (opzione `speedscope`predefinita) e . `Speedscope`i file possono <https://www.speedscope.app>essere aperti all'indirizzo .

> [!NOTE]
> Il runtime di .NET Core `nettrace` genera tracce nel formato. Le tracce vengono convertite in speedscope (se specificato) al termine della traccia. Poiché alcune conversioni possono comportare `nettrace` la perdita di dati, il file originale viene mantenuto accanto al file convertito.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Usare dotnet-trace per raccogliere i valori dei contatori nel tempoUse dotnet-trace to collect counter values over time

`dotnet-trace`potere:

* Utilizzare `EventCounter` per il monitoraggio dell'integrità di base in ambienti sensibili alle prestazioni. Ad esempio, in produzione.
* Raccogliere le tracce in modo che non hanno bisogno di essere visualizzati in tempo reale.

Ad esempio, per raccogliere i valori dei contatori delle prestazioni di runtime, utilizzare il comando seguente:For example, to collect runtime performance counter values, use the following command:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Il comando precedente indica ai contatori di runtime di segnalare una volta ogni secondo per il monitoraggio dello stato leggero. La `EventCounterIntervalSec=1` sostituzione con un valore più alto (ad esempio, 60) consente la raccolta di una traccia più piccola con minore granularità nei dati del contatore.

Il comando seguente riduce l'overhead e le dimensioni di traccia più di quello precedente:The following command reduces overhead and trace size more than the preceding one:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

Il comando precedente disabilita gli eventi di runtime e il profiler dello stack gestito.

## <a name="net-providers"></a>Provider .NET

Il runtime di .NET Core supporta i provider .NET seguenti. .NET Core usa le stesse `Event Tracing for Windows (ETW)` `EventPipe` parole chiave per abilitare entrambe le tracce.

| Nome provider                            | Informazioni |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Provider di runtime](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Parole chiave di runtime CLRCLR Runtime Keywords](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Provider di rundown](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Parole chiave run-down CLRCLR Rundown Keywords](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Abilita il profiler di esempio. |
