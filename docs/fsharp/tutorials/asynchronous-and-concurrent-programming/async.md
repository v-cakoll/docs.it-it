---
title: Programmazione asincrona inF#
description: Informazioni su F# come fornisce un supporto pulito per modalità asincrona basato su un modello di programmazione a livello di linguaggio derivato dai concetti di base della programmazione funzionale.
ms.date: 12/17/2018
ms.openlocfilehash: 1ede4a5c1e26df271ac94f9b2c216ac84fb38f59
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395784"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="36bb0-103">Programmazione asincrona in F @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="36bb0-103">Async programming in F\#</span></span>

<span data-ttu-id="36bb0-104">La programmazione asincrona è un meccanismo essenziale per le applicazioni moderne per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="36bb0-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="36bb0-105">Ci sono due casi d'uso principali che la maggior parte degli sviluppatori incontrerà:</span><span class="sxs-lookup"><span data-stu-id="36bb0-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="36bb0-106">Presentazione di un processo server che può soddisfare un numero significativo di richieste in ingresso simultanee, riducendo al minimo le risorse di sistema occupate durante l'elaborazione delle richieste in attesa di input da sistemi o servizi esterni a tale processo</span><span class="sxs-lookup"><span data-stu-id="36bb0-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="36bb0-107">Gestione di un'interfaccia utente reattiva o di un thread principale durante l'avanzamento simultaneo del lavoro in background</span><span class="sxs-lookup"><span data-stu-id="36bb0-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="36bb0-108">Sebbene il lavoro in background comporti spesso l'utilizzo di più thread, è importante prendere in considerazione i concetti di modalità asincrona e multithread separatamente.</span><span class="sxs-lookup"><span data-stu-id="36bb0-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="36bb0-109">In realtà, si tratta di problemi distinti e uno non implica l'altro.</span><span class="sxs-lookup"><span data-stu-id="36bb0-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="36bb0-110">Il contenuto di questo articolo descrive in modo più dettagliato questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="36bb0-110">What follows in this article will describe this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="36bb0-111">Modalità asincrona definito</span><span class="sxs-lookup"><span data-stu-id="36bb0-111">Asynchrony defined</span></span>

<span data-ttu-id="36bb0-112">Il punto precedente, che modalità asincrona è indipendente dall'utilizzo di più thread, vale la pena spiegare ulteriormente un po'.</span><span class="sxs-lookup"><span data-stu-id="36bb0-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="36bb0-113">Esistono tre concetti a volte correlati, ma strettamente indipendenti tra loro:</span><span class="sxs-lookup"><span data-stu-id="36bb0-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="36bb0-114">Concorrenza Quando più calcoli vengono eseguiti in periodi di tempo sovrapposti.</span><span class="sxs-lookup"><span data-stu-id="36bb0-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="36bb0-115">Parallelismo Quando più calcoli o varie parti di un singolo calcolo vengono eseguiti esattamente allo stesso tempo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="36bb0-116">Modalità asincrona Quando uno o più calcoli possono essere eseguiti separatamente dal flusso principale del programma.</span><span class="sxs-lookup"><span data-stu-id="36bb0-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="36bb0-117">Tutti e tre sono concetti ortogonali, ma possono essere facilmente configurati, soprattutto quando vengono usati insieme.</span><span class="sxs-lookup"><span data-stu-id="36bb0-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="36bb0-118">Ad esempio, potrebbe essere necessario eseguire più calcoli asincroni in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="36bb0-119">Questo non significa che il parallelismo o modalità asincrona ne implicano l'altro.</span><span class="sxs-lookup"><span data-stu-id="36bb0-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="36bb0-120">Se si considera l'etimologia della parola "Asynchronous", sono necessarie due parti:</span><span class="sxs-lookup"><span data-stu-id="36bb0-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="36bb0-121">"a", che significa "not".</span><span class="sxs-lookup"><span data-stu-id="36bb0-121">"a", meaning "not".</span></span>
- <span data-ttu-id="36bb0-122">"sincrono", che significa "allo stesso tempo".</span><span class="sxs-lookup"><span data-stu-id="36bb0-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="36bb0-123">Quando si impostano questi due termini, si noterà che "Asynchronous" significa "not allo stesso tempo".</span><span class="sxs-lookup"><span data-stu-id="36bb0-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="36bb0-124">La procedura è terminata.</span><span class="sxs-lookup"><span data-stu-id="36bb0-124">That's it!</span></span> <span data-ttu-id="36bb0-125">In questa definizione non esiste alcuna implicazione della concorrenza o del parallelismo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="36bb0-126">Questo vale anche per la pratica.</span><span class="sxs-lookup"><span data-stu-id="36bb0-126">This is also true in practice.</span></span>

