---
title: Programmazione asincrona
description: Informazioni su come F è un supporto pulito per l'asincronia basato su un modello di programmazione a livello di linguaggio derivato dai concetti di programmazione funzionale di base.
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608036"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="e540f-103">Programmazione asincrona in FAsync programming in F\#</span><span class="sxs-lookup"><span data-stu-id="e540f-103">Async programming in F\#</span></span>

<span data-ttu-id="e540f-104">La programmazione asincrona è un meccanismo essenziale per le applicazioni moderne per motivi diversi.</span><span class="sxs-lookup"><span data-stu-id="e540f-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="e540f-105">Esistono due casi d'uso principali che la maggior parte degli sviluppatori incontrerà:There are two primary use cases that most developers will encounter:</span><span class="sxs-lookup"><span data-stu-id="e540f-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="e540f-106">La presentazione di un processo server in grado di soddisfare un numero significativo di richieste in ingresso simultanee, riducendo al minimo le risorse di sistema occupate durante l'elaborazione delle richieste attende gli input da sistemi o servizi esterni a tale processo</span><span class="sxs-lookup"><span data-stu-id="e540f-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="e540f-107">Mantenimento di un'interfaccia utente reattiva o di un thread principale durante lo stato di avanzamento simultaneo del lavoro in background</span><span class="sxs-lookup"><span data-stu-id="e540f-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="e540f-108">Anche se il lavoro in background spesso comporta l'utilizzo di più thread, è importante considerare i concetti di asincronia e multithreading separatamente.</span><span class="sxs-lookup"><span data-stu-id="e540f-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="e540f-109">In realtà, sono preoccupazioni separate, e una non implica l'altra.</span><span class="sxs-lookup"><span data-stu-id="e540f-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="e540f-110">Ciò che segue in questo articolo descrive questo in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="e540f-110">What follows in this article describes this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="e540f-111">Asincronità definita</span><span class="sxs-lookup"><span data-stu-id="e540f-111">Asynchrony defined</span></span>

<span data-ttu-id="e540f-112">Il punto precedente - che l'asincronia è indipendente dall'utilizzo di più thread - vale la pena spiegare un po 'di più.</span><span class="sxs-lookup"><span data-stu-id="e540f-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="e540f-113">Ci sono tre concetti che a volte sono correlati, ma strettamente indipendenti l'uno dall'altro:</span><span class="sxs-lookup"><span data-stu-id="e540f-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="e540f-114">Concorrenza; quando più calcoli vengono eseguiti in periodi di tempo sovrapposti.</span><span class="sxs-lookup"><span data-stu-id="e540f-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="e540f-115">Parallelismo; quando più calcoli o più parti di un singolo calcolo vengono eseguite esattamente nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="e540f-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="e540f-116">Asincronia; quando uno o più calcoli possono essere eseguiti separatamente dal flusso principale del programma.</span><span class="sxs-lookup"><span data-stu-id="e540f-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="e540f-117">Tutti e tre sono concetti ortogonali, ma possono essere facilmente confusi, soprattutto quando vengono utilizzati insieme.</span><span class="sxs-lookup"><span data-stu-id="e540f-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="e540f-118">Ad esempio, potrebbe essere necessario eseguire più calcoli asincroni in parallelo.</span><span class="sxs-lookup"><span data-stu-id="e540f-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="e540f-119">Ciò non significa che il parallelismo o l'asincronia si implichino l'un l'altro.</span><span class="sxs-lookup"><span data-stu-id="e540f-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="e540f-120">Se si considera l'etimologia della parola "asincrono", ci sono due pezzi coinvolti:</span><span class="sxs-lookup"><span data-stu-id="e540f-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="e540f-121">"a", che significa "non".</span><span class="sxs-lookup"><span data-stu-id="e540f-121">"a", meaning "not".</span></span>
- <span data-ttu-id="e540f-122">"sincrono", che significa "allo stesso tempo".</span><span class="sxs-lookup"><span data-stu-id="e540f-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="e540f-123">Quando si mettono insieme questi due termini, si noterà che "asincrono" significa "non allo stesso tempo".</span><span class="sxs-lookup"><span data-stu-id="e540f-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="e540f-124">L'operazione è terminata.</span><span class="sxs-lookup"><span data-stu-id="e540f-124">That's it!</span></span> <span data-ttu-id="e540f-125">Non vi è alcuna implicazione di concorrenza o parallelismo in questa definizione.</span><span class="sxs-lookup"><span data-stu-id="e540f-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="e540f-126">Questo vale anche nella pratica.</span><span class="sxs-lookup"><span data-stu-id="e540f-126">This is also true in practice.</span></span>

