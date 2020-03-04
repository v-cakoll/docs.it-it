---
title: Come usare ed eseguire il debug di assembly non caricabili in .NET Core
description: Informazioni su come usare un oggetto AssemblyLoadContext ritirabile per caricare e scaricare assembly gestiti e come eseguire il debug di problemi che impediscono lo scaricamento.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 267c2209556b66ab3541c9c79c99d7eceb2024da
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159741"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="489b3-103">Come usare ed eseguire il debug di assembly non caricabili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="489b3-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="489b3-104">A partire da .NET Core 3.0, è supportata la possibilità di caricare e successivamente scaricare un set di assembly.</span><span class="sxs-lookup"><span data-stu-id="489b3-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="489b3-105">In .NET Framework, per questo scopo vengono usati domini di app personalizzati, ma .NET Core supporta un singolo dominio di app predefinito.</span><span class="sxs-lookup"><span data-stu-id="489b3-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="489b3-106">.NET Core 3.0 e versioni successive supportano la possibilità di scaricamento tramite la classe <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="489b3-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="489b3-107">È possibile caricare un set di assembly in un oggetto `AssemblyLoadContext` ritirabile, eseguirvi metodi o semplicemente ispezionarli tramite reflection e infine scaricare l'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="489b3-108">Che Scarica gli assembly caricati nel `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-108">That unloads the assemblies loaded into the `AssemblyLoadContext`.</span></span>

<span data-ttu-id="489b3-109">Esiste una differenza rilevante tra lo scaricamento tramite `AssemblyLoadContext` e con l'uso di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="489b3-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="489b3-110">Con gli AppDomain, lo scaricamento è forzato.</span><span class="sxs-lookup"><span data-stu-id="489b3-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="489b3-111">In fase di scaricamento, tutti i thread in esecuzione nell'AppDomain di destinazione vengono interrotti, gli oggetti COM gestiti creati nell'AppDomain di destinazione vengono eliminati definitivamente e così via.</span><span class="sxs-lookup"><span data-stu-id="489b3-111">At unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, and so on.</span></span> <span data-ttu-id="489b3-112">Con `AssemblyLoadContext`, lo scaricamento è di tipo "cooperativo".</span><span class="sxs-lookup"><span data-stu-id="489b3-112">With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="489b3-113">La chiamata al metodo <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> avvia semplicemente lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="489b3-114">Lo scaricamento termina dopo che si sono verificate le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="489b3-114">The unloading finishes after:</span></span>

- <span data-ttu-id="489b3-115">Nessuno dei thread include metodi relativi agli assembly caricati nell'`AssemblyLoadContext` nel rispettivo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="489b3-115">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="489b3-116">Nessuno dei tipi degli assembly caricati nel `AssemblyLoadContext`, le istanze di tali tipi e gli assembly a cui viene fatto riferimento:</span><span class="sxs-lookup"><span data-stu-id="489b3-116">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types, and the assemblies themselves are referenced by:</span></span>
  - <span data-ttu-id="489b3-117">Riferimenti esterni all'`AssemblyLoadContext`, ad eccezione di riferimenti deboli (<xref:System.WeakReference> o <xref:System.WeakReference%601>).</span><span class="sxs-lookup"><span data-stu-id="489b3-117">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="489b3-118">Handle di Garbage Collector forte (GC) ([GCHandleType. Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) o [GCHandleType. bloccato](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) sia all'interno che all'esterno del `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-118">Strong garbage collector (GC) handles ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) or [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="use-collectible-assemblyloadcontext"></a><span data-ttu-id="489b3-119">USA AssemblyLoadContext da collezione</span><span class="sxs-lookup"><span data-stu-id="489b3-119">Use collectible AssemblyLoadContext</span></span>