<span data-ttu-id="36bb0-127">In termini pratici, i calcoli asincroni in F# sono pianificati per l'esecuzione indipendentemente dal flusso di programma principale.</span><span class="sxs-lookup"><span data-stu-id="36bb0-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="36bb0-128">Questo non implica la concorrenza o il parallelismo, né implica che un calcolo avvenga sempre in background.</span><span class="sxs-lookup"><span data-stu-id="36bb0-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="36bb0-129">Infatti, i calcoli asincroni possono anche essere eseguiti in modo sincrono, a seconda della natura del calcolo e dell'ambiente in cui è in esecuzione il calcolo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="36bb0-130">Il principale vantaggio è che i calcoli asincroni sono indipendenti dal flusso di programma principale.</span><span class="sxs-lookup"><span data-stu-id="36bb0-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="36bb0-131">Sebbene ci siano poche garanzie su quando o come viene eseguito un calcolo asincrono, esistono alcuni approcci per orchestrarli e pianificarli.</span><span class="sxs-lookup"><span data-stu-id="36bb0-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="36bb0-132">Nella parte restante di questo articolo vengono esaminati F# i concetti di base per modalità asincrona e viene illustrato come utilizzare i tipi, F#le funzioni e le espressioni incorporati in.</span><span class="sxs-lookup"><span data-stu-id="36bb0-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="36bb0-133">Concetti di base</span><span class="sxs-lookup"><span data-stu-id="36bb0-133">Core concepts</span></span>

<span data-ttu-id="36bb0-134">In F#la programmazione asincrona è incentrata su tre concetti fondamentali:</span><span class="sxs-lookup"><span data-stu-id="36bb0-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="36bb0-135">Il tipo `Async<'T>`, che rappresenta un calcolo asincrono componibile.</span><span class="sxs-lookup"><span data-stu-id="36bb0-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="36bb0-136">Funzioni del modulo `Async`, che consentono di pianificare il lavoro asincrono, comporre calcoli asincroni e trasformare risultati asincroni.</span><span class="sxs-lookup"><span data-stu-id="36bb0-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="36bb0-137">[Espressione di calcolo](../../language-reference/computation-expressions.md)`async { }`, che fornisce una sintassi pratica per la compilazione e il controllo di calcoli asincroni.</span><span class="sxs-lookup"><span data-stu-id="36bb0-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="36bb0-138">È possibile vedere questi tre concetti nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="36bb0-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="36bb0-139">Nell'esempio, la funzione `printTotalFileBytes` è di tipo `string -> Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="36bb0-140">La chiamata alla funzione non esegue effettivamente il calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="36bb0-141">Viene invece restituito un `Async<unit>` che funge da \* specifica-del lavoro da eseguire in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-141">Instead, it returns an `Async<unit>` that acts as a \*specification- of the work that is to execute asynchronously.</span></span> <span data-ttu-id="36bb0-142">Chiamerà `Async.AwaitTask` nel corpo, che converte il risultato di <xref:System.IO.File.WriteAllBytesAsync%2A> in un tipo appropriato quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-142">It will call `Async.AwaitTask` in its body, which will convert the result of <xref:System.IO.File.WriteAllBytesAsync%2A> to an appropriate type when it is called.</span></span>