<span data-ttu-id="e540f-127">In termini pratici, i calcoli asincroni in F , sono pianificati per l'esecuzione indipendentemente dal flusso di programma principale.</span><span class="sxs-lookup"><span data-stu-id="e540f-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="e540f-128">Ciò non implica la concorrenza o il parallelismo, né implica che un calcolo avvenga sempre in background.</span><span class="sxs-lookup"><span data-stu-id="e540f-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="e540f-129">Infatti, i calcoli asincroni possono anche essere eseguiti in modo sincrono, a seconda della natura del calcolo e dell'ambiente in cui è in esecuzione il calcolo.</span><span class="sxs-lookup"><span data-stu-id="e540f-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="e540f-130">L'asporto principale che si dovrebbe avere è che i calcoli asincroni sono indipendenti dal flusso di programma principale.</span><span class="sxs-lookup"><span data-stu-id="e540f-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="e540f-131">Sebbene esistano poche garanzie su quando o come viene eseguito un calcolo asincrono, esistono alcuni approcci per orchestrarli e pianificarli.</span><span class="sxs-lookup"><span data-stu-id="e540f-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="e540f-132">Nella parte restante di questo articolo vengono esaminati i concetti di base per l'asincronia di F e viene illustrato come usare i tipi, le funzioni e le espressioni incorporate in F.</span><span class="sxs-lookup"><span data-stu-id="e540f-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="e540f-133">Concetti principali</span><span class="sxs-lookup"><span data-stu-id="e540f-133">Core concepts</span></span>

<span data-ttu-id="e540f-134">In F , la programmazione asincrona è incentrata su tre concetti di base:In F , asynchronous programming is centered around three core concepts:</span><span class="sxs-lookup"><span data-stu-id="e540f-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="e540f-135">Tipo, `Async<'T>` che rappresenta un calcolo asincrono componibile.</span><span class="sxs-lookup"><span data-stu-id="e540f-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="e540f-136">Le `Async` funzioni del modulo, che consentono di pianificare il lavoro asincrono, comporre calcoli asincroni e trasformare i risultati asincroni.</span><span class="sxs-lookup"><span data-stu-id="e540f-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="e540f-137">L'espressione `async { }` di [calcolo](../../language-reference/computation-expressions.md), che fornisce una sintassi comoda per la compilazione e il controllo dei calcoli asincroni.</span><span class="sxs-lookup"><span data-stu-id="e540f-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="e540f-138">È possibile visualizzare questi tre concetti nell'esempio seguente:You can see these three concepts in the following example:</span><span class="sxs-lookup"><span data-stu-id="e540f-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="e540f-139">Nell'esempio, `printTotalFileBytes` la funzione `string -> Async<unit>`è di tipo .</span><span class="sxs-lookup"><span data-stu-id="e540f-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="e540f-140">La chiamata alla funzione non esegue effettivamente il calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="e540f-141">Al contrario, `Async<unit>` restituisce un che funge da *specifica* del lavoro che deve essere eseguito in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="e540f-142">Chiama `Async.AwaitTask` nel suo corpo, che converte il risultato di <xref:System.IO.File.ReadAllBytesAsync%2A> in un tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="e540f-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="e540f-143">Un'altra linea importante `Async.RunSynchronously`è la chiamata a .</span><span class="sxs-lookup"><span data-stu-id="e540f-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="e540f-144">Si tratta di una delle funzioni di avvio del modulo asincrono che è necessario chiamare se si desidera eseguire effettivamente un calcolo asincrono F .</span><span class="sxs-lookup"><span data-stu-id="e540f-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="e540f-145">Si tratta di una differenza fondamentale con `async` lo stile di programmazione di C/Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e540f-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="e540f-146">In F , i calcoli asincroni possono essere considerati come **attività Cold**.</span><span class="sxs-lookup"><span data-stu-id="e540f-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="e540f-147">Devono essere avviati in modo esplicito per l'esecuzione effettiva.</span><span class="sxs-lookup"><span data-stu-id="e540f-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="e540f-148">Questo ha alcuni vantaggi, in quanto consente di combinare e sequenza lavoro asincrono molto più facilmente rispetto a C .</span><span class="sxs-lookup"><span data-stu-id="e540f-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="e540f-149">Combinare i calcoli asincroniCombine asynchronous computations</span><span class="sxs-lookup"><span data-stu-id="e540f-149">Combine asynchronous computations</span></span>

