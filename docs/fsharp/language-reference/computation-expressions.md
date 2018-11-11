---
title: Espressioni di calcolo (F#)
description: Informazioni su come creare una sintassi efficiente per la scrittura di calcoli in F# che possa essere sequenziata e combinati tramite costrutti del flusso di controllo e associazioni.
ms.date: 07/27/2018
ms.openlocfilehash: 148d1a661fb7630782c6dc48507a66e7bdc1d56b
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "48839869"
---
# <a name="computation-expressions"></a>Espressioni di calcolo

Le espressioni di calcolo in F# forniscono una sintassi efficiente per la scrittura di calcoli che possono essere sequenziati e combinati tramite costrutti del flusso di controllo e associazioni. A seconda del tipo dell'espressione di calcolo, è possibile pensare come un modo per esprimere monads, monoids, trasformatori monad e funtori applicative. Tuttavia, a differenza di altri linguaggi (ad esempio *in notazione* in Haskell), non sono associate a una singola astrazione e non fare affidamento su macro o altre forme di metaprogrammazione per eseguire una sintassi pratica e sensibile al contesto.

## <a name="overview"></a>Panoramica

I calcoli possono assumere molte forme. La forma più comune di calcolo è l'esecuzione a thread singolo, che è facile da comprendere e modificare. Tuttavia, non tutte le forme di calcolo sono semplice come l'esecuzione a thread singolo. Di seguito sono riportati alcuni esempi:

* Calcoli non deterministiche
* Calcoli asincroni
* Calcoli effectful
* Calcoli propria

Più in generale, esistono *sensibile al contesto* i calcoli che è necessario eseguire in determinate parti di un'applicazione. Scrittura di codice sensibile al contesto può essere problematico, in quanto è facile per i calcoli "perdite" di fuori di un determinato contesto senza astrazioni per impedire questa operazione. Queste astrazioni sono spesso difficili da scrivere da soli, motivo per cui F# offre un modo generalizzato per eseguire cosiddette **espressioni di calcolo**.

Le espressioni di calcolo offrono un modello di sintassi e astrazione uniforme per la codifica dei calcoli sensibile al contesto.

Ogni espressione di calcolo è supportata da un *generatore* tipo. Il tipo di generatore definisce le operazioni disponibili per l'espressione di calcolo. Visualizzare [creando un nuovo tipo di espressione di calcolo](computation-expressions.md#creating-a-new-type-of-computation-expression), che mostra come creare un'espressione di calcolo personalizzato.

### <a name="syntax-overview"></a>Panoramica della sintassi

Tutte le espressioni di calcolo disponibili nel formato seguente:

```
builder-expr { cexper }
```

in cui `builder-expr` è il nome di un tipo di generatore che definisce l'espressione di calcolo e `cexper` corrisponde al corpo di espressione dell'espressione di calcolo. Ad esempio, `async` codice di espressione di calcolo simile al seguente:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

È una sintassi speciale, aggiuntiva disponibile all'interno di un'espressione di calcolo, come illustrato nell'esempio precedente. Le forme di espressioni seguenti sono possibili con le espressioni di calcolo:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Ognuna di queste parole chiave e altri standard F# le parole chiave sono disponibili solo in un'espressione di calcolo se sono stati definiti nel tipo di generatore di backup. È l'unica eccezione a questa `match!`, che è a sua volta zucchero sintattico per l'uso di `let!` seguita da un criterio di ricerca sul risultato.

Il tipo di generatore è un oggetto che definisce i metodi speciali che controllano il modo in cui che vengono combinati i frammenti dell'espressione di calcolo; vale a dire i relativi metodi controllano il comportamento di espressione di calcolo. Un altro modo per descrivere una classe del generatore è dire che permette di personalizzare il funzionamento di molti costrutti F#, ad esempio cicli e associazioni.

### `let!`

Il `let!` parola chiave associa il risultato di una chiamata a un'altra espressione di calcolo a un nome:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Se si associa la chiamata a un'espressione di calcolo con `let`, non sarà possibile ottenere il risultato dell'espressione di calcolo. Al contrario, verrà associato il valore della *non realizzati* le chiamate a quell ' espressione di calcolo. Usare `let!` da associare al risultato.

`let!` è definito dal `Bind(x, f)` membro del tipo di generatore.

### `do!`

Il `do!` è la parola chiave per la chiamata di un'espressione di calcolo che restituisce un `unit`-come tipo (definito dal `Zero` membro sul generatore):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Per il [flusso di lavoro asincroni](asynchronous-workflows.md), questo tipo è `Async<unit>`. Per altre espressioni di calcolo, il tipo è probabilmente `CExpType<unit>`.

`do!` è definito dal `Bind(x, f)` membro del tipo di generatore, dove `f` produce un `unit`.

### `yield`

Il `yield` parola chiave sia per la restituzione di un valore dall'espressione di calcolo in modo che possa essere utilizzato come un <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Come con le [yield (parola chiave) in c#](../../csharp/language-reference/keywords/yield.md), ogni elemento nell'espressione di calcolo viene restituito perché viene scorsa.

`yield` è definito dal `Yield(x)` membro del tipo di generatore, in cui `x` è l'elemento per produrre nuovamente.

### `yield!`

Il `yield!` la parola chiave è per rendere flat una raccolta di valori da un'espressione di calcolo:

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

Durante la valutazione, l'espressione di calcolo denominato `yield!` verranno dispone i relativi elementi restituiti indietro uno alla volta, rendere flat il risultato.

`yield!` è definito dal `YieldFrom(x)` membro del tipo di generatore, in cui `x` è una raccolta di valori.

### `return`

Il `return` (parola chiave) esegue il wrapping di un valore di tipo corrispondente all'espressione di calcolo. A parte le espressioni di calcolo usando `yield`, viene utilizzato su "completa" di un'espressione di calcolo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` è definito per il `Return(x)` membro del tipo di generatore, in cui `x` è l'elemento di cui eseguire il wrapping.

### `return!`

Il `return!` (parola chiave) il valore di un'espressione di calcolo di realizzazione ed esegue il wrapping di tale risultato nel tipo corrispondente all'espressione di calcolo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` è definito per il `ReturnFrom(x)` membro del tipo di generatore, in cui `x` è un'altra espressione di calcolo.

### `match!`

A partire da F# 4.5, il `match!` parola chiave consente di rendere inline una chiamata a un altro calcolo corrispondenza di espressione e modello per il risultato:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Quando si chiama un'espressione di calcolo con `match!`, potrà trarre il risultato della chiamata, ad esempio `let!`. Viene spesso utilizzata quando si chiama un'espressione di calcolo in cui il risultato è un' [facoltativi](options.md).

## <a name="built-in-computation-expressions"></a>Espressioni di calcolo incorporato

Libreria di base F# definisce tre espressioni di calcolo predefinito: [espressioni di sequenza](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di Query](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Creare un nuovo tipo di espressione di calcolo

È possibile definire le caratteristiche delle proprie espressioni di calcolo tramite la creazione di una classe del generatore e la definizione di determinati metodi speciali sulla classe. La classe del generatore possibile definire i metodi elencati nella tabella seguente.

Nella tabella seguente vengono descritti i metodi che possono essere usati in una classe del generatore del flusso di lavoro.

|**Metodo**|**Firma tipica**|**Descrizione**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Chiamato per `let!` e `do!` nelle espressioni di calcolo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Esegue il wrapping di un'espressione di calcolo come una funzione.|
|`Return`|`'T -> M<'T>`|Chiamato per `return` nelle espressioni di calcolo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Chiamato per `return!` nelle espressioni di calcolo.|
|`Run`|`M<'T> -> M<'T>` oppure<br /><br />`M<'T> -> 'T`|Esegue un'espressione di calcolo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oppure<br /><br />`M<unit> * M<'T> -> M<'T>`|Chiamato per la sequenziazione in espressioni di calcolo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oppure<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Chiamato per `for...do` espressioni nelle espressioni di calcolo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Chiamato per `try...finally` espressioni nelle espressioni di calcolo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Chiamato per `try...with` espressioni nelle espressioni di calcolo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Chiamato per `use` associazioni nelle espressioni di calcolo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Chiamato per `while...do` espressioni nelle espressioni di calcolo.|
|`Yield`|`'T -> M<'T>`|Chiamato per `yield` espressioni nelle espressioni di calcolo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Chiamato per `yield!` espressioni nelle espressioni di calcolo.|
|`Zero`|`unit -> M<'T>`|Chiamato per vuoto `else` rami di `if...then` espressioni nelle espressioni di calcolo.|

Molti dei metodi in una classe generatore usano e restituiscono un `M<'T>` construct che è in genere un tipo definito separatamente che caratterizza il tipo di calcoli combinate, ad esempio, `Async<'T>` per i flussi di lavoro asincroni e `Seq<'T>` per i flussi di lavoro di sequenza. Le firme di questi metodi consentono loro di essere combinate e annidate tra loro, in modo che sia possibile passare l'oggetto del flusso di lavoro restituito da un costrutto a quella successiva. Il compilatore, quando analizza un'espressione di calcolo, converte l'espressione in una serie di chiamate di funzione annidata usando i metodi nella tabella precedente e il codice nell'espressione di calcolo.

L'espressione annidata è nel formato seguente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Nel codice precedente, le chiamate a `Run` e `Delay` vengono omessi se non sono definiti nella classe del generatore di espressioni di calcolo. Il corpo dell'espressione di calcolo, di seguito è indicato come `{| cexpr |}`, viene convertita in chiamate che riguardano i metodi della classe del generatore per le conversioni descritte nella tabella seguente. L'espressione di calcolo `{| cexpr |}` viene definito in modo ricorsivo in base a queste conversioni in cui `expr` è un'espressione F# e `cexpr` è un'espressione di calcolo.

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
Nella tabella precedente, `other-expr` descrive un'espressione che non è elencata nella tabella. Una classe generatore non è necessario implementare tutti i metodi e supportano tutte le conversioni elencate nella tabella precedente. Tali costrutti che non sono implementati non sono disponibili nelle espressioni di calcolo di quel tipo. Ad esempio, se non si desidera supportare le `use` parola chiave nelle espressioni di calcolo, è possibile omettere la definizione di `Use` nella classe del generatore.

Esempio di codice seguente illustra un'espressione di calcolo che incapsula un calcolo in una serie di passaggi che può essere valutato una sola operazione alla volta. Oggetto discriminate tipo unione, `OkOrException`, consente di codificare lo stato di errore dell'espressione valutato fino a questo momento. Questo codice illustra alcuni modelli tipici che è possibile usare nelle espressioni di calcolo, ad esempio le implementazioni di boilerplate di alcuni dei metodi del generatore.

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

Un'espressione di calcolo ha un tipo sottostante, che restituisce l'espressione. Il tipo sottostante può rappresentare un risultato calcolato o un calcolo ritardato che può essere eseguito o può fornire un modo per eseguire l'iterazione attraverso un certo tipo di raccolta. Nell'esempio precedente, il tipo sottostante è stata **alla fine**. Per un'espressione di sequenza, il tipo sottostante è <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Per un'espressione di query, il tipo sottostante è <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Per un flusso di lavoro asincrono, il tipo sottostante è [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). Il `Async` oggetto rappresenta il lavoro da eseguire per calcolare il risultato. Ad esempio, si chiama [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) per eseguire un calcolo e restituire il risultato.

## <a name="custom-operations"></a>Operazioni personalizzate

È possibile definire un'operazione personalizzata su un'espressione di calcolo e usare un'operazione personalizzata come operatore in un'espressione di calcolo. Ad esempio, è possibile includere un operatore di query in un'espressione di query. Quando si definisce un'operazione personalizzata, è necessario definire il risultato e per i metodi dell'espressione di calcolo. Per definire un'operazione personalizzata, inserirlo in una classe del generatore per l'espressione di calcolo e quindi applicare il [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Questo attributo accetta una stringa come argomento, ovvero il nome da usare in un'operazione personalizzata. Questo nome entra nell'ambito all'inizio della parentesi graffa di apertura dell'espressione di calcolo. Pertanto, non è consigliabile utilizzare gli identificatori che hanno lo stesso nome di un'operazione personalizzata in questo blocco. Ad esempio, evitare l'utilizzo di identificatori, ad esempio `all` o `last` nelle espressioni di query.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Estensione generatori esistenti con nuove operazioni personalizzato

Se si dispone già di una classe del generatore, delle operazioni personalizzate possono essere estesi all'esterno di questa classe del generatore. Le estensioni devono essere dichiarate nei moduli. Gli spazi dei nomi non possono contenere membri di estensione, ad eccezione dello stesso file e lo stesso gruppo di dichiarazione dello spazio dei nomi in cui è definito il tipo.

L'esempio seguente illustra l'estensione dell'oggetto esistente `Microsoft.FSharp.Linq.QueryBuilder` classe.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Flussi di lavoro asincroni](asynchronous-workflows.md)
- [Sequenze](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Espressioni di query](query-expressions.md)
