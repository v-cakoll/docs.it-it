---
title: Espressioni di calcolo
description: Informazioni su come creare una sintassi pratica per la scrittura di F# calcoli in che possono essere sequenziati e combinati mediante costrutti e associazioni del flusso di controllo.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794544"
---
# <a name="computation-expressions"></a><span data-ttu-id="b2e13-103">Espressioni di calcolo</span><span class="sxs-lookup"><span data-stu-id="b2e13-103">Computation Expressions</span></span>

<span data-ttu-id="b2e13-104">Le espressioni di F# calcolo in forniscono una sintassi pratica per la scrittura di calcoli che possono essere sequenziati e combinati mediante costrutti e associazioni del flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="b2e13-105">A seconda del tipo di espressione di calcolo, possono essere considerati come un modo per esprimere monadi, monoids, i trasformatori Monad e funtori applicativi.</span><span class="sxs-lookup"><span data-stu-id="b2e13-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="b2e13-106">Tuttavia, a differenza di altri linguaggi (ad esempio *do-Notation* in Haskell), non sono collegati a un'unica astrazione e non si basano su macro o altre forme di metaprogrammazione per realizzare una sintassi pratica e sensibile al contesto.</span><span class="sxs-lookup"><span data-stu-id="b2e13-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="b2e13-107">Panoramica di</span><span class="sxs-lookup"><span data-stu-id="b2e13-107">Overview</span></span>

<span data-ttu-id="b2e13-108">I calcoli possono assumere molte forme.</span><span class="sxs-lookup"><span data-stu-id="b2e13-108">Computations can take many forms.</span></span> <span data-ttu-id="b2e13-109">Il tipo di calcolo più comune è l'esecuzione a thread singolo, che è facile da comprendere e modificare.</span><span class="sxs-lookup"><span data-stu-id="b2e13-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="b2e13-110">Tuttavia, non tutte le forme di calcolo sono semplici come l'esecuzione a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="b2e13-111">Alcuni esempi includono:</span><span class="sxs-lookup"><span data-stu-id="b2e13-111">Some examples include:</span></span>

- <span data-ttu-id="b2e13-112">Calcoli non deterministici</span><span class="sxs-lookup"><span data-stu-id="b2e13-112">Non-deterministic computations</span></span>
- <span data-ttu-id="b2e13-113">Calcoli asincroni</span><span class="sxs-lookup"><span data-stu-id="b2e13-113">Asynchronous computations</span></span>
- <span data-ttu-id="b2e13-114">Calcoli effettivi</span><span class="sxs-lookup"><span data-stu-id="b2e13-114">Effectful computations</span></span>
- <span data-ttu-id="b2e13-115">Calcoli generativi</span><span class="sxs-lookup"><span data-stu-id="b2e13-115">Generative computations</span></span>

<span data-ttu-id="b2e13-116">Più in generale, esistono calcoli *sensibili al contesto* che è necessario eseguire in determinate parti di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2e13-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="b2e13-117">La scrittura di codice sensibile al contesto può essere complessa, in quanto è facile "perdere" i calcoli all'esterno di un determinato contesto senza astrazioni per impedire l'esecuzione di questa operazione.</span><span class="sxs-lookup"><span data-stu-id="b2e13-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="b2e13-118">Queste astrazioni sono spesso difficili da scrivere autonomamente, motivo F# per cui ha un metodo generalizzato per eseguire queste operazioni, denominate espressioni di **calcolo**.</span><span class="sxs-lookup"><span data-stu-id="b2e13-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="b2e13-119">Le espressioni di calcolo offrono una sintassi uniforme e un modello di astrazione per la codifica di calcoli sensibili al contesto.</span><span class="sxs-lookup"><span data-stu-id="b2e13-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="b2e13-120">Ogni espressione di calcolo è supportata da un tipo di *Generatore* .</span><span class="sxs-lookup"><span data-stu-id="b2e13-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="b2e13-121">Il tipo di generatore definisce le operazioni disponibili per l'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="b2e13-122">Vedere [creazione di un nuovo tipo di espressione di calcolo](computation-expressions.md#creating-a-new-type-of-computation-expression), che Mostra come creare un'espressione di calcolo personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b2e13-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="b2e13-123">Cenni preliminari sulla sintassi</span><span class="sxs-lookup"><span data-stu-id="b2e13-123">Syntax overview</span></span>

