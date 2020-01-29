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
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="2576e-103">Dump Collection and Analysis Utility (`dotnet-dump`)</span><span class="sxs-lookup"><span data-stu-id="2576e-103">Dump collection and analysis utility (`dotnet-dump`)</span></span>

<span data-ttu-id="2576e-104">**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2576e-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="2576e-105">`dotnet-dump` non è supportato in macOS.</span><span class="sxs-lookup"><span data-stu-id="2576e-105">`dotnet-dump` isn't supported on macOS.</span></span>

## <a name="installing-dotnet-dump"></a><span data-ttu-id="2576e-106">Installazione di `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="2576e-106">Installing `dotnet-dump`</span></span>

<span data-ttu-id="2576e-107">Per installare la versione di rilascio più recente del [pacchetto NuGet](https://www.nuget.org/packages/dotnet-dump)di `dotnet-dump`, usare il comando [DotNet tool install](../tools/dotnet-tool-install.md) :</span><span class="sxs-lookup"><span data-stu-id="2576e-107">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a><span data-ttu-id="2576e-108">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2576e-108">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="2576e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2576e-109">Description</span></span>

<span data-ttu-id="2576e-110">Lo strumento `dotnet-dump` Global è un modo per raccogliere e analizzare i dump di Windows e Linux senza che sia necessario un debugger nativo come `lldb` in Linux.</span><span class="sxs-lookup"><span data-stu-id="2576e-110">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="2576e-111">Questo strumento è importante su piattaforme come Alpine Linux in cui non è disponibile un `lldb` completamente funzionante.</span><span class="sxs-lookup"><span data-stu-id="2576e-111">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="2576e-112">Lo strumento `dotnet-dump` consente di eseguire i comandi SOS per analizzare gli arresti anomali e il Garbage Collector (GC), ma non è un debugger nativo, quindi non sono supportati elementi come la visualizzazione di stack frame nativi.</span><span class="sxs-lookup"><span data-stu-id="2576e-112">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="2576e-113">Options</span><span class="sxs-lookup"><span data-stu-id="2576e-113">Options</span></span>

- **`--version`**

  <span data-ttu-id="2576e-114">Visualizza la versione dell'utilità DotNet-Counters.</span><span class="sxs-lookup"><span data-stu-id="2576e-114">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2576e-115">Mostra la guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2576e-115">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="2576e-116">Comandi</span><span class="sxs-lookup"><span data-stu-id="2576e-116">Commands</span></span>

| <span data-ttu-id="2576e-117">Comando</span><span class="sxs-lookup"><span data-stu-id="2576e-117">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="2576e-118">raccolta del dump DotNet</span><span class="sxs-lookup"><span data-stu-id="2576e-118">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="2576e-119">analisi DotNet-dump</span><span class="sxs-lookup"><span data-stu-id="2576e-119">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="2576e-120">raccolta del dump DotNet</span><span class="sxs-lookup"><span data-stu-id="2576e-120">dotnet-dump collect</span></span>

<span data-ttu-id="2576e-121">Acquisisce un dump da un processo.</span><span class="sxs-lookup"><span data-stu-id="2576e-121">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="2576e-122">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2576e-122">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="2576e-123">Options</span><span class="sxs-lookup"><span data-stu-id="2576e-123">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="2576e-124">Mostra la guida della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2576e-124">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="2576e-125">Specifica il numero ID del processo da cui raccogliere un dump della memoria.</span><span class="sxs-lookup"><span data-stu-id="2576e-125">Specifies the process ID number to collect a memory dump from.</span></span>

- **`--type <Heap|Mini>`**

  <span data-ttu-id="2576e-126">Specifica il tipo di dump, che determina i tipi di informazioni raccolte dal processo.</span><span class="sxs-lookup"><span data-stu-id="2576e-126">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="2576e-127">Esistono due tipi:</span><span class="sxs-lookup"><span data-stu-id="2576e-127">There are two types:</span></span>

  - <span data-ttu-id="2576e-128">`Heap`: un dump di grandi dimensioni e relativamente completo che contiene elenchi di moduli, elenchi di thread, tutti gli stack, informazioni sulle eccezioni, informazioni sulla gestione e tutta la memoria eccetto le immagini mappate.</span><span class="sxs-lookup"><span data-stu-id="2576e-128">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="2576e-129">`Mini`: un piccolo dump contenente elenchi di moduli, elenchi di thread, informazioni sulle eccezioni e tutti gli stack.</span><span class="sxs-lookup"><span data-stu-id="2576e-129">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="2576e-130">Se non è specificato, il valore predefinito è `Heap`.</span><span class="sxs-lookup"><span data-stu-id="2576e-130">If not specified, `Heap` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="2576e-131">Percorso completo e nome del file in cui deve essere scritto il dump raccolto.</span><span class="sxs-lookup"><span data-stu-id="2576e-131">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="2576e-132">Se non è specificato:</span><span class="sxs-lookup"><span data-stu-id="2576e-132">If not specified:</span></span>

  - <span data-ttu-id="2576e-133">Il valore predefinito è *. \ dump_YYYYMMDD_HHMMSS. dmp* in Windows.</span><span class="sxs-lookup"><span data-stu-id="2576e-133">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="2576e-134">Il valore predefinito è *./core_YYYYMMDD_HHMMSS* in Linux.</span><span class="sxs-lookup"><span data-stu-id="2576e-134">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="2576e-135">AAAAMMGG è anno/mese/giorno e HHMMSS è ora/minuto/secondo.</span><span class="sxs-lookup"><span data-stu-id="2576e-135">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="2576e-136">Abilita la registrazione diagnostica della raccolta dump.</span><span class="sxs-lookup"><span data-stu-id="2576e-136">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="2576e-137">analisi DotNet-dump</span><span class="sxs-lookup"><span data-stu-id="2576e-137">dotnet-dump analyze</span></span>

<span data-ttu-id="2576e-138">Avvia una shell interattiva per esplorare un dump.</span><span class="sxs-lookup"><span data-stu-id="2576e-138">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="2576e-139">La shell accetta diversi [comandi SOS](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="2576e-139">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="2576e-140">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2576e-140">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="2576e-141">Argomenti</span><span class="sxs-lookup"><span data-stu-id="2576e-141">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="2576e-142">Specifica il percorso del file di dump da analizzare.</span><span class="sxs-lookup"><span data-stu-id="2576e-142">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="2576e-143">Options</span><span class="sxs-lookup"><span data-stu-id="2576e-143">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="2576e-144">Specifica il [comando](#analyze-sos-commands) da eseguire nella shell all'avvio.</span><span class="sxs-lookup"><span data-stu-id="2576e-144">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="2576e-145">Analizzare i comandi SOS</span><span class="sxs-lookup"><span data-stu-id="2576e-145">Analyze SOS commands</span></span>

| <span data-ttu-id="2576e-146">Comando</span><span class="sxs-lookup"><span data-stu-id="2576e-146">Command</span></span>                             | <span data-ttu-id="2576e-147">Funzione</span><span class="sxs-lookup"><span data-stu-id="2576e-147">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="2576e-148">Visualizza tutti i comandi disponibili</span><span class="sxs-lookup"><span data-stu-id="2576e-148">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="2576e-149">Visualizza il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-149">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="2576e-150">Esce dalla modalità interattiva.</span><span class="sxs-lookup"><span data-stu-id="2576e-150">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="2576e-151">Fornisce l'analisi dello stack del solo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2576e-151">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="2576e-152">Elenca i thread gestiti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2576e-152">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="2576e-153">Visualizza informazioni sulle macchine a stati asincrone nell'heap sottoposta a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2576e-153">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="2576e-154">Visualizza i dettagli di un assembly.</span><span class="sxs-lookup"><span data-stu-id="2576e-154">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="2576e-155">Visualizza informazioni su una struttura di classe EE in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-155">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="2576e-156">Visualizza informazioni su un delegato.</span><span class="sxs-lookup"><span data-stu-id="2576e-156">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="2576e-157">Visualizza informazioni su tutti gli AppDomain e tutti gli assembly all'interno dei domini.</span><span class="sxs-lookup"><span data-stu-id="2576e-157">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="2576e-158">Visualizza informazioni sull'heap sottoposta a Garbage Collection e sulle statistiche della raccolta sugli oggetti.</span><span class="sxs-lookup"><span data-stu-id="2576e-158">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="2576e-159">Visualizza il linguaggio MSIL (Microsoft Intermediate Language) associato a un metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="2576e-159">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="2576e-160">Scrive nel file specificato il contenuto di un log di stress in memoria.</span><span class="sxs-lookup"><span data-stu-id="2576e-160">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="2576e-161">Visualizza informazioni su una struttura MethodDesc in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-161">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="2576e-162">Visualizza informazioni su una struttura del modulo EE in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-162">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="2576e-163">Visualizza informazioni su una tabella dei metodi in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-163">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="2576e-164">Visualizza informazioni su un oggetto in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-164">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="2576e-165">Visualizza tutti gli oggetti gestiti trovati nell'ambito dei limiti dello stack corrente.</span><span class="sxs-lookup"><span data-stu-id="2576e-165">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="2576e-166">Visualizza le informazioni sulla memoria del processo utilizzata dalle strutture di dati di runtime interno.</span><span class="sxs-lookup"><span data-stu-id="2576e-166">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="2576e-167">Visualizza tutti gli oggetti registrati per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="2576e-167">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="2576e-168">Visualizza informazioni sui riferimenti (o radici) a un oggetto in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-168">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="2576e-169">Visualizza la posizione nell'heap GC dell'argomento passato.</span><span class="sxs-lookup"><span data-stu-id="2576e-169">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="2576e-170">Visualizza la struttura MethodDesc in corrispondenza dell'indirizzo specificato nel codice JIT.</span><span class="sxs-lookup"><span data-stu-id="2576e-170">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="2576e-171">Rilascia tutte le risorse utilizzate dalla famiglia di comandi `hist*`.</span><span class="sxs-lookup"><span data-stu-id="2576e-171">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="2576e-172">Inizializza le strutture SOS dal log di stress salvato nell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="2576e-172">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="2576e-173">Consente di visualizzare le rilocazioni dei log di Garbage Collection stress correlati a `<arguments>`.</span><span class="sxs-lookup"><span data-stu-id="2576e-173">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="2576e-174">Visualizza tutte le voci del log che fanno riferimento a un oggetto in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="2576e-174">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="2576e-175">Visualizza informazioni correlate sia alle promozioni sia alle rilocazioni della radice specificata.</span><span class="sxs-lookup"><span data-stu-id="2576e-175">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="2576e-176">Consente di visualizzare i moduli nativi nel processo.</span><span class="sxs-lookup"><span data-stu-id="2576e-176">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="2576e-177">Consente di visualizzare la struttura MethodTable e la struttura EEClass per la `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="2576e-177">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="2576e-178">Visualizza tutti gli oggetti derivati dalla classe Exception in corrispondenza dell'indirizzo `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="2576e-178">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="2576e-179">Abilita il supporto del server di simboli</span><span class="sxs-lookup"><span data-stu-id="2576e-179">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="2576e-180">Visualizza le informazioni sul contenitore SyncBlock.</span><span class="sxs-lookup"><span data-stu-id="2576e-180">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="2576e-181">Imposta o Visualizza l'ID del thread corrente per i comandi SOS.</span><span class="sxs-lookup"><span data-stu-id="2576e-181">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="2576e-182">Utilizzo di `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="2576e-182">Using `dotnet-dump`</span></span>

<span data-ttu-id="2576e-183">Il primo passaggio consiste nel raccogliere un dump.</span><span class="sxs-lookup"><span data-stu-id="2576e-183">The first step is to collect a dump.</span></span> <span data-ttu-id="2576e-184">Questo passaggio può essere ignorato se è già stato generato un dump di base.</span><span class="sxs-lookup"><span data-stu-id="2576e-184">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="2576e-185">Il sistema operativo o la [funzionalità di generazione del dump](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) predefinita del runtime di .NET Core possono creare dump di base.</span><span class="sxs-lookup"><span data-stu-id="2576e-185">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="2576e-186">Analizzare ora il dump principale con il comando `analyze`:</span><span class="sxs-lookup"><span data-stu-id="2576e-186">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="2576e-187">Questa azione Visualizza una sessione interattiva che accetta comandi come:</span><span class="sxs-lookup"><span data-stu-id="2576e-187">This action brings up an interactive session that accepts commands like:</span></span>

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

<span data-ttu-id="2576e-188">Per visualizzare un'eccezione non gestita che ha interrotto l'app:</span><span class="sxs-lookup"><span data-stu-id="2576e-188">To see an unhandled exception that killed your app:</span></span>

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

## <a name="special-instructions-for-docker"></a><span data-ttu-id="2576e-189">Istruzioni speciali per Docker</span><span class="sxs-lookup"><span data-stu-id="2576e-189">Special instructions for Docker</span></span>

<span data-ttu-id="2576e-190">Se si esegue Docker, la raccolta di dump richiede funzionalità di `SYS_PTRACE` (`--cap-add=SYS_PTRACE` o `--privileged`).</span><span class="sxs-lookup"><span data-stu-id="2576e-190">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="2576e-191">Nelle immagini Docker di Microsoft .NET Core SDK Linux, alcuni comandi `dotnet-dump` possono generare l'eccezione seguente:</span><span class="sxs-lookup"><span data-stu-id="2576e-191">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="2576e-192">Eccezione non gestita: System. DllNotFoundException: Impossibile caricare la libreria condivisa ' libdl.so ' o una delle sue dipendenze.</span><span class="sxs-lookup"><span data-stu-id="2576e-192">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="2576e-193">Per risolvere il problema, installare il pacchetto "libc6-dev".</span><span class="sxs-lookup"><span data-stu-id="2576e-193">To work around this problem, install the "libc6-dev" package.</span></span>
