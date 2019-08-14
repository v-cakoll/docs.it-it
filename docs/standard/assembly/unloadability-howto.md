---
title: Come usare ed eseguire il debug di assembly non caricabili in .NET Core
description: Informazioni su come usare un oggetto AssemblyLoadContext ritirabile per caricare e scaricare assembly gestiti e come eseguire il debug di problemi che impediscono lo scaricamento.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: a3ba2c2809aedd0af03ec965089f8779c430a335
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68671246"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Come usare ed eseguire il debug di assembly non caricabili in .NET Core

A partire da .NET Core 3.0, è supportata la possibilità di caricare e successivamente scaricare un set di assembly. In .NET Framework, per questo scopo vengono usati domini di app personalizzati, ma .NET Core supporta un singolo dominio di app predefinito.

.NET Core 3.0 e versioni successive supportano la possibilità di scaricamento tramite la classe <xref:System.Runtime.Loader.AssemblyLoadContext>. È possibile caricare un set di assembly in un oggetto `AssemblyLoadContext` ritirabile, eseguirvi metodi o semplicemente ispezionarli tramite reflection e infine scaricare l'`AssemblyLoadContext`. In questo modo, gli assembly caricati nell'`AssemblyLoadContext` vengono scaricati.

Esiste una differenza rilevante tra lo scaricamento tramite `AssemblyLoadContext` e con l'uso di AppDomain. Con gli AppDomain, lo scaricamento è forzato. In fase di scaricamento, tutti i thread in esecuzione nell'AppDomain di destinazione vengono interrotti, gli oggetti COM gestiti creati nell'AppDomain di destinazione vengono eliminati definitivamente e così via. Con `AssemblyLoadContext`, lo scaricamento è di tipo "cooperativo". La chiamata al metodo <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> avvia semplicemente lo scaricamento. Lo scaricamento termina dopo che si sono verificate le condizioni seguenti:

- Nessuno dei thread include metodi relativi agli assembly caricati nell'`AssemblyLoadContext` nel rispettivo stack di chiamate.
- Nessuno dei tipi relativi agli assembly caricati nell'`AssemblyLoadContext`, nessuna delle istanze di questi tipi e nessuno degli assembly all'esterno dell'`AssemblyLoadContext` è referenziato da:
  - Riferimenti esterni all'`AssemblyLoadContext`, ad eccezione di riferimenti deboli (<xref:System.WeakReference> o <xref:System.WeakReference%601>).
  - Handle GC sicuri (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal> o <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) dall'interno e dall'esterno dell'`AssemblyLoadContext`.

## <a name="using-collectible-assemblyloadcontext"></a>Uso di un AssemblyLoadContext ritirabile

Questa sezione contiene un'esercitazione dettagliata che illustra come caricare in modo semplice un'applicazione .NET Core in un `AssemblyLoadContext` ritirabile, eseguirne il punto di ingresso e quindi scaricarlo. L'esempio completo è disponibile all'indirizzo <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.

### <a name="create-a-collectible-assemblyloadcontext"></a>Creare un AssemblyLoadContext ritirabile

È necessario derivare la classe dall'<xref:System.Runtime.Loader.AssemblyLoadContext> ed eseguire l'overload del relativo metodo <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>. Questo metodo risolve i riferimenti a tutti gli assembly che sono dipendenze degli assembly caricati nell'`AssemblyLoadContext`.
Il codice seguente offre un esempio della versione più semplice dell'`AssemblyLoadContext` personalizzato:

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

Come si può notare, il metodo `Load` restituisce `null`. Ciò significa che tutti gli assembly di dipendenza vengono caricati nel contesto predefinito e il nuovo contesto contiene solo gli assembly che vi sono stati caricati in modo esplicito.

Se si vuole che nell'`AssemblyLoadContext` vengano caricate anche alcune o tutte le dipendenze, è possibile usare l'oggetto `AssemblyDependencyResolver` nel metodo `Load`. L'oggetto `AssemblyDependencyResolver` risolve i nomi degli assembly in percorsi assoluti di file di assembly in base al file *.deps.json* contenuto nella directory dell'assembly principale caricato nel contesto e in base ai file di assembly in tale directory.

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a>Usare un AssemblyLoadContext ritirabile personalizzato

In questa sezione si presuppone che venga usata la versione più semplice dell'`TestAssemblyLoadContext`.

È possibile creare un'istanza dell'`AssemblyLoadContext` personalizzato e caricarvi un assembly, come indicato di seguito:

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

Per ogni assembly a cui fa riferimento l'assembly caricato, viene chiamato il metodo `TestAssemblyLoadContext.Load` in modo che `TestAssemblyLoadContext` possa determinare il percorso da cui ottenere l'assembly. In questo caso, viene restituito `null` per indicare che deve essere caricato nel contesto predefinito dai percorsi usati dal runtime per caricare gli assembly per impostazione predefinita.

Ora che è stato caricato un assembly, è possibile eseguire un metodo da tale contesto. Eseguire il metodo `Main`:

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

