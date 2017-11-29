---
title: 'Programmazione asincrona in F #'
description: "Informazioni su come la programmazione asincrona F # viene eseguita tramite un modello di programmazione a livello di linguaggio che è facile da usare e il linguaggio naturale."
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: 23528d84d0f28283868a1ea316953543d0fd566a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="async-programming-in-f"></a><span data-ttu-id="8330c-104">Programmazione asincrona in F #</span><span class="sxs-lookup"><span data-stu-id="8330c-104">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="8330c-105">Alcune imprecisioni sono stati individuati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8330c-105">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="8330c-106">Da riscrivere.</span><span class="sxs-lookup"><span data-stu-id="8330c-106">It is being rewritten.</span></span>  <span data-ttu-id="8330c-107">Vedere [problema #666](https://github.com/dotnet/docs/issues/666) per informazioni sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="8330c-107">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="8330c-108">Programmazione F # può essere eseguita tramite un modello di programmazione a livello di linguaggio progettato per essere facile da usare e il linguaggio naturale.</span><span class="sxs-lookup"><span data-stu-id="8330c-108">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="8330c-109">La base della programmazione asincrona in F # è `Async<'T>`, una rappresentazione di lavoro che può essere attivata per l'esecuzione in background, in cui `'T` è il tipo restituito tramite speciale `return` (parola chiave) o `unit` se non include il flusso di lavoro asincroni risultato da restituire.</span><span class="sxs-lookup"><span data-stu-id="8330c-109">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="8330c-110">Il concetto chiave per comprendere è che il tipo dell'espressione async `Async<'T>`, che è semplicemente un _specifica_ di lavoro da eseguire in un contesto asincrono.</span><span class="sxs-lookup"><span data-stu-id="8330c-110">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="8330c-111">Non viene eseguita finché non viene esplicitamente avviata con una delle funzioni iniziale (ad esempio `Async.RunSynchronously`).</span><span class="sxs-lookup"><span data-stu-id="8330c-111">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="8330c-112">Si tratta di un modo diverso pensare di eseguire il lavoro, alla fine viene piuttosto semplice in pratica.</span><span class="sxs-lookup"><span data-stu-id="8330c-112">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="8330c-113">Ad esempio, che si desidera scaricare il codice HTML da dotnetfoundation.org senza bloccare il thread principale.</span><span class="sxs-lookup"><span data-stu-id="8330c-113">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="8330c-114">È possibile ottenere questo risultato simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8330c-114">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "http://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="8330c-115">E questo è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="8330c-115">And that’s it!</span></span> <span data-ttu-id="8330c-116">A parte l'utilizzo di `async`, `let!`, e `return`, si tratta solo normale codice F #.</span><span class="sxs-lookup"><span data-stu-id="8330c-116">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="8330c-117">Esistono alcuni costrutti sintattici che vale la pena notare:</span><span class="sxs-lookup"><span data-stu-id="8330c-117">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="8330c-118">`let!`Associa il risultato di un'espressione async (che viene eseguito in un altro contesto).</span><span class="sxs-lookup"><span data-stu-id="8330c-118">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="8330c-119">`use!`funziona come `let!`, ma elimina le risorse associate, quando esce dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="8330c-119">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="8330c-120">`do!`attende un flusso di lavoro asincrono non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="8330c-120">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="8330c-121">`return`Restituisce semplicemente un risultato da un'espressione di tipo asincrono.</span><span class="sxs-lookup"><span data-stu-id="8330c-121">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="8330c-122">`return!`esegue un altro flusso di lavoro asincrono e restituisce il valore restituito come risultato.</span><span class="sxs-lookup"><span data-stu-id="8330c-122">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="8330c-123">Inoltre, normale `let`, `use`, e `do` parole chiave possono essere utilizzate con le versioni asincrone come se fossero in una funzione normale.</span><span class="sxs-lookup"><span data-stu-id="8330c-123">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="8330c-124">Come avviare codice asincrono in F #</span><span class="sxs-lookup"><span data-stu-id="8330c-124">How to start Async Code in F#</span></span> #

<span data-ttu-id="8330c-125">Come accennato in precedenza, il codice asincrono è una specifica di lavoro da eseguire in un altro contesto che deve essere avviata in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="8330c-125">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="8330c-126">Di seguito sono due modi principali per ottenere questo risultato:</span><span class="sxs-lookup"><span data-stu-id="8330c-126">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="8330c-127">`Async.RunSynchronously`Avvia un flusso di lavoro asincrono in un altro thread e attendere il risultato.</span><span class="sxs-lookup"><span data-stu-id="8330c-127">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "http://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  <span data-ttu-id="8330c-128">`Async.Start`avviare un flusso di lavoro asincrono in un altro thread e verrà **non** attende il relativo risultato.</span><span class="sxs-lookup"><span data-stu-id="8330c-128">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "http://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="8330c-129">Esistono altri modi per avviare un flusso di lavoro asincroni disponibile per gli scenari più specifici.</span><span class="sxs-lookup"><span data-stu-id="8330c-129">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="8330c-130">Sono descritti in dettaglio [negli argomenti di riferimento Async](https://msdn.microsoft.com/library/ee370232.aspx).</span><span class="sxs-lookup"><span data-stu-id="8330c-130">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="8330c-131">Nota sulla thread</span><span class="sxs-lookup"><span data-stu-id="8330c-131">A Note on Threads</span></span>

