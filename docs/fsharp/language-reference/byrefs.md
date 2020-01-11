---
title: Byref
description: Informazioni sui tipi ByRef e di tipo ByRef in F#, usati per la programmazione di basso livello.
ms.date: 11/04/2019
ms.openlocfilehash: 5aaee1e4eac9ce0d7e9ba89a2ab5f745d31367a0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901303"
---
# <a name="byrefs"></a>Byref

F#in sono presenti due principali aree funzionali che occupano lo spazio di programmazione di basso livello:

* Il `byref`/`inref`i tipi di `outref` /, ovvero i puntatori gestiti. Hanno restrizioni sull'utilizzo, in modo da non poter compilare un programma non valido in fase di esecuzione.
* Uno struct di tipo `byref`, ovvero una [struttura](structures.md) con semantica simile e le stesse restrizioni della fase di compilazione di `byref<'T>`. Un esempio è <xref:System.Span%601>.

## <a name="syntax"></a>Sintassi

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a>ByRef, inref e outref

Esistono tre tipi di `byref`:

* `inref<'T>`, un puntatore gestito per la lettura del valore sottostante.
* `outref<'T>`, un puntatore gestito per la scrittura nel valore sottostante.
* `byref<'T>`, un puntatore gestito per la lettura e la scrittura del valore sottostante.

È possibile passare un `byref<'T>` in cui è prevista una `inref<'T>`. Analogamente, è possibile passare un `byref<'T>` in cui è prevista una `outref<'T>`.

## <a name="using-byrefs"></a>Utilizzo di ByRef

Per usare una `inref<'T>`, è necessario ottenere un valore di puntatore con `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Per scrivere nel puntatore usando un `outref<'T>` o `byref<'T>`, è necessario anche fare in modo che si prenda un puntatore per `mutable`.

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

Se si scrive solo il puntatore anziché leggerlo, provare a usare `outref<'T>` anziché `byref<'T>`.

### <a name="inref-semantics"></a>Semantica di Inref

Esaminare il codice seguente:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semanticamente, questo significa quanto segue:

* Il titolare del puntatore `x` può utilizzarlo solo per leggere il valore.
* Ogni puntatore acquisito per `struct` campi annidati all'interno di `SomeStruct` viene assegnato al tipo `inref<_>`.

Si verifica anche quanto segue:

* Non esiste alcuna implicazione che altri thread o alias non dispongano dell'accesso in scrittura ai `x`.
* Non esiste alcuna implicazione che `SomeStruct` sia immutabile in virtù della `x` essere un `inref`.

Tuttavia, per F# i **tipi di valore** non modificabili, il puntatore `this` viene dedotto come `inref`.

Ognuna di queste regole significa che il titolare di un puntatore `inref` potrebbe non modificare il contenuto immediato della memoria a cui punta.

### <a name="outref-semantics"></a>Semantica di Outref

Lo scopo di `outref<'T>` è indicare che il puntatore deve essere scritto solo in. In modo imprevisto, `outref<'T>` consente di leggere il valore sottostante nonostante il nome. Per motivi di compatibilità. Semanticamente, `outref<'T>` non è diverso da `byref<'T>`.

### <a name="interop-with-c"></a>Interoperabilità con C\#

C#supporta le parole chiave `in ref` e `out ref`, oltre a `ref` restituisce. Nella tabella seguente viene illustrato F# come interpretare C# gli elementi generati:

|C#costruire|F#deduce|
|------------|---------|
|`ref` valore restituito|`outref<'T>`|
|`ref readonly` valore restituito|`inref<'T>`|
|Parametro `in ref`.|`inref<'T>`|
|Parametro `out ref`.|`outref<'T>`|

La tabella seguente mostra cosa F# genera:

|F#costruire|Costrutto emesso|
|------------|-----------------|
|`inref<'T>` argomento|attributo `[In]` sull'argomento|
|`inref<'T>` restituito|`modreq` attributo per valore|
|`inref<'T>` nello slot o nell'implementazione astratta|`modreq` sull'argomento o sulla restituzione|
|`outref<'T>` argomento|attributo `[Out]` sull'argomento|

### <a name="type-inference-and-overloading-rules"></a>Regole di overload e inferenza del tipo

Un tipo di `inref<'T>` viene dedotto dal F# compilatore nei casi seguenti:

1. Un parametro .NET o un tipo restituito con un attributo `IsReadOnly`.
2. Puntatore `this` su un tipo struct senza campi modificabili.
3. Indirizzo di una posizione di memoria derivata da un altro puntatore `inref<_>`.

Quando viene eseguito un indirizzo implicito di un `inref`, un overload con un argomento di tipo `SomeType` è preferibile a un overload di con un argomento di tipo `inref<SomeType>`. Ad esempio:

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

In entrambi i casi, gli overload che accettano `System.DateTime` vengono risolti anziché gli overload che assumono `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>Struct di tipo ByRef

Oltre al `byref`/`inref`/`outref` Trio, è possibile definire struct personalizzati che possono rispettare la semantica di tipo `byref`. Questa operazione viene eseguita con l'attributo <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` non implica `Struct`. Entrambi devono essere presenti nel tipo.

Uno struct "`byref`-like" in F# è un tipo di valore associato allo stack. Non viene mai allocato nell'heap gestito. Uno struct di tipo `byref`è utile per la programmazione a prestazioni elevate, in quanto viene applicato con un set di controlli sicuri sulla durata e non sull'acquisizione. Le regole sono:

* Possono essere usati come parametri di funzione, parametri di metodo, variabili locali, restituzione di metodi.
* Non possono essere membri statici o di istanza di una classe o di uno struct normale.
* Non possono essere acquisiti da alcun costrutto di chiusura (`async` metodi o espressioni lambda).
* Non possono essere usati come parametro generico.

Questo ultimo punto è fondamentale per F# la programmazione in stile pipeline, perché `|>` è una funzione generica che parametrizza i relativi tipi di input. Questa restrizione può essere attenuata per `|>` in futuro, in quanto è inline e non esegue chiamate a funzioni generiche non inline nel corpo.

Sebbene queste regole limitino fortemente l'utilizzo, lo fanno per soddisfare la promessa di un calcolo ad alte prestazioni in modo sicuro.

## <a name="byref-returns"></a>ByRef restituisce

I ritorni F# ByRef da funzioni o membri possono essere prodotti e utilizzati. Quando si utilizza un metodo di restituzione di `byref`, il valore viene dereferenziato in modo implicito. Ad esempio:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Per evitare la dereferenziazione implicita, ad esempio il passaggio di un riferimento tramite più chiamate concatenate, usare `&x` (dove `x` è il valore).

È anche possibile assegnare direttamente a un `byref`restituito. Si consideri il seguente programma (estremamente imperativo):

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

L'output è il seguente.

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Ambito per ByRef

Il riferimento di un valore associato a `let`non può superare l'ambito in cui è stato definito. Il codice seguente, ad esempio, non è consentito:

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

In questo modo si evita di ottenere risultati diversi a seconda che si compilino con le ottimizzazioni.