<span data-ttu-id="36bb0-143">Un'altra linea importante è la chiamata a `Async.RunSynchronously`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="36bb0-144">Si tratta di una delle funzioni di avvio del modulo asincrono che è necessario chiamare se si desidera eseguire effettivamente un F# calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="36bb0-145">Si tratta di una differenza fondamentale con C#lo stile/VB della programmazione `async`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-145">This is a fundamental difference with the C#/VB style of `async` programming.</span></span> <span data-ttu-id="36bb0-146">In F#i calcoli asincroni possono essere considerati **attività a freddo**.</span><span class="sxs-lookup"><span data-stu-id="36bb0-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="36bb0-147">Devono essere avviate in modo esplicito per eseguire effettivamente.</span><span class="sxs-lookup"><span data-stu-id="36bb0-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="36bb0-148">Questo offre alcuni vantaggi, in quanto consente di combinare e sequenziare il lavoro asincrono in modo molto più C#semplice rispetto a/VB.</span><span class="sxs-lookup"><span data-stu-id="36bb0-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C#/VB.</span></span>

## <a name="combining-asynchronous-computations"></a><span data-ttu-id="36bb0-149">Combinazione di calcoli asincroni</span><span class="sxs-lookup"><span data-stu-id="36bb0-149">Combining asynchronous computations</span></span>

<span data-ttu-id="36bb0-150">Di seguito è riportato un esempio che si basa su quello precedente combinando i calcoli:</span><span class="sxs-lookup"><span data-stu-id="36bb0-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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

<span data-ttu-id="36bb0-151">Come si può notare, la funzione `main` ha più chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="36bb0-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="36bb0-152">A livello concettuale, esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36bb0-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="36bb0-153">Trasformare gli argomenti della riga di comando in calcoli `Async<unit>` con `Array.map`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="36bb0-154">Creare un `Async<'T[]>` che pianifica ed esegue i calcoli `printTotalFileBytes` in parallelo durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="36bb0-155">Creare un `Async<unit>` che eseguirà il calcolo parallelo e ignorerà il risultato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="36bb0-156">Eseguire in modo esplicito l'ultimo calcolo con `Async.RunSynchronously` e bloccare fino a quando non viene completato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="36bb0-157">Quando viene eseguito il programma, `printTotalFileBytes` viene eseguito in parallelo per ogni argomento della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="36bb0-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="36bb0-158">Poiché i calcoli asincroni vengono eseguiti indipendentemente dal flusso di programma, non è presente alcun ordine in cui stampano le informazioni e terminano l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="36bb0-159">I calcoli verranno pianificati in parallelo, ma l'ordine di esecuzione non è garantito.</span><span class="sxs-lookup"><span data-stu-id="36bb0-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequencing-asynchronous-computations"></a><span data-ttu-id="36bb0-160">Sequenziazione di calcoli asincroni</span><span class="sxs-lookup"><span data-stu-id="36bb0-160">Sequencing asynchronous computations</span></span>

<span data-ttu-id="36bb0-161">Poiché `Async<'T>` è una specifica di lavoro anziché un'attività già in esecuzione, è possibile eseguire facilmente trasformazioni più complesse.</span><span class="sxs-lookup"><span data-stu-id="36bb0-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="36bb0-162">Di seguito è riportato un esempio che consente di sequenziare un set di calcoli asincroni in modo che vengano eseguiti uno dopo l'altro.</span><span class="sxs-lookup"><span data-stu-id="36bb0-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="36bb0-163">In questo modo si pianifica `printTotalFileBytes` per l'esecuzione in base all'ordine degli elementi di `argv` anziché pianificarli in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="36bb0-164">Poiché l'elemento successivo non verrà pianificato fino al termine dell'esecuzione dell'ultimo calcolo, i calcoli vengono sequenziati in modo che non si verifichi alcuna sovrapposizione nell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="36bb0-165">Funzioni del modulo Async importanti</span><span class="sxs-lookup"><span data-stu-id="36bb0-165">Important Async module functions</span></span>

