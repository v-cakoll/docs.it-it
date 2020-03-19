---
title: Byref
description: Informazioni sui tipi di tipo byref e byref in F , utilizzati per la programmazione di basso livello.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187043"
---
# <a name="byrefs"></a>Byref

F è dotata di due aree di funzionalità principali che si occupano dello spazio di programmazione di basso livello:

* `byref` / I `inref` / tipi, ovvero puntatori gestiti. `outref` Sono previste restrizioni sull'utilizzo in modo che non sia possibile compilare un programma non valido in fase di esecuzione.
* Uno `byref`struct di tipo -like, ovvero una [struttura](structures.md) con semantica `byref<'T>`simile e le stesse restrizioni in fase di compilazione di . Un esempio <xref:System.Span%601>è .

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

## <a name="byref-inref-and-outref"></a>Byref, inref e outref

Ci sono tre `byref`forme di :

* `inref<'T>`, un puntatore gestito per la lettura del valore sottostante.
* `outref<'T>`, un puntatore gestito per la scrittura nel valore sottostante.
* `byref<'T>`, un puntatore gestito per la lettura e la scrittura del valore sottostante.

Un `byref<'T>` può essere `inref<'T>` passato dove è previsto un an. Analogamente, `byref<'T>` un oggetto `outref<'T>` può essere passato dove è previsto un oggetto.

## <a name="using-byrefs"></a>Utilizzo di byrefsUsing byrefs

Per utilizzare `inref<'T>`un oggetto , è `&`necessario ottenere un valore del puntatore con :

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Per scrivere sul puntatore `outref<'T>` `byref<'T>`utilizzando un oggetto o , è `mutable`inoltre necessario impostare il valore desiderato come puntatore a .

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

Se si scrive solo il puntatore anziché leggerlo, è consigliabile utilizzare `outref<'T>` anziché `byref<'T>`.

### <a name="inref-semantics"></a>Semantica di inref

Esaminare il codice seguente:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Dal punto di vista semantico, ciò significa quanto segue:

* Il titolare `x` del puntatore può utilizzarlo solo per leggere il valore.
* A tutti `struct` i puntatori acquisiti ai campi annidati all'interno `SomeStruct` viene assegnato il tipo `inref<_>`.

Vale anche quanto segue:

* Non è implicato che altri thread o alias non `x`dispongano dell'accesso in scrittura a .
* Non c'è implicazione che `SomeStruct` sia immutabile in virtù di `x` essere un `inref`.

Tuttavia, per i tipi di valore F, che **non sono** modificabili, il `this` puntatore viene dedotto come un `inref`oggetto .

Tutte queste regole insieme significano `inref` che il titolare di un puntatore non può modificare il contenuto immediato della memoria a cui viene fatto riferimento.

### <a name="outref-semantics"></a>Semantica di Outref

Lo scopo `outref<'T>` di è quello di indicare che il puntatore deve essere scritto solo in. Inaspettatamente, `outref<'T>` consente di leggere il valore sottostante nonostante il nome. Questo è a scopo di compatibilità. Dal punto `outref<'T>` di vista `byref<'T>`semantico, non è diverso da .

### <a name="interop-with-c"></a>Interoperabilità con C\#

Oltre alle parole `in ref` `out ref` chiave e, `ref` in aggiunta alle parole chiave, Cè supporta le parole chiave e . Nella tabella seguente viene illustrato il modo in cui F , interpreta ciò che viene generato da C:

|Costrutti di C|Deduzioni di F|
|------------|---------|
|`ref`valore restituito|`outref<'T>`|
|`ref readonly`valore restituito|`inref<'T>`|
|Parametro `in ref`.|`inref<'T>`|
|Parametro `out ref`.|`outref<'T>`|

Nella tabella seguente viene illustrato ciò che viene generato da F:

|Costrutto F|Costrutto Emitted|
|------------|-----------------|
|`inref<'T>` argomento|`[In]`attributo sull'argomento|
|`inref<'T>`Ritorno|`modreq`attributo sul valore|
|`inref<'T>`in slot astratto o implementazione|`modreq`sull'argomento o ritorno|
|`outref<'T>` argomento|`[Out]`attributo sull'argomento|

### <a name="type-inference-and-overloading-rules"></a>Inferenza dei tipi e regole di overloadType inference and overloading rules

Un `inref<'T>` tipo viene dedotto dal compilatore F , nei seguenti casi:

1. Un parametro .NET o `IsReadOnly` un tipo restituito con un attributo.
2. Puntatore `this` a un tipo struct senza campi modificabili.
3. Indirizzo di una posizione di `inref<_>` memoria derivata da un altro puntatore.

Quando viene preso `inref` un indirizzo implicito di un `SomeType` oggetto, un overload con un `inref<SomeType>`argomento di tipo è preferibile a un overload con un argomento di tipo . Ad esempio:

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

In entrambi i casi, `System.DateTime` gli overload che utilizzano vengono risolti anziché gli overload che utilizzano `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>Struct simili a Byref

`byref` / `inref` / `outref` Oltre al trio, è possibile definire le proprie strutture `byref`che possono aderire alla semantica -like. Questa operazione viene <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> eseguita con l'attributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`non implica `Struct`. Entrambi devono essere presenti nel tipo.

Uno`byref`struct "-like" in F è un tipo di valore associato allo stack. Non viene mai allocato nell'heap gestito. Un `byref`-like struct è utile per la programmazione ad alte prestazioni, in quanto viene applicato con set di controlli sicuri sulla durata e non acquisizione. Le regole sono:

* Possono essere utilizzati come parametri di funzione, parametri di metodo, variabili locali, restituisce il metodo.
* Non possono essere membri statici o di istanza di una classe o di uno struct normale.
* Non possono essere acquisiti`async` da alcun costrutto di chiusura (metodi o espressioni lambda).
* Non possono essere utilizzati come parametro generico.

Quest'ultimo punto è fondamentale per la `|>` programmazione in stile pipeline F , così come una funzione generica che parametrizza i relativi tipi di input. Questa restrizione può `|>` essere rilassata per in futuro, in quanto è inline e non effettua alcuna chiamata a funzioni generiche non inline nel suo corpo.

Sebbene queste regole limitino fortemente l'utilizzo, lo fanno per soddisfare la promessa di calcolo ad alte prestazioni in modo sicuro.

## <a name="byref-returns"></a>Restituzione Byref

I ritorni a capo di Byref da funzioni o membri di F , possono essere prodotti e utilizzati. Quando si `byref`utilizza un metodo che restituisce, il valore viene dereferenziato in modo implicito. Ad esempio:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

Per restituire un valore byref, la variabile che contiene il valore deve rimanere più lunga dell'ambito corrente.
Inoltre, per restituire byref, utilizzare `&value` (dove value è una variabile che si trova più a lungo dell'ambito corrente).

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Per evitare la dereferenziazione implicita, ad `&x` esempio `x` il passaggio di un riferimento tramite più chiamate concatenate, usare (dove è il valore).

È inoltre possibile assegnare `byref`direttamente a un reso . Si consideri il seguente programma (altamente imperativo):

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

## <a name="scoping-for-byrefs"></a>Definizione dell'ambito per byrefs

Un `let`valore associato non può avere il riferimento supera l'ambito in cui è stato definito. Ad esempio, non è consentito quanto segue:

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

In questo modo si evita di ottenere risultati diversi a seconda se si esegue la compilazione con ottimizzazioni o meno.