<span data-ttu-id="489b3-120">Questa sezione contiene un'esercitazione dettagliata che illustra come caricare in modo semplice un'applicazione .NET Core in un `AssemblyLoadContext` ritirabile, eseguirne il punto di ingresso e quindi scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="489b3-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="489b3-121">È possibile trovare un esempio completo in [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span><span class="sxs-lookup"><span data-stu-id="489b3-121">You can find a complete sample at [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="489b3-122">Creare un AssemblyLoadContext ritirabile</span><span class="sxs-lookup"><span data-stu-id="489b3-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="489b3-123">È necessario derivare la classe dall'<xref:System.Runtime.Loader.AssemblyLoadContext> ed eseguire l'overload del relativo metodo <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="489b3-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="489b3-124">Questo metodo risolve i riferimenti a tutti gli assembly che sono dipendenze degli assembly caricati nell'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="489b3-125">Il codice seguente offre un esempio della versione più semplice dell'`AssemblyLoadContext` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="489b3-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="489b3-126">Come si può notare, il metodo `Load` restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="489b3-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="489b3-127">Ciò significa che tutti gli assembly di dipendenza vengono caricati nel contesto predefinito e il nuovo contesto contiene solo gli assembly che vi sono stati caricati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="489b3-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="489b3-128">Se si vuole che nell'`AssemblyLoadContext` vengano caricate anche alcune o tutte le dipendenze, è possibile usare l'oggetto `AssemblyDependencyResolver` nel metodo `Load`.</span><span class="sxs-lookup"><span data-stu-id="489b3-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="489b3-129">Il `AssemblyDependencyResolver` risolve i nomi degli assembly nei percorsi assoluti dei file di assembly.</span><span class="sxs-lookup"><span data-stu-id="489b3-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths.</span></span> <span data-ttu-id="489b3-130">Il resolver usa il file con estensione *Deps. JSON* e i file di assembly nella directory dell'assembly principale caricato nel contesto.</span><span class="sxs-lookup"><span data-stu-id="489b3-130">The resolver uses the *.deps.json* file and assembly files in the directory of the main assembly loaded into the context.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="489b3-131">Usare un AssemblyLoadContext ritirabile personalizzato</span><span class="sxs-lookup"><span data-stu-id="489b3-131">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="489b3-132">In questa sezione si presuppone che venga usata la versione più semplice dell'`TestAssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-132">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="489b3-133">È possibile creare un'istanza dell'`AssemblyLoadContext` personalizzato e caricarvi un assembly, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="489b3-133">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="489b3-134">Per ogni assembly a cui fa riferimento l'assembly caricato, viene chiamato il metodo `TestAssemblyLoadContext.Load` in modo che `TestAssemblyLoadContext` possa determinare il percorso da cui ottenere l'assembly.</span><span class="sxs-lookup"><span data-stu-id="489b3-134">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="489b3-135">In questo caso, viene restituito `null` per indicare che deve essere caricato nel contesto predefinito dai percorsi usati dal runtime per caricare gli assembly per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="489b3-135">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="489b3-136">Ora che è stato caricato un assembly, è possibile eseguire un metodo da tale contesto.</span><span class="sxs-lookup"><span data-stu-id="489b3-136">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="489b3-137">Eseguire il metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="489b3-137">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="489b3-138">Dopo che il metodo `Main` ha restituito un risultato, è possibile avviare lo scaricamento chiamando il metodo `Unload` sull'`AssemblyLoadContext` personalizzato o rimuovendo il riferimento all'`AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="489b3-138">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="489b3-139">Questa operazione è sufficiente per scaricare l'assembly di test.</span><span class="sxs-lookup"><span data-stu-id="489b3-139">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="489b3-140">È possibile includere tutto questo in un metodo separato non abilitato per l'inlining per assicurarsi che `TestAssemblyLoadContext`, `Assembly` e `MethodInfo` (ovvero l'`Assembly.EntryPoint`) non possano essere mantenuti attivi da riferimenti di slot dello stack (variabili locali reali o introdotte da JIT).</span><span class="sxs-lookup"><span data-stu-id="489b3-140">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="489b3-141">Tali riferimenti potrebbero mantenere attivi `TestAssemblyLoadContext` e impedire lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-141">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="489b3-142">Restituire inoltre un riferimento debole all'`AssemblyLoadContext` in modo da poterlo usare in un secondo momento per determinare che lo scaricamento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="489b3-142">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="489b3-143">A questo punto è possibile eseguire questa funzione per caricare, eseguire e scaricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="489b3-143">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="489b3-144">Lo scaricamento non viene tuttavia completato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="489b3-144">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="489b3-145">Come indicato in precedenza, si basa sulla Garbage Collector raccogliere tutti gli oggetti dall'assembly di test.</span><span class="sxs-lookup"><span data-stu-id="489b3-145">As previously mentioned, it relies on the garbage collector to collect all the objects from the test assembly.</span></span> <span data-ttu-id="489b3-146">In molti casi non è necessario attendere il completamento dello scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-146">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="489b3-147">Vi sono tuttavia casi in cui è utile sapere che l'operazione è stata completata,</span><span class="sxs-lookup"><span data-stu-id="489b3-147">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="489b3-148">ad esempio quando è necessario eliminare il file di assembly caricato nell'`AssemblyLoadContext` personalizzato dal disco.</span><span class="sxs-lookup"><span data-stu-id="489b3-148">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="489b3-149">In casi come questo è possibile usare il frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="489b3-149">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="489b3-150">Attiva Garbage Collection e attende che i finalizzatori in sospeso si trovino in un ciclo fino a quando il riferimento debole al `AssemblyLoadContext` personalizzato non è impostato su `null`, a indicare che l'oggetto di destinazione è stato raccolto.</span><span class="sxs-lookup"><span data-stu-id="489b3-150">It triggers garbage collection and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="489b3-151">Nella maggior parte dei casi, è necessario solo un pass-through del ciclo.</span><span class="sxs-lookup"><span data-stu-id="489b3-151">In most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="489b3-152">Tuttavia, per i casi più complessi, in cui gli oggetti creati dal codice in esecuzione nell'`AssemblyLoadContext` hanno finalizzatori, può essere necessario un numero maggiore di passaggi.</span><span class="sxs-lookup"><span data-stu-id="489b3-152">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="489b3-153">L'evento di scaricamento</span><span class="sxs-lookup"><span data-stu-id="489b3-153">The Unloading event</span></span>

<span data-ttu-id="489b3-154">Talvolta può essere necessario che il codice caricato in un `AssemblyLoadContext` personalizzato esegua alcune operazioni di pulizia in fase di avvio dello scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-154">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="489b3-155">Ad esempio, potrebbe essere necessario arrestare i thread o pulire gli handle GC complessi.</span><span class="sxs-lookup"><span data-stu-id="489b3-155">For example, it may need to stop threads or clean up strong GC handles.</span></span> <span data-ttu-id="489b3-156">In questi casi può essere usato l'evento `Unloading`.</span><span class="sxs-lookup"><span data-stu-id="489b3-156">The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="489b3-157">A questo evento può essere associato un gestore che esegue la pulizia necessaria.</span><span class="sxs-lookup"><span data-stu-id="489b3-157">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="489b3-158">Risolvere i problemi di scaricamento</span><span class="sxs-lookup"><span data-stu-id="489b3-158">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="489b3-159">A causa della natura cooperativa dello scaricamento, è facile dimenticare i riferimenti che potrebbero mantenere il materiale in un `AssemblyLoadContext` ritirabile e impedire lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-159">Due to the cooperative nature of the unloading, it's easy to forget about references that may be keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="489b3-160">Di seguito è riportato un riepilogo delle entità (alcune delle quali non sono ovvie) che possono conservare i riferimenti:</span><span class="sxs-lookup"><span data-stu-id="489b3-160">Here is a summary of entities (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="489b3-161">I riferimenti regolari detenuti dall'esterno dei `AssemblyLoadContext` ritirabili archiviati in uno slot dello stack o in un registro del processore (variabili locali del metodo, creati in modo esplicito dal codice utente o in modo implicito dal compilatore just-in-time (JIT)), una variabile statica o un handle GC sicuro (blocco) e che puntano in modo transitivo a:</span><span class="sxs-lookup"><span data-stu-id="489b3-161">Regular references held from outside of the collectible `AssemblyLoadContext` that are stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the just-in-time (JIT) compiler), a static variable, or a strong (pinning) GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="489b3-162">Un assembly caricato nell'`AssemblyLoadContext` ritirabile.</span><span class="sxs-lookup"><span data-stu-id="489b3-162">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="489b3-163">Un tipo di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="489b3-163">A type from such an assembly.</span></span>
  - <span data-ttu-id="489b3-164">Un'istanza di un tipo incluso in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="489b3-164">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="489b3-165">Thread che eseguono codice da un assembly caricato nell'`AssemblyLoadContext` ritirabile.</span><span class="sxs-lookup"><span data-stu-id="489b3-165">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="489b3-166">Istanze di tipi di `AssemblyLoadContext` personalizzati e non ritirabili creati all'interno del `AssemblyLoadContext`ritirabile.</span><span class="sxs-lookup"><span data-stu-id="489b3-166">Instances of custom, non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="489b3-167">In sospeso <xref:System.Threading.RegisteredWaitHandle> istanze con callback impostati sui metodi nel `AssemblyLoadContext`personalizzato.</span><span class="sxs-lookup"><span data-stu-id="489b3-167">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`.</span></span>