<span data-ttu-id="36bb0-166">Quando si scrive codice asincrono in F# , in genere si interagisce con un Framework che gestisce la pianificazione dei calcoli.</span><span class="sxs-lookup"><span data-stu-id="36bb0-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="36bb0-167">Tuttavia, questo non è sempre il caso, quindi è consigliabile apprendere le varie funzioni di avvio per pianificare il lavoro asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="36bb0-168">Poiché F# i calcoli asincroni sono una _specifica_ di lavoro anziché una rappresentazione di un lavoro già in esecuzione, è necessario avviarli in modo esplicito con una funzione iniziale.</span><span class="sxs-lookup"><span data-stu-id="36bb0-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="36bb0-169">Sono disponibili molte [funzioni di avvio asincrone](https://msdn.microsoft.com/library/ee370232.aspx) che risultano utili in contesti diversi.</span><span class="sxs-lookup"><span data-stu-id="36bb0-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="36bb0-170">Nella sezione seguente vengono descritte alcune delle funzioni di avvio più comuni.</span><span class="sxs-lookup"><span data-stu-id="36bb0-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="36bb0-171">Async. StartChild</span><span class="sxs-lookup"><span data-stu-id="36bb0-171">Async.StartChild</span></span>

<span data-ttu-id="36bb0-172">Avvia un calcolo figlio all'interno di un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="36bb0-173">Questo consente l'esecuzione simultanea di più calcoli asincroni.</span><span class="sxs-lookup"><span data-stu-id="36bb0-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="36bb0-174">Il calcolo figlio condivide un token di annullamento con il calcolo padre.</span><span class="sxs-lookup"><span data-stu-id="36bb0-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="36bb0-175">Se il calcolo padre viene annullato, viene annullato anche il calcolo figlio.</span><span class="sxs-lookup"><span data-stu-id="36bb0-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="36bb0-176">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-176">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="36bb0-177">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-177">When to use:</span></span>

- <span data-ttu-id="36bb0-178">Quando si desidera eseguire contemporaneamente più calcoli asincroni anziché uno alla volta, ma non sono stati pianificati in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="36bb0-179">Quando si desidera associare la durata di un calcolo figlio a quella di un calcolo padre.</span><span class="sxs-lookup"><span data-stu-id="36bb0-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="36bb0-180">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-180">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-181">L'avvio di più calcoli con `Async.StartChild` non corrisponde alla pianificazione in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="36bb0-182">Se si desidera pianificare calcoli in parallelo, utilizzare `Async.Parallel`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="36bb0-183">L'annullamento di un calcolo padre attiverà l'annullamento di tutti i calcoli figlio avviati.</span><span class="sxs-lookup"><span data-stu-id="36bb0-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="36bb0-184">Async. StartImmediate</span><span class="sxs-lookup"><span data-stu-id="36bb0-184">Async.StartImmediate</span></span>

<span data-ttu-id="36bb0-185">Esegue un calcolo asincrono, a partire immediatamente dal thread del sistema operativo corrente.</span><span class="sxs-lookup"><span data-stu-id="36bb0-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="36bb0-186">Questa operazione è utile se è necessario aggiornare qualcosa nel thread chiamante durante il calcolo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="36bb0-187">Se, ad esempio, un calcolo asincrono deve aggiornare un'interfaccia utente, ad esempio l'aggiornamento di un indicatore di stato, è necessario utilizzare `Async.StartImmediate`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="36bb0-188">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="36bb0-189">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-189">When to use:</span></span>

