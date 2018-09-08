---
title: Espressioni di calcolo (F#)
description: 'Informazioni su come creare una sintassi efficiente per la scrittura di calcoli in F # che possa essere sequenziata e combinati tramite costrutti del flusso di controllo e associazioni.'
ms.date: 07/27/2018
ms.openlocfilehash: ce81af7966a436b3973de277fb2a78ec06f4c471
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200064"
---
# <a name="computation-expressions"></a><span data-ttu-id="ddffa-103">Espressioni di calcolo</span><span class="sxs-lookup"><span data-stu-id="ddffa-103">Computation Expressions</span></span>

<span data-ttu-id="ddffa-104">Le espressioni di calcolo in F # forniscono una sintassi efficiente per la scrittura di calcoli che possono essere sequenziati e combinati tramite costrutti del flusso di controllo e associazioni.</span><span class="sxs-lookup"><span data-stu-id="ddffa-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="ddffa-105">A seconda del tipo dell'espressione di calcolo, è possibile pensare come un modo per esprimere monads, monoids, trasformatori monad e funtori applicative.</span><span class="sxs-lookup"><span data-stu-id="ddffa-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="ddffa-106">Tuttavia, a differenza di altri linguaggi (ad esempio *in notazione* in Haskell), non sono associate a una singola astrazione e non fare affidamento su macro o altre forme di metaprogrammazione per eseguire una sintassi pratica e sensibile al contesto.</span><span class="sxs-lookup"><span data-stu-id="ddffa-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="ddffa-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ddffa-107">Overview</span></span>

<span data-ttu-id="ddffa-108">I calcoli possono assumere molte forme.</span><span class="sxs-lookup"><span data-stu-id="ddffa-108">Computations can take many forms.</span></span> <span data-ttu-id="ddffa-109">La forma più comune di calcolo è l'esecuzione a thread singolo, che è facile da comprendere e modificare.</span><span class="sxs-lookup"><span data-stu-id="ddffa-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="ddffa-110">Tuttavia, non tutte le forme di calcolo sono semplice come l'esecuzione a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="ddffa-111">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="ddffa-111">Some examples include:</span></span>

* <span data-ttu-id="ddffa-112">Calcoli non deterministiche</span><span class="sxs-lookup"><span data-stu-id="ddffa-112">Non-deterministic computations</span></span>
* <span data-ttu-id="ddffa-113">Calcoli asincroni</span><span class="sxs-lookup"><span data-stu-id="ddffa-113">Asynchronous computations</span></span>
* <span data-ttu-id="ddffa-114">Calcoli effectful</span><span class="sxs-lookup"><span data-stu-id="ddffa-114">Effectful computations</span></span>
* <span data-ttu-id="ddffa-115">Calcoli propria</span><span class="sxs-lookup"><span data-stu-id="ddffa-115">Generative computations</span></span>

<span data-ttu-id="ddffa-116">Più in generale, esistono *sensibile al contesto* i calcoli che è necessario eseguire in determinate parti di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ddffa-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="ddffa-117">Scrittura di codice sensibile al contesto può essere problematico, in quanto è facile per i calcoli "perdite" di fuori di un determinato contesto senza astrazioni per impedire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="ddffa-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="ddffa-118">Queste astrazioni sono spesso difficili da scrivere da soli, motivo per cui F # offre un modo generalizzato per eseguire cosiddette **espressioni di calcolo**.</span><span class="sxs-lookup"><span data-stu-id="ddffa-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="ddffa-119">Le espressioni di calcolo offrono un modello di sintassi e astrazione uniforme per la codifica dei calcoli sensibile al contesto.</span><span class="sxs-lookup"><span data-stu-id="ddffa-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="ddffa-120">Ogni espressione di calcolo è supportata da un *generatore* tipo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="ddffa-121">Il tipo di generatore definisce le operazioni disponibili per l'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="ddffa-122">Visualizzare [creando un nuovo tipo di espressione di calcolo](computation-expressions.md#creating-a-new-type-of-computation-expression), che mostra come creare un'espressione di calcolo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ddffa-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="ddffa-123">Panoramica della sintassi</span><span class="sxs-lookup"><span data-stu-id="ddffa-123">Syntax overview</span></span>

<span data-ttu-id="ddffa-124">Tutte le espressioni di calcolo disponibili nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="ddffa-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="ddffa-125">in cui `builder-expr` è il nome di un tipo di generatore che definisce l'espressione di calcolo e `cexper` corrisponde al corpo di espressione dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="ddffa-126">Ad esempio, `async` codice di espressione di calcolo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ddffa-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="ddffa-127">È una sintassi speciale, aggiuntiva disponibile all'interno di un'espressione di calcolo, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="ddffa-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="ddffa-128">Le forme di espressioni seguenti sono possibili con le espressioni di calcolo:</span><span class="sxs-lookup"><span data-stu-id="ddffa-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="ddffa-129">Ognuna di queste parole chiave e altri standard F # le parole chiave sono disponibili solo in un'espressione di calcolo se sono stati definiti nel tipo di generatore di backup.</span><span class="sxs-lookup"><span data-stu-id="ddffa-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="ddffa-130">È l'unica eccezione a questa `match!`, che è a sua volta zucchero sintattico per l'uso di `let!` seguita da un criterio di ricerca sul risultato.</span><span class="sxs-lookup"><span data-stu-id="ddffa-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="ddffa-131">Il tipo di generatore è un oggetto che definisce i metodi speciali che controllano il modo in cui che vengono combinati i frammenti dell'espressione di calcolo; vale a dire i relativi metodi controllano il comportamento di espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="ddffa-132">Un altro modo per descrivere una classe del generatore è dire che permette di personalizzare il funzionamento di molti costrutti F #, ad esempio cicli e associazioni.</span><span class="sxs-lookup"><span data-stu-id="ddffa-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="ddffa-133">Il `let!` parola chiave associa il risultato di una chiamata a un'altra espressione di calcolo a un nome:</span><span class="sxs-lookup"><span data-stu-id="ddffa-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="ddffa-134">Se si associa la chiamata a un'espressione di calcolo con `let`, non sarà possibile ottenere il risultato dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="ddffa-135">Al contrario, verrà associato il valore della *non realizzati* le chiamate a quell ' espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="ddffa-136">Usare `let!` da associare al risultato.</span><span class="sxs-lookup"><span data-stu-id="ddffa-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="ddffa-137">`let!` è definito dal `Bind(x, f)` membro del tipo di generatore.</span><span class="sxs-lookup"><span data-stu-id="ddffa-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="ddffa-138">Il `do!` è la parola chiave per la chiamata di un'espressione di calcolo che restituisce un `unit`-come tipo (definito dal `Zero` membro sul generatore):</span><span class="sxs-lookup"><span data-stu-id="ddffa-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! sumbitData data url
        ...
    }