<span data-ttu-id="8330c-132">La frase "in un altro thread" è indicata in precedenza, ma è importante sapere che **ciò non significa che i flussi di lavoro asincroni sono facciata per il multithreading**.</span><span class="sxs-lookup"><span data-stu-id="8330c-132">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="8330c-133">Il flusso di lavoro effettivamente "passa" tra thread, richiesta di finanziamenti per una piccola quantità di tempo per eseguire operazioni utili.</span><span class="sxs-lookup"><span data-stu-id="8330c-133">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="8330c-134">Quando un flusso di lavoro asincrono è in modo efficace "in attesa" (ad esempio, in attesa di una chiamata di rete restituire un valore), qualsiasi thread che è stata richiesta di finanziamenti al momento viene liberata fino a passare eseguire operazioni utili in un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="8330c-134">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="8330c-135">Questo consente di flussi di lavoro asincroni utilizzare il sistema in cui in che vengono eseguiti nel modo e li rende particolarmente efficaci per gli scenari dei / o di volumi elevati.</span><span class="sxs-lookup"><span data-stu-id="8330c-135">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="8330c-136">Come aggiungere codice asincrono di parallelismo</span><span class="sxs-lookup"><span data-stu-id="8330c-136">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="8330c-137">In alcuni casi può necessario per eseguire più processi asincroni in parallelo, raccogliere i risultati e interpretati in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="8330c-137">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="8330c-138">`Async.Parallel`Consente di eseguire queste operazioni senza dover usare Task Parallel Library, che comporta la necessità di forzare `Task<'T>` e `Async<'T>` tipi.</span><span class="sxs-lookup"><span data-stu-id="8330c-138">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="8330c-139">Nell'esempio seguente utilizzerà `Async.Parallel` per scaricare il codice HTML da quattro parti comuni in parallelo, attendere il completamento di tali attività e quindi stampare il codice HTML che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="8330c-139">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "http://www.microsoft.com"
      "http://www.google.com"
      "http://www.amazon.com"
      "http://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="8330c-140">Consigli e informazioni importanti</span><span class="sxs-lookup"><span data-stu-id="8330c-140">Important Info and Advice</span></span>

*   <span data-ttu-id="8330c-141">Aggiungere "Async" alla fine di qualsiasi funzione che è possibile utilizzare</span><span class="sxs-lookup"><span data-stu-id="8330c-141">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="8330c-142">Si tratta di una convenzione di denominazione, semplificare le operazioni come il rilevamento di API.</span><span class="sxs-lookup"><span data-stu-id="8330c-142">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="8330c-143">In particolare se sono presenti versioni sincrone e asincrone della stessa routine, è consigliabile indicare esplicitamente che è asincrono tramite il nome.</span><span class="sxs-lookup"><span data-stu-id="8330c-143">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="8330c-144">Restare in attesa il compilatore!</span><span class="sxs-lookup"><span data-stu-id="8330c-144">Listen to the compiler!</span></span>

 <span data-ttu-id="8330c-145">Il compilatore F # è molto rigido, rendendo quasi impossibile eseguire un'operazione troubling come eseguire il codice "async" in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="8330c-145">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="8330c-146">Se si individua un avviso, che è un segno che il codice non verrà eseguito come si ritiene che verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="8330c-146">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="8330c-147">Se il compilatore può rendere soddisfatti, l'esecuzione del codice probabilmente come previsto.</span><span class="sxs-lookup"><span data-stu-id="8330c-147">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="8330c-148">Per i programmatori c# /VB C in F #</span><span class="sxs-lookup"><span data-stu-id="8330c-148">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="8330c-149">In questa sezione presuppone che si abbia familiarità con il modello asincrono in c# o VB.</span><span class="sxs-lookup"><span data-stu-id="8330c-149">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="8330c-150">Se il non computer [di programmazione asincrona in c#](../../../csharp/async.md) è un punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="8330c-150">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="8330c-151">È presente una differenza fondamentale tra il modello asincrono di c# /VB C e il modello asincrono di F #.</span><span class="sxs-lookup"><span data-stu-id="8330c-151">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="8330c-152">Quando si chiama una funzione che restituisce un `Task` o `Task<'T>`, tale processo ha già iniziato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8330c-152">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="8330c-153">L'handle restituito rappresenta un processo asincrono già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8330c-153">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="8330c-154">Al contrario, quando si chiama una funzione async in F #, di `Async<'a>` restituito rappresenta un processo che sarà **generato** a un certo punto.</span><span class="sxs-lookup"><span data-stu-id="8330c-154">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="8330c-155">La comprensione di questo modello è potente, perché consente infatti di processi asincroni in F # per concatenare più semplice, eseguita in modo condizionale e avviare con una granularità più preciso del controllo.</span><span class="sxs-lookup"><span data-stu-id="8330c-155">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="8330c-156">Esistono alcuni altri analogie e differenze non degni di nota.</span><span class="sxs-lookup"><span data-stu-id="8330c-156">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="8330c-157">Analogie</span><span class="sxs-lookup"><span data-stu-id="8330c-157">Similarities</span></span>