Dopo che il metodo `Main` ha restituito un risultato, è possibile avviare lo scaricamento chiamando il metodo `Unload` sull'`AssemblyLoadContext` personalizzato o rimuovendo il riferimento all'`AssemblyLoadContext`:

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

Questa operazione è sufficiente per scaricare l'assembly di test. È possibile includere tutto questo in un metodo separato non abilitato per l'inlining per assicurarsi che `TestAssemblyLoadContext`, `Assembly` e `MethodInfo` (ovvero l'`Assembly.EntryPoint`) non possano essere mantenuti attivi da riferimenti di slot dello stack (variabili locali reali o introdotte da JIT). Tali riferimenti potrebbero mantenere attivi `TestAssemblyLoadContext` e impedire lo scaricamento.

Restituire inoltre un riferimento debole all'`AssemblyLoadContext` in modo da poterlo usare in un secondo momento per determinare che lo scaricamento è stato completato.

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

A questo punto è possibile eseguire questa funzione per caricare, eseguire e scaricare l'assembly.

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

Lo scaricamento non viene tuttavia completato immediatamente. Come indicato in precedenza, si basa sul processo di Garbage Collection per raccogliere tutti gli oggetti dall'assembly di test. In molti casi non è necessario attendere il completamento dello scaricamento. Vi sono tuttavia casi in cui è utile sapere che l'operazione è stata completata, ad esempio quando è necessario eliminare il file di assembly caricato nell'`AssemblyLoadContext` personalizzato dal disco. In casi come questo è possibile usare il frammento di codice seguente. Attiva un processo di Garbage Collection e rimane in attesa dei finalizzatori in sospeso in un ciclo finché il riferimento debole all'`AssemblyLoadContext` personalizzato non è impostato su `null`, a indicare che l'oggetto di destinazione è stato raccolto. Si noti che, nella maggior parte dei casi, è sufficiente un passaggio attraverso il ciclo. Tuttavia, per i casi più complessi, in cui gli oggetti creati dal codice in esecuzione nell'`AssemblyLoadContext` hanno finalizzatori, può essere necessario un numero maggiore di passaggi.

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a>L'evento di scaricamento

Talvolta può essere necessario che il codice caricato in un `AssemblyLoadContext` personalizzato esegua alcune operazioni di pulizia in fase di avvio dello scaricamento. Può ad esempio essere necessario arrestare i thread, pulire alcuni handle GC sicuri e così via. In questi casi può essere usato l'evento `Unloading`. A questo evento può essere associato un gestore che esegue la pulizia necessaria.

### <a name="troubleshoot-unloadability-issues"></a>Risolvere i problemi di scaricamento

Considerata la natura cooperativa dello scaricamento, può capitare spesso di dimenticare i riferimenti che mantengono attivi gli elementi presenti in un `AssemblyLoadContext` ritirabile e impediscono lo scaricamento. Di seguito è riportato un riepilogo degli oggetti (alcuni dei quali non ovvi) che possono mantenere attivi i riferimenti:

- Riferimenti regolari all'esterno dell'`AssemblyLoadContext` ritirabile, memorizzati in uno slot dello stack o in un registro del processore (variabili locali del metodo, create in modo esplicito dal codice utente o in modo implicito da JIT), in una variabile statica o in un handle GC sicuro o di blocco, che puntano in modo transitivo a:
  - Un assembly caricato nell'`AssemblyLoadContext` ritirabile.
  - Un tipo di tale assembly.
  - Un'istanza di un tipo incluso in tale assembly.
- Thread che eseguono codice da un assembly caricato nell'`AssemblyLoadContext` ritirabile.
- Istanze di tipi `AssemblyLoadContext` personalizzati non ritirabili creati all'interno dell'`AssemblyLoadContext` ritirabile
- Istanze di <xref:System.Threading.RegisteredWaitHandle> in sospeso con callback impostati sui metodi nell'`AssemblyLoadContext` personalizzato

Suggerimenti per trovare lo slot dello stack o il registro del processore alla radice di un oggetto:

- Il passaggio dei risultati delle chiamate di funzione direttamente a un'altra funzione può creare una radice anche in assenza di variabili locali create dall'utente.
- Se un riferimento a un oggetto era disponibile in un punto qualsiasi di un metodo, è possibile che JIT abbia deciso di mantenerlo in uno slot dello stack o in un registro del processore per tutto il tempo desiderato nella funzione corrente.

## <a name="debug-unloading-issues"></a>Eseguire il debug dei problemi di scaricamento

Il debug dei problemi relativi allo scaricamento può essere tedioso. Possono verificarsi situazioni in cui non si riesce a capire ciò che mantiene attivo un `AssemblyLoadContext`, ma lo scaricamento ha esito negativo.
La strategia migliore per risolvere problemi di questo tipo è quella di usare WinDbg (LLDB su Unix) con il plug-in SOS. È necessario trovare ciò che mantiene attiva un'istanza di `LoaderAllocator` appartenente allo specifico `AssemblyLoadContext`.
Questo plug-in consente di esaminare gli oggetti heap GC e le relative gerarchie e radici.
Per caricare il plug-in nel debugger, immettere il comando seguente nella riga di comando del debugger:

In WinDbg (sembra che WinDbg esegua automaticamente questa operazione quando inserisce un'interruzione nell'applicazione .NET Core):

```console
.loadby sos coreclr
```

In LLDB:

```console
plugin load /path/to/libsosplugin.so
```

Si proverà a eseguire il debug di un programma di esempio che presenta problemi di scaricamento. Di seguito è incluso il codice sorgente. Quando viene eseguito in WinDbg, il programma si interrompe nel debugger subito dopo il tentativo di verifica dello scaricamento. A questo punto è possibile iniziare a cercare i colpevoli.

Si noti che, se si esegue il debug con LLDB in Unix, i comandi SOS negli esempi seguenti non devono essere preceduti da `!`.

```console
!dumpheap -type LoaderAllocator
```

Questo comando esegue il dump di tutti gli oggetti con un nome di tipo contenente `LoaderAllocator` che si trovano nell'heap GC. Ecco un esempio:

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48     
000002b78000ceb0 00007ffadc93a218       24     

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

Nella sezione "Statistics:" controllare l'oggetto `MT` (`MethodTable`) appartenente alla classe `System.Reflection.LoaderAllocator`, che è l'oggetto a cui si è interessati. Quindi, nell'elenco all'inizio, trovare la voce con il valore di `MT` corrispondente e ottenere l'indirizzo dell'oggetto stesso. In questo caso, l'indirizzo è "000002b78000ce40"

Ora che si conosce l'indirizzo dell'oggetto `LoaderAllocator`, è possibile usare un altro comando per trovare le relative radici GC

```console
!gcroot -all 0x000002b78000ce40 
```

Questo comando esegue il dump della catena di riferimenti agli oggetti che portano all'istanza di `LoaderAllocator`. L'elenco inizia con la radice, ovvero l'entità che mantiene attiva l'istanza di `LoaderAllocator` e pertanto è il nucleo del problema di cui si sta eseguendo il debug. La radice può essere uno slot dello stack, un registro del processore, un handle GC o una variabile statica.

Di seguito è riportato un esempio dell'output del comando `gcroot`:

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

A questo punto è necessario identificare la posizione della radice per poterla correggere. Il caso più semplice è quello in cui la radice è uno slot dello stack o un registro del processore. In tal caso, l'oggetto `gcroot` mostra il nome della funzione il cui frame contiene la radice e il thread che esegue tale funzione. Il caso più complicato è quello in cui la radice è una variabile statica o un handle GC. 

Nell'esempio precedente, la prima radice è una variabile locale di tipo `System.Reflection.RuntimeMethodInfo` memorizzata nel frame della funzione `example.Program.Main(System.String[])` all'indirizzo `rbp-20` (`rbp` è il registro del processore `rbp` e -20 è un offset esadecimale rispetto a tale registro).

La seconda radice è un oggetto `GCHandle` normale (sicuro) che contiene un riferimento a un'istanza della classe `test.Test`. 

La terza radice è un oggetto `GCHandle` bloccato. Si tratta in realtà di una variabile statica. Purtroppo non esiste alcun modo per capirlo. Le entità statiche per i tipi di riferimento vengono memorizzate in una matrice di oggetti gestiti in strutture di runtime interne.

Un altro caso che può impedire lo scaricamento di un `AssemblyLoadContext` è quello in cui un thread presenta un frame di un metodo di un assembly caricato nell'`AssemblyLoadContext` nel relativo stack. È possibile verificarlo eseguendo il dump degli stack di chiamate gestite di tutti i thread:

```console
~*e !clrstack
```

Questo comando indica di applicare il comando `!clrstack` a tutti i thread. Di seguito è riportato l'output del comando per l'esempio. Purtroppo, LLDB in Unix non dispone di alcun modo per applicare un comando a tutti i thread ed è quindi necessario passare da un thread all'altro e ripetere il comando `clrstack` manualmente.
Ignorare tutti i thread in cui il debugger riporta il messaggio "Unable to walk the managed stack" per segnalare che non è possibile esaminare lo stack gestito.

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998] 
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28] 
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0] 
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000 
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568] 
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0] 

```

Come si può notare, nell'ultimo thread è presente `test.Program.ThreadProc()`. Si tratta di una funzione dell'assembly caricato nell'`AssemblyLoadContext` che mantiene quindi attivo l'`AssemblyLoadContext`.

## <a name="example-source-with-unloadability-issues"></a>Esempio di codice sorgente con problemi di scaricamento

Il codice seguente viene usato nell'esempio di debug precedente.

### <a name="main-testing-program"></a>Programma di test principale

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a>Programma caricato in TestAssemblyLoadContext

Il codice seguente rappresenta l'oggetto `test.dll` passato al metodo `ExecuteAndUnload` nel programma di test principale.

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
