---
title: Espressioni di calcolo
description: Informazioni su come creare una sintassi comoda per la scrittura di calcoli in F , che possono essere sequenziati e combinati usando costrutti e associazioni del flusso di controllo.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400232"
---
# <a name="computation-expressions"></a>Espressioni di calcolo

Le espressioni di calcolo in F, forniscono una sintassi comoda per la scrittura di calcoli che possono essere sequenziati e combinati usando costrutti e associazioni del flusso di controllo. A seconda del tipo di espressione di calcolo, possono essere pensati come un modo per esprimere monadi, monoidi, trasformatori di monade e funtori applicativi. Tuttavia, a differenza di altri linguaggi (come la *notazione do* in Haskell), non sono legati a una singola astrazione e non si basano su macro o altre forme di metaprogrammazione per realizzare una sintassi conveniente e sensibile al contesto.

## <a name="overview"></a>Panoramica

I calcoli possono assumere molte forme. La forma più comune di calcolo è l'esecuzione a thread singolo, che è facile da comprendere e modificare. Tuttavia, non tutte le forme di calcolo sono semplici come l'esecuzione a thread singolo. Di seguito sono riportati alcuni esempi:

- Calcoli non deterministici
- Calcoli asincroni
- Calcoli efficaci
- Calcoli generativi

Più in generale, sono disponibili calcoli *sensibili al contesto* che è necessario eseguire in alcune parti di un'applicazione. La scrittura di codice sensibile al contesto può essere complessa, in quanto è facile "perdere" calcoli all'esterno di un determinato contesto senza astrazioni per impedire questa operazione. Queste astrazioni sono spesso difficili da scrivere da soli, motivo per cui F è un modo generalizzato per eseguire le cosiddette espressioni di **calcolo.**

Le espressioni di calcolo offrono un modello uniforme di sintassi e astrazione per la codifica dei calcoli sensibili al contesto.

Ogni espressione di calcolo è supportata da un tipo di *generatore.* Il tipo di generatore definisce le operazioni disponibili per l'espressione di calcolo. Vedere [Creazione di un nuovo tipo di espressione di calcolo](computation-expressions.md#creating-a-new-type-of-computation-expression), che illustra come creare un'espressione di calcolo personalizzata.

### <a name="syntax-overview"></a>Panoramica della sintassi

Tutte le espressioni di calcolo hanno la forma seguente:All computation expressions have the following form:

```fsharp
builder-expr { cexper }
```

dove `builder-expr` è il nome di un tipo di `cexper` generatore che definisce l'espressione di calcolo ed è il corpo dell'espressione di calcolo. Ad esempio, il codice dell'espressione di calcolo può essere simile al seguente:For example, `async` computation expression code can look like this:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

All'interno di un'espressione di calcolo è disponibile una sintassi aggiuntiva speciale, come illustrato nell'esempio precedente. Le forme di espressione seguenti sono possibili con le espressioni di calcolo:The following expression forms are possible with computation expressions:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Ognuna di queste parole chiave e altre parole chiave standard di F , sono disponibili solo in un'espressione di calcolo se sono stati definiti nel tipo di generatore di backup. L'unica eccezione `match!`a questo è , che `let!` è a sua volta zucchero sintattico per l'uso di seguito da una corrispondenza di modello sul risultato.

Il tipo di generatore è un oggetto che definisce metodi speciali che regolano il modo in cui i frammenti dell'espressione di calcolo vengono combinati; vale a dire, i relativi metodi controllano il modo in cui si comporta l'espressione di calcolo. Un altro modo per descrivere una classe del generatore consiste nel dire che consente di personalizzare il funzionamento di molti costrutti F , ad esempio cicli e associazioni.

### `let!`

La `let!` parola chiave associa il risultato di una chiamata a un'altra espressione di calcolo a un nome:The keyword binds the result of a call to another computation expression to a name:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Se si associa la chiamata `let`a un'espressione di calcolo con , non si otterrà il risultato dell'espressione di calcolo. Al contrario, sarà associato il valore della chiamata *non realizzata* a tale espressione di calcolo. Utilizzare `let!` per eseguire l'associazione al risultato.

`let!`è definito `Bind(x, f)` dal membro nel tipo di generatore.

### `do!`

La `do!` parola chiave è per chiamare `unit`un'espressione di `Zero` calcolo che restituisce un tipo -like (definito dal membro nel generatore):The keyword is for calling a computation expression that returns a -like type (defined by the member on the builder):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Per il flusso di `Async<unit>`lavoro [asincrono,](asynchronous-workflows.md)questo tipo è . Per altre espressioni di calcolo, `CExpType<unit>`è probabile che il tipo sia .

