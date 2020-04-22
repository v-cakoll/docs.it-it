---
title: Esercitazione sul debug di una perdita di memoriaDebug a memory leak tutorial
description: Informazioni su come eseguire il debug di una perdita di memoria in .NET Core.Learn how to debug a memory leak in .NET Core.
ms.topic: tutorial
ms.date: 04/20/2020
ms.openlocfilehash: d47992bab9dab64cf7f88ff679eef407dd891b5a
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021363"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a>Esercitazione: Eseguire il debug di una perdita di memoria in .NET CoreTutorial: Debug a memory leak in .NET Core

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

Questa esercitazione illustra gli strumenti per analizzare una perdita di memoria .NET Core.This tutorial demonstrates the tools to analyze a .NET Core memory leak.

Questa esercitazione usa un'app di esempio progettata per causare una perdita intenzionale di memoria. Il campione viene fornito come esercizio. È possibile analizzare un'applicazione che perde involontariamente memoria troppo.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> - Esaminare l'utilizzo della memoria gestita con [dotnet-counters](dotnet-counters.md).
> - Generare un file dump.
> - Analizzare l'utilizzo della memoria utilizzando il file di dump.

## <a name="prerequisites"></a>Prerequisiti

L'esercitazione usa:

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) o versione successiva.
- [dotnet-trace](dotnet-trace.md) per elencare i processi.
- [dotnet-counters](dotnet-counters.md) per controllare l'utilizzo della memoria gestita.
- [dotnet-dump](dotnet-dump.md) per raccogliere e analizzare un file dump.
- Esempio [di app di destinazione](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) del debug da diagnosticare.

L'esercitazione presuppone che l'esempio e gli strumenti siano installati e pronti per l'uso.

## <a name="examine-managed-memory-usage"></a>Esaminare l'utilizzo della memoria gestitaExamine managed memory usage

Prima di iniziare a raccogliere i dati di diagnostica per aiutare a causa principale questo scenario, è necessario assicurarsi che si sta effettivamente vedendo una perdita di memoria (crescita della memoria). È possibile utilizzare lo strumento [dotnet-counters](dotnet-counters.md) per confermarlo.

Aprire una finestra della console e passare alla directory in cui è stato scaricato e decompresso la destinazione di [debug di esempio.](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) Eseguire la destinazione:

```dotnetcli
dotnet run
```

Da una console separata, trovare l'ID processo utilizzando lo strumento [dotnet-trace:](dotnet-trace.md)

```console
dotnet-trace ps
```

L'output dovrebbe essere simile al:

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

A questo punto, controllare l'utilizzo della memoria gestita con lo strumento [dotnet-counters.](dotnet-counters.md) L'oggetto `--refresh-interval` specifica il numero di secondi tra gli aggiornamenti:

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

L'output live dovrebbe essere simile al:

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

Concentrandosi su questa linea:

```console
    GC Heap Size (MB)                                  4
```

Si può vedere che la memoria heap gestita è 4 MB subito dopo l'avvio.

A questo punto, premere l'URL `http://localhost:5000/api/diagscenario/memleak/20000`.

Osservare che l'utilizzo della memoria è cresciuto fino a 30 MB.

```console
    GC Heap Size (MB)                                 30
```

Guardando l'utilizzo della memoria, si può tranquillamente dire che la memoria è in crescita o perdite. Il passo successivo è quello di raccogliere i dati giusti per l'analisi della memoria.

### <a name="generate-memory-dump"></a>Genera immagine della memoria

Quando si analizzano possibili perdite di memoria, è necessario accedere all'heap di memoria dell'app. Quindi è possibile analizzare il contenuto della memoria. Esaminando le relazioni tra gli oggetti, si creano teorie sul motivo per cui la memoria non viene liberata. A common diagnostics data source is a memory dump on Windows or the equivalent core dump on Linux. Per generare un dump di un'applicazione .NET Core, è possibile utilizzare lo strumento [dotnet-dump).](dotnet-dump.md)

Utilizzando la destinazione di debug di esempio avviata in precedenza, eseguire il comando seguente per generare un dump principale di Linux:Using the [sample debug target](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) previously started, run the following command to generate a Linux core dump:

```dotnetcli
dotnet-dump collect -p 4807
```

Il risultato è un dump principale che si trova nella stessa cartella.

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a>Riavviare il processo non riuscito

Una volta raccolto il dump, è necessario disporre di informazioni sufficienti per diagnosticare il processo non riuscito. Se il processo non riuscito è in esecuzione su un server di produzione, ora è il momento ideale per la correzione a breve termine riavviando il processo.

In questa esercitazione è ora completata [l'obiettivo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) di debug di esempio ed è possibile chiuderla. Passare al terminale che ha `Control-C`avviato il server e premere .

### <a name="analyze-the-core-dump"></a>Analizzare il dump principale

Ora che si dispone di un dump principale generato, utilizzare lo strumento [dotnet-dump](dotnet-dump.md) per analizzare il dump:

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

Dove `core_20190430_185145` è il nome del dump principale che si desidera analizzare.

> [!NOTE]
> Se viene visualizzato un errore che si lamenta che non è possibile *trovare libdl.so,* potrebbe essere necessario installare il pacchetto *libc6-dev.* Per altre informazioni, vedere [Prerequisiti per .NET Core in Linux](../install/dependencies.md?pivots=os-linux).

Verrà visualizzato un messaggio di richiesta in cui è possibile immettere i comandi SOS. In genere, la prima cosa che si desidera esaminare è lo stato complessivo dell'heap gestito:

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

Qui potete vedere che `String` la `Customer` maggior parte degli oggetti sono o oggetti.

È possibile `dumpheap` utilizzare nuovamente il comando con la tabella dei metodi `String` (MT) per ottenere un elenco di tutte le istanze:You can use the command again with the method table (MT) to get a list of all the instances:

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

È ora possibile `gcroot` utilizzare `System.String` il comando su un'istanza per vedere come e perché l'oggetto è radicato. Siate pazienti perché questo comando richiede alcuni minuti con un heap di 30 MB:

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

Si può vedere `String` che il `Customer` è tenuto direttamente dall'oggetto e indirettamente tenuto da un `CustomerCache` oggetto.

È possibile continuare il dump degli `String` oggetti per verificare che la maggior parte degli oggetti segua un modello simile. A questo punto, l'indagine ha fornito informazioni sufficienti per identificare la causa principale nel codice.

Questa procedura generale consente di identificare l'origine delle perdite di memoria principali.

## <a name="clean-up-resources"></a>Pulire le risorse

In questa esercitazione è stato avviato un server Web di esempio. Questo server dovrebbe essere stato arrestato come spiegato nella sezione [Riavviare il processo non riuscito.](#restart-the-failed-process)

È inoltre possibile eliminare il file dump creato.

## <a name="next-steps"></a>Passaggi successivi

Congratulazioni per aver completato questo tutorial.

Stiamo ancora pubblicando altre esercitazioni di diagnostica. È possibile leggere le versioni bozza nel repository [dotnet/diagnostics.](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

In questa esercitazione sono illustrate le nozioni di base degli strumenti di diagnostica .NET principali. Per l'utilizzo avanzato, vedere la documentazione di riferimento seguente:For advanced usage, see the following reference documentation:

* [dotnet-trace](dotnet-trace.md) per elencare i processi.
* [dotnet-counters](dotnet-counters.md) per controllare l'utilizzo della memoria gestita.
* [dotnet-dump](dotnet-dump.md) per raccogliere e analizzare un file dump.
