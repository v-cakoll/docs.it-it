---
title: dotnet-dump - .NET Core
description: Installazione e utilizzo dello strumento da riga di comando dotnet-dump.
ms.date: 10/14/2019
ms.openlocfilehash: c78ddb6447021f61f2452c075733b7d33e051ca0
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888202"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a>Utilità di raccolta`dotnet-dump`e analisi di dump ( )

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

> [!NOTE]
> `dotnet-dump`non è supportato su macOS.

## <a name="installing-dotnet-dump"></a>Installazione del `dotnet-dump`

Per installare la versione `dotnet-dump` più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-dump), utilizzare il comando [dotnet tool install:](../tools/dotnet-tool-install.md)

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a>Riepilogo

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a>Descrizione

Lo `dotnet-dump` strumento globale è un modo per raccogliere e analizzare `lldb` i dump di Windows e Linux senza alcun debugger nativo coinvolto come su Linux. Questo strumento è importante su piattaforme `lldb` come Alpine Linux in cui non è disponibile un completamente funzionante. Lo `dotnet-dump` strumento consente di eseguire comandi SOS per analizzare gli arresti anomali e il Garbage Collector (GC), ma non è un debugger nativo, pertanto elementi quali la visualizzazione di stack frame nativi non sono supportati.

## <a name="options"></a>Opzioni

- **`--version`**

  Visualizza la versione dell'utilità dotnet-dump.

- **`-h|--help`**

  Mostra la Guida della riga di comando.

## <a name="commands"></a>Comandi:

