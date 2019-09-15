---
title: Come usare ed eseguire il debug di assembly non caricabili in .NET Core
description: Informazioni su come usare un oggetto AssemblyLoadContext ritirabile per caricare e scaricare assembly gestiti e come eseguire il debug di problemi che impediscono lo scaricamento.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 52cd864393342e2bc31f872b9d09cb484c2c8463
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972991"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="093e7-103">Come usare ed eseguire il debug di assembly non caricabili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="093e7-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="093e7-104">A partire da .NET Core 3.0, è supportata la possibilità di caricare e successivamente scaricare un set di assembly.</span><span class="sxs-lookup"><span data-stu-id="093e7-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="093e7-105">In .NET Framework, per questo scopo vengono usati domini di app personalizzati, ma .NET Core supporta un singolo dominio di app predefinito.</span><span class="sxs-lookup"><span data-stu-id="093e7-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="093e7-106">.NET Core 3.0 e versioni successive supportano la possibilità di scaricamento tramite la classe <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="093e7-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="093e7-107">È possibile caricare un set di assembly in un oggetto `AssemblyLoadContext` ritirabile, eseguirvi metodi o semplicemente ispezionarli tramite reflection e infine scaricare l'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="093e7-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="093e7-108">In questo modo, gli assembly caricati nell'`AssemblyLoadContext` vengono scaricati.</span><span class="sxs-lookup"><span data-stu-id="093e7-108">That unloads the assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="093e7-109">Esiste una differenza rilevante tra lo scaricamento tramite `AssemblyLoadContext` e con l'uso di AppDomain.</span><span class="sxs-lookup"><span data-stu-id="093e7-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="093e7-110">Con gli AppDomain, lo scaricamento è forzato.</span><span class="sxs-lookup"><span data-stu-id="093e7-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="093e7-111">Al momento dello scaricamento, tutti i thread in esecuzione nell'AppDomain di destinazione vengono interrotti, gli oggetti COM gestiti creati nell'AppDomain di destinazione vengono eliminati e così via. Con `AssemblyLoadContext`, lo scaricamento è "cooperativa".</span><span class="sxs-lookup"><span data-stu-id="093e7-111">At unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, etc. With `AssemblyLoadContext`, the unload is "cooperative."</span></span> <span data-ttu-id="093e7-112">La chiamata al metodo <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> avvia semplicemente lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-112">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="093e7-113">Lo scaricamento termina dopo che si sono verificate le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="093e7-113">The unloading finishes after:</span></span>

- <span data-ttu-id="093e7-114">Nessuno dei thread include metodi relativi agli assembly caricati nell'`AssemblyLoadContext` nel rispettivo stack di chiamate.</span><span class="sxs-lookup"><span data-stu-id="093e7-114">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="093e7-115">Nessuno dei tipi relativi agli assembly caricati nell'`AssemblyLoadContext`, nessuna delle istanze di questi tipi e nessuno degli assembly all'esterno dell'`AssemblyLoadContext` è referenziato da:</span><span class="sxs-lookup"><span data-stu-id="093e7-115">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types and the assemblies themselves outside of the `AssemblyLoadContext` are referenced by:</span></span>
  - <span data-ttu-id="093e7-116">Riferimenti esterni all'`AssemblyLoadContext`, ad eccezione di riferimenti deboli (<xref:System.WeakReference> o <xref:System.WeakReference%601>).</span><span class="sxs-lookup"><span data-stu-id="093e7-116">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="093e7-117">Handle GC sicuri (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span><span class="sxs-lookup"><span data-stu-id="093e7-117">Strong GC handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span></span> <span data-ttu-id="093e7-118">o <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) dall'interno e dall'esterno dell'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="093e7-118">or <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="use-collectible-assemblyloadcontext"></a><span data-ttu-id="093e7-119">USA AssemblyLoadContext da collezione</span><span class="sxs-lookup"><span data-stu-id="093e7-119">Use collectible AssemblyLoadContext</span></span>

