---
title: Espressioni di calcolo (F#)
description: 'Informazioni su come creare una semplice sintassi per la scrittura di calcoli in F # che possono essere ordinati in sequenza e combinati con i costrutti del flusso di controllo e le associazioni.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: acabbf5d-fbb8-479f-894c-7251bf16c8c3
ms.openlocfilehash: c4ff998c65f3a5c458f36312f6887d869569d814
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="computation-expressions"></a><span data-ttu-id="ec449-104">Espressioni di calcolo</span><span class="sxs-lookup"><span data-stu-id="ec449-104">Computation Expressions</span></span>

<span data-ttu-id="ec449-105">Espressioni di calcolo in F # forniscono una sintassi efficiente per la scrittura di calcoli che possono essere ordinati in sequenza e combinati con i costrutti del flusso di controllo e le associazioni.</span><span class="sxs-lookup"><span data-stu-id="ec449-105">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="ec449-106">Possono essere utilizzati per fornire una sintassi efficiente per *Monad*, una funzionalità di programmazione funzionale che può essere utilizzata per gestire i dati, controllo e gli effetti collaterali nei programmi funzionali.</span><span class="sxs-lookup"><span data-stu-id="ec449-106">They can be used to provide a convenient syntax for *monads*, a functional programming feature that can be used to manage data, control, and side effects in functional programs.</span></span>


## <a name="built-in-workflows"></a><span data-ttu-id="ec449-107">Flussi di lavoro predefiniti</span><span class="sxs-lookup"><span data-stu-id="ec449-107">Built-in Workflows</span></span>
<span data-ttu-id="ec449-108">Le espressioni di sequenza sono un esempio di un'espressione di calcolo, come flussi di lavoro asincroni e le espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="ec449-108">Sequence expressions are an example of a computation expression, as are asynchronous workflows and query expressions.</span></span> <span data-ttu-id="ec449-109">Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di Query](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ec449-109">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

<span data-ttu-id="ec449-110">Alcune funzionalità sono comuni a entrambe le espressioni di sequenza e flussi di lavoro asincroni e viene illustrata la sintassi di base per un'espressione di calcolo:</span><span class="sxs-lookup"><span data-stu-id="ec449-110">Certain features are common to both sequence expressions and asynchronous workflows and illustrate the basic syntax for a computation expression:</span></span>

```fsharp
builder-name { expression }
```

<span data-ttu-id="ec449-111">La sintassi precedente specifica che l'espressione specificata è un'espressione di calcolo di un tipo specificato dal *nome generatore*.</span><span class="sxs-lookup"><span data-stu-id="ec449-111">The previous syntax specifies that the given expression is a computation expression of a type specified by *builder-name*.</span></span> <span data-ttu-id="ec449-112">L'espressione di calcolo può essere un flusso di lavoro predefinito, ad esempio `seq` o `async`, oppure può essere un elemento è definito.</span><span class="sxs-lookup"><span data-stu-id="ec449-112">The computation expression can be a built-in workflow, such as `seq` or `async`, or it can be something you define.</span></span> <span data-ttu-id="ec449-113">Il *nome generatore* è l'identificatore per un'istanza di un tipo speciale noto come il *tipo generatore*.</span><span class="sxs-lookup"><span data-stu-id="ec449-113">The *builder-name* is the identifier for an instance of a special type known as the *builder type*.</span></span> <span data-ttu-id="ec449-114">Il tipo di generatore è un tipo di classe che definisce i metodi speciali che controllano il modo in cui che i frammenti dell'espressione di calcolo vengono combinati, ovvero codice che determina la modalità di esecuzione l'espressione.</span><span class="sxs-lookup"><span data-stu-id="ec449-114">The builder type is a class type that defines special methods that govern the way the fragments of the computation expression are combined, that is, code that controls how the expression executes.</span></span> <span data-ttu-id="ec449-115">Un altro modo per descrivere una classe del generatore è ad esempio che consente di personalizzare il funzionamento di molti costrutti F #, ad esempio cicli e associazioni.</span><span class="sxs-lookup"><span data-stu-id="ec449-115">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

<span data-ttu-id="ec449-116">Nelle espressioni di calcolo, due forme sono disponibili per alcuni costrutti di linguaggio comuni.</span><span class="sxs-lookup"><span data-stu-id="ec449-116">In computation expressions, two forms are available for some common language constructs.</span></span> <span data-ttu-id="ec449-117">È possibile richiamare i costrutti variant utilizzando un!</span><span class="sxs-lookup"><span data-stu-id="ec449-117">You can invoke the variant constructs by using a !</span></span> <span data-ttu-id="ec449-118">(punto esclamativo) suffisso in determinate parole chiave, ad esempio `let!`, `do!`e così via.</span><span class="sxs-lookup"><span data-stu-id="ec449-118">(bang) suffix on certain keywords, such as `let!`, `do!`, and so on.</span></span> <span data-ttu-id="ec449-119">Questi moduli speciali che alcune funzioni definite nella classe del generatore per sostituire il normale comportamento predefinito di queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="ec449-119">These special forms cause certain functions defined in the builder class to replace the ordinary built-in behavior of these operations.</span></span> <span data-ttu-id="ec449-120">Questi moduli sono simili al `yield!` costituito il `yield` parola chiave utilizzata nelle espressioni di sequenza.</span><span class="sxs-lookup"><span data-stu-id="ec449-120">These forms resemble the `yield!` form of the `yield` keyword that is used in sequence expressions.</span></span> <span data-ttu-id="ec449-121">Per ulteriori informazioni, vedere [sequenze](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="ec449-121">For more information, see [Sequences](sequences.md).</span></span>


## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="ec449-122">Creare un nuovo tipo di espressione di calcolo</span><span class="sxs-lookup"><span data-stu-id="ec449-122">Creating a New Type of Computation Expression</span></span>
<span data-ttu-id="ec449-123">Creazione di una classe del generatore e definendo determinati metodi speciali sulla classe, è possibile definire le caratteristiche di espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-123">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="ec449-124">La classe del generatore può facoltativamente definire i metodi elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ec449-124">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="ec449-125">Nella tabella seguente vengono descritti i metodi che possono essere utilizzati in una classe del generatore del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ec449-125">The following table describes methods that can be used in a workflow builder class.</span></span>


|<span data-ttu-id="ec449-126">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="ec449-126">**Method**</span></span>|<span data-ttu-id="ec449-127">**Firma tipica**</span><span class="sxs-lookup"><span data-stu-id="ec449-127">**Typical signature(s)**</span></span>|<span data-ttu-id="ec449-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ec449-128">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="ec449-129">Chiamato per `let!` e `do!` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-129">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="ec449-130">Esegue il wrapping di un'espressione di calcolo come una funzione.</span><span class="sxs-lookup"><span data-stu-id="ec449-130">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="ec449-131">Chiamato per `return` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-131">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="ec449-132">Chiamato per `return!` nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-132">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="ec449-133">`M<'T> -> M<'T>` oppure</span><span class="sxs-lookup"><span data-stu-id="ec449-133">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="ec449-134">Esegue un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-134">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="ec449-135">`M<'T> * M<'T> -> M<'T>` oppure</span><span class="sxs-lookup"><span data-stu-id="ec449-135">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="ec449-136">Chiamato per la sequenziazione nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-136">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="ec449-137">`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure</span><span class="sxs-lookup"><span data-stu-id="ec449-137">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="ec449-138">Chiamato per `for...do` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-138">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="ec449-139">Chiamato per `try...finally` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-139">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="ec449-140">Chiamato per `try...with` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-140">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="ec449-141">Chiamato per `use` associazioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-141">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="ec449-142">Chiamato per `while...do` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-142">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="ec449-143">Chiamato per `yield` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-143">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="ec449-144">Chiamato per `yield!` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-144">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="ec449-145">Chiamato per vuoto `else` rami di `if...then` espressioni nelle espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-145">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
<span data-ttu-id="ec449-146">Molti dei metodi in una classe generatore utilizzano e restituire un `M<'T>` costrutto, ovvero in genere un tipo definito separatamente che caratterizza il tipo di calcoli combinati, ad esempio, `Async<'T>` per flussi di lavoro asincroni e `Seq<'T>` per i flussi di lavoro di sequenza.</span><span class="sxs-lookup"><span data-stu-id="ec449-146">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="ec449-147">Le firme di questi metodi affinché possano essere combinate e annidati tra loro, in modo che l'oggetto del flusso di lavoro restituito da un costrutto può essere passato a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="ec449-147">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="ec449-148">Il compilatore, quando si analizza un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione nidificata utilizzando i metodi nella tabella precedente e il codice nell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-148">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="ec449-149">L'espressione nidificata è nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="ec449-149">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="ec449-150">Nel codice precedente, le chiamate a `Run` e `Delay` vengono omessi se non sono definiti nella classe del generatore di espressioni di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-150">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="ec449-151">Il corpo dell'espressione di calcolo, qui indicato come `{| cexpr |}`, viene convertito nelle chiamate che includono i metodi della classe del generatore dalle conversioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ec449-151">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="ec449-152">L'espressione di calcolo `{| cexpr |}` viene definito in modo ricorsivo in base a queste conversioni in cui `expr` è un'espressione F # e `cexpr` è un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-152">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="ec449-153">Espressione</span><span class="sxs-lookup"><span data-stu-id="ec449-153">Expression</span></span>|<span data-ttu-id="ec449-154">Conversione</span><span class="sxs-lookup"><span data-stu-id="ec449-154">Translation</span></span>|
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
<span data-ttu-id="ec449-155">Nella tabella precedente, `other-expr` descrive un'espressione che non è elencata nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ec449-155">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="ec449-156">Una classe del generatore non è necessario implementare tutti i metodi e supporta tutte le traduzioni elencate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="ec449-156">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="ec449-157">Tali costrutti che non sono implementati non sono disponibili nelle espressioni di calcolo di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="ec449-157">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="ec449-158">Ad esempio, se non si desidera supportare la `use` (parola chiave) nelle espressioni di calcolo, è possibile omettere la definizione di `Use` nella classe del generatore.</span><span class="sxs-lookup"><span data-stu-id="ec449-158">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="ec449-159">Esempio di codice seguente è illustrata un'espressione di calcolo che incapsula un calcolo di una serie di passaggi che possono essere valutate una sola operazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="ec449-159">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="ec449-160">Unioni di un tipo di unione `OkOrException`, codifica lo stato di errore dell'espressione valutato fino a questo punto.</span><span class="sxs-lookup"><span data-stu-id="ec449-160">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="ec449-161">Questo codice illustra alcuni modelli tipici che è possibile utilizzare nelle espressioni di calcolo, ad esempio le implementazioni di boilerplate di alcuni metodi del generatore.</span><span class="sxs-lookup"><span data-stu-id="ec449-161">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="ec449-162">Un'espressione di calcolo è un tipo sottostante, che restituisce l'espressione.</span><span class="sxs-lookup"><span data-stu-id="ec449-162">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="ec449-163">Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito o può fornire un modo per eseguire l'iterazione con alcuni tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="ec449-163">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="ec449-164">Nell'esempio precedente, il tipo sottostante è **infine**.</span><span class="sxs-lookup"><span data-stu-id="ec449-164">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="ec449-165">Per un'espressione di sequenza, il tipo sottostante è <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec449-165">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ec449-166">Per un'espressione di query, il tipo sottostante è <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec449-166">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ec449-167">Per un flusso di lavoro asincrono, il tipo sottostante è [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="ec449-167">For an asychronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="ec449-168">Il `Async` oggetto rappresenta il lavoro da eseguire per calcolare il risultato.</span><span class="sxs-lookup"><span data-stu-id="ec449-168">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="ec449-169">Ad esempio, si chiama [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un calcolo e restituire il risultato.</span><span class="sxs-lookup"><span data-stu-id="ec449-169">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="ec449-170">Operazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ec449-170">Custom Operations</span></span>
<span data-ttu-id="ec449-171">È possibile definire un'operazione personalizzata in un'espressione di calcolo e utilizzare un'operazione personalizzata di un operatore in un'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-171">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="ec449-172">Ad esempio, è possibile includere un operatore di query in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="ec449-172">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="ec449-173">Quando si definisce un'operazione personalizzata, è necessario definire il rendimento e i metodi dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-173">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="ec449-174">Per definire un'operazione personalizzata, inserirlo in una classe del generatore per l'espressione di calcolo e quindi applicare il [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="ec449-174">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="ec449-175">Questo attributo accetta una stringa come argomento, ovvero il nome da utilizzare in un'operazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ec449-175">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="ec449-176">Questo nome viene fornito nell'ambito all'inizio di una parentesi graffa dell'espressione di calcolo.</span><span class="sxs-lookup"><span data-stu-id="ec449-176">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="ec449-177">Pertanto, è consigliabile utilizzare identificatori che hanno lo stesso nome di un'operazione personalizzata in questo blocco.</span><span class="sxs-lookup"><span data-stu-id="ec449-177">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="ec449-178">Ad esempio, evitare l'utilizzo di identificatori, ad esempio `all` o `last` nelle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="ec449-178">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec449-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec449-179">See Also</span></span>
[<span data-ttu-id="ec449-180">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ec449-180">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ec449-181">Flussi di lavoro asincroni</span><span class="sxs-lookup"><span data-stu-id="ec449-181">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="ec449-182">Sequenze</span><span class="sxs-lookup"><span data-stu-id="ec449-182">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="ec449-183">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="ec449-183">Query Expressions</span></span>](query-expressions.md)