> [!TIP]
> <span data-ttu-id="489b3-168">I riferimenti agli oggetti archiviati negli slot dello stack o nei registri del processore e che potrebbero impedire lo scaricamento di un `AssemblyLoadContext` possono verificarsi nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="489b3-168">Object references that are stored in stack slots or processor registers and that could prevent unloading of an `AssemblyLoadContext` can occur in the following situations:</span></span>
>
> - <span data-ttu-id="489b3-169">Quando i risultati della chiamata di funzione vengono passati direttamente a un'altra funzione, anche se non è presente alcuna variabile locale creata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="489b3-169">When function call results are passed directly to another function, even though there is no user-created local variable.</span></span>
> - <span data-ttu-id="489b3-170">Quando il compilatore JIT mantiene un riferimento a un oggetto che era disponibile in un determinato punto di un metodo.</span><span class="sxs-lookup"><span data-stu-id="489b3-170">When the JIT compiler keeps a reference to an object that was available at some point in a method.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="489b3-171">Eseguire il debug dei problemi di scaricamento</span><span class="sxs-lookup"><span data-stu-id="489b3-171">Debug unloading issues</span></span>

<span data-ttu-id="489b3-172">Il debug dei problemi relativi allo scaricamento può essere tedioso.</span><span class="sxs-lookup"><span data-stu-id="489b3-172">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="489b3-173">Possono verificarsi situazioni in cui non si riesce a capire ciò che mantiene attivo un `AssemblyLoadContext`, ma lo scaricamento ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="489b3-173">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span> <span data-ttu-id="489b3-174">La strategia migliore per risolvere problemi di questo tipo è quella di usare WinDbg (LLDB su Unix) con il plug-in SOS.</span><span class="sxs-lookup"><span data-stu-id="489b3-174">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="489b3-175">È necessario trovare ciò che mantiene attiva un'istanza di `LoaderAllocator` appartenente allo specifico `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-175">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span> <span data-ttu-id="489b3-176">Il plug-in SOS consente di esaminare gli oggetti heap GC, le gerarchie e le radici.</span><span class="sxs-lookup"><span data-stu-id="489b3-176">The SOS plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>