<span data-ttu-id="093e7-120">Questa sezione contiene un'esercitazione dettagliata che illustra come caricare in modo semplice un'applicazione .NET Core in un `AssemblyLoadContext` ritirabile, eseguirne il punto di ingresso e quindi scaricarlo.</span><span class="sxs-lookup"><span data-stu-id="093e7-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="093e7-121">È possibile trovare un esempio completo all' [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="093e7-121">You can find a complete sample at [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="093e7-122">Creare un AssemblyLoadContext ritirabile</span><span class="sxs-lookup"><span data-stu-id="093e7-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="093e7-123">È necessario derivare la classe dall'<xref:System.Runtime.Loader.AssemblyLoadContext> ed eseguire l'overload del relativo metodo <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="093e7-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="093e7-124">Questo metodo risolve i riferimenti a tutti gli assembly che sono dipendenze degli assembly caricati nell'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="093e7-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>
<span data-ttu-id="093e7-125">Il codice seguente offre un esempio della versione più semplice dell'`AssemblyLoadContext` personalizzato:</span><span class="sxs-lookup"><span data-stu-id="093e7-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="093e7-126">Come si può notare, il metodo `Load` restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="093e7-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="093e7-127">Ciò significa che tutti gli assembly di dipendenza vengono caricati nel contesto predefinito e il nuovo contesto contiene solo gli assembly che vi sono stati caricati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="093e7-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="093e7-128">Se si vuole che nell'`AssemblyLoadContext` vengano caricate anche alcune o tutte le dipendenze, è possibile usare l'oggetto `AssemblyDependencyResolver` nel metodo `Load`.</span><span class="sxs-lookup"><span data-stu-id="093e7-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="093e7-129">L'oggetto `AssemblyDependencyResolver` risolve i nomi degli assembly in percorsi assoluti di file di assembly in base al file *.deps.json* contenuto nella directory dell'assembly principale caricato nel contesto e in base ai file di assembly in tale directory.</span><span class="sxs-lookup"><span data-stu-id="093e7-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths using the *.deps.json* file contained in the directory of the main assembly loaded into the context and using assembly files in that directory.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="093e7-130">Usare un AssemblyLoadContext ritirabile personalizzato</span><span class="sxs-lookup"><span data-stu-id="093e7-130">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="093e7-131">In questa sezione si presuppone che venga usata la versione più semplice dell'`TestAssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="093e7-131">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="093e7-132">È possibile creare un'istanza dell'`AssemblyLoadContext` personalizzato e caricarvi un assembly, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="093e7-132">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="093e7-133">Per ogni assembly a cui fa riferimento l'assembly caricato, viene chiamato il metodo `TestAssemblyLoadContext.Load` in modo che `TestAssemblyLoadContext` possa determinare il percorso da cui ottenere l'assembly.</span><span class="sxs-lookup"><span data-stu-id="093e7-133">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="093e7-134">In questo caso, viene restituito `null` per indicare che deve essere caricato nel contesto predefinito dai percorsi usati dal runtime per caricare gli assembly per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="093e7-134">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="093e7-135">Ora che è stato caricato un assembly, è possibile eseguire un metodo da tale contesto.</span><span class="sxs-lookup"><span data-stu-id="093e7-135">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="093e7-136">Eseguire il metodo `Main`:</span><span class="sxs-lookup"><span data-stu-id="093e7-136">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="093e7-137">Dopo che il metodo `Main` ha restituito un risultato, è possibile avviare lo scaricamento chiamando il metodo `Unload` sull'`AssemblyLoadContext` personalizzato o rimuovendo il riferimento all'`AssemblyLoadContext`:</span><span class="sxs-lookup"><span data-stu-id="093e7-137">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="093e7-138">Questa operazione è sufficiente per scaricare l'assembly di test.</span><span class="sxs-lookup"><span data-stu-id="093e7-138">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="093e7-139">È possibile includere tutto questo in un metodo separato non abilitato per l'inlining per assicurarsi che `TestAssemblyLoadContext`, `Assembly` e `MethodInfo` (ovvero l'`Assembly.EntryPoint`) non possano essere mantenuti attivi da riferimenti di slot dello stack (variabili locali reali o introdotte da JIT).</span><span class="sxs-lookup"><span data-stu-id="093e7-139">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="093e7-140">Tali riferimenti potrebbero mantenere attivi `TestAssemblyLoadContext` e impedire lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-140">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="093e7-141">Restituire inoltre un riferimento debole all'`AssemblyLoadContext` in modo da poterlo usare in un secondo momento per determinare che lo scaricamento è stato completato.</span><span class="sxs-lookup"><span data-stu-id="093e7-141">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="093e7-142">A questo punto è possibile eseguire questa funzione per caricare, eseguire e scaricare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="093e7-142">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="093e7-143">Lo scaricamento non viene tuttavia completato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="093e7-143">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="093e7-144">Come indicato in precedenza, si basa sul processo di Garbage Collection per raccogliere tutti gli oggetti dall'assembly di test.</span><span class="sxs-lookup"><span data-stu-id="093e7-144">As previously mentioned, it relies on the GC to collect all the objects from the test assembly.</span></span> <span data-ttu-id="093e7-145">In molti casi non è necessario attendere il completamento dello scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-145">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="093e7-146">Vi sono tuttavia casi in cui è utile sapere che l'operazione è stata completata,</span><span class="sxs-lookup"><span data-stu-id="093e7-146">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="093e7-147">ad esempio quando è necessario eliminare il file di assembly caricato nell'`AssemblyLoadContext` personalizzato dal disco.</span><span class="sxs-lookup"><span data-stu-id="093e7-147">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="093e7-148">In casi come questo è possibile usare il frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="093e7-148">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="093e7-149">Attiva un processo di Garbage Collection e rimane in attesa dei finalizzatori in sospeso in un ciclo finché il riferimento debole all'`AssemblyLoadContext` personalizzato non è impostato su `null`, a indicare che l'oggetto di destinazione è stato raccolto.</span><span class="sxs-lookup"><span data-stu-id="093e7-149">It triggers a GC and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="093e7-150">Si noti che, nella maggior parte dei casi, è sufficiente un passaggio attraverso il ciclo.</span><span class="sxs-lookup"><span data-stu-id="093e7-150">Note that in most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="093e7-151">Tuttavia, per i casi più complessi, in cui gli oggetti creati dal codice in esecuzione nell'`AssemblyLoadContext` hanno finalizzatori, può essere necessario un numero maggiore di passaggi.</span><span class="sxs-lookup"><span data-stu-id="093e7-151">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="093e7-152">L'evento di scaricamento</span><span class="sxs-lookup"><span data-stu-id="093e7-152">The Unloading event</span></span>

<span data-ttu-id="093e7-153">Talvolta può essere necessario che il codice caricato in un `AssemblyLoadContext` personalizzato esegua alcune operazioni di pulizia in fase di avvio dello scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-153">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="093e7-154">Può ad esempio essere necessario arrestare i thread, pulire alcuni handle GC sicuri e così via. In questi casi può essere usato l'evento `Unloading`.</span><span class="sxs-lookup"><span data-stu-id="093e7-154">For example, it may need to stop threads, clean up some strong GC handles, etc. The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="093e7-155">A questo evento può essere associato un gestore che esegue la pulizia necessaria.</span><span class="sxs-lookup"><span data-stu-id="093e7-155">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="093e7-156">Risolvere i problemi di scaricamento</span><span class="sxs-lookup"><span data-stu-id="093e7-156">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="093e7-157">Considerata la natura cooperativa dello scaricamento, può capitare spesso di dimenticare i riferimenti che mantengono attivi gli elementi presenti in un `AssemblyLoadContext` ritirabile e impediscono lo scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-157">Due to the cooperative nature of the unloading, it's easy to forget about references keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="093e7-158">Di seguito è riportato un riepilogo degli oggetti (alcuni dei quali non ovvi) che possono mantenere attivi i riferimenti:</span><span class="sxs-lookup"><span data-stu-id="093e7-158">Here is a summary of things (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="093e7-159">Riferimenti regolari all'esterno dell'`AssemblyLoadContext` ritirabile, memorizzati in uno slot dello stack o in un registro del processore (variabili locali del metodo, create in modo esplicito dal codice utente o in modo implicito da JIT), in una variabile statica o in un handle GC sicuro o di blocco, che puntano in modo transitivo a:</span><span class="sxs-lookup"><span data-stu-id="093e7-159">Regular references held from outside of the collectible `AssemblyLoadContext`, stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the JIT), a static variable or a strong / pinning GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="093e7-160">Un assembly caricato nell'`AssemblyLoadContext` ritirabile.</span><span class="sxs-lookup"><span data-stu-id="093e7-160">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="093e7-161">Un tipo di tale assembly.</span><span class="sxs-lookup"><span data-stu-id="093e7-161">A type from such an assembly.</span></span>
  - <span data-ttu-id="093e7-162">Un'istanza di un tipo incluso in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="093e7-162">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="093e7-163">Thread che eseguono codice da un assembly caricato nell'`AssemblyLoadContext` ritirabile.</span><span class="sxs-lookup"><span data-stu-id="093e7-163">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="093e7-164">Istanze di tipi `AssemblyLoadContext` personalizzati non ritirabili creati all'interno dell'`AssemblyLoadContext` ritirabile</span><span class="sxs-lookup"><span data-stu-id="093e7-164">Instances of custom non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`</span></span>
