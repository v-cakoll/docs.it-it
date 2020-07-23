---
title: strumento DotNet-Trace-.NET Core
description: Installazione e utilizzo dello strumento da riga di comando DotNet-Trace.
ms.date: 11/21/2019
ms.openlocfilehash: 6dd968dc49522229dca02c0dc6f3de898026dd82
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924851"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>utilità di analisi delle prestazioni DotNet-Trace

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

## <a name="install-dotnet-trace"></a>Installare dotnet-Trace

Installare `dotnet-trace` il [pacchetto NuGet](https://www.nuget.org/packages/dotnet-trace) con il comando [DotNet tool install](../tools/dotnet-tool-install.md) :

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
* È basato sulla tecnologia multipiattaforma `EventPipe` del runtime di .NET Core.
* Offre la stessa esperienza in Windows, Linux o macOS.

## <a name="options"></a>Opzioni

- **`--version`**

  Visualizza la versione dell'utilità DotNet-Trace.

- **`-h|--help`**

  Mostra la guida della riga di comando.

## <a name="commands"></a>Comandi

| Comando                                                   |
|-----------------------------------------------------------|
| [raccolta traccia DotNet](#dotnet-trace-collect)             |
| [conversione DotNet-Trace](#dotnet-trace-convert)             |
| [PS DotNet-Trace](#dotnet-trace-ps)                       |
| [elenco DotNet-Trace-profili](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a>raccolta traccia DotNet

Raccoglie una traccia di diagnostica da un processo in esecuzione.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>Opzioni

- **`-p|--process-id <PID>`**

  Processo da cui raccogliere la traccia.

- **`--buffersize <size>`**

  Imposta la dimensione del buffer circolare in memoria, in megabyte. Valore predefinito di 256 MB.

- **`-o|--output <trace-file-path>`**

  Percorso di output per i dati di traccia raccolti. Se non è specificato, il valore predefinito è `trace.nettrace` .

- **`--providers <list-of-comma-separated-providers>`**

  Elenco delimitato da virgole di `EventPipe` provider da abilitare. Questi provider integrano tutti i provider impliciti in `--profile <profile-name>` . Se è presente un'incoerenza per un determinato provider, questa configurazione ha la precedenza sulla configurazione implicita del profilo.

  Questo elenco di provider ha il formato seguente:

  - `Provider[,Provider]`
  - `Provider`il formato è: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]` .
  - `KeyValueArgs`il formato è: `[key1=value1][;key2=value2]` .

- **`--profile <profile-name>`**

  Set predefinito di configurazioni del provider che consente di specificare brevemente gli scenari di traccia comuni.

- **`--format {NetTrace|Speedscope}`**

  Imposta il formato di output per la conversione del file di traccia. Il valore predefinito è `NetTrace`.

## <a name="dotnet-trace-convert"></a>conversione DotNet-Trace

Converte `nettrace` le tracce in formati alternativi per l'utilizzo con strumenti di analisi di traccia alternativi.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>Argomenti

- **`<input-filename>`**

  File di traccia di input da convertire. Il valore predefinito è *Trace. NetTrace*.

### <a name="options"></a>Opzioni

- **`--format <NetTrace|Speedscope>`**

  Imposta il formato di output per la conversione del file di traccia.

- **`-o|--output <output-filename>`**

  Nome file di output. Verrà aggiunta l'estensione del formato di destinazione.

## <a name="dotnet-trace-ps"></a>PS DotNet-Trace

Elenca i processi dotNET a cui è possibile collegarsi.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>elenco DotNet-Trace-profili

Elenca i profili di traccia predefiniti con una descrizione dei provider e dei filtri presenti in ciascun profilo.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Raccogliere una traccia con DotNet-Trace

Per raccogliere le tracce utilizzando `dotnet-trace` :

- Ottenere l'identificatore di processo (PID) dell'applicazione .NET Core da cui raccogliere le tracce.

  - In Windows, ad esempio, è possibile usare Gestione attività o il `tasklist` comando.
  - In Linux, ad esempio, il `ps` comando.
  - [PS DotNet-Trace](#dotnet-trace-ps)

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

- Arrestare la raccolta premendo il `<Enter>` tasto. `dotnet-trace`completerà la registrazione degli eventi nel file *Trace. NetTrace* .

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Visualizzare la traccia acquisita da DotNet-Trace

In Windows è possibile visualizzare i file con *estensione NetTrace* in [PerfView](https://github.com/microsoft/perfview) per l'analisi: per le tracce raccolte su altre piattaforme, il file di traccia può essere spostato in un computer Windows per essere visualizzato in PerfView.

In Linux è possibile visualizzare la traccia cambiando il formato di output di `dotnet-trace` in `speedscope` . Il formato del file di output può essere modificato usando l' `-f|--format` opzione. `-f speedscope` verrà `dotnet-trace` generato un `speedscope` file. È possibile scegliere tra `nettrace` (opzione predefinita) e `speedscope` . `Speedscope`i file possono essere aperti in <https://www.speedscope.app> .

> [!NOTE]
> Il runtime di .NET Core genera tracce nel `nettrace` formato. Le tracce vengono convertite in speedscope (se specificato) dopo che la traccia è stata completata. Poiché alcune conversioni possono comportare la perdita di dati, il `nettrace` file originale viene mantenuto accanto al file convertito.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Usare DotNet-Trace per raccogliere i valori dei contatori nel tempo

`dotnet-trace`possibile

* Usare `EventCounter` per il monitoraggio dello stato di base in ambienti sensibili alle prestazioni. Ad esempio, nell'ambiente di produzione.
* Raccogli tracce in modo che non debbano essere visualizzate in tempo reale.

Per raccogliere i valori dei contatori delle prestazioni in fase di esecuzione, ad esempio, usare il comando seguente:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Il comando precedente indica ai contatori di runtime di segnalare una volta al secondo per il monitoraggio di stato leggero. `EventCounterIntervalSec=1`La sostituzione con un valore superiore (ad esempio, 60) consente la raccolta di una traccia più piccola con una minore granularità nei dati del contatore.

Il seguente comando riduce le dimensioni del sovraccarico e della traccia rispetto a quello precedente:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

Il comando precedente Disabilita gli eventi di runtime e il profiler dello stack gestito.

## <a name="net-providers"></a>Provider .NET

Il runtime di .NET Core supporta i provider .NET seguenti. .NET Core usa le stesse parole chiave per abilitare `Event Tracing for Windows (ETW)` le `EventPipe` tracce e.

| Nome provider                            | Informazioni |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Provider di runtime](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Parole chiave di runtime CLR](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Provider di rundown](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Parole chiave di rundown CLR](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Abilita il profiler di esempio. |