<span data-ttu-id="b2e13-124">Tutte le espressioni di calcolo hanno il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="b2e13-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="b2e13-125">dove `builder-expr` è il nome di un tipo di generatore che definisce l'espressione di calcolo e `cexper` è il corpo dell'espressione dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="b2e13-126">`async` codice dell'espressione di calcolo, ad esempio, può essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b2e13-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="b2e13-127">All'interno di un'espressione di calcolo è disponibile una speciale sintassi aggiuntiva, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="b2e13-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="b2e13-128">Con le espressioni di calcolo sono possibili i form di espressione seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2e13-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="b2e13-129">Ognuna di queste parole chiave e altre parole F# chiave standard sono disponibili in un'espressione di calcolo solo se sono state definite nel tipo di generatore di backup.</span><span class="sxs-lookup"><span data-stu-id="b2e13-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="b2e13-130">L'unica eccezione è `match!`, ovvero lo zucchero sintattico per l'uso di `let!` seguito da una corrispondenza di criteri nel risultato.</span><span class="sxs-lookup"><span data-stu-id="b2e13-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="b2e13-131">Il tipo di generatore è un oggetto che definisce metodi speciali che governano il modo in cui vengono combinati i frammenti dell'espressione di calcolo. ovvero, i metodi controllano il comportamento dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="b2e13-132">Un altro modo per descrivere una classe del generatore consiste nel dire che consente di personalizzare l'operazione di molti F# costrutti, ad esempio cicli e associazioni.</span><span class="sxs-lookup"><span data-stu-id="b2e13-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="b2e13-133">La parola chiave `let!` associa il risultato di una chiamata a un'altra espressione di calcolo a un nome:</span><span class="sxs-lookup"><span data-stu-id="b2e13-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="b2e13-134">Se si associa la chiamata a un'espressione di calcolo con `let`, non sarà possibile ottenere il risultato dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="b2e13-135">Al contrario, sarà necessario associare il valore della chiamata non *realizzata* a tale espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="b2e13-136">Utilizzare `let!` per eseguire l'associazione al risultato.</span><span class="sxs-lookup"><span data-stu-id="b2e13-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="b2e13-137">`let!` viene definito dal membro `Bind(x, f)` sul tipo di generatore.</span><span class="sxs-lookup"><span data-stu-id="b2e13-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="b2e13-138">La parola chiave `do!` è per chiamare un'espressione di calcolo che restituisce un tipo simile a `unit`(definito dal membro `Zero` nel generatore):</span><span class="sxs-lookup"><span data-stu-id="b2e13-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="b2e13-139">Per il [flusso di lavoro asincrono](asynchronous-workflows.md), questo tipo è `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="b2e13-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="b2e13-140">Per altre espressioni di calcolo, è probabile che il tipo sia `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="b2e13-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="b2e13-141">`do!` viene definito dal membro `Bind(x, f)` sul tipo di generatore, in cui `f` genera un `unit`.</span><span class="sxs-lookup"><span data-stu-id="b2e13-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="b2e13-142">La parola chiave `yield` è per restituire un valore dall'espressione di calcolo in modo che possa essere utilizzata come <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="b2e13-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="b2e13-143">Nella maggior parte dei casi, può essere omesso dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="b2e13-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="b2e13-144">Il modo più comune per omettere `yield` è con l'operatore `->`:</span><span class="sxs-lookup"><span data-stu-id="b2e13-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="b2e13-145">Per espressioni più complesse che potrebbero restituire molti valori diversi e, forse, in modo condizionale, la semplice omissione della parola chiave può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2e13-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