- <span data-ttu-id="093e7-165">Istanze di <xref:System.Threading.RegisteredWaitHandle> in sospeso con callback impostati sui metodi nell'`AssemblyLoadContext` personalizzato</span><span class="sxs-lookup"><span data-stu-id="093e7-165">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`</span></span>

<span data-ttu-id="093e7-166">Suggerimenti per trovare lo slot dello stack o il registro del processore alla radice di un oggetto:</span><span class="sxs-lookup"><span data-stu-id="093e7-166">Hints to find stack slot / processor register rooting an object:</span></span>

- <span data-ttu-id="093e7-167">Il passaggio dei risultati delle chiamate di funzione direttamente a un'altra funzione può creare una radice anche in assenza di variabili locali create dall'utente.</span><span class="sxs-lookup"><span data-stu-id="093e7-167">Passing function call results directly to another function may create a root even though there is no user-created local variable.</span></span>
- <span data-ttu-id="093e7-168">Se un riferimento a un oggetto era disponibile in un punto qualsiasi di un metodo, è possibile che JIT abbia deciso di mantenerlo in uno slot dello stack o in un registro del processore per tutto il tempo desiderato nella funzione corrente.</span><span class="sxs-lookup"><span data-stu-id="093e7-168">If a reference to an object was available at any point in a method, the JIT might have decided to keep the reference in a stack slot / processor register for as long as it wants in the current function.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="093e7-169">Eseguire il debug dei problemi di scaricamento</span><span class="sxs-lookup"><span data-stu-id="093e7-169">Debug unloading issues</span></span>