<span data-ttu-id="e540f-150">Ecco un esempio che si basa su quello precedente combinando i calcoli:</span><span class="sxs-lookup"><span data-stu-id="e540f-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="e540f-151">Come si può `main` vedere, la funzione ha un bel paio di altre chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="e540f-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="e540f-152">Concettualmente, esegue le operazioni seguenti:Conceptually, it does the following:</span><span class="sxs-lookup"><span data-stu-id="e540f-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="e540f-153">Trasformare gli argomenti della `Async<unit>` riga `Array.map`di comando in calcoli con .</span><span class="sxs-lookup"><span data-stu-id="e540f-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="e540f-154">Creare `Async<'T[]>` un che pianifica `printTotalFileBytes` ed esegue i calcoli in parallelo durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e540f-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="e540f-155">Creare `Async<unit>` un oggetto che eseguirà il calcolo parallelo e ne ignorerà il risultato.</span><span class="sxs-lookup"><span data-stu-id="e540f-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="e540f-156">Eseguire in modo `Async.RunSynchronously` esplicito l'ultimo calcolo con e bloccare fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="e540f-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="e540f-157">Quando questo programma `printTotalFileBytes` viene eseguito, viene eseguito in parallelo per ogni argomento della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e540f-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="e540f-158">Poiché i calcoli asincroni vengono eseguiti indipendentemente dal flusso del programma, non esiste alcun ordine in cui stampano le informazioni e completano l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e540f-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="e540f-159">I calcoli verranno pianificati in parallelo, ma l'ordine di esecuzione non è garantito.</span><span class="sxs-lookup"><span data-stu-id="e540f-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="e540f-160">Calcoli asincroni di sequenzaSequence asynchronous computations</span><span class="sxs-lookup"><span data-stu-id="e540f-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="e540f-161">Poiché `Async<'T>` è una specifica di lavoro piuttosto che un'attività già in esecuzione, è possibile eseguire facilmente trasformazioni più complesse.</span><span class="sxs-lookup"><span data-stu-id="e540f-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="e540f-162">Ecco un esempio che sequenzia un set di calcoli asincroni in modo che vengano eseguiti uno dopo l'altro.</span><span class="sxs-lookup"><span data-stu-id="e540f-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="e540f-163">Questa pianificazione `printTotalFileBytes` verrà pianificata per l'esecuzione nell'ordine degli elementi di `argv` anziché programmarli in parallelo.</span><span class="sxs-lookup"><span data-stu-id="e540f-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="e540f-164">Poiché l'elemento successivo verrà pianificato solo dopo il termine dell'esecuzione dell'ultimo calcolo, i calcoli vengono sequenziati in modo che non vi sia alcuna sovrapposizione nella loro esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e540f-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="e540f-165">Importanti funzioni del modulo asincrono</span><span class="sxs-lookup"><span data-stu-id="e540f-165">Important Async module functions</span></span>

<span data-ttu-id="e540f-166">Quando si scrive codice asincrono in F , in genere si interagisce con un framework che gestisce la pianificazione dei calcoli per l'utente.</span><span class="sxs-lookup"><span data-stu-id="e540f-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="e540f-167">Tuttavia, questo non è sempre il caso, quindi è bene imparare le varie funzioni di partenza per pianificare il lavoro asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="e540f-168">Poiché i calcoli asincroni F , sono una _specifica_ di lavoro anziché una rappresentazione del lavoro che è già in esecuzione, devono essere avviati in modo esplicito con una funzione di avvio.</span><span class="sxs-lookup"><span data-stu-id="e540f-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="e540f-169">Esistono molte funzioni di [avvio asincrone](https://msdn.microsoft.com/library/ee370232.aspx) che sono utili in contesti diversi.</span><span class="sxs-lookup"><span data-stu-id="e540f-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="e540f-170">Nella sezione seguente vengono descritte alcune delle funzioni di avvio più comuni.</span><span class="sxs-lookup"><span data-stu-id="e540f-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="e540f-171">Async.StartChild</span><span class="sxs-lookup"><span data-stu-id="e540f-171">Async.StartChild</span></span>

<span data-ttu-id="e540f-172">Avvia un calcolo figlio all'interno di un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="e540f-173">In questo modo è possibile eseguire contemporaneamente più calcoli asincroni.</span><span class="sxs-lookup"><span data-stu-id="e540f-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="e540f-174">Il calcolo figlio condivide un token di annullamento con il calcolo padre.</span><span class="sxs-lookup"><span data-stu-id="e540f-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="e540f-175">Se il calcolo padre viene annullato, viene annullato anche il calcolo figlio.</span><span class="sxs-lookup"><span data-stu-id="e540f-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="e540f-176">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="e540f-177">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="e540f-177">When to use:</span></span>

- <span data-ttu-id="e540f-178">Quando si desidera eseguire più calcoli asincroni contemporaneamente anziché uno alla volta, ma non è pianificato in parallelo.</span><span class="sxs-lookup"><span data-stu-id="e540f-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="e540f-179">Quando si desidera legare la durata di un calcolo figlio a quella di un calcolo padre.</span><span class="sxs-lookup"><span data-stu-id="e540f-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="e540f-180">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-180">What to watch out for:</span></span>

- <span data-ttu-id="e540f-181">L'avvio `Async.StartChild` di più calcoli con non è come programmarli in parallelo.</span><span class="sxs-lookup"><span data-stu-id="e540f-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="e540f-182">Se si desidera pianificare i `Async.Parallel`calcoli in parallelo, utilizzare .</span><span class="sxs-lookup"><span data-stu-id="e540f-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="e540f-183">L'annullamento di un calcolo padre attiverà l'annullamento di tutti i calcoli figlio avviati.</span><span class="sxs-lookup"><span data-stu-id="e540f-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="e540f-184">Async.StartImmediate</span><span class="sxs-lookup"><span data-stu-id="e540f-184">Async.StartImmediate</span></span>

<span data-ttu-id="e540f-185">Esegue un calcolo asincrono, avviato immediatamente dal thread del sistema operativo corrente.</span><span class="sxs-lookup"><span data-stu-id="e540f-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="e540f-186">Ciò è utile se è necessario aggiornare un elemento sul thread chiamante durante il calcolo.</span><span class="sxs-lookup"><span data-stu-id="e540f-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="e540f-187">Ad esempio, se un calcolo asincrono deve aggiornare `Async.StartImmediate` un'interfaccia utente (ad esempio l'aggiornamento di un indicatore di stato), deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e540f-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="e540f-188">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="e540f-189">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="e540f-189">When to use:</span></span>

- <span data-ttu-id="e540f-190">Quando è necessario aggiornare un elemento sul thread chiamante nel mezzo di un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="e540f-191">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-191">What to watch out for:</span></span>

- <span data-ttu-id="e540f-192">Il codice nel calcolo asincrono verrà eseguito su qualsiasi thread di uno viene pianificato.</span><span class="sxs-lookup"><span data-stu-id="e540f-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="e540f-193">Ciò può essere problematico se tale thread è in qualche modo sensibile, ad esempio un thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e540f-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="e540f-194">In questi `Async.StartImmediate` casi, è probabile che sia inappropriato da usare.</span><span class="sxs-lookup"><span data-stu-id="e540f-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="e540f-195">Async.StartAsTask</span><span class="sxs-lookup"><span data-stu-id="e540f-195">Async.StartAsTask</span></span>

<span data-ttu-id="e540f-196">Esegue un calcolo nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="e540f-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="e540f-197">Restituisce <xref:System.Threading.Tasks.Task%601> un che verrà completato nello stato corrispondente una volta terminato il calcolo (produce il risultato, genera un'eccezione o viene annullato).</span><span class="sxs-lookup"><span data-stu-id="e540f-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="e540f-198">Se non viene fornito alcun token di annullamento, viene utilizzato il token di annullamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="e540f-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="e540f-199">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="e540f-200">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="e540f-200">When to use:</span></span>

- <span data-ttu-id="e540f-201">Quando è necessario chiamare in un'API <xref:System.Threading.Tasks.Task%601> .NET che prevede che un per rappresentare il risultato di un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="e540f-202">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-202">What to watch out for:</span></span>

- <span data-ttu-id="e540f-203">Questa chiamata allocherà un oggetto aggiuntivo, `Task` che può aumentare l'overhead se viene utilizzato spesso.</span><span class="sxs-lookup"><span data-stu-id="e540f-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="e540f-204">Async.Parallel</span><span class="sxs-lookup"><span data-stu-id="e540f-204">Async.Parallel</span></span>

<span data-ttu-id="e540f-205">Pianifica una sequenza di calcoli asincroni da eseguire in parallelo.</span><span class="sxs-lookup"><span data-stu-id="e540f-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="e540f-206">Il grado di parallelismo può essere facoltativamente sintonizzato/limitato specificando `maxDegreesOfParallelism` il parametro.</span><span class="sxs-lookup"><span data-stu-id="e540f-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="e540f-207">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="e540f-208">Quando usarlo:</span><span class="sxs-lookup"><span data-stu-id="e540f-208">When to use it:</span></span>

- <span data-ttu-id="e540f-209">Se è necessario eseguire un set di calcoli contemporaneamente e non si fa affidamento sull'ordine di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e540f-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="e540f-210">Se non sono necessari risultati dai calcoli pianificati in parallelo fino al completamento di tutti.</span><span class="sxs-lookup"><span data-stu-id="e540f-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="e540f-211">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-211">What to watch out for:</span></span>

- <span data-ttu-id="e540f-212">È possibile accedere alla matrice di valori risultante solo dopo aver completato tutti i calcoli.</span><span class="sxs-lookup"><span data-stu-id="e540f-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="e540f-213">I calcoli verranno eseguiti comunque finiscano per essere pianificati.</span><span class="sxs-lookup"><span data-stu-id="e540f-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="e540f-214">Ciò significa che non è possibile fare affidamento sul loro ordine di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e540f-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="e540f-215">Async.Sequential</span><span class="sxs-lookup"><span data-stu-id="e540f-215">Async.Sequential</span></span>

<span data-ttu-id="e540f-216">Pianifica una sequenza di calcoli asincroni da eseguire nell'ordine in cui vengono passati.</span><span class="sxs-lookup"><span data-stu-id="e540f-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="e540f-217">Verrà eseguito il primo calcolo, quindi il successivo e così via.</span><span class="sxs-lookup"><span data-stu-id="e540f-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="e540f-218">Nessun calcolo verrà eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="e540f-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="e540f-219">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="e540f-220">Quando usarlo:</span><span class="sxs-lookup"><span data-stu-id="e540f-220">When to use it:</span></span>

- <span data-ttu-id="e540f-221">Se è necessario eseguire più calcoli in ordine.</span><span class="sxs-lookup"><span data-stu-id="e540f-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="e540f-222">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-222">What to watch out for:</span></span>

- <span data-ttu-id="e540f-223">È possibile accedere alla matrice di valori risultante solo dopo aver completato tutti i calcoli.</span><span class="sxs-lookup"><span data-stu-id="e540f-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="e540f-224">I calcoli verranno eseguiti nell'ordine in cui vengono passati a questa funzione, il che può significare che verrà trascorso più tempo prima che vengano restituiti i risultati.</span><span class="sxs-lookup"><span data-stu-id="e540f-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="e540f-225">Async.AwaitTask</span><span class="sxs-lookup"><span data-stu-id="e540f-225">Async.AwaitTask</span></span>

<span data-ttu-id="e540f-226">Restituisce un calcolo asincrono <xref:System.Threading.Tasks.Task%601> che attende il completamento dell'utente e ne restituisce il risultato come`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="e540f-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="e540f-227">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="e540f-228">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="e540f-228">When to use:</span></span>

