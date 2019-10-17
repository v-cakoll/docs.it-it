---
title: DotNet-Trace-.NET Core
description: Installazione e utilizzo dello strumento da riga di comando DotNet-Trace.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321582"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a>Trace for Performance Analysis Utility (`dotnet-trace`)

**Questo articolo si applica a:** .net core 3,0 SDK e versioni successive

## <a name="installing-dotnet-trace"></a>Installazione di `dotnet-trace`

Per installare la versione di rilascio più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-trace)di `dotnet-trace`, usare il comando [DotNet tool install](../tools/dotnet-tool-install.md) :

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Riepilogo

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Descrizione

Lo strumento `dotnet-trace` è uno strumento globale dell'interfaccia della riga di comando multipiattaforma che consente di raccogliere le tracce di .NET Core di un processo in esecuzione senza alcun profiler nativo. È basato sulla tecnologia di `EventPipe` multipiattaforma del runtime di .NET Core. `dotnet-trace` offre la stessa esperienza in Windows, Linux o macOS.

## <a name="options"></a>Opzioni

- **`--version`**

Visualizzare la versione dell'utilità DotNet-Counters.

- **`-h|--help`**

Mostra la guida della riga di comando.

## <a name="commands"></a>Comandi

| Comando                                                     |
| ----------------------------------------------------------- |
| [raccolta traccia DotNet](#dotnet-trace-collect)               |
| [conversione DotNet-Trace](#dotnet-trace-convert)               |
| [elenco DotNet-Trace-processi](#dotnet-trace-list-processes) |
| [elenco DotNet-Trace-profili](#dotnet-trace-list-profiles)   |

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

  Imposta la dimensione del buffer circolare in memoria in megabyte. Valore predefinito di 256 MB.

- **`-o|--output <trace-file-path>`**

  Percorso di output per i dati di traccia raccolti. Se non viene specificato, il valore predefinito è `trace.nettrace`.

- **`--providers <list-of-comma-separated-providers>`**

  Elenco delimitato da virgole di provider di `EventPipe` da abilitare. Questi provider integrano tutti i provider impliciti dal `--profile <profile-name>`. Se è presente un'incoerenza per un determinato provider, la configurazione ha la precedenza sulla configurazione implicita del profilo.

  Questo elenco di provider ha il formato seguente:

  - `Provider[,Provider]`
  - il formato del `Provider` è: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - il formato del `KeyValueArgs` è: `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Set predefinito di configurazioni del provider che consente di specificare brevemente gli scenari di traccia comuni.

- **`--format <NetTrace|Speedscope>`**

  Imposta il formato di output per la conversione del file di traccia.

## <a name="dotnet-trace-convert"></a>conversione DotNet-Trace

Converte `nettrace` tracce in formati alternativi per l'utilizzo con strumenti di analisi di traccia alternativi.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>argomenti

- **`<input-filename>`**

  File di traccia di input da convertire. Il valore predefinito è *Trace. NetTrace*.

### <a name="options"></a>Opzioni

- **`--format <NetTrace|Speedscope>`**

  Imposta il formato di output per la conversione del file di traccia.

- **`-o|--output <output-filename>`**

  Nome file di output. Verrà aggiunta l'estensione del formato di destinazione.

## <a name="dotnet-trace-list-processes"></a>elenco DotNet-Trace-processi

Elenca i processi DotNet che è possibile tracciare.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>elenco DotNet-Trace-profili

Elenca i profili di traccia predefiniti con una descrizione dei provider e dei filtri presenti in ciascun profilo.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Raccogliere una traccia con `dotnet-trace`

- Per raccogliere le tracce con `dotnet-trace`, è necessario innanzitutto individuare l'identificatore di processo (PID) dell'applicazione .NET Core da cui raccogliere le tracce.

  - In Windows sono disponibili opzioni come l'utilizzo di gestione attività o del comando `tasklist`.
  - In Linux l'opzione Trivial potrebbe usare `ps` comando.

È anche possibile usare il comando [DotNet-Trace list-processes](#dotnet-trace-list-processes) per scoprire quali processi di .NET Core sono in esecuzione, insieme ai relativi PID.

- Eseguire quindi il comando seguente:

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- Infine, arrestare la raccolta premendo il tasto `<Enter>` e `dotnet-trace` terminerà la registrazione degli eventi nel file `trace.nettrace`.

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a>Visualizzazione della traccia acquisita da `dotnet-trace`

In Windows è possibile visualizzare i file di `.nettrace` in [PerfView](https://github.com/microsoft/perfview) per l'analisi, esattamente come le tracce raccolte con ETW o LTTng. Per le tracce raccolte in Linux, è possibile spostare la traccia in un computer Windows per la visualizzazione in PerfView.

È anche possibile visualizzare la traccia in un computer Linux cambiando il formato di output di `dotnet-trace` in `speedscope`. È possibile modificare il formato del file di output utilizzando l'opzione `-f|--format`-`-f speedscope` renderà `dotnet-trace` produrre un file `speedscope`. Attualmente è possibile scegliere tra `nettrace` (opzione predefinita) e `speedscope`. è possibile aprire i file di `Speedscope` in <https://www.speedscope.app>.

> [!NOTE]
> Il runtime di .NET Core genera tracce nel formato `nettrace` e viene convertito in speedscope (se specificato) dopo il completamento della traccia. Poiché alcune conversioni possono comportare la perdita di dati, il file di `nettrace` originale viene mantenuto accanto al file convertito.

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a>Utilizzo di `dotnet-trace` per raccogliere i valori dei contatori nel tempo

Se si sta provando a usare `EventCounter` per il monitoraggio dello stato di base in impostazioni sensibili alle prestazioni, ad esempio gli ambienti di produzione e si desidera raccogliere tracce invece di controllarle in tempo reale, è possibile eseguire questa operazione anche con `dotnet-trace`.

Se ad esempio si desidera raccogliere i valori dei contatori delle prestazioni in fase di esecuzione, è possibile utilizzare il comando seguente:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Questo comando indica ai contatori di runtime di essere segnalati una volta al secondo per il monitoraggio dell'integrità leggero. La sostituzione di `EventCounterIntervalSec=1` con un valore superiore (ad esempio 60) consente di raccogliere una traccia più piccola con una minore granularità nei dati del contatore.

Se si vuole disabilitare gli eventi di runtime per ridurre ulteriormente l'overhead (e le dimensioni della traccia), è possibile usare il comando seguente per disabilitare gli eventi di runtime e il profiler dello stack gestito.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a>Provider .NET

Il runtime di .NET Core supporta i provider .NET seguenti. .NET Core usa le stesse parole chiave per abilitare sia `Event Tracing for Windows (ETW)` che `EventPipe` tracce.

| Nome provider                            | Informazioni |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [Il provider di runtime](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Parole chiave di runtime CLR](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [Il provider di rundown](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Parole chiave di rundown CLR](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Abilita il profiler di esempio. |