*   <span data-ttu-id="8330c-158">`let!`, `use!`, e `do!` sono analoghi alle `await` durante la chiamata dall'interno di un processo asincrono un `async{ }` blocco.</span><span class="sxs-lookup"><span data-stu-id="8330c-158">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="8330c-159">Tre parole chiave possono essere utilizzate solo all'interno di un `async { }` blocco, analoga a quanto `await` può essere richiamato solo all'interno di un `async` metodo.</span><span class="sxs-lookup"><span data-stu-id="8330c-159">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="8330c-160">In breve, `let!` viene utilizzata quando si desidera acquisire e utilizzare un risultato, `use!` è lo stesso, ma per un elemento il cui risorse devono ottenere eliminate dopo essere stato utilizzato, e `do!` viene utilizzata quando si desidera attendere per un flusso di lavoro asincrono senza valore restituito di fine prima di proseguire.</span><span class="sxs-lookup"><span data-stu-id="8330c-160">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="8330c-161">F # supporta il parallelismo dei dati in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="8330c-161">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="8330c-162">Anche se opera in modo molto diverso, `Async.Parallel` corrisponde a `Task.WhenAll` per lo scenario di che i risultati di un set di processi asincroni quando vengono completate.</span><span class="sxs-lookup"><span data-stu-id="8330c-162">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="8330c-163">Differenze</span><span class="sxs-lookup"><span data-stu-id="8330c-163">Differences</span></span>

*   <span data-ttu-id="8330c-164">Annidati `let!` non è consentito, a differenza di annidati`await`</span><span class="sxs-lookup"><span data-stu-id="8330c-164">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="8330c-165">A differenza di `await`, che può essere nidificata in modo indefinito, `let!` non può e deve avere il relativo risultato associato prima di utilizzarlo all'interno di un altro `let!`, `do!`, o `use!`.</span><span class="sxs-lookup"><span data-stu-id="8330c-165">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="8330c-166">Supporto per l'annullamento è più semplice in F # rispetto a in c# o VB.</span><span class="sxs-lookup"><span data-stu-id="8330c-166">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="8330c-167">Il supporto di annullamento di una metà di attività tramite l'esecuzione in C# /VB richiede il controllo di `IsCancellationRequested` proprietà o chiamare il metodo `ThrowIfCancellationRequested()` su un `CancellationToken` oggetto passato al metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="8330c-167">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="8330c-168">Al contrario, F # asincrono flussi di lavoro sono con maggiore naturalezza annullabile.</span><span class="sxs-lookup"><span data-stu-id="8330c-168">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="8330c-169">Annullamento è un semplice processo in tre fasi.</span><span class="sxs-lookup"><span data-stu-id="8330c-169">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="8330c-170">Creare un nuovo oggetto `CancellationTokenSource`.</span><span class="sxs-lookup"><span data-stu-id="8330c-170">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="8330c-171">Passare a una funzione di avvio.</span><span class="sxs-lookup"><span data-stu-id="8330c-171">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="8330c-172">Chiamare `Cancel` sul token.</span><span class="sxs-lookup"><span data-stu-id="8330c-172">Call `Cancel` on the token.</span></span>

<span data-ttu-id="8330c-173">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8330c-173">Example:</span></span>

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "http://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="8330c-174">E questo è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="8330c-174">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="8330c-175">Ulteriori risorse:</span><span class="sxs-lookup"><span data-stu-id="8330c-175">Further resources:</span></span>

*   [<span data-ttu-id="8330c-176">Flussi di lavoro asincrono su MSDN</span><span class="sxs-lookup"><span data-stu-id="8330c-176">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="8330c-177">Sequenze asincrone per F #</span><span class="sxs-lookup"><span data-stu-id="8330c-177">Asynchronous Sequences for F#</span></span>](http://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="8330c-178">Utilità di F # dati HTTP</span><span class="sxs-lookup"><span data-stu-id="8330c-178">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