- <span data-ttu-id="e540f-229">Quando si utilizza un'API .NET che restituisce un all'interno di un <xref:System.Threading.Tasks.Task%601> calcolo asincrono F .</span><span class="sxs-lookup"><span data-stu-id="e540f-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="e540f-230">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-230">What to watch out for:</span></span>

- <span data-ttu-id="e540f-231">Le eccezioni <xref:System.AggregateException> vengono incapsulate in seguito alla convenzione della libreria Task Parallel Library e questo è diverso dal modo in cui il asincrono di F , in genere espone le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="e540f-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="e540f-232">Async.Catch</span><span class="sxs-lookup"><span data-stu-id="e540f-232">Async.Catch</span></span>

<span data-ttu-id="e540f-233">Crea un calcolo asincrono `Async<'T>`che esegue `Async<Choice<'T, exn>>`un determinato oggetto , restituendo un oggetto .</span><span class="sxs-lookup"><span data-stu-id="e540f-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="e540f-234">Se l'oggetto specificato `Async<'T>` viene `Choice1Of2` completato correttamente, viene restituito un oggetto con il valore risultante.</span><span class="sxs-lookup"><span data-stu-id="e540f-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="e540f-235">Se viene generata un'eccezione `Choice2of2` prima del completamento, viene restituito un oggetto con l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="e540f-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="e540f-236">Se viene utilizzato su un calcolo asincrono che è a sua volta composto da molti calcoli e uno di questi calcoli genera un'eccezione, il calcolo di chelo comprende verrà interrotto completamente.</span><span class="sxs-lookup"><span data-stu-id="e540f-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="e540f-237">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="e540f-238">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="e540f-238">When to use:</span></span>