<span data-ttu-id="489b3-177">Per caricare il plug-in nel debugger, immettere il comando seguente nella riga di comando del debugger:</span><span class="sxs-lookup"><span data-stu-id="489b3-177">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="489b3-178">In WinDbg (sembra che WinDbg esegua automaticamente questa operazione quando inserisce un'interruzione nell'applicazione .NET Core):</span><span class="sxs-lookup"><span data-stu-id="489b3-178">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="489b3-179">In LLDB:</span><span class="sxs-lookup"><span data-stu-id="489b3-179">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="489b3-180">Viene ora eseguito il debug di un programma di esempio con problemi di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-180">Let's debug an example program that has problems with unloading.</span></span> <span data-ttu-id="489b3-181">Di seguito è incluso il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="489b3-181">Source code is included below.</span></span> <span data-ttu-id="489b3-182">Quando viene eseguito in WinDbg, il programma si interrompe nel debugger subito dopo il tentativo di verifica dello scaricamento.</span><span class="sxs-lookup"><span data-stu-id="489b3-182">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="489b3-183">A questo punto è possibile iniziare a cercare i colpevoli.</span><span class="sxs-lookup"><span data-stu-id="489b3-183">You can then start looking for the culprits.</span></span>

> [!TIP]
> <span data-ttu-id="489b3-184">Se si esegue il debug con LLDB in UNIX, i comandi SOS negli esempi seguenti non hanno le `!` di fronte.</span><span class="sxs-lookup"><span data-stu-id="489b3-184">If you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="489b3-185">Questo comando esegue il dump di tutti gli oggetti con un nome di tipo contenente `LoaderAllocator` che si trovano nell'heap GC.</span><span class="sxs-lookup"><span data-stu-id="489b3-185">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="489b3-186">Esempio:</span><span class="sxs-lookup"><span data-stu-id="489b3-186">Here is an example:</span></span>

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