`do!`è definito `Bind(x, f)` dal membro nel tipo `f` di `unit`generatore, dove produce un oggetto .

### `yield`

La `yield` parola chiave è per la restituzione di un valore <xref:System.Collections.Generic.IEnumerable%601>dall'espressione di calcolo in modo che possa essere utilizzata come:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Nella maggior parte dei casi, può essere omesso dai chiamanti. Il modo più comune `yield` per omettere è con l'operatore: `->`

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

Per le espressioni più complesse che potrebbero produrre molti valori diversi e, forse in modo condizionale, è possibile omettere semplicemente la parola chiave:For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:

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

Come con la [parola chiave yield in C,](../../csharp/language-reference/keywords/yield.md)ogni elemento nell'espressione di calcolo viene restituito durante l'iterazione.

`yield`è definito `Yield(x)` dal membro nel tipo `x` di generatore, dove è l'elemento da restituire.

### `yield!`

La `yield!` parola chiave è per appiattire una raccolta di valori da un'espressione di calcolo:The keyword is for flattening a collection of values from a computation expression:

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

Quando viene valutata, `yield!` l'espressione di calcolo chiamata da avrà i relativi elementi restituiti uno per uno, appiattindo il risultato.

`yield!`è definito `YieldFrom(x)` dal membro nel tipo `x` di generatore, dove è una raccolta di valori.

A `yield` `yield!` differenza di , deve essere specificato in modo esplicito. Il comportamento non è implicito nelle espressioni di calcolo.

### `return`

La `return` parola chiave esegue il wrapping di un valore nel tipo corrispondente all'espressione di calcolo. Oltre alle espressioni `yield`di calcolo che utilizzano , viene utilizzato per "completare" un'espressione di calcolo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return`è definito `Return(x)` dal membro nel tipo `x` di generatore, dove è l'elemento di cui eseguire il wrapping.

### `return!`

La `return!` parola chiave realizza il valore di un'espressione di calcolo ed esegue il wrapping del tipo corrispondente all'espressione di calcolo:The keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!`è definito `ReturnFrom(x)` dal membro nel tipo `x` di generatore, dove è un'altra espressione di calcolo.

### `match!`

La `match!` parola chiave consente di inline una chiamata a un'altra espressione di calcolo e la corrispondenza del modello sul risultato:The keyword allows you to inline a call to another computation expression and pattern match on its result:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Quando si chiama `match!`un'espressione di calcolo con `let!`, verrà realizzato il risultato della chiamata come . Viene spesso utilizzato quando si chiama un'espressione di calcolo in cui il risultato è [facoltativo.](options.md)

## <a name="built-in-computation-expressions"></a>Espressioni di calcolo incorporate