- <span data-ttu-id="36bb0-190">Quando è necessario aggiornare qualcosa nel thread chiamante durante un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="36bb0-191">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-191">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-192">Il codice nel calcolo asincrono verrà eseguito su qualsiasi thread su cui si verifica la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="36bb0-193">Questa operazione può risultare problematica se il thread è in qualche modo sensibile, ad esempio un thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="36bb0-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="36bb0-194">In questi casi `Async.StartImmediate` è probabilmente inappropriato per l'uso di.</span><span class="sxs-lookup"><span data-stu-id="36bb0-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="36bb0-195">Async. StartAsTask</span><span class="sxs-lookup"><span data-stu-id="36bb0-195">Async.StartAsTask</span></span>

<span data-ttu-id="36bb0-196">Esegue un calcolo nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="36bb0-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="36bb0-197">Restituisce un <xref:System.Threading.Tasks.Task%601> che verrà completato nello stato corrispondente al termine del calcolo (genera il risultato, genera un'eccezione o viene annullato).</span><span class="sxs-lookup"><span data-stu-id="36bb0-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="36bb0-198">Se non viene fornito alcun token di annullamento, viene utilizzato il token di annullamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="36bb0-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="36bb0-199">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="36bb0-200">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-200">When to use:</span></span>

- <span data-ttu-id="36bb0-201">Quando è necessario chiamare un'API .NET che prevede un <xref:System.Threading.Tasks.Task%601> per rappresentare il risultato di un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="36bb0-202">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-202">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-203">Questa chiamata consente di allocare un oggetto `Task` aggiuntivo, che può aumentare il sovraccarico se usato spesso.</span><span class="sxs-lookup"><span data-stu-id="36bb0-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="36bb0-204">Async. Parallel</span><span class="sxs-lookup"><span data-stu-id="36bb0-204">Async.Parallel</span></span>

<span data-ttu-id="36bb0-205">Pianifica una sequenza di calcoli asincroni da eseguire in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="36bb0-206">Il grado di parallelismo può essere facoltativamente ottimizzato/limitato specificando il parametro `maxDegreesOfParallelism`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="36bb0-207">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="36bb0-208">Quando utilizzarlo:</span><span class="sxs-lookup"><span data-stu-id="36bb0-208">When to use it:</span></span>

- <span data-ttu-id="36bb0-209">Se è necessario eseguire contemporaneamente un set di calcoli e non si ha alcuna dipendenza dall'ordine di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="36bb0-210">Se non sono necessari i risultati dei calcoli pianificati in parallelo fino a quando non sono stati completati.</span><span class="sxs-lookup"><span data-stu-id="36bb0-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="36bb0-211">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-211">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-212">Una volta completati tutti i calcoli, è possibile accedere alla matrice di valori risultante.</span><span class="sxs-lookup"><span data-stu-id="36bb0-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="36bb0-213">I calcoli verranno eseguiti, ma finiranno per essere pianificati.</span><span class="sxs-lookup"><span data-stu-id="36bb0-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="36bb0-214">Ciò significa che non è possibile fare affidamento sull'ordine di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="36bb0-215">Asincrono. sequenziale</span><span class="sxs-lookup"><span data-stu-id="36bb0-215">Async.Sequential</span></span>

<span data-ttu-id="36bb0-216">Pianifica una sequenza di calcoli asincroni da eseguire nell'ordine in cui vengono passati.</span><span class="sxs-lookup"><span data-stu-id="36bb0-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="36bb0-217">Il primo calcolo verrà eseguito, quindi il successivo e così via.</span><span class="sxs-lookup"><span data-stu-id="36bb0-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="36bb0-218">Nessun calcolo verrà eseguito in parallelo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="36bb0-219">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="36bb0-220">Quando utilizzarlo:</span><span class="sxs-lookup"><span data-stu-id="36bb0-220">When to use it:</span></span>