- <span data-ttu-id="e540f-239">Quando si esegue un lavoro asincrono che potrebbe non riuscire con un'eccezione e si desidera gestire tale eccezione nel chiamante.</span><span class="sxs-lookup"><span data-stu-id="e540f-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="e540f-240">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-240">What to watch out for:</span></span>

- <span data-ttu-id="e540f-241">Quando si utilizzano calcoli asincroni combinati o in sequenza, il calcolo di comprendente si interrompe completamente se uno dei relativi calcoli "interni" genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e540f-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="e540f-242">Async.Ignore</span><span class="sxs-lookup"><span data-stu-id="e540f-242">Async.Ignore</span></span>

<span data-ttu-id="e540f-243">Crea un calcolo asincrono che esegue il calcolo specificato e ne ignora il risultato.</span><span class="sxs-lookup"><span data-stu-id="e540f-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="e540f-244">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="e540f-245">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="e540f-245">When to use:</span></span>

- <span data-ttu-id="e540f-246">Quando si dispone di un calcolo asincrono il cui risultato non è necessario.</span><span class="sxs-lookup"><span data-stu-id="e540f-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="e540f-247">Questo è analogo `ignore` al codice per il codice non asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="e540f-248">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-248">What to watch out for:</span></span>

- <span data-ttu-id="e540f-249">Se è necessario utilizzare questo `Async.Start` perché si desidera `Async<unit>`utilizzare o un'altra funzione che richiede , considerare se scartare il risultato è bene fare.</span><span class="sxs-lookup"><span data-stu-id="e540f-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="e540f-250">L'eliminazione dei risultati solo per adattarsi a una firma del tipo non deve essere in genere eseguita.</span><span class="sxs-lookup"><span data-stu-id="e540f-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="e540f-251">Async.RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="e540f-251">Async.RunSynchronously</span></span>