La libreria di base di F , definisce tre espressioni di calcolo incorporate: Espressioni di [sequenza](sequences.md), [Flussi di lavoro asincroni](asynchronous-workflows.md)ed [Espressioni di query](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Creazione di un nuovo tipo di espressione di calcoloCreating a New Type of Computation Expression

È possibile definire le caratteristiche delle proprie espressioni di calcolo creando una classe builder e definendo determinati metodi speciali sulla classe. La classe del generatore può facoltativamente definire i metodi elencati nella tabella seguente.

Nella tabella seguente vengono descritti i metodi che possono essere utilizzati in una classe del generatore di flussi di lavoro.

|**Metodo**|**Firma(e) tipica**|**Descrizione**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Chiamato `let!` e `do!` nelle espressioni di calcolo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Esegue il wrapping di un'espressione di calcolo come funzione.|
|`Return`|`'T -> M<'T>`|Chiamato `return` nelle espressioni di calcolo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Chiamato `return!` nelle espressioni di calcolo.|
|`Run`|`M<'T> -> M<'T>` oppure<br /><br />`M<'T> -> 'T`|Esegue un'espressione di calcolo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oppure<br /><br />`M<unit> * M<'T> -> M<'T>`|Chiamato per la sequenza nelle espressioni di calcolo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Chiamato `for...do` per le espressioni nelle espressioni di calcolo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Chiamato `try...finally` per le espressioni nelle espressioni di calcolo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Chiamato `try...with` per le espressioni nelle espressioni di calcolo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Chiamato `use` per le associazioni nelle espressioni di calcolo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Chiamato `while...do` per le espressioni nelle espressioni di calcolo.|
|`Yield`|`'T -> M<'T>`|Chiamato `yield` per le espressioni nelle espressioni di calcolo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Chiamato `yield!` per le espressioni nelle espressioni di calcolo.|
|`Zero`|`unit -> M<'T>`|Chiamato per `else` rami `if...then` vuoti di espressioni nelle espressioni di calcolo.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Indica che l'espressione di `Run` calcolo viene passata al membro come citazione. Converte tutte le istanze di un calcolo in una citazione.|

Molti dei metodi in una classe `M<'T>` del generatore utilizzano e restituiscono un costrutto, che in genere `Async<'T>` è un `Seq<'T>` tipo definito separatamente che caratterizza il tipo di calcoli combinati, ad esempio, per i flussi di lavoro asincroni e per i flussi di lavoro di sequenza. Le firme di questi metodi consentono di combinarle e annidate tra loro, in modo che l'oggetto flusso di lavoro restituito da un costrutto possa essere passato al successivo. Il compilatore, quando analizza un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione annidate utilizzando i metodi nella tabella precedente e il codice nell'espressione di calcolo.

L'espressione nidificata è del formato seguente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Nel codice precedente, le `Run` `Delay` chiamate a e vengono omesse se non sono definite nella classe del generatore di espressioni di calcolo. Il corpo dell'espressione di calcolo, qui indicato come `{| cexpr |}`, viene convertito in chiamate che coinvolgono i metodi della classe builder dalle traduzioni descritte nella tabella seguente. L'espressione `{| cexpr |}` di calcolo viene definita in modo `expr` ricorsivo in `cexpr` base a queste traduzioni, in cui è un'espressione F , ed è un'espressione di calcolo.

|Expression|Traduzione|
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

Nella tabella precedente `other-expr` viene descritta un'espressione che non è altrimenti elencata nella tabella. Non è necessario che una classe builder implementi tutti i metodi e supporti tutte le traduzioni elencate nella tabella precedente. I costrutti non implementati non sono disponibili nelle espressioni di calcolo di quel tipo. Ad esempio, se non si `use` desidera supportare la parola chiave nelle espressioni `Use` di calcolo, è possibile omettere la definizione di nella classe del generatore.

Nell'esempio di codice seguente viene illustrata un'espressione di calcolo che incapsula un calcolo come una serie di passaggi che possono essere valutati un passaggio alla volta. Un tipo di `OkOrException`unione discriminato, , codifica lo stato di errore dell'espressione come valutato finora. Questo codice illustra diversi modelli tipici che è possibile usare nelle espressioni di calcolo, ad esempio le implementazioni boilerplate di alcuni dei metodi di costruzione.

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

Un'espressione di calcolo ha un tipo sottostante, che l'espressione restituisce. Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito oppure può fornire un modo per scorrere un tipo di raccolta. Nell'esempio precedente, il tipo sottostante era **Eventually**. Per un'espressione di sequenza, il tipo sottostante è <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Per un'espressione di query, il tipo sottostante è <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Per un flusso di lavoro [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)asincrono, il tipo sottostante è . L'oggetto `Async` rappresenta il lavoro da eseguire per calcolare il risultato. Ad esempio, [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) si chiama per eseguire un calcolo e restituire il risultato.

## <a name="custom-operations"></a>Operazioni personalizzate

È possibile definire un'operazione personalizzata in un'espressione di calcolo e usare un'operazione personalizzata come operatore in un'espressione di calcolo. Ad esempio, è possibile includere un operatore di query in un'espressione di query. Quando si definisce un'operazione personalizzata, è necessario definire i metodi Yield e For nell'espressione di calcolo. Per definire un'operazione personalizzata, inserirla in una [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)classe del generatore per l'espressione di calcolo, quindi applicare l'opzione . Questo attributo accetta una stringa come argomento, ovvero il nome da utilizzare in un'operazione personalizzata. Questo nome viene inserito nell'ambito all'inizio della parentesi graffa di apertura dell'espressione di calcolo. Pertanto, è consigliabile non utilizzare identificatori che hanno lo stesso nome di un'operazione personalizzata in questo blocco. Ad esempio, evitare l'uso `all` `last` di identificatori come o nelle espressioni di query.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Estensione dei costruttori esistenti con le nuove operazioni personalizzateExtending existing Builders with new Custom Operations

Se si dispone già di una classe builder, le relative operazioni personalizzate possono essere estese dall'esterno di questa classe del generatore. Le estensioni devono essere dichiarate nei moduli. Gli spazi dei nomi non possono contenere membri di estensione tranne che nello stesso file e nello stesso gruppo di dichiarazioni dello spazio dei nomi in cui è definito il tipo.

Nell'esempio seguente viene illustrata l'estensione della classe esistente. `Microsoft.FSharp.Linq.QueryBuilder`

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Vedere anche

- [Guida di riferimento al linguaggio F](index.md)
- [Flussi di lavoro asincroni](asynchronous-workflows.md)
- [Sequenze](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Espressioni di queryQuery Expressions](query-expressions.md)
