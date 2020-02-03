---
title: DotNet-dump-.NET Core
description: Installazione e utilizzo dello strumento da riga di comando DotNet-dump.
ms.date: 10/14/2019
ms.openlocfilehash: 3c0e28d4efc96ae53ec7dfae243725ab400e6b8f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737665"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a>Dump Collection and Analysis Utility (`dotnet-dump`)

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

> [!NOTE]
> `dotnet-dump` non è supportato in macOS.

## <a name="installing-dotnet-dump"></a>Installazione del `dotnet-dump`

Per installare la versione di rilascio più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-dump)di `dotnet-dump`, usare il comando [DotNet tool install](../tools/dotnet-tool-install.md) :

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a>Riepilogo

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a>Descrizione

Lo strumento `dotnet-dump` Global è un modo per raccogliere e analizzare i dump di Windows e Linux senza che sia necessario un debugger nativo come `lldb` in Linux. Questo strumento è importante su piattaforme come Alpine Linux in cui non è disponibile un `lldb` completamente funzionante. Lo strumento `dotnet-dump` consente di eseguire i comandi SOS per analizzare gli arresti anomali e il Garbage Collector (GC), ma non è un debugger nativo, quindi non sono supportati elementi come la visualizzazione di stack frame nativi.

## <a name="options"></a>Opzioni

- **`--version`**

  Visualizza la versione dell'utilità DotNet-Counters.

- **`-h|--help`**

  Mostra la guida della riga di comando.

## <a name="commands"></a>Commands