<span data-ttu-id="e540f-252">Esegue un calcolo asincrono e attende il risultato sul thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="e540f-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="e540f-253">Questa chiamata è bloccante.</span><span class="sxs-lookup"><span data-stu-id="e540f-253">This call is blocking.</span></span>

<span data-ttu-id="e540f-254">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="e540f-255">Quando usarlo:</span><span class="sxs-lookup"><span data-stu-id="e540f-255">When to use it:</span></span>

- <span data-ttu-id="e540f-256">Se è necessario, utilizzarlo solo una volta in un'applicazione - nel punto di ingresso per un eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e540f-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="e540f-257">Quando non si è a cuore le prestazioni e si desidera eseguire un set di altre operazioni asincrone contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e540f-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="e540f-258">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-258">What to watch out for:</span></span>

- <span data-ttu-id="e540f-259">La `Async.RunSynchronously` chiamata blocca il thread chiamante fino al completamento dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e540f-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="e540f-260">Async.Start</span><span class="sxs-lookup"><span data-stu-id="e540f-260">Async.Start</span></span>

<span data-ttu-id="e540f-261">Avvia un calcolo asincrono `unit`nel pool di thread che restituisce .</span><span class="sxs-lookup"><span data-stu-id="e540f-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="e540f-262">Non aspetta il suo risultato.</span><span class="sxs-lookup"><span data-stu-id="e540f-262">Doesn't wait for its result.</span></span> <span data-ttu-id="e540f-263">I calcoli annidati iniziati con `Async.Start` vengono avviati completamente indipendentemente dal calcolo padre che li ha chiamati.</span><span class="sxs-lookup"><span data-stu-id="e540f-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="e540f-264">La loro durata non è legata ad alcun calcolo padre.</span><span class="sxs-lookup"><span data-stu-id="e540f-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="e540f-265">Se il calcolo padre viene annullato, non viene annullato alcun calcolo figlio.</span><span class="sxs-lookup"><span data-stu-id="e540f-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="e540f-266">Firma:</span><span class="sxs-lookup"><span data-stu-id="e540f-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="e540f-267">Utilizzare solo quando:</span><span class="sxs-lookup"><span data-stu-id="e540f-267">Use only when:</span></span>

