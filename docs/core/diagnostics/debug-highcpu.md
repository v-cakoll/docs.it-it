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
# <a name="debug-high-cpu-usage-in-net-core"></a>Eseguire il debug di un utilizzo elevato della CPU in .NET Core

**Questo articolo si applica a: ✔️** .net core 3,1 SDK e versioni successive

In questa esercitazione si apprenderà come eseguire il debug di uno scenario di utilizzo eccessivo della CPU. Usando l'esempio fornito ASP.NET Core repository del codice sorgente dell' [app Web](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) , è possibile causare un deadlock intenzionalmente. L'endpoint riscontra un accumulo di blocchi e thread. Si apprenderà come usare diversi strumenti per diagnosticare questo scenario con diversi elementi chiave dei dati di diagnostica.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> - Esaminare l'utilizzo elevato della CPU
> - Determinare l'utilizzo della CPU con i [contatori DotNet](dotnet-counters.md)
> - Usare [DotNet-Trace](dotnet-trace.md) per la generazione di tracce
> - Prestazioni del profilo in PerfView
> - Diagnosticare e risolvere un utilizzo eccessivo della CPU

## <a name="prerequisites"></a>Prerequisiti

L'esercitazione usa:

- [.NET Core 3,1 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.
- [Esempio di destinazione di debug](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) per attivare lo scenario.
- [DotNet-Trace](dotnet-trace.md) per elencare i processi e generare un profilo.
- [DotNet-contatori](dotnet-counters.md) per il monitoraggio dell'utilizzo della CPU.

## <a name="cpu-counters"></a>Contatori CPU

Prima di provare a raccogliere i dati di diagnostica, è necessario osservare una condizione di CPU elevata. Eseguire l' [applicazione di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) usando il comando seguente dalla directory radice del progetto.

```dotnetcli
dotnet run
```

Per trovare l'ID del processo, usare il comando seguente:

```dotnetcli
dotnet-trace ps
```

Prendere nota dell'ID del processo dall'output del comando. Il nostro ID processo era `22884` , ma il tuo sarà diverso. Per controllare l'utilizzo della CPU corrente, usare il comando [DotNet-Counters](dotnet-counters.md) Tool:

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

`refresh-interval`È il numero di secondi tra i valori della CPU di polling del contatore. L'output avrà un aspetto analogo al seguente:

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

Con l'app Web in esecuzione, immediatamente dopo l'avvio, la CPU non viene usata e viene segnalata all'indirizzo `0%` . Passare alla `api/diagscenario/highcpu` Route con `60000` come parametro di route:

[https://localhost:5001/api/diagscenario/highcpu/60000](https://localhost:5001/api/diagscenario/highcpu/60000)

A questo punto, eseguire di nuovo il comando [DotNet-Counters](dotnet-counters.md) . Per monitorare solo `cpu-usage` , specificare `System.Runtime[cpu-usage]` come parte del comando.

```dotnetcli
dotnet-counters monitor System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

Si noterà un aumento dell'utilizzo della CPU, come illustrato di seguito:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

Per tutta la durata della richiesta, l'utilizzo della CPU passerà circa il 25%. A seconda del computer host, è previsto un utilizzo della CPU variabile.

> [!TIP]
> Per visualizzare un utilizzo della CPU ancora più elevato, è possibile usare questo endpoint in più schede del browser simultaneamente.

A questo punto, è possibile dire che la CPU è in esecuzione in modo più elevato del previsto.

## <a name="trace-generation"></a>Generazione traccia

Quando si analizza una richiesta lenta, è necessario uno strumento di diagnostica in grado di fornire informazioni approfondite sulle operazioni del codice. La scelta consueta è un profiler ed è possibile scegliere tra diverse opzioni del profiler.

### <a name="linux"></a>[Linux](#tab/linux)

Lo `perf` strumento può essere usato per generare profili di app .NET Core. Uscire dall'istanza precedente della [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios).

Impostare la `COMPlus_PerfMapEnabled` variabile di ambiente in modo che l'app .NET Core crei un `map` file nella `/tmp` Directory. Questo `map` file viene usato da `perf` per eseguire il mapping dell'indirizzo della CPU alle funzioni generate tramite JIT in base al nome. Per altre informazioni, vedere [scrivere la mappa delle prestazioni](../run-time-config/debugging-profiling.md#write-perf-map).

Eseguire la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) nella stessa sessione terminal.

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

Eseguire di nuovo l'endpoint API CPU ( <https://localhost:5001/api/diagscenario/highcpu/60000> ) elevato. Mentre è in esecuzione entro la richiesta di 1 minuto, eseguire il `perf` comando con l'ID del processo:

```bash
sudo perf record -p 2266 -g
```

Il `perf` comando avvia il processo di raccolta delle prestazioni. Consente di eseguire circa 20-30 secondi, quindi premere <kbd>CTRL + C</kbd> per uscire dal processo di raccolta. È possibile usare lo stesso `perf` comando per visualizzare l'output della traccia.

```bash
sudo perf report -f
```

È anche possibile generare un _grafico Flame_ usando i comandi seguenti:

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

Questo comando genera un oggetto `flamegraph.svg` che è possibile visualizzare nel browser per esaminare il problema relativo alle prestazioni:

[![Immagine di Flame Graph SVG](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)

### <a name="windows"></a>[Windows](#tab/windows)

In Windows è possibile usare lo strumento [DotNet-Trace](dotnet-trace.md) come profiler. Utilizzando la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios)precedente, verificare di nuovo l'endpoint CPU () elevato <https://localhost:5001/api/diagscenario/highcpu/60000> . Mentre è in esecuzione entro la richiesta di 1 minuto, utilizzare il `collect` comando come segue:

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

Consentire l'esecuzione di [DotNet-Trace](dotnet-trace.md) per circa 20-30 secondi, quindi premere <kbd>invio</kbd> per uscire dalla raccolta. Il risultato è un `nettrace` file che si trova nella stessa cartella. I `nettrace` file sono un ottimo modo per usare gli strumenti di analisi esistenti in Windows.

Aprire `nettrace` con [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) come illustrato di seguito.

[![Immagine di PerfView](media/perfview.jpg)](media/perfview.jpg#lightbox)

---

## <a name="see-also"></a>Vedere anche

- [DotNet-Trace](dotnet-trace.md) per elencare i processi
- [contatori DotNet](dotnet-counters.md) per controllare l'utilizzo di managed memory
- [DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump
- [DotNet/diagnostica](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Eseguire il debug di un deadlock in .NET Core](debug-deadlock.md)