- <span data-ttu-id="36bb0-221">Se è necessario eseguire più calcoli in ordine.</span><span class="sxs-lookup"><span data-stu-id="36bb0-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="36bb0-222">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-222">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-223">Una volta completati tutti i calcoli, è possibile accedere alla matrice di valori risultante.</span><span class="sxs-lookup"><span data-stu-id="36bb0-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="36bb0-224">I calcoli verranno eseguiti nell'ordine in cui vengono passati a questa funzione, il che può comportare una maggiore quantità di tempo prima che vengano restituiti i risultati.</span><span class="sxs-lookup"><span data-stu-id="36bb0-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="36bb0-225">Async. AwaitTask</span><span class="sxs-lookup"><span data-stu-id="36bb0-225">Async.AwaitTask</span></span>

<span data-ttu-id="36bb0-226">Restituisce un calcolo asincrono che attende il completamento dell'<xref:System.Threading.Tasks.Task%601> specificato e ne restituisce il risultato come `Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="36bb0-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="36bb0-227">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="36bb0-228">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-228">When to use:</span></span>

- <span data-ttu-id="36bb0-229">Quando si utilizza un'API .NET che restituisce un <xref:System.Threading.Tasks.Task%601> all'interno di un F# calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="36bb0-230">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-230">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-231">Le eccezioni vengono incapsulate in <xref:System.AggregateException> in seguito alla convenzione della Task Parallel Library ed è diverso dal F# modo in cui Async rileva in genere le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="36bb0-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="36bb0-232">Asincrono. catch</span><span class="sxs-lookup"><span data-stu-id="36bb0-232">Async.Catch</span></span>

<span data-ttu-id="36bb0-233">Crea un calcolo asincrono che esegue un dato `Async<'T>`, restituendo un `Async<Choice<'T, exn>>`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="36bb0-234">Se il `Async<'T>` specificato viene completato correttamente, viene restituito un `Choice1Of2` con il valore risultante.</span><span class="sxs-lookup"><span data-stu-id="36bb0-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="36bb0-235">Se viene generata un'eccezione prima che venga completata, viene restituito un `Choice2of2` con l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="36bb0-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="36bb0-236">Se viene usato in un calcolo asincrono costituito da un numero elevato di calcoli e uno di questi calcoli genera un'eccezione, il calcolo che la comprende verrà interrotto interamente.</span><span class="sxs-lookup"><span data-stu-id="36bb0-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="36bb0-237">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="36bb0-238">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-238">When to use:</span></span>

- <span data-ttu-id="36bb0-239">Quando si eseguono operazioni asincrone che possono avere esito negativo con un'eccezione e si desidera gestire tale eccezione nel chiamante.</span><span class="sxs-lookup"><span data-stu-id="36bb0-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="36bb0-240">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-240">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-241">Quando si usano calcoli asincroni combinati o sequenziati, il calcolo comprendente verrà interrotto completamente se uno dei calcoli "interni" genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="36bb0-242">Async. ignore</span><span class="sxs-lookup"><span data-stu-id="36bb0-242">Async.Ignore</span></span>

<span data-ttu-id="36bb0-243">Crea un calcolo asincrono che esegue il calcolo specificato e ne ignora il risultato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="36bb0-244">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="36bb0-245">Quando usare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-245">When to use:</span></span>

- <span data-ttu-id="36bb0-246">Quando si dispone di un calcolo asincrono il cui risultato non è necessario.</span><span class="sxs-lookup"><span data-stu-id="36bb0-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="36bb0-247">Questo è analogo al codice @no__t 0 per il codice non asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="36bb0-248">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-248">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-249">Se è necessario usare questo oggetto perché si vuole usare `Async.Start` o un'altra funzione che richiede `Async<unit>`, valutare se l'eliminazione del risultato è accettabile.</span><span class="sxs-lookup"><span data-stu-id="36bb0-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="36bb0-250">Non è in genere consigliabile ignorare i risultati solo per adattarli a una firma di tipo.</span><span class="sxs-lookup"><span data-stu-id="36bb0-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="36bb0-251">Async. RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="36bb0-251">Async.RunSynchronously</span></span>

<span data-ttu-id="36bb0-252">Esegue un calcolo asincrono e ne attende il risultato nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="36bb0-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="36bb0-253">Questa chiamata è in blocco.</span><span class="sxs-lookup"><span data-stu-id="36bb0-253">This call is blocking.</span></span>

