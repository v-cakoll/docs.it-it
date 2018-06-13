---
title: Espressioni di calcolo (F#)
description: 'Informazioni su come creare una semplice sintassi per la scrittura di calcoli in F # che possono essere ordinati in sequenza e combinati con i costrutti del flusso di controllo e le associazioni.'
ms.date: 05/16/2016
ms.openlocfilehash: a4ddb3fde284452bc901c5270551611e43742c1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566613"
---
# <a name="computation-expressions"></a>Espressioni di calcolo

Espressioni di calcolo in F # forniscono una sintassi efficiente per la scrittura di calcoli che possono essere ordinati in sequenza e combinati con i costrutti del flusso di controllo e le associazioni. Possono essere utilizzati per fornire una sintassi efficiente per *Monad*, una funzionalità di programmazione funzionale che può essere utilizzata per gestire i dati, controllo e gli effetti collaterali nei programmi funzionali.


## <a name="built-in-workflows"></a>Flussi di lavoro predefiniti
Le espressioni di sequenza sono un esempio di un'espressione di calcolo, come flussi di lavoro asincroni e le espressioni di query. Per ulteriori informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di Query](query-expressions.md).

Alcune funzionalità sono comuni a entrambe le espressioni di sequenza e flussi di lavoro asincroni e viene illustrata la sintassi di base per un'espressione di calcolo:

```fsharp
builder-name { expression }
```

La sintassi precedente specifica che l'espressione specificata è un'espressione di calcolo di un tipo specificato dal *nome generatore*. L'espressione di calcolo può essere un flusso di lavoro predefinito, ad esempio `seq` o `async`, oppure può essere un elemento è definito. Il *nome generatore* è l'identificatore per un'istanza di un tipo speciale noto come il *tipo generatore*. Il tipo di generatore è un tipo di classe che definisce i metodi speciali che controllano il modo in cui che i frammenti dell'espressione di calcolo vengono combinati, ovvero codice che determina la modalità di esecuzione l'espressione. Un altro modo per descrivere una classe del generatore è ad esempio che consente di personalizzare il funzionamento di molti costrutti F #, ad esempio cicli e associazioni.

Nelle espressioni di calcolo, due forme sono disponibili per alcuni costrutti di linguaggio comuni. È possibile richiamare i costrutti variant utilizzando un! (punto esclamativo) suffisso in determinate parole chiave, ad esempio `let!`, `do!`e così via. Questi moduli speciali che alcune funzioni definite nella classe del generatore per sostituire il normale comportamento predefinito di queste operazioni. Questi moduli sono simili al `yield!` costituito il `yield` parola chiave utilizzata nelle espressioni di sequenza. Per ulteriori informazioni, vedere [sequenze](sequences.md).


## <a name="creating-a-new-type-of-computation-expression"></a>Creare un nuovo tipo di espressione di calcolo
Creazione di una classe del generatore e definendo determinati metodi speciali sulla classe, è possibile definire le caratteristiche di espressioni di calcolo. La classe del generatore può facoltativamente definire i metodi elencati nella tabella seguente.

Nella tabella seguente vengono descritti i metodi che possono essere utilizzati in una classe del generatore del flusso di lavoro.


|**Metodo**|**Firma tipica**|**Descrizione**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Chiamato per `let!` e `do!` nelle espressioni di calcolo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Esegue il wrapping di un'espressione di calcolo come una funzione.|
|`Return`|`'T -> M<'T>`|Chiamato per `return` nelle espressioni di calcolo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Chiamato per `return!` nelle espressioni di calcolo.|
|`Run`|`M<'T> -> M<'T>` oppure<br /><br />`M<'T> -> 'T`|Esegue un'espressione di calcolo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oppure<br /><br />`M<unit> * M<'T> -> M<'T>`|Chiamato per la sequenziazione nelle espressioni di calcolo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Chiamato per `for...do` espressioni nelle espressioni di calcolo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Chiamato per `try...finally` espressioni nelle espressioni di calcolo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Chiamato per `try...with` espressioni nelle espressioni di calcolo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Chiamato per `use` associazioni nelle espressioni di calcolo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Chiamato per `while...do` espressioni nelle espressioni di calcolo.|
|`Yield`|`'T -> M<'T>`|Chiamato per `yield` espressioni nelle espressioni di calcolo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Chiamato per `yield!` espressioni nelle espressioni di calcolo.|
|`Zero`|`unit -> M<'T>`|Chiamato per vuoto `else` rami di `if...then` espressioni nelle espressioni di calcolo.|
Molti dei metodi in una classe generatore utilizzano e restituire un `M<'T>` costrutto, ovvero in genere un tipo definito separatamente che caratterizza il tipo di calcoli combinati, ad esempio, `Async<'T>` per flussi di lavoro asincroni e `Seq<'T>` per i flussi di lavoro di sequenza. Le firme di questi metodi affinché possano essere combinate e annidati tra loro, in modo che l'oggetto del flusso di lavoro restituito da un costrutto può essere passato a quella successiva. Il compilatore, quando si analizza un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione nidificata utilizzando i metodi nella tabella precedente e il codice nell'espressione di calcolo.

L'espressione nidificata è nel formato seguente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Nel codice precedente, le chiamate a `Run` e `Delay` vengono omessi se non sono definiti nella classe del generatore di espressioni di calcolo. Il corpo dell'espressione di calcolo, qui indicato come `{| cexpr |}`, viene convertito nelle chiamate che includono i metodi della classe del generatore dalle conversioni descritte nella tabella seguente. L'espressione di calcolo `{| cexpr |}` viene definito in modo ricorsivo in base a queste conversioni in cui `expr` è un'espressione F # e `cexpr` è un'espressione di calcolo.



|Espressione|Conversione|
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
Nella tabella precedente, `other-expr` descrive un'espressione che non è elencata nella tabella. Una classe del generatore non è necessario implementare tutti i metodi e supporta tutte le traduzioni elencate nella tabella precedente. Tali costrutti che non sono implementati non sono disponibili nelle espressioni di calcolo di quel tipo. Ad esempio, se non si desidera supportare la `use` (parola chiave) nelle espressioni di calcolo, è possibile omettere la definizione di `Use` nella classe del generatore.

Esempio di codice seguente è illustrata un'espressione di calcolo che incapsula un calcolo di una serie di passaggi che possono essere valutate una sola operazione alla volta. Unioni di un tipo di unione `OkOrException`, codifica lo stato di errore dell'espressione valutato fino a questo punto. Questo codice illustra alcuni modelli tipici che è possibile utilizzare nelle espressioni di calcolo, ad esempio le implementazioni di boilerplate di alcuni metodi del generatore.

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

Un'espressione di calcolo è un tipo sottostante, che restituisce l'espressione. Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito o può fornire un modo per eseguire l'iterazione con alcuni tipi di raccolta. Nell'esempio precedente, il tipo sottostante è **infine**. Per un'espressione di sequenza, il tipo sottostante è <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Per un'espressione di query, il tipo sottostante è <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Per un flusso di lavoro asincrono, il tipo sottostante è [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). Il `Async` oggetto rappresenta il lavoro da eseguire per calcolare il risultato. Ad esempio, si chiama [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un calcolo e restituire il risultato.

## <a name="custom-operations"></a>Operazioni personalizzate
È possibile definire un'operazione personalizzata in un'espressione di calcolo e utilizzare un'operazione personalizzata di un operatore in un'espressione di calcolo. Ad esempio, è possibile includere un operatore di query in un'espressione di query. Quando si definisce un'operazione personalizzata, è necessario definire il rendimento e i metodi dell'espressione di calcolo. Per definire un'operazione personalizzata, inserirlo in una classe del generatore per l'espressione di calcolo e quindi applicare il [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Questo attributo accetta una stringa come argomento, ovvero il nome da utilizzare in un'operazione personalizzata. Questo nome viene fornito nell'ambito all'inizio di una parentesi graffa dell'espressione di calcolo. Pertanto, è consigliabile utilizzare identificatori che hanno lo stesso nome di un'operazione personalizzata in questo blocco. Ad esempio, evitare l'utilizzo di identificatori, ad esempio `all` o `last` nelle espressioni di query.

## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Flussi di lavoro asincroni](asynchronous-workflows.md)

[Sequenze](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[Espressioni di query](query-expressions.md)
