---
title: Esercitazione sul debug di una perdita di memoria
description: Informazioni su come eseguire il debug di una perdita di memoria in .NET Core.
ms.topic: tutorial
ms.date: 12/17/2019
ms.openlocfilehash: 014945394f87edd02c94f7c3b28043bd07470d8b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737738"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a>Esercitazione: eseguire il debug di una perdita di memoria in .NET Core

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

Questa esercitazione illustra gli strumenti per analizzare una perdita di memoria di .NET Core.

Questa esercitazione usa un'app di esempio progettata per la perdita di memoria intenzionalmente. L'esempio viene fornito come esercizio. È possibile analizzare un'app che ha inavvertitamente una perdita di memoria.

In questa esercitazione si eseguono le attività seguenti:

> [!div class="checklist"]
>
> - Esaminare managed memory utilizzo con i [contatori DotNet](dotnet-counters.md).
> - Genera un file dump.
> - Analizzare l'utilizzo della memoria utilizzando il file dump.

## <a name="prerequisites"></a>Prerequisiti

L'esercitazione USA:

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.
- [DotNet-Trace](dotnet-trace.md) per elencare i processi.
- [DotNet-contatori](dotnet-counters.md) per controllare l'utilizzo del managed memory.
- [DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump.
- App di [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) da diagnosticare.

Nell'esercitazione si presuppone che gli strumenti e gli esempi siano installati e pronti per l'utilizzo.

## <a name="examine-managed-memory-usage"></a>Esaminare l'utilizzo di managed memory

Prima di iniziare a raccogliere i dati di diagnostica per aiutare la radice a causa di questo scenario, è necessario assicurarsi che si stia effettivamente osservando una perdita di memoria (aumento della memoria). È possibile utilizzare lo strumento [DotNet-Counters](dotnet-counters.md) per verificare che.

Aprire una finestra della console e passare alla directory in cui è stata scaricata e decompressa la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/). Eseguire la destinazione:

```dotnetcli
dotnet run
```

Da una console separata, trovare l'ID processo usando lo strumento [DotNet-Trace](dotnet-trace.md) :

```console
dotnet-trace ps
```

L'output dovrebbe essere simile a:

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

A questo punto, controllare managed memory utilizzo con lo strumento [DotNet-Counters](dotnet-counters.md) . Il `--refresh-interval` specifica il numero di secondi tra gli aggiornamenti:

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

L'output Live dovrebbe essere simile al seguente:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

Attenzione a questa riga:

```console
    GC Heap Size (MB)                                  4
```

È possibile osservare che la memoria heap gestita è 4 MB subito dopo l'avvio.

A questo punto, fare clic sull'URL `http://localhost:5000/api/diagscenario/memleak/20000`.

Osservare che l'utilizzo della memoria è aumentato fino a 30 MB.

```console
    GC Heap Size (MB)                                 30
```

Osservando l'utilizzo della memoria, è possibile tranquillamente indicare che la memoria sta crescendo o perdendo. Il passaggio successivo consiste nel raccogliere i dati appropriati per l'analisi della memoria.

### <a name="generate-memory-dump"></a>Genera dump della memoria

Quando si analizzano possibili perdite di memoria, è necessario accedere all'heap di memoria dell'app. È quindi possibile analizzare il contenuto della memoria. Esaminando le relazioni tra gli oggetti, è possibile creare teorie sui motivi per cui la memoria non viene liberata. Un'origine dati di diagnostica comune è un dump della memoria in Windows o il dump di core equivalente in Linux. Per generare un dump di un'applicazione .NET Core, è possibile usare lo strumento [DotNet-dump](dotnet-dump.md) .

Usando la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) precedentemente avviata, eseguire il comando seguente per generare un dump di Linux Core:

```dotnetcli
dotnet-dump collect -p 4807
```

Il risultato è un dump di base che si trova nella stessa cartella.

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a>Riavvia il processo non riuscito

Una volta raccolto il dump, è necessario disporre di informazioni sufficienti per diagnosticare il processo non riuscito. Se il processo non riuscito viene eseguito in un server di produzione, è ora ideale per la correzione a breve termine riavviando il processo.

In questa esercitazione viene ora eseguita la [destinazione di debug di esempio](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) , che può essere chiusa. Passare al terminale che ha avviato il server e premere `Control-C`.

### <a name="analyze-the-core-dump"></a>Analizzare il dump di base

Ora che è stato generato un dump di base, usare lo strumento [DotNet-dump)](dotnet-dump.md) per analizzare il dump:

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

Dove `core_20190430_185145` è il nome del dump di base che si vuole analizzare.

> [!NOTE]
> Se viene visualizzato un errore che segnala che non è possibile trovare *libdl.so* , potrebbe essere necessario installare il pacchetto *libc6-dev* . Per altre informazioni, vedere [Prerequisiti per .NET Core in Linux](../linux-prerequisites.md).

Verrà visualizzato un prompt in cui è possibile immettere i comandi SOS. In genere, la prima cosa che si vuole esaminare è lo stato complessivo dell'heap gestito:

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

Qui è possibile notare che la maggior parte degli oggetti è `String` o `Customer` oggetti.

È possibile usare di nuovo il comando `dumpheap` con la tabella dei metodi (MT) per ottenere un elenco di tutte le istanze di `String`:

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

È ora possibile usare il comando `gcroot` in un'istanza di `System.String` per vedere come e perché l'oggetto è radicato. Essere paziente perché questo comando richiede diversi minuti con un heap di 30 MB:

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

È possibile osservare che l'`String` viene mantenuta direttamente dall'oggetto `Customer` e che è indirettamente utilizzata da un oggetto `CustomerCache`.

È possibile continuare a eseguire il dump degli oggetti per vedere che la maggior parte degli oggetti `String` segue un modello simile. A questo punto, l'indagine forniva informazioni sufficienti per identificare la causa radice nel codice.

Questa procedura generale consente di identificare l'origine delle perdite di memoria principali.

## <a name="clean-up-resources"></a>Pulire le risorse

In questa esercitazione è stato avviato un server Web di esempio. Questo server dovrebbe essere stato arrestato come illustrato nella sezione [riavviare il processo non riuscito](#restart-the-failed-process) .

È anche possibile eliminare il file di dump creato.

## <a name="next-steps"></a>Passaggi successivi

Congratulazioni per aver completato questa esercitazione.

Stiamo ancora pubblicando altre esercitazioni diagnostiche. È possibile leggere le versioni bozza nel repository [DotNet/Diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial) .

Questa esercitazione ha trattato le nozioni di base degli strumenti di diagnostica .NET principali. Per informazioni sull'utilizzo avanzato, vedere la documentazione di riferimento seguente:

* [DotNet-Trace](dotnet-trace.md) per elencare i processi.
* [DotNet-contatori](dotnet-counters.md) per controllare l'utilizzo del managed memory.
* [DotNet-dump](dotnet-dump.md) per la raccolta e l'analisi di un file dump.