<span data-ttu-id="36bb0-254">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="36bb0-255">Quando utilizzarlo:</span><span class="sxs-lookup"><span data-stu-id="36bb0-255">When to use it:</span></span>

- <span data-ttu-id="36bb0-256">Se necessario, usarlo una sola volta in un'applicazione, in corrispondenza del punto di ingresso di un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="36bb0-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="36bb0-257">Quando non si è interessati alle prestazioni e si desidera eseguire contemporaneamente un set di altre operazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="36bb0-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="36bb0-258">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-258">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-259">La chiamata a `Async.RunSynchronously` blocca il thread chiamante fino al completamento dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="36bb0-260">Async. Start</span><span class="sxs-lookup"><span data-stu-id="36bb0-260">Async.Start</span></span>

<span data-ttu-id="36bb0-261">Avvia un calcolo asincrono nel pool di thread che restituisce `unit`.</span><span class="sxs-lookup"><span data-stu-id="36bb0-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="36bb0-262">Non attende il risultato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-262">Doesn't wait for its result.</span></span> <span data-ttu-id="36bb0-263">I calcoli annidati avviati con `Async.Start` vengono avviati completamente indipendentemente dal calcolo padre che li ha chiamati.</span><span class="sxs-lookup"><span data-stu-id="36bb0-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="36bb0-264">La loro durata non è associata ad alcun calcolo padre.</span><span class="sxs-lookup"><span data-stu-id="36bb0-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="36bb0-265">Se il calcolo padre viene annullato, nessun calcolo figlio viene annullato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="36bb0-266">Firma</span><span class="sxs-lookup"><span data-stu-id="36bb0-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="36bb0-267">Usare solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36bb0-267">Use only when:</span></span>

- <span data-ttu-id="36bb0-268">Si dispone di un calcolo asincrono che non restituisce un risultato e/o ne richiede l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="36bb0-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="36bb0-269">Non è necessario stabilire quando un calcolo asincrono viene completato.</span><span class="sxs-lookup"><span data-stu-id="36bb0-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="36bb0-270">Non si è interessati al thread in cui viene eseguito un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="36bb0-271">Non è necessario conoscere o segnalare le eccezioni derivanti dall'attività.</span><span class="sxs-lookup"><span data-stu-id="36bb0-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="36bb0-272">Elementi da controllare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-272">What to watch out for:</span></span>

- <span data-ttu-id="36bb0-273">Le eccezioni generate da calcoli avviati con `Async.Start` non vengono propagate al chiamante.</span><span class="sxs-lookup"><span data-stu-id="36bb0-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="36bb0-274">Lo stack di chiamate verrà completamente rimosso.</span><span class="sxs-lookup"><span data-stu-id="36bb0-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="36bb0-275">Eventuali operazioni con effetto, ad esempio la chiamata di `printfn`, avviate con `Async.Start` non determinano l'esecuzione dell'effetto sul thread principale dell'esecuzione di un programma.</span><span class="sxs-lookup"><span data-stu-id="36bb0-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperating-with-net"></a><span data-ttu-id="36bb0-276">Interoperabilità con .NET</span><span class="sxs-lookup"><span data-stu-id="36bb0-276">Interoperating with .NET</span></span>