```

<span data-ttu-id="ddffa-139">Per il [flusso di lavoro asincroni](asynchronous-workflows.md), questo tipo è `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="ddffa-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="ddffa-140">Per altre espressioni di calcolo, il tipo è probabilmente `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="ddffa-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="ddffa-141">`do!` è definito dal `Bind(x, f)` membro del tipo di generatore, dove `f` produce un `unit`.</span><span class="sxs-lookup"><span data-stu-id="ddffa-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="ddffa-142">Il `yield` parola chiave sia per la restituzione di un valore dall'espressione di calcolo in modo che possa essere utilizzato come un <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="ddffa-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="ddffa-143">Come con le [yield (parola chiave) in c#](../../csharp/language-reference/keywords/yield.md), ogni elemento nell'espressione di calcolo viene restituito perché viene scorsa.</span><span class="sxs-lookup"><span data-stu-id="ddffa-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="ddffa-144">`yield` è definito dal `Yield(x)` membro del tipo di generatore, in cui `x` è l'elemento per produrre nuovamente.</span><span class="sxs-lookup"><span data-stu-id="ddffa-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="ddffa-145">Il `yield!` la parola chiave è per rendere flat una raccolta di valori da un'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="ddffa-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

<span data-ttu-id="ddffa-146">Durante la valutazione, l'espressione di calcolo denominato `yield!` verranno dispone i relativi elementi restituiti indietro uno alla volta, rendere flat il risultato.</span><span class="sxs-lookup"><span data-stu-id="ddffa-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="ddffa-147">`yield!` è definito dal `YieldFrom(x)` membro del tipo di generatore, in cui `x` è una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="ddffa-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="ddffa-148">Il `return` (parola chiave) esegue il wrapping di un valore di tipo corrispondente all'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="ddffa-149">A parte le espressioni di calcolo usando `yield`, viene utilizzato su "completa" di un'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="ddffa-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="ddffa-150">`return` è definito per il `Return(x)` membro del tipo di generatore, in cui `x` è l'elemento di cui eseguire il wrapping.</span><span class="sxs-lookup"><span data-stu-id="ddffa-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="ddffa-151">Il `return!` (parola chiave) il valore di un'espressione di calcolo di realizzazione ed esegue il wrapping di tale risultato nel tipo corrispondente all'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="ddffa-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="ddffa-152">`return!` è definito per il `ReturnFrom(x)` membro del tipo di generatore, in cui `x` è un'altra espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="ddffa-153">A partire da F # 4.5, il `match!` parola chiave consente di rendere inline una chiamata a un altro calcolo corrispondenza di espressione e modello per il risultato:</span><span class="sxs-lookup"><span data-stu-id="ddffa-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="ddffa-154">Quando si chiama un'espressione di calcolo con `match!`, potrà trarre il risultato della chiamata, ad esempio `let!`.</span><span class="sxs-lookup"><span data-stu-id="ddffa-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="ddffa-155">Viene spesso utilizzata quando si chiama un'espressione di calcolo in cui il risultato è un' [facoltativi](options.md).</span><span class="sxs-lookup"><span data-stu-id="ddffa-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="ddffa-156">Espressioni di calcolo incorporato</span><span class="sxs-lookup"><span data-stu-id="ddffa-156">Built-in computation expressions</span></span>

<span data-ttu-id="ddffa-157">Libreria di base F # definisce tre espressioni di calcolo predefinito: [espressioni di sequenza](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di Query](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ddffa-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="ddffa-158">Creare un nuovo tipo di espressione di calcolo</span><span class="sxs-lookup"><span data-stu-id="ddffa-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="ddffa-159">È possibile definire le caratteristiche delle proprie espressioni di calcolo tramite la creazione di una classe del generatore e la definizione di determinati metodi speciali sulla classe.</span><span class="sxs-lookup"><span data-stu-id="ddffa-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="ddffa-160">La classe del generatore possibile definire i metodi elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ddffa-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="ddffa-161">Nella tabella seguente vengono descritti i metodi che possono essere usati in una classe del generatore del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ddffa-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="ddffa-162">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="ddffa-162">**Method**</span></span>|<span data-ttu-id="ddffa-163">**Firma tipica**</span><span class="sxs-lookup"><span data-stu-id="ddffa-163">**Typical signature(s)**</span></span>|<span data-ttu-id="ddffa-164">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ddffa-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="ddffa-165">Chiamato per `let!` e `do!` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="ddffa-166">Esegue il wrapping di un'espressione di calcolo come una funzione.</span><span class="sxs-lookup"><span data-stu-id="ddffa-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="ddffa-167">Chiamato per `return` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="ddffa-168">Chiamato per `return!` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="ddffa-169">`M<'T> -> M<'T>` oppure</span><span class="sxs-lookup"><span data-stu-id="ddffa-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="ddffa-170">Esegue un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="ddffa-171">`M<'T> * M<'T> -> M<'T>` oppure</span><span class="sxs-lookup"><span data-stu-id="ddffa-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="ddffa-172">Chiamato per la sequenziazione in espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="ddffa-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure</span><span class="sxs-lookup"><span data-stu-id="ddffa-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="ddffa-174">Chiamato per `for...do` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="ddffa-175">Chiamato per `try...finally` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="ddffa-176">Chiamato per `try...with` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="ddffa-177">Chiamato per `use` associazioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="ddffa-178">Chiamato per `while...do` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="ddffa-179">Chiamato per `yield` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="ddffa-180">Chiamato per `yield!` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="ddffa-181">Chiamato per vuoto `else` rami di `if...then` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|

<span data-ttu-id="ddffa-182">Molti dei metodi in una classe generatore usano e restituiscono un `M<'T>` construct che è in genere un tipo definito separatamente che caratterizza il tipo di calcoli combinate, ad esempio, `Async<'T>` per i flussi di lavoro asincroni e `Seq<'T>` per i flussi di lavoro di sequenza.</span><span class="sxs-lookup"><span data-stu-id="ddffa-182">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="ddffa-183">Le firme di questi metodi consentono loro di essere combinate e annidate tra loro, in modo che sia possibile passare l'oggetto del flusso di lavoro restituito da un costrutto a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="ddffa-183">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="ddffa-184">Il compilatore, quando analizza un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione annidata usando i metodi nella tabella precedente e il codice nell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-184">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="ddffa-185">L'espressione annidata è nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="ddffa-185">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="ddffa-186">Nel codice precedente, le chiamate a `Run` e `Delay` vengono omessi se non sono definiti nella classe del generatore di espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-186">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="ddffa-187">Il corpo dell'espressione di calcolo, di seguito è indicato come `{| cexpr |}`, viene convertita in chiamate che riguardano i metodi della classe del generatore per le conversioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ddffa-187">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="ddffa-188">L'espressione di calcolo `{| cexpr |}` viene definito in modo ricorsivo in base a queste conversioni in cui `expr` è un'espressione F # e `cexpr` è un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-188">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="ddffa-189">Espressione</span><span class="sxs-lookup"><span data-stu-id="ddffa-189">Expression</span></span>|<span data-ttu-id="ddffa-190">Conversione</span><span class="sxs-lookup"><span data-stu-id="ddffa-190">Translation</span></span>|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
<span data-ttu-id="ddffa-191">Nella tabella precedente, `other-expr` descrive un'espressione che non è elencata nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ddffa-191">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="ddffa-192">Una classe generatore non è necessario implementare tutti i metodi e supportano tutte le conversioni elencate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="ddffa-192">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="ddffa-193">Tali costrutti che non sono implementati non sono disponibili nelle espressioni di calcolo di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-193">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="ddffa-194">Ad esempio, se non si desidera supportare le `use` parola chiave nelle espressioni di calcolo, è possibile omettere la definizione di `Use` nella classe del generatore.</span><span class="sxs-lookup"><span data-stu-id="ddffa-194">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="ddffa-195">Esempio di codice seguente illustra un'espressione di calcolo che incapsula un calcolo in una serie di passaggi che può essere valutato una sola operazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="ddffa-195">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="ddffa-196">Oggetto discriminate tipo unione, `OkOrException`, consente di codificare lo stato di errore dell'espressione valutato fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="ddffa-196">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="ddffa-197">Questo codice illustra alcuni modelli tipici che è possibile usare nelle espressioni di calcolo, ad esempio le implementazioni di boilerplate di alcuni dei metodi del generatore.</span><span class="sxs-lookup"><span data-stu-id="ddffa-197">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> NotYetDone (fun () -> func value)
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

<span data-ttu-id="ddffa-198">Un'espressione di calcolo ha un tipo sottostante, che restituisce l'espressione.</span><span class="sxs-lookup"><span data-stu-id="ddffa-198">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="ddffa-199">Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito o può fornire un modo per eseguire l'iterazione attraverso un certo tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="ddffa-199">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="ddffa-200">Nell'esempio precedente, il tipo sottostante è stata **alla fine**.</span><span class="sxs-lookup"><span data-stu-id="ddffa-200">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="ddffa-201">Per un'espressione di sequenza, il tipo sottostante è <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ddffa-201">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ddffa-202">Per un'espressione di query, il tipo sottostante è <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ddffa-202">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ddffa-203">Per un flusso di lavoro asincrono, il tipo sottostante è [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="ddffa-203">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="ddffa-204">Il `Async` oggetto rappresenta il lavoro da eseguire per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="ddffa-204">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="ddffa-205">Ad esempio, si chiama [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un calcolo e restituire il risultato.</span><span class="sxs-lookup"><span data-stu-id="ddffa-205">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="ddffa-206">Operazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ddffa-206">Custom Operations</span></span>

<span data-ttu-id="ddffa-207">È possibile definire un'operazione personalizzata su un'espressione di calcolo e usare un'operazione personalizzata come operatore in un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-207">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="ddffa-208">Ad esempio, è possibile includere un operatore di query in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="ddffa-208">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="ddffa-209">Quando si definisce un'operazione personalizzata, è necessario definire il risultato e per i metodi dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-209">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="ddffa-210">Per definire un'operazione personalizzata, inserirlo in una classe del generatore per l'espressione di calcolo e quindi applicare il [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="ddffa-210">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="ddffa-211">Questo attributo accetta una stringa come argomento, ovvero il nome da usare in un'operazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ddffa-211">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="ddffa-212">Questo nome entra nell'ambito all'inizio della parentesi graffa di apertura dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-212">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="ddffa-213">Pertanto, non è consigliabile utilizzare gli identificatori che hanno lo stesso nome di un'operazione personalizzata in questo blocco.</span><span class="sxs-lookup"><span data-stu-id="ddffa-213">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="ddffa-214">Ad esempio, evitare l'utilizzo di identificatori, ad esempio `all` o `last` nelle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="ddffa-214">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="ddffa-215">Estensione generatori esistenti con nuove operazioni personalizzato</span><span class="sxs-lookup"><span data-stu-id="ddffa-215">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="ddffa-216">Se si dispone già di una classe del generatore, delle operazioni personalizzate possono essere estesi all'esterno di questa classe del generatore.</span><span class="sxs-lookup"><span data-stu-id="ddffa-216">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="ddffa-217">Le estensioni devono essere dichiarate nei moduli.</span><span class="sxs-lookup"><span data-stu-id="ddffa-217">Extensions must be declared in modules.</span></span> <span data-ttu-id="ddffa-218">Gli spazi dei nomi non possono contenere membri di estensione, ad eccezione dello stesso file e lo stesso gruppo di dichiarazione dello spazio dei nomi in cui è definito il tipo.</span><span class="sxs-lookup"><span data-stu-id="ddffa-218">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="ddffa-219">L'esempio seguente illustra l'estensione dell'oggetto esistente `Microsoft.FSharp.Linq.QueryBuilder` classe.</span><span class="sxs-lookup"><span data-stu-id="ddffa-219">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="ddffa-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddffa-220">See also</span></span>

- [<span data-ttu-id="ddffa-221">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ddffa-221">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ddffa-222">Flussi di lavoro asincroni</span><span class="sxs-lookup"><span data-stu-id="ddffa-222">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="ddffa-223">Sequenze</span><span class="sxs-lookup"><span data-stu-id="ddffa-223">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="ddffa-224">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="ddffa-224">Query Expressions</span></span>](query-expressions.md)