<span data-ttu-id="489b3-187">Nella sezione "Statistics:" controllare l'oggetto `MT` (`MethodTable`) appartenente alla classe `System.Reflection.LoaderAllocator`, che è l'oggetto a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="489b3-187">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="489b3-188">Quindi, nell'elenco all'inizio, trovare la voce con `MT` corrispondente a tale voce e ottenere l'indirizzo dell'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="489b3-188">Then, in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="489b3-189">In questo caso, è "000002b78000ce40".</span><span class="sxs-lookup"><span data-stu-id="489b3-189">In our case, it is "000002b78000ce40".</span></span>

<span data-ttu-id="489b3-190">Ora che si conosce l'indirizzo dell'oggetto `LoaderAllocator`, è possibile usare un altro comando per trovare le relative radici GC:</span><span class="sxs-lookup"><span data-stu-id="489b3-190">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots:</span></span>

```console
!gcroot -all 0x000002b78000ce40
```

<span data-ttu-id="489b3-191">Questo comando esegue il dump della catena di riferimenti agli oggetti che portano all'istanza di `LoaderAllocator`.</span><span class="sxs-lookup"><span data-stu-id="489b3-191">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="489b3-192">L'elenco inizia con la radice, ovvero l'entità che mantiene il `LoaderAllocator` attivo e pertanto è il nucleo del problema.</span><span class="sxs-lookup"><span data-stu-id="489b3-192">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem.</span></span> <span data-ttu-id="489b3-193">La radice può essere uno slot dello stack, un registro del processore, un handle GC o una variabile statica.</span><span class="sxs-lookup"><span data-stu-id="489b3-193">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="489b3-194">Di seguito è riportato un esempio dell'output del comando `gcroot`:</span><span class="sxs-lookup"><span data-stu-id="489b3-194">Here is an example of the output of the `gcroot` command:</span></span>

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

<span data-ttu-id="489b3-195">Il passaggio successivo consiste nel determinare dove si trova la radice in modo che sia possibile risolverlo.</span><span class="sxs-lookup"><span data-stu-id="489b3-195">The next step is to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="489b3-196">Il caso più semplice è quello in cui la radice è uno slot dello stack o un registro del processore.</span><span class="sxs-lookup"><span data-stu-id="489b3-196">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="489b3-197">In tal caso, il `gcroot` Mostra il nome della funzione il cui frame contiene la radice e il thread che esegue tale funzione.</span><span class="sxs-lookup"><span data-stu-id="489b3-197">In that case, the `gcroot` shows the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="489b3-198">Il caso più complicato è quello in cui la radice è una variabile statica o un handle GC.</span><span class="sxs-lookup"><span data-stu-id="489b3-198">The difficult case is when the root is a static variable or a GC handle.</span></span>

