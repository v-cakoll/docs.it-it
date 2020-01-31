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
# <a name="computation-expressions"></a>Espressioni di calcolo

Le espressioni di F# calcolo in forniscono una sintassi pratica per la scrittura di calcoli che possono essere sequenziati e combinati mediante costrutti e associazioni del flusso di controllo. A seconda del tipo di espressione di calcolo, possono essere considerati come un modo per esprimere monadi, monoids, i trasformatori Monad e funtori applicativi. Tuttavia, a differenza di altri linguaggi (ad esempio *do-Notation* in Haskell), non sono collegati a un'unica astrazione e non si basano su macro o altre forme di metaprogrammazione per realizzare una sintassi pratica e sensibile al contesto.

## <a name="overview"></a>Panoramica di

I calcoli possono assumere molte forme. Il tipo di calcolo più comune è l'esecuzione a thread singolo, che è facile da comprendere e modificare. Tuttavia, non tutte le forme di calcolo sono semplici come l'esecuzione a thread singolo. Alcuni esempi includono:

- Calcoli non deterministici
- Calcoli asincroni
- Calcoli effettivi
- Calcoli generativi

Più in generale, esistono calcoli *sensibili al contesto* che è necessario eseguire in determinate parti di un'applicazione. La scrittura di codice sensibile al contesto può essere complessa, in quanto è facile "perdere" i calcoli all'esterno di un determinato contesto senza astrazioni per impedire l'esecuzione di questa operazione. Queste astrazioni sono spesso difficili da scrivere autonomamente, motivo F# per cui ha un metodo generalizzato per eseguire queste operazioni, denominate espressioni di **calcolo**.

Le espressioni di calcolo offrono una sintassi uniforme e un modello di astrazione per la codifica di calcoli sensibili al contesto.

Ogni espressione di calcolo è supportata da un tipo di *Generatore* . Il tipo di generatore definisce le operazioni disponibili per l'espressione di calcolo. Vedere [creazione di un nuovo tipo di espressione di calcolo](computation-expressions.md#creating-a-new-type-of-computation-expression), che Mostra come creare un'espressione di calcolo personalizzata.

### <a name="syntax-overview"></a>Cenni preliminari sulla sintassi

Tutte le espressioni di calcolo hanno il formato seguente:

```fsharp
builder-expr { cexper }
```

dove `builder-expr` è il nome di un tipo di generatore che definisce l'espressione di calcolo e `cexper` è il corpo dell'espressione dell'espressione di calcolo. `async` codice dell'espressione di calcolo, ad esempio, può essere simile al seguente:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

All'interno di un'espressione di calcolo è disponibile una speciale sintassi aggiuntiva, come illustrato nell'esempio precedente. Con le espressioni di calcolo sono possibili i form di espressione seguenti:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Ognuna di queste parole chiave e altre parole F# chiave standard sono disponibili in un'espressione di calcolo solo se sono state definite nel tipo di generatore di backup. L'unica eccezione è `match!`, ovvero lo zucchero sintattico per l'uso di `let!` seguito da una corrispondenza di criteri nel risultato.

Il tipo di generatore è un oggetto che definisce metodi speciali che governano il modo in cui vengono combinati i frammenti dell'espressione di calcolo. ovvero, i metodi controllano il comportamento dell'espressione di calcolo. Un altro modo per descrivere una classe del generatore consiste nel dire che consente di personalizzare l'operazione di molti F# costrutti, ad esempio cicli e associazioni.

### `let!`

La parola chiave `let!` associa il risultato di una chiamata a un'altra espressione di calcolo a un nome:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Se si associa la chiamata a un'espressione di calcolo con `let`, non sarà possibile ottenere il risultato dell'espressione di calcolo. Al contrario, sarà necessario associare il valore della chiamata non *realizzata* a tale espressione di calcolo. Utilizzare `let!` per eseguire l'associazione al risultato.

`let!` viene definito dal membro `Bind(x, f)` sul tipo di generatore.

### `do!`

La parola chiave `do!` è per chiamare un'espressione di calcolo che restituisce un tipo simile a `unit`(definito dal membro `Zero` nel generatore):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Per il [flusso di lavoro asincrono](asynchronous-workflows.md), questo tipo è `Async<unit>`. Per altre espressioni di calcolo, è probabile che il tipo sia `CExpType<unit>`.

`do!` viene definito dal membro `Bind(x, f)` sul tipo di generatore, in cui `f` genera un `unit`.