<span data-ttu-id="093e7-170">Il debug dei problemi relativi allo scaricamento può essere tedioso.</span><span class="sxs-lookup"><span data-stu-id="093e7-170">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="093e7-171">Possono verificarsi situazioni in cui non si riesce a capire ciò che mantiene attivo un `AssemblyLoadContext`, ma lo scaricamento ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="093e7-171">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span>
<span data-ttu-id="093e7-172">La strategia migliore per risolvere problemi di questo tipo è quella di usare WinDbg (LLDB su Unix) con il plug-in SOS.</span><span class="sxs-lookup"><span data-stu-id="093e7-172">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="093e7-173">È necessario trovare ciò che mantiene attiva un'istanza di `LoaderAllocator` appartenente allo specifico `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="093e7-173">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span>
<span data-ttu-id="093e7-174">Questo plug-in consente di esaminare gli oggetti heap GC e le relative gerarchie e radici.</span><span class="sxs-lookup"><span data-stu-id="093e7-174">This plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>
<span data-ttu-id="093e7-175">Per caricare il plug-in nel debugger, immettere il comando seguente nella riga di comando del debugger:</span><span class="sxs-lookup"><span data-stu-id="093e7-175">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="093e7-176">In WinDbg (sembra che WinDbg esegua automaticamente questa operazione quando inserisce un'interruzione nell'applicazione .NET Core):</span><span class="sxs-lookup"><span data-stu-id="093e7-176">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="093e7-177">In LLDB:</span><span class="sxs-lookup"><span data-stu-id="093e7-177">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="093e7-178">Si proverà a eseguire il debug di un programma di esempio che presenta problemi di scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-178">Let's try to debug an example program that has problems with unloading.</span></span> <span data-ttu-id="093e7-179">Di seguito è incluso il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="093e7-179">Source code is included below.</span></span> <span data-ttu-id="093e7-180">Quando viene eseguito in WinDbg, il programma si interrompe nel debugger subito dopo il tentativo di verifica dello scaricamento.</span><span class="sxs-lookup"><span data-stu-id="093e7-180">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="093e7-181">A questo punto è possibile iniziare a cercare i colpevoli.</span><span class="sxs-lookup"><span data-stu-id="093e7-181">You can then start looking for the culprits.</span></span>