<span data-ttu-id="489b3-199">Nell'esempio precedente, la prima radice è una variabile locale di tipo `System.Reflection.RuntimeMethodInfo` memorizzata nel frame della funzione `example.Program.Main(System.String[])` all'indirizzo `rbp-20` (`rbp` è il registro del processore `rbp` e -20 è un offset esadecimale rispetto a tale registro).</span><span class="sxs-lookup"><span data-stu-id="489b3-199">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="489b3-200">La seconda radice è un oggetto `GCHandle` normale (sicuro) che contiene un riferimento a un'istanza della classe `test.Test`.</span><span class="sxs-lookup"><span data-stu-id="489b3-200">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span>

<span data-ttu-id="489b3-201">La terza radice è un oggetto `GCHandle` bloccato.</span><span class="sxs-lookup"><span data-stu-id="489b3-201">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="489b3-202">Questo è in realtà una variabile statica, ma sfortunatamente non esiste alcun modo per indicare.</span><span class="sxs-lookup"><span data-stu-id="489b3-202">This one is actually a static variable, but unfortunately, there is no way to tell.</span></span> <span data-ttu-id="489b3-203">Le entità statiche per i tipi di riferimento vengono memorizzate in una matrice di oggetti gestiti in strutture di runtime interne.</span><span class="sxs-lookup"><span data-stu-id="489b3-203">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="489b3-204">Un altro caso che può impedire lo scaricamento di un `AssemblyLoadContext` è quello in cui un thread presenta un frame di un metodo di un assembly caricato nell'`AssemblyLoadContext` nel relativo stack.</span><span class="sxs-lookup"><span data-stu-id="489b3-204">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="489b3-205">È possibile verificarlo eseguendo il dump degli stack di chiamate gestite di tutti i thread:</span><span class="sxs-lookup"><span data-stu-id="489b3-205">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="489b3-206">Questo comando indica di applicare il comando `!clrstack` a tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="489b3-206">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="489b3-207">Di seguito è riportato l'output del comando per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="489b3-207">The following is the output of that command for the example.</span></span> <span data-ttu-id="489b3-208">Sfortunatamente, LLDB in UNIX non ha alcun modo per applicare un comando a tutti i thread, quindi è necessario cambiare manualmente i thread e ripetere il comando `clrstack`.</span><span class="sxs-lookup"><span data-stu-id="489b3-208">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you must manually switch threads and repeat the `clrstack` command.</span></span> <span data-ttu-id="489b3-209">Ignorare tutti i thread in cui il debugger indica che "non è possibile esaminare lo stack gestito".</span><span class="sxs-lookup"><span data-stu-id="489b3-209">Ignore all threads where the debugger says "Unable to walk the managed stack".</span></span>

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

<span data-ttu-id="489b3-210">Come si può notare, nell'ultimo thread è presente `test.Program.ThreadProc()`.</span><span class="sxs-lookup"><span data-stu-id="489b3-210">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="489b3-211">Si tratta di una funzione dell'assembly caricato nell'`AssemblyLoadContext` che mantiene quindi attivo l'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="489b3-211">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="489b3-212">Esempio di codice sorgente con problemi di scaricamento</span><span class="sxs-lookup"><span data-stu-id="489b3-212">Example source with unloadability issues</span></span>

<span data-ttu-id="489b3-213">Il codice seguente viene usato nell'esempio di debug precedente.</span><span class="sxs-lookup"><span data-stu-id="489b3-213">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="489b3-214">Programma di test principale</span><span class="sxs-lookup"><span data-stu-id="489b3-214">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="489b3-215">Programma caricato in TestAssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="489b3-215">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="489b3-216">Il codice seguente rappresenta il file *test. dll* passato al metodo `ExecuteAndUnload` nel programma di test principale.</span><span class="sxs-lookup"><span data-stu-id="489b3-216">The following code represents the *test.dll* passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