- <span data-ttu-id="e540f-268">Si dispone di un calcolo asincrono che non produce un risultato e/o richiede l'elaborazione di uno.</span><span class="sxs-lookup"><span data-stu-id="e540f-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="e540f-269">Non è necessario sapere quando viene completato un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="e540f-270">Non si è a cuore il thread su cui viene eseguito un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="e540f-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="e540f-271">Non è necessario essere a conoscenza o segnalare le eccezioni risultanti dall'attività.</span><span class="sxs-lookup"><span data-stu-id="e540f-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="e540f-272">A cosa fare attenzione:</span><span class="sxs-lookup"><span data-stu-id="e540f-272">What to watch out for:</span></span>

- <span data-ttu-id="e540f-273">Le eccezioni generate dai `Async.Start` calcoli avviati con non vengono propagate al chiamante.</span><span class="sxs-lookup"><span data-stu-id="e540f-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="e540f-274">Lo stack di chiamate verrà completamente rimosso.</span><span class="sxs-lookup"><span data-stu-id="e540f-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="e540f-275">Qualsiasi lavoro effettivo (ad `printfn`esempio `Async.Start` la chiamata ) avviato con non causerà l'effetto si verifica sul thread principale dell'esecuzione di un programma.</span><span class="sxs-lookup"><span data-stu-id="e540f-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="e540f-276">Interoperabilità con .NET</span><span class="sxs-lookup"><span data-stu-id="e540f-276">Interoperate with .NET</span></span>