<span data-ttu-id="093e7-182">Si noti che, se si esegue il debug con LLDB in Unix, i comandi SOS negli esempi seguenti non devono essere preceduti da `!`.</span><span class="sxs-lookup"><span data-stu-id="093e7-182">Note that if you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="093e7-183">Questo comando esegue il dump di tutti gli oggetti con un nome di tipo contenente `LoaderAllocator` che si trovano nell'heap GC.</span><span class="sxs-lookup"><span data-stu-id="093e7-183">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="093e7-184">Di seguito è fornito un esempio:</span><span class="sxs-lookup"><span data-stu-id="093e7-184">Here is an example:</span></span>

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

<span data-ttu-id="093e7-185">Nella sezione "Statistics:" controllare l'oggetto `MT` (`MethodTable`) appartenente alla classe `System.Reflection.LoaderAllocator`, che è l'oggetto a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="093e7-185">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="093e7-186">Quindi, nell'elenco all'inizio, trovare la voce con il valore di `MT` corrispondente e ottenere l'indirizzo dell'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="093e7-186">Then in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="093e7-187">In questo caso, l'indirizzo è "000002b78000ce40"</span><span class="sxs-lookup"><span data-stu-id="093e7-187">In our case, it is "000002b78000ce40"</span></span>

<span data-ttu-id="093e7-188">Ora che si conosce l'indirizzo dell'oggetto `LoaderAllocator`, è possibile usare un altro comando per trovare le relative radici GC</span><span class="sxs-lookup"><span data-stu-id="093e7-188">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots</span></span>

```console
!gcroot -all 0x000002b78000ce40 
```

<span data-ttu-id="093e7-189">Questo comando esegue il dump della catena di riferimenti agli oggetti che portano all'istanza di `LoaderAllocator`.</span><span class="sxs-lookup"><span data-stu-id="093e7-189">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="093e7-190">L'elenco inizia con la radice, ovvero l'entità che mantiene attiva l'istanza di `LoaderAllocator` e pertanto è il nucleo del problema di cui si sta eseguendo il debug.</span><span class="sxs-lookup"><span data-stu-id="093e7-190">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem you're debugging.</span></span> <span data-ttu-id="093e7-191">La radice può essere uno slot dello stack, un registro del processore, un handle GC o una variabile statica.</span><span class="sxs-lookup"><span data-stu-id="093e7-191">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="093e7-192">Di seguito è riportato un esempio dell'output del comando `gcroot`:</span><span class="sxs-lookup"><span data-stu-id="093e7-192">Here is an example of the output of the `gcroot` command:</span></span>

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

<span data-ttu-id="093e7-193">A questo punto è necessario identificare la posizione della radice per poterla correggere.</span><span class="sxs-lookup"><span data-stu-id="093e7-193">Now you need to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="093e7-194">Il caso più semplice è quello in cui la radice è uno slot dello stack o un registro del processore.</span><span class="sxs-lookup"><span data-stu-id="093e7-194">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="093e7-195">In tal caso, l'oggetto `gcroot` mostra il nome della funzione il cui frame contiene la radice e il thread che esegue tale funzione.</span><span class="sxs-lookup"><span data-stu-id="093e7-195">In that case, the `gcroot` shows you the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="093e7-196">Il caso più complicato è quello in cui la radice è una variabile statica o un handle GC.</span><span class="sxs-lookup"><span data-stu-id="093e7-196">The difficult case is when the root is a static variable or a GC handle.</span></span> 