### `yield`

La parola chiave `yield` è per restituire un valore dall'espressione di calcolo in modo che possa essere utilizzata come <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Nella maggior parte dei casi, può essere omesso dai chiamanti. Il modo più comune per omettere `yield` è con l'operatore `->`:

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

Per espressioni più complesse che potrebbero restituire molti valori diversi e, forse, in modo condizionale, la semplice omissione della parola chiave può eseguire le operazioni seguenti:

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

Come per la [parola chiave yield C#in ](../../csharp/language-reference/keywords/yield.md), ogni elemento nell'espressione di calcolo viene restituito mentre viene iterato.

`yield` viene definito dal membro `Yield(x)` sul tipo di generatore, dove `x` è l'elemento da restituire.

### `yield!`

La parola chiave `yield!` è per rendere flat una raccolta di valori da un'espressione di calcolo:

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

Quando viene valutato, l'espressione di calcolo chiamata da `yield!` avrà gli elementi restituiti uno alla volta, rendendo flat il risultato.

`yield!` viene definito dal membro `YieldFrom(x)` sul tipo di generatore, dove `x` è una raccolta di valori.

Diversamente da `yield`, `yield!` necessario specificare in modo esplicito. Il suo comportamento non è implicito nelle espressioni di calcolo.

### `return`

La parola chiave `return` esegue il wrapping di un valore nel tipo corrispondente all'espressione di calcolo. A parte le espressioni di calcolo con `yield`, viene usato per "completare" un'espressione di calcolo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` viene definito dal membro `Return(x)` sul tipo di generatore, dove `x` è l'elemento di cui eseguire il wrapping.

### `return!`

La parola chiave `return!` rende conto del valore di un'espressione di calcolo ed esegue il wrapping del risultato nel tipo corrispondente all'espressione di calcolo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` viene definito dal membro `ReturnFrom(x)` sul tipo di generatore, dove `x` è un'altra espressione di calcolo.

### `match!`

La parola chiave `match!` consente di inline una chiamata a un'altra espressione di calcolo e il criterio di ricerca corrisponde al risultato:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Quando si chiama un'espressione di calcolo con `match!`, realizzerà il risultato della chiamata, ad esempio `let!`. Questa operazione viene spesso utilizzata quando si chiama un'espressione di calcolo in cui il risultato è [facoltativo](options.md).

## <a name="built-in-computation-expressions"></a>Espressioni di calcolo predefinite

La F# libreria principale definisce tre espressioni di calcolo predefinite: [espressioni di sequenza](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md)ed [espressioni di query](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Creazione di un nuovo tipo di espressione di calcolo

È possibile definire le caratteristiche delle proprie espressioni di calcolo creando una classe del generatore e definendo determinati metodi speciali sulla classe. La classe Builder può facoltativamente definire i metodi elencati nella tabella seguente.

Nella tabella seguente vengono descritti i metodi che possono essere utilizzati in una classe del generatore di flussi di lavoro.

|**Metodo**|**Firme tipiche**|**Descrizione**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Chiamato per `let!` e `do!` nelle espressioni di calcolo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Esegue il wrapping di un'espressione di calcolo come funzione.|
|`Return`|`'T -> M<'T>`|Chiamato per `return` nelle espressioni di calcolo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Chiamato per `return!` nelle espressioni di calcolo.|
|`Run`|`M<'T> -> M<'T>` oppure<br /><br />`M<'T> -> 'T`|Esegue un'espressione di calcolo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oppure<br /><br />`M<unit> * M<'T> -> M<'T>`|Chiamato per la sequenziazione nelle espressioni di calcolo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Chiamato per `for...do` espressioni nelle espressioni di calcolo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Chiamato per `try...finally` espressioni nelle espressioni di calcolo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Chiamato per `try...with` espressioni nelle espressioni di calcolo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Chiamato per `use` associazioni nelle espressioni di calcolo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Chiamato per `while...do` espressioni nelle espressioni di calcolo.|
|`Yield`|`'T -> M<'T>`|Chiamato per `yield` espressioni nelle espressioni di calcolo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Chiamato per `yield!` espressioni nelle espressioni di calcolo.|
|`Zero`|`unit -> M<'T>`|Chiamato per `else` rami vuoti delle espressioni `if...then` nelle espressioni di calcolo.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Indica che l'espressione di calcolo viene passata al membro `Run` come virgoletta. Converte tutte le istanze di un calcolo in una virgoletta.|

Molti dei metodi di una classe Builder utilizzano e restituiscono un costrutto di `M<'T>`, che in genere è un tipo definito separatamente che caratterizza il tipo di calcoli combinati, ad esempio `Async<'T>` per i flussi di lavoro asincroni e `Seq<'T>` per i flussi di lavoro di sequenza. Le firme di questi metodi consentono di combinarle e nidificarle tra loro, in modo che l'oggetto flusso di lavoro restituito da un costrutto possa essere passato a quello successivo. Il compilatore, durante l'analisi di un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione annidate utilizzando i metodi della tabella precedente e il codice dell'espressione di calcolo.

Il formato dell'espressione annidata è il seguente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Nel codice precedente, le chiamate a `Run` e `Delay` vengono omesse se non sono definite nella classe del generatore di espressioni di calcolo. Il corpo dell'espressione di calcolo, qui indicato come `{| cexpr |}`, viene convertito in chiamate che coinvolgono i metodi della classe Builder dalle traduzioni descritte nella tabella seguente. L'espressione di calcolo `{| cexpr |}` viene definita in modo ricorsivo in base a queste traduzioni F# in cui `expr` è un'espressione e `cexpr` è un'espressione di calcolo.

|Espressione|Conversione|
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

Nella tabella precedente, `other-expr` descrive un'espressione che non è elencata diversamente nella tabella. Una classe Builder non deve implementare tutti i metodi e supportare tutte le traduzioni elencate nella tabella precedente. Questi costrutti non implementati non sono disponibili nelle espressioni di calcolo di quel tipo. Se, ad esempio, non si desidera supportare la parola chiave `use` nelle espressioni di calcolo, è possibile omettere la definizione di `Use` nella classe del generatore.

Nell'esempio di codice seguente viene illustrata un'espressione di calcolo che incapsula un calcolo come una serie di passaggi che possono essere valutati un passaggio alla volta. Un tipo di unione discriminata, `OkOrException`, codifica lo stato di errore dell'espressione come valutato finora. Questo codice illustra diversi modelli tipici che è possibile usare nelle espressioni di calcolo, ad esempio le implementazioni standard di alcuni metodi del generatore.

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

Un'espressione di calcolo ha un tipo sottostante, restituito dall'espressione. Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito oppure può fornire un modo per scorrere un tipo di raccolta. Nell'esempio precedente, il tipo sottostante era **alla fine**. Per un'espressione di sequenza, il tipo sottostante viene <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Per un'espressione di query, il tipo sottostante viene <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Per un flusso di lavoro asincrono, il tipo sottostante viene [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). L'oggetto `Async` rappresenta il lavoro da eseguire per calcolare il risultato. Ad esempio, si chiama [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un calcolo e restituire il risultato.

## <a name="custom-operations"></a>Operazioni personalizzate

È possibile definire un'operazione personalizzata su un'espressione di calcolo e utilizzare un'operazione personalizzata come operatore in un'espressione di calcolo. È ad esempio possibile includere un operatore di query in un'espressione di query. Quando si definisce un'operazione personalizzata, è necessario definire i metodi yield e for nell'espressione di calcolo. Per definire un'operazione personalizzata, inserirla in una classe di generatore per l'espressione di calcolo, quindi applicare la [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Questo attributo accetta una stringa come argomento, che è il nome da usare in un'operazione personalizzata. Questo nome entra nell'ambito all'inizio della parentesi graffa di apertura dell'espressione di calcolo. Pertanto, non è consigliabile utilizzare identificatori con lo stesso nome di un'operazione personalizzata in questo blocco. Ad esempio, evitare l'utilizzo di identificatori come `all` o `last` nelle espressioni di query.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Estensione di generatori esistenti con nuove operazioni personalizzate

Se si dispone già di una classe Builder, le operazioni personalizzate possono essere estese dall'esterno di questa classe del generatore. Le estensioni devono essere dichiarate nei moduli. Gli spazi dei nomi non possono contenere membri di estensione eccetto nello stesso file e nello stesso gruppo di dichiarazioni dello spazio dei nomi in cui è definito il tipo.

Nell'esempio seguente viene illustrata l'estensione della classe `Microsoft.FSharp.Linq.QueryBuilder` esistente.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Flussi di lavoro asincroni](asynchronous-workflows.md)
- [Sequenze](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Espressioni di query](query-expressions.md)