<span data-ttu-id="e540f-277">È possibile che si stia lavorando con una libreria .NET o una codebase di codice di C, che utilizza la programmazione asincrona in stile [async/await.](../../../standard/async.md)</span><span class="sxs-lookup"><span data-stu-id="e540f-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="e540f-278">Poiché il linguaggio C e <xref:System.Threading.Tasks.Task%601> la <xref:System.Threading.Tasks.Task> maggior parte delle librerie `Async<'T>`.NET utilizzano i tipi e come astrazioni di base anziché , è necessario attraversare un limite tra questi due approcci all'asincronia.</span><span class="sxs-lookup"><span data-stu-id="e540f-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="e540f-279">Come utilizzare .NET async e`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="e540f-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="e540f-280">L'utilizzo di librerie asincrone <xref:System.Threading.Tasks.Task%601> e codebase .NET che usano ,vale a dire i calcoli asincroni che hanno valori restituiti, è semplice e dispone di supporto incorporato con F.</span><span class="sxs-lookup"><span data-stu-id="e540f-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="e540f-281">È possibile `Async.AwaitTask` utilizzare la funzione per attendere un calcolo asincrono .NET:You can use the function to await a .NET asynchronous computation:</span><span class="sxs-lookup"><span data-stu-id="e540f-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="e540f-282">È possibile `Async.StartAsTask` utilizzare la funzione per passare un calcolo asincrono a un chiamante .NET:You can use the function to pass an asynchronous computation to a .NET caller:</span><span class="sxs-lookup"><span data-stu-id="e540f-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="e540f-283">Come utilizzare .NET async e`Task`</span><span class="sxs-lookup"><span data-stu-id="e540f-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="e540f-284">Per utilizzare le API <xref:System.Threading.Tasks.Task> che utilizzano, ovvero i calcoli asincroni .NET che non restituiscono un valore, potrebbe essere necessario aggiungere una funzione aggiuntiva che convertirà un `Async<'T>` <xref:System.Threading.Tasks.Task>oggetto in :</span><span class="sxs-lookup"><span data-stu-id="e540f-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="e540f-285">Esiste già `Async.AwaitTask` un che <xref:System.Threading.Tasks.Task> accetta un come input.</span><span class="sxs-lookup"><span data-stu-id="e540f-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="e540f-286">Con questa e `startTaskFromAsyncUnit` la funzione definita in <xref:System.Threading.Tasks.Task> precedenza, è possibile avviare e attendere i tipi da un calcolo asincrono di F.</span><span class="sxs-lookup"><span data-stu-id="e540f-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="e540f-287">Relazione con il multithreading</span><span class="sxs-lookup"><span data-stu-id="e540f-287">Relationship to multi-threading</span></span>

<span data-ttu-id="e540f-288">Anche se il threading è menzionato in tutto questo articolo, ci sono due cose importanti da ricordare:</span><span class="sxs-lookup"><span data-stu-id="e540f-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="e540f-289">Non esiste alcuna affinità tra un calcolo asincrono e un thread, a meno che non venga avviato in modo esplicito nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="e540f-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="e540f-290">La programmazione asincrona in F non è un'astrazione per il multithreading.</span><span class="sxs-lookup"><span data-stu-id="e540f-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="e540f-291">Ad esempio, un calcolo può effettivamente essere eseguito sul thread del chiamante, a seconda della natura del lavoro.</span><span class="sxs-lookup"><span data-stu-id="e540f-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="e540f-292">Un calcolo potrebbe anche "saltare" tra i thread, prendendoli in prestito per una piccola quantità di tempo per fare un lavoro utile tra i periodi di "attesa" (ad esempio quando una chiamata di rete è in transito).</span><span class="sxs-lookup"><span data-stu-id="e540f-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="e540f-293">Anche se F , fornisce alcune funzionalità per avviare un calcolo asincrono sul thread corrente (o in modo esplicito non nel thread corrente), l'asincronia in genere non è associata a una particolare strategia di threading.</span><span class="sxs-lookup"><span data-stu-id="e540f-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="e540f-294">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e540f-294">See also</span></span>

- [<span data-ttu-id="e540f-295">Modello di programmazione asincrona di F</span><span class="sxs-lookup"><span data-stu-id="e540f-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="e540f-296">Guida asincrona di Jet.com</span><span class="sxs-lookup"><span data-stu-id="e540f-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="e540f-297">Guida alla programmazione asincrona per il divertimento e il profitto</span><span class="sxs-lookup"><span data-stu-id="e540f-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="e540f-298">Async in C 'NET e F ': ottenutri asincroni in C #</span><span class="sxs-lookup"><span data-stu-id="e540f-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