<span data-ttu-id="093e7-197">Nell'esempio precedente, la prima radice è una variabile locale di tipo `System.Reflection.RuntimeMethodInfo` memorizzata nel frame della funzione `example.Program.Main(System.String[])` all'indirizzo `rbp-20` (`rbp` è il registro del processore `rbp` e -20 è un offset esadecimale rispetto a tale registro).</span><span class="sxs-lookup"><span data-stu-id="093e7-197">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="093e7-198">La seconda radice è un oggetto `GCHandle` normale (sicuro) che contiene un riferimento a un'istanza della classe `test.Test`.</span><span class="sxs-lookup"><span data-stu-id="093e7-198">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span> 

<span data-ttu-id="093e7-199">La terza radice è un oggetto `GCHandle` bloccato.</span><span class="sxs-lookup"><span data-stu-id="093e7-199">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="093e7-200">Si tratta in realtà di una variabile statica.</span><span class="sxs-lookup"><span data-stu-id="093e7-200">This one is actually a static variable.</span></span> <span data-ttu-id="093e7-201">Purtroppo non esiste alcun modo per capirlo.</span><span class="sxs-lookup"><span data-stu-id="093e7-201">Unfortunately, there is no way to tell.</span></span> <span data-ttu-id="093e7-202">Le entità statiche per i tipi di riferimento vengono memorizzate in una matrice di oggetti gestiti in strutture di runtime interne.</span><span class="sxs-lookup"><span data-stu-id="093e7-202">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="093e7-203">Un altro caso che può impedire lo scaricamento di un `AssemblyLoadContext` è quello in cui un thread presenta un frame di un metodo di un assembly caricato nell'`AssemblyLoadContext` nel relativo stack.</span><span class="sxs-lookup"><span data-stu-id="093e7-203">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="093e7-204">È possibile verificarlo eseguendo il dump degli stack di chiamate gestite di tutti i thread:</span><span class="sxs-lookup"><span data-stu-id="093e7-204">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="093e7-205">Questo comando indica di applicare il comando `!clrstack` a tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="093e7-205">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="093e7-206">Di seguito è riportato l'output del comando per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="093e7-206">The following is the output of that command for the example.</span></span> <span data-ttu-id="093e7-207">Purtroppo, LLDB in Unix non dispone di alcun modo per applicare un comando a tutti i thread ed è quindi necessario passare da un thread all'altro e ripetere il comando `clrstack` manualmente.</span><span class="sxs-lookup"><span data-stu-id="093e7-207">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you'll need to resort to manually switching threads and repeating the `clrstack` command.</span></span>
<span data-ttu-id="093e7-208">Ignorare tutti i thread in cui il debugger riporta il messaggio "Unable to walk the managed stack" per segnalare che non è possibile esaminare lo stack gestito.</span><span class="sxs-lookup"><span data-stu-id="093e7-208">Ignore all threads where the debugger says "Unable to walk the managed stack."</span></span>

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

<span data-ttu-id="093e7-209">Come si può notare, nell'ultimo thread è presente `test.Program.ThreadProc()`.</span><span class="sxs-lookup"><span data-stu-id="093e7-209">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="093e7-210">Si tratta di una funzione dell'assembly caricato nell'`AssemblyLoadContext` che mantiene quindi attivo l'`AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="093e7-210">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="093e7-211">Esempio di codice sorgente con problemi di scaricamento</span><span class="sxs-lookup"><span data-stu-id="093e7-211">Example source with unloadability issues</span></span>

<span data-ttu-id="093e7-212">Il codice seguente viene usato nell'esempio di debug precedente.</span><span class="sxs-lookup"><span data-stu-id="093e7-212">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="093e7-213">Programma di test principale</span><span class="sxs-lookup"><span data-stu-id="093e7-213">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="093e7-214">Programma caricato in TestAssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="093e7-214">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="093e7-215">Il codice seguente rappresenta il file *test. dll* passato al `ExecuteAndUnload` metodo nel programma di test principale.</span><span class="sxs-lookup"><span data-stu-id="093e7-215">The following code represents the *test.dll* passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