| Comando                                     |
| ------------------------------------------- |
| [dotnet-dump raccogliere](#dotnet-dump-collect) |
| [dotnet-dump analisi](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a>dotnet-dump raccogliere

Acquisisce un dump da un processo.

### <a name="synopsis"></a>Riepilogo

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a>Opzioni

- **`-h|--help`**

  Mostra la Guida della riga di comando.

- **`-p|--process-id <PID>`**

  Specifica il numero ID del processo da cui raccogliere un dump della memoria.

- **`--type <Heap|Mini>`**

  Specifica il tipo di dump, che determina i tipi di informazioni raccolte dal processo. Ne esistono di due tipi:

  - `Heap`- Un dump di grandi dimensioni e relativamente completo contenente elenchi di moduli, elenchi di thread, tutti gli stack, informazioni sulle eccezioni, informazioni sull'handle e tutta la memoria ad eccezione delle immagini mappate.
  - `Mini`- Un piccolo dump contenente elenchi di moduli, elenchi di thread, informazioni sulle eccezioni e tutti gli stack.

  Se non `Heap` specificato, è l'impostazione predefinita.

- **`-o|--output <output_dump_path>`**

  Il percorso completo e il nome del file in cui deve essere scritto il dump raccolto.

  Se non specificato:

  - Il valore predefinito è *.dump_YYYYMMDD_HHMMSS.dmp* in Windows.
  - Il valore predefinito è *./core_YYYYMMDD_HHMMSS* su Linux.

  AAAAMMGG è Anno/Mese/Giorno e HHMMSS è Ora/Minuto/Secondo.

- **`--diag`**

  Abilita la registrazione diagnostica della raccolta di dump.

## <a name="dotnet-dump-analyze"></a>dotnet-dump analisi

Avvia una shell interattiva per esplorare un dump. La shell accetta vari [comandi SOS](#analyze-sos-commands).

### <a name="synopsis"></a>Riepilogo

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a>Argomenti

- **`<dump_path>`**

  Specifica il percorso del file dump da analizzare.

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
| `dumpasync <arguments>`             | Visualizza informazioni sui computer con stato asincrono nell'heap sottoposto a Garbage Collection.                |
| `dumpassembly <arguments>`          | Visualizza i dettagli relativi a un assieme.                                                           |
| `dumpclass <arguments>`             | Visualizza informazioni su una struttura di classi EE in corrispondenza dell'indirizzo specificato.                     |
| `dumpdelegate <arguments>`          | Visualizza informazioni su un delegato.                                                        |
| `dumpdomain <arguments>`            | Visualizza informazioni su tutti gli appDomain e tutti gli assembly all'interno dei domini.                |
| `dumpheap <arguments>`              | Visualizza informazioni sull'heap sottoposto a Garbage Collection e sulle statistiche di raccolta relative agli oggetti.       |
| `dumpil <arguments>`                | Visualizza il linguaggio MSIL (Microsoft Intermediate Language) associato a un metodo gestito. |
| `dumplog <arguments>`               | Scrive nel file specificato il contenuto di un log di stress in memoria.                         |
| `dumpmd <arguments>`                | Visualizza informazioni su una struttura MethodDesc in corrispondenza dell'indirizzo specificato.                   |
| `dumpmodule <arguments>`            | Visualizza informazioni su una struttura di modulo EE in corrispondenza dell'indirizzo specificato.                    |
| `dumpmt <arguments>`                | Visualizza informazioni su una tabella dei metodi in corrispondenza dell'indirizzo specificato.                           |
| `dumpobj <arguments>`               | Visualizza informazioni su un oggetto in corrispondenza dell'indirizzo specificato.                                       |
| `dso|dumpstackobjects <arguments>`  | Visualizza tutti gli oggetti gestiti trovati nell'ambito dei limiti dello stack corrente.                    |
| `eeheap <arguments>`                | Visualizza informazioni sulla memoria del processo utilizzata dalle strutture di dati di runtime interne.              |
| `finalizequeue <arguments>`         | Visualizza tutti gli oggetti registrati per la finalizzazione.                                             |
| `gcroot <arguments>`                | Visualizza informazioni sui riferimenti (o radici) a un oggetto in corrispondenza dell'indirizzo specificato.              |
| `gcwhere <arguments>`               | Visualizza la posizione nell'heap GC dell'argomento passato.                               |
| `ip2md <arguments>`                 | Visualizza la struttura MethodDesc in corrispondenza dell'indirizzo specificato nel codice JIT.                       |
| `histclear <arguments>`             | Rilascia tutte le risorse utilizzate dalla famiglia di comandi `hist*`.                                |
| `histinit <arguments>`              | Inizializza le strutture SOS dal log di stress salvato nell'oggetto del debug.                     |
| `histobj <arguments>`               | Visualizza le rilocazioni del `<arguments>`registro sollecitazioni di Garbage Collection relative a .              |
| `histobjfind <arguments>`           | Visualizza tutte le voci del log che fanno riferimento a un oggetto in corrispondenza dell'indirizzo specificato.               |
| `histroot <arguments>`              | Visualizza informazioni correlate sia alle promozioni sia alle rilocazioni della radice specificata.        |
| `lm|modules`                        | Visualizza i moduli nativi nel processo.                                                   |
| `name2ee <arguments>`               | Visualizza la struttura MethodTable e la `<argument>`struttura EEClass per l'oggetto .                |
| `pe|printexception <arguments>`     | Visualizza qualsiasi oggetto derivato dalla `<argument>`classe Exception in corrispondenza dell'indirizzo .             |
| `setsymbolserver <arguments>`       | Abilita il supporto del server di simboli                                                             |
| `syncblk <arguments>`               | Visualizza le informazioni sul supporto SyncBlock.                                                           |
| `threads|setthread <threadid>`      | Imposta o visualizza l'ID thread corrente per i comandi SOS.                                  |

## <a name="using-dotnet-dump"></a>Utilizzo di `dotnet-dump`

Il primo passo è quello di raccogliere una discarica. Questo passaggio può essere ignorato se è già stato generato un dump principale. Il sistema operativo o la funzionalità di [generazione](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) di dump incorporata del runtime di .NET Core può creare dump di base.

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

Ora analizzare il `analyze` dump principale con il comando:

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

Questa azione visualizza una sessione interattiva che accetta comandi come:

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

Per visualizzare un'eccezione non gestita che ha ucciso l'app:

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

Se si esegue in Docker, `SYS_PTRACE` la`--cap-add=SYS_PTRACE` raccolta `--privileged`di dump richiede funzionalità ( o ).

Nelle immagini Di Microsoft .NET Core `dotnet-dump` SDK Linux Docker, alcuni comandi possono generare l'eccezione seguente:

> Eccezione non gestita: System.DllNotFoundException: Impossibile caricare la libreria condivisa 'libdl.so' o l'eccezione di una delle relative dipendenze' .

Per risolvere questo problema, installare il pacchetto "libc6-dev".