<span data-ttu-id="36bb0-277">È possibile che si stia lavorando a una libreria C# .NET o a una codebase che usa la programmazione asincrona di tipo [Async/Await](../../../standard/async.md).</span><span class="sxs-lookup"><span data-stu-id="36bb0-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="36bb0-278">Poiché C# e la maggior parte delle librerie .NET utilizzano i tipi <xref:System.Threading.Tasks.Task%601> e <xref:System.Threading.Tasks.Task> come astrazioni di base invece che `Async<'T>`, è necessario attraversare un limite tra questi due approcci a modalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="36bb0-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="36bb0-279">Come usare Async .NET e `Task<T>`</span><span class="sxs-lookup"><span data-stu-id="36bb0-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="36bb0-280">L'utilizzo di librerie asincrone .NET e codebase che utilizzano <xref:System.Threading.Tasks.Task%601>, ovvero calcoli asincroni con valori restituiti, è semplice e include supporto incorporato con F#.</span><span class="sxs-lookup"><span data-stu-id="36bb0-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="36bb0-281">È possibile utilizzare la funzione `Async.AwaitTask` per attendere un calcolo asincrono di .NET:</span><span class="sxs-lookup"><span data-stu-id="36bb0-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="36bb0-282">È possibile usare la funzione `Async.StartAsTask` per passare un calcolo asincrono a un chiamante .NET:</span><span class="sxs-lookup"><span data-stu-id="36bb0-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="36bb0-283">Come usare Async .NET e `Task`</span><span class="sxs-lookup"><span data-stu-id="36bb0-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="36bb0-284">Per lavorare con le API che usano <xref:System.Threading.Tasks.Task>, ovvero i calcoli asincroni .NET che non restituiscono un valore, potrebbe essere necessario aggiungere una funzione aggiuntiva che consentirà di convertire un `Async<'T>` in un <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="36bb0-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="36bb0-285">Esiste già un `Async.AwaitTask` che accetta un <xref:System.Threading.Tasks.Task> come input.</span><span class="sxs-lookup"><span data-stu-id="36bb0-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="36bb0-286">Con questa e la funzione `startTaskFromAsyncUnit` definita in precedenza, è possibile avviare e attendere i tipi <xref:System.Threading.Tasks.Task> F# da un calcolo asincrono.</span><span class="sxs-lookup"><span data-stu-id="36bb0-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multithreading"></a><span data-ttu-id="36bb0-287">Relazione con il multithreading</span><span class="sxs-lookup"><span data-stu-id="36bb0-287">Relationship to multithreading</span></span>

<span data-ttu-id="36bb0-288">Sebbene il threading venga indicato in questo articolo, ci sono due aspetti importanti da ricordare:</span><span class="sxs-lookup"><span data-stu-id="36bb0-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="36bb0-289">Non esiste alcuna affinità tra un calcolo asincrono e un thread, a meno che non sia stato avviato in modo esplicito sul thread corrente.</span><span class="sxs-lookup"><span data-stu-id="36bb0-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="36bb0-290">La programmazione asincrona F# in non è un'astrazione per il multithreading.</span><span class="sxs-lookup"><span data-stu-id="36bb0-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="36bb0-291">Un calcolo, ad esempio, può essere effettivamente eseguito sul thread del chiamante, a seconda della natura del lavoro.</span><span class="sxs-lookup"><span data-stu-id="36bb0-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="36bb0-292">Un calcolo potrebbe anche "passare" tra i thread, per consentirne il prestito per un periodo di tempo ridotto per eseguire operazioni utili tra i periodi di "attesa", ad esempio quando una chiamata di rete è in transito.</span><span class="sxs-lookup"><span data-stu-id="36bb0-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="36bb0-293">Sebbene F# fornisca alcune capacità per avviare un calcolo asincrono sul thread corrente (o non in modo esplicito nel thread corrente), modalità asincrona in genere non è associato a una particolare strategia di Threading.</span><span class="sxs-lookup"><span data-stu-id="36bb0-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="36bb0-294">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36bb0-294">See also</span></span>

- [<span data-ttu-id="36bb0-295">Modello F# di programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="36bb0-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="36bb0-296">Guida asincrona di F# Jet. com</span><span class="sxs-lookup"><span data-stu-id="36bb0-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="36bb0-297">F#Guida alla programmazione asincrona di Fun and profit</span><span class="sxs-lookup"><span data-stu-id="36bb0-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="36bb0-298">Async in C# e F#: aspetti asincroni inC#</span><span class="sxs-lookup"><span data-stu-id="36bb0-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