| Comando                                     |
| ------------------------------------------- |
| [raccolta del dump DotNet](#dotnet-dump-collect) |
| [analisi DotNet-dump](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a>raccolta del dump DotNet

Acquisisce un dump da un processo.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a>Opzioni

- **`-h|--help`**

  Mostra la guida della riga di comando.

- **`-p|--process-id <PID>`**

  Specifica il numero ID del processo da cui raccogliere un dump della memoria.

- **`--type <Heap|Mini>`**

  Specifica il tipo di dump, che determina i tipi di informazioni raccolte dal processo. Esistono due tipi:

  - `Heap`: un dump di grandi dimensioni e relativamente completo che contiene elenchi di moduli, elenchi di thread, tutti gli stack, informazioni sulle eccezioni, informazioni sulla gestione e tutta la memoria eccetto le immagini mappate.
  - `Mini`: un piccolo dump contenente elenchi di moduli, elenchi di thread, informazioni sulle eccezioni e tutti gli stack.

  Se non è specificato, il valore predefinito è `Heap`.

- **`-o|--output <output_dump_path>`**

  Percorso completo e nome del file in cui deve essere scritto il dump raccolto.

  Se non è specificato:

  - Il valore predefinito è *. \ dump_YYYYMMDD_HHMMSS. dmp* in Windows.
  - Il valore predefinito è *./core_YYYYMMDD_HHMMSS* in Linux.

  AAAAMMGG è anno/mese/giorno e HHMMSS è ora/minuto/secondo.

- **`--diag`**

  Abilita la registrazione diagnostica della raccolta dump.

## <a name="dotnet-dump-analyze"></a>analisi DotNet-dump

Avvia una shell interattiva per esplorare un dump. La shell accetta diversi [comandi SOS](#analyze-sos-commands).

### <a name="synopsis"></a>Riepilogo

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a>Argomenti

- **`<dump_path>`**

  Specifica il percorso del file di dump da analizzare.

### <a name="options"></a>Opzioni

- **`-c|--command <debug_command>`**

  Specifica il [comando](#analyze-sos-commands) da eseguire nella shell all'avvio.

### <a name="analyze-sos-commands"></a>Analizzare i comandi SOS

| Comando                             | Funzione                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | Visualizza tutti i comandi disponibili                                                               |
| `soshelp|help <command>`            | Visualizza il comando specificato.                                                               |
| `exit|quit`                         | Esce dalla modalità interattiva.                                                                       |
| `clrstack <arguments>`              | Fornisce l'analisi dello stack del solo codice gestito.                                                  |
| `clrthreads <arguments>`            | Elenca i thread gestiti in esecuzione.                                                            |
| `dumpasync <arguments>`             | Visualizza informazioni sulle macchine a stati asincrone nell'heap sottoposta a Garbage Collection.                |
| `dumpassembly <arguments>`          | Visualizza i dettagli di un assembly.                                                           |
| `dumpclass <arguments>`             | Visualizza informazioni su una struttura di classe EE in corrispondenza dell'indirizzo specificato.                     |
| `dumpdelegate <arguments>`          | Visualizza informazioni su un delegato.                                                        |
| `dumpdomain <arguments>`            | Visualizza informazioni su tutti gli AppDomain e tutti gli assembly all'interno dei domini.                |
| `dumpheap <arguments>`              | Visualizza informazioni sull'heap sottoposta a Garbage Collection e sulle statistiche della raccolta sugli oggetti.       |
| `dumpil <arguments>`                | Visualizza il linguaggio MSIL (Microsoft Intermediate Language) associato a un metodo gestito. |
| `dumplog <arguments>`               | Scrive nel file specificato il contenuto di un log di stress in memoria.                         |
| `dumpmd <arguments>`                | Visualizza informazioni su una struttura MethodDesc in corrispondenza dell'indirizzo specificato.                   |
| `dumpmodule <arguments>`            | Visualizza informazioni su una struttura del modulo EE in corrispondenza dell'indirizzo specificato.                    |
| `dumpmt <arguments>`                | Visualizza informazioni su una tabella dei metodi in corrispondenza dell'indirizzo specificato.                           |
| `dumpobj <arguments>`               | Visualizza informazioni su un oggetto in corrispondenza dell'indirizzo specificato.                                       |
| `dso|dumpstackobjects <arguments>`  | Visualizza tutti gli oggetti gestiti trovati nell'ambito dei limiti dello stack corrente.                    |
| `eeheap <arguments>`                | Visualizza le informazioni sulla memoria del processo utilizzata dalle strutture di dati di runtime interno.              |
| `finalizequeue <arguments>`         | Visualizza tutti gli oggetti registrati per la finalizzazione.                                             |
| `gcroot <arguments>`                | Visualizza informazioni sui riferimenti (o radici) a un oggetto in corrispondenza dell'indirizzo specificato.              |
| `gcwhere <arguments>`               | Visualizza la posizione nell'heap GC dell'argomento passato.                               |
| `ip2md <arguments>`                 | Visualizza la struttura MethodDesc in corrispondenza dell'indirizzo specificato nel codice JIT.                       |
| `histclear <arguments>`             | Rilascia tutte le risorse utilizzate dalla famiglia di comandi `hist*`.                                |
| `histinit <arguments>`              | Inizializza le strutture SOS dal log di stress salvato nell'oggetto del debug.                     |
| `histobj <arguments>`               | Consente di visualizzare le rilocazioni dei log di Garbage Collection stress correlati a `<arguments>`.              |
| `histobjfind <arguments>`           | Visualizza tutte le voci del log che fanno riferimento a un oggetto in corrispondenza dell'indirizzo specificato.               |
| `histroot <arguments>`              | Visualizza informazioni correlate sia alle promozioni sia alle rilocazioni della radice specificata.        |
| `lm|modules`                        | Consente di visualizzare i moduli nativi nel processo.                                                   |
| `name2ee <arguments>`               | Consente di visualizzare la struttura MethodTable e la struttura EEClass per la `<argument>`.                |
| `pe|printexception <arguments>`     | Visualizza tutti gli oggetti derivati dalla classe Exception in corrispondenza dell'indirizzo `<argument>`.             |
| `setsymbolserver <arguments>`       | Abilita il supporto del server di simboli                                                             |
| `syncblk <arguments>`               | Visualizza le informazioni sul contenitore SyncBlock.                                                           |
| `threads|setthread <threadid>`      | Imposta o Visualizza l'ID del thread corrente per i comandi SOS.                                  |

## <a name="using-dotnet-dump"></a>Utilizzo di `dotnet-dump`

Il primo passaggio consiste nel raccogliere un dump. Questo passaggio può essere ignorato se è già stato generato un dump di base. Il sistema operativo o la [funzionalità di generazione del dump](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) predefinita del runtime di .NET Core possono creare dump di base.

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

Analizzare ora il dump principale con il comando `analyze`:

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

Questa azione Visualizza una sessione interattiva che accetta comandi come:

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

Per visualizzare un'eccezione non gestita che ha interrotto l'app:

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a>Istruzioni speciali per Docker

Se si esegue Docker, la raccolta di dump richiede funzionalità di `SYS_PTRACE` (`--cap-add=SYS_PTRACE` o `--privileged`).

Nelle immagini Docker di Microsoft .NET Core SDK Linux, alcuni comandi `dotnet-dump` possono generare l'eccezione seguente:

> Eccezione non gestita: System. DllNotFoundException: Impossibile caricare la libreria condivisa ' libdl.so ' o una delle sue dipendenze.

Per risolvere il problema, installare il pacchetto "libc6-dev".