<span data-ttu-id="b2e13-146">Come per la [parola chiave yield C#in ](../../csharp/language-reference/keywords/yield.md), ogni elemento nell'espressione di calcolo viene restituito mentre viene iterato.</span><span class="sxs-lookup"><span data-stu-id="b2e13-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="b2e13-147">`yield` viene definito dal membro `Yield(x)` sul tipo di generatore, dove `x` è l'elemento da restituire.</span><span class="sxs-lookup"><span data-stu-id="b2e13-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="b2e13-148">La parola chiave `yield!` è per rendere flat una raccolta di valori da un'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="b2e13-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="b2e13-149">Quando viene valutato, l'espressione di calcolo chiamata da `yield!` avrà gli elementi restituiti uno alla volta, rendendo flat il risultato.</span><span class="sxs-lookup"><span data-stu-id="b2e13-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="b2e13-150">`yield!` viene definito dal membro `YieldFrom(x)` sul tipo di generatore, dove `x` è una raccolta di valori.</span><span class="sxs-lookup"><span data-stu-id="b2e13-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="b2e13-151">Diversamente da `yield`, `yield!` necessario specificare in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="b2e13-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="b2e13-152">Il suo comportamento non è implicito nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="b2e13-153">La parola chiave `return` esegue il wrapping di un valore nel tipo corrispondente all'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="b2e13-154">A parte le espressioni di calcolo con `yield`, viene usato per "completare" un'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="b2e13-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="b2e13-155">`return` viene definito dal membro `Return(x)` sul tipo di generatore, dove `x` è l'elemento di cui eseguire il wrapping.</span><span class="sxs-lookup"><span data-stu-id="b2e13-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="b2e13-156">La parola chiave `return!` rende conto del valore di un'espressione di calcolo ed esegue il wrapping del risultato nel tipo corrispondente all'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="b2e13-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="b2e13-157">`return!` viene definito dal membro `ReturnFrom(x)` sul tipo di generatore, dove `x` è un'altra espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="b2e13-158">La parola chiave `match!` consente di inline una chiamata a un'altra espressione di calcolo e il criterio di ricerca corrisponde al risultato:</span><span class="sxs-lookup"><span data-stu-id="b2e13-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="b2e13-159">Quando si chiama un'espressione di calcolo con `match!`, realizzerà il risultato della chiamata, ad esempio `let!`.</span><span class="sxs-lookup"><span data-stu-id="b2e13-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="b2e13-160">Questa operazione viene spesso utilizzata quando si chiama un'espressione di calcolo in cui il risultato è [facoltativo](options.md).</span><span class="sxs-lookup"><span data-stu-id="b2e13-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="b2e13-161">Espressioni di calcolo predefinite</span><span class="sxs-lookup"><span data-stu-id="b2e13-161">Built-in computation expressions</span></span>

<span data-ttu-id="b2e13-162">La F# libreria principale definisce tre espressioni di calcolo predefinite: [espressioni di sequenza](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di query](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b2e13-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="b2e13-163">Creazione di un nuovo tipo di espressione di calcolo</span><span class="sxs-lookup"><span data-stu-id="b2e13-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="b2e13-164">È possibile definire le caratteristiche delle proprie espressioni di calcolo creando una classe del generatore e definendo determinati metodi speciali sulla classe.</span><span class="sxs-lookup"><span data-stu-id="b2e13-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="b2e13-165">La classe Builder può facoltativamente definire i metodi elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b2e13-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="b2e13-166">Nella tabella seguente vengono descritti i metodi che possono essere utilizzati in una classe del generatore di flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b2e13-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="b2e13-167">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="b2e13-167">**Method**</span></span>|<span data-ttu-id="b2e13-168">**Firme tipiche**</span><span class="sxs-lookup"><span data-stu-id="b2e13-168">**Typical signature(s)**</span></span>|<span data-ttu-id="b2e13-169">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b2e13-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="b2e13-170">Chiamato per `let!` e `do!` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="b2e13-171">Esegue il wrapping di un'espressione di calcolo come funzione.</span><span class="sxs-lookup"><span data-stu-id="b2e13-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="b2e13-172">Chiamato per `return` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="b2e13-173">Chiamato per `return!` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="b2e13-174">`M<'T> -> M<'T>` oppure</span><span class="sxs-lookup"><span data-stu-id="b2e13-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="b2e13-175">Esegue un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="b2e13-176">`M<'T> * M<'T> -> M<'T>` oppure</span><span class="sxs-lookup"><span data-stu-id="b2e13-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="b2e13-177">Chiamato per la sequenziazione nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="b2e13-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure</span><span class="sxs-lookup"><span data-stu-id="b2e13-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="b2e13-179">Chiamato per `for...do` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="b2e13-180">Chiamato per `try...finally` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="b2e13-181">Chiamato per `try...with` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="b2e13-182">Chiamato per `use` associazioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="b2e13-183">Chiamato per `while...do` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="b2e13-184">Chiamato per `yield` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="b2e13-185">Chiamato per `yield!` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="b2e13-186">Chiamato per `else` rami vuoti delle espressioni `if...then` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="b2e13-187">Indica che l'espressione di calcolo viene passata al membro `Run` come virgoletta.</span><span class="sxs-lookup"><span data-stu-id="b2e13-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="b2e13-188">Converte tutte le istanze di un calcolo in una virgoletta.</span><span class="sxs-lookup"><span data-stu-id="b2e13-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="b2e13-189">Molti dei metodi di una classe Builder utilizzano e restituiscono un costrutto di `M<'T>`, che in genere è un tipo definito separatamente che caratterizza il tipo di calcoli combinati, ad esempio `Async<'T>` per i flussi di lavoro asincroni e `Seq<'T>` per i flussi di lavoro di sequenza.</span><span class="sxs-lookup"><span data-stu-id="b2e13-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="b2e13-190">Le firme di questi metodi consentono di combinarle e nidificarle tra loro, in modo che l'oggetto flusso di lavoro restituito da un costrutto possa essere passato a quello successivo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="b2e13-191">Il compilatore, durante l'analisi di un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione annidate utilizzando i metodi della tabella precedente e il codice dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="b2e13-192">Il formato dell'espressione annidata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b2e13-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="b2e13-193">Nel codice precedente, le chiamate a `Run` e `Delay` vengono omesse se non sono definite nella classe del generatore di espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="b2e13-194">Il corpo dell'espressione di calcolo, qui indicato come `{| cexpr |}`, viene convertito in chiamate che coinvolgono i metodi della classe Builder dalle traduzioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b2e13-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="b2e13-195">L'espressione di calcolo `{| cexpr |}` viene definita in modo ricorsivo in base a queste traduzioni F# in cui `expr` è un'espressione e `cexpr` è un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="b2e13-196">Espressione</span><span class="sxs-lookup"><span data-stu-id="b2e13-196">Expression</span></span>|<span data-ttu-id="b2e13-197">Conversione</span><span class="sxs-lookup"><span data-stu-id="b2e13-197">Translation</span></span>|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

<span data-ttu-id="b2e13-198">Nella tabella precedente, `other-expr` descrive un'espressione che non è elencata diversamente nella tabella.</span><span class="sxs-lookup"><span data-stu-id="b2e13-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="b2e13-199">Una classe Builder non deve implementare tutti i metodi e supportare tutte le traduzioni elencate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="b2e13-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="b2e13-200">Questi costrutti non implementati non sono disponibili nelle espressioni di calcolo di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="b2e13-201">Se, ad esempio, non si desidera supportare la parola chiave `use` nelle espressioni di calcolo, è possibile omettere la definizione di `Use` nella classe del generatore.</span><span class="sxs-lookup"><span data-stu-id="b2e13-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="b2e13-202">Nell'esempio di codice seguente viene illustrata un'espressione di calcolo che incapsula un calcolo come una serie di passaggi che possono essere valutati un passaggio alla volta.</span><span class="sxs-lookup"><span data-stu-id="b2e13-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="b2e13-203">Un tipo di unione discriminata, `OkOrException`, codifica lo stato di errore dell'espressione come valutato finora.</span><span class="sxs-lookup"><span data-stu-id="b2e13-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="b2e13-204">Questo codice illustra diversi modelli tipici che è possibile usare nelle espressioni di calcolo, ad esempio le implementazioni standard di alcuni metodi del generatore.</span><span class="sxs-lookup"><span data-stu-id="b2e13-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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
        | Done value -> func value
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
// returns "Done 7"
comp |> step |> step |> step |> step
```

<span data-ttu-id="b2e13-205">Un'espressione di calcolo ha un tipo sottostante, restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="b2e13-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="b2e13-206">Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito oppure può fornire un modo per scorrere un tipo di raccolta.</span><span class="sxs-lookup"><span data-stu-id="b2e13-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="b2e13-207">Nell'esempio precedente, il tipo sottostante era **alla fine**.</span><span class="sxs-lookup"><span data-stu-id="b2e13-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="b2e13-208">Per un'espressione di sequenza, il tipo sottostante viene <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2e13-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2e13-209">Per un'espressione di query, il tipo sottostante viene <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2e13-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2e13-210">Per un flusso di lavoro asincrono, il tipo sottostante viene [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="b2e13-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="b2e13-211">L'oggetto `Async` rappresenta il lavoro da eseguire per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="b2e13-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="b2e13-212">Ad esempio, si chiama [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un calcolo e restituire il risultato.</span><span class="sxs-lookup"><span data-stu-id="b2e13-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="b2e13-213">Operazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b2e13-213">Custom Operations</span></span>

<span data-ttu-id="b2e13-214">È possibile definire un'operazione personalizzata su un'espressione di calcolo e utilizzare un'operazione personalizzata come operatore in un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="b2e13-215">È ad esempio possibile includere un operatore di query in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="b2e13-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="b2e13-216">Quando si definisce un'operazione personalizzata, è necessario definire i metodi yield e for nell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="b2e13-217">Per definire un'operazione personalizzata, inserirla in una classe di generatore per l'espressione di calcolo, quindi applicare la [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="b2e13-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="b2e13-218">Questo attributo accetta una stringa come argomento, che è il nome da usare in un'operazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b2e13-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="b2e13-219">Questo nome entra nell'ambito all'inizio della parentesi graffa di apertura dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="b2e13-220">Pertanto, non è consigliabile utilizzare identificatori con lo stesso nome di un'operazione personalizzata in questo blocco.</span><span class="sxs-lookup"><span data-stu-id="b2e13-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="b2e13-221">Ad esempio, evitare l'utilizzo di identificatori come `all` o `last` nelle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="b2e13-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="b2e13-222">Estensione di generatori esistenti con nuove operazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b2e13-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="b2e13-223">Se si dispone già di una classe Builder, le operazioni personalizzate possono essere estese dall'esterno di questa classe del generatore.</span><span class="sxs-lookup"><span data-stu-id="b2e13-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="b2e13-224">Le estensioni devono essere dichiarate nei moduli.</span><span class="sxs-lookup"><span data-stu-id="b2e13-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="b2e13-225">Gli spazi dei nomi non possono contenere membri di estensione eccetto nello stesso file e nello stesso gruppo di dichiarazioni dello spazio dei nomi in cui è definito il tipo.</span><span class="sxs-lookup"><span data-stu-id="b2e13-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="b2e13-226">Nell'esempio seguente viene illustrata l'estensione della classe `Microsoft.FSharp.Linq.QueryBuilder` esistente.</span><span class="sxs-lookup"><span data-stu-id="b2e13-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="b2e13-227">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2e13-227">See also</span></span>

- [<span data-ttu-id="b2e13-228">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="b2e13-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="b2e13-229">Flussi di lavoro asincroni</span><span class="sxs-lookup"><span data-stu-id="b2e13-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="b2e13-230">Sequenze</span><span class="sxs-lookup"><span data-stu-id="b2e13-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="b2e13-231">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="b2e13-231">Query Expressions</span></span>](query-expressions.md)
