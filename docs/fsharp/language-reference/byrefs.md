---
title: 'ByRef (F #)'
description: 'Informazioni su byref e tipi byref simili in F #, che vengono usati per la programmazione di basso livello.'
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48030814"
---
# <a name="byrefs"></a>Zkratka

F # ha due aree delle funzionalità principali relativi allo spazio di programmazione di basso livello:

* Il `byref` / `inref` / `outref` tipi, ovvero un puntatori gestiti. Presentano le restrizioni sull'utilizzo in modo che non è possibile compilare un programma che non è valido in fase di esecuzione.
* Oggetto `byref`-come struct, ovvero un [struttura](structures.md) che ha una semantica simile e le stesse restrizioni in fase di compilazione come `byref<'T>`. Un esempio è <xref:System.Span%601>.

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

## <a name="byref-inref-and-outref"></a>ByRef inref e outref

Esistono tre forme di `byref`:

* `inref<'T>`, un puntatore gestito per leggere il valore sottostante.
* `outref<'T>`, un puntatore gestito per la scrittura del valore sottostante.
* `byref<'T>`, un puntatore gestito per leggere e scrivere il valore sottostante.

Oggetto `byref<'T>` può essere passato in cui un `inref<'T>` è previsto. Analogamente, un `byref<'T>` può essere passato in cui un `outref<'T>` è previsto.

## <a name="using-byrefs"></a>Usando i tipi ByRef

Usare un `inref<'T>`, è necessario ottenere un valore del puntatore con `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

Per scrivere il puntatore del mouse utilizzando un `outref<'T>` oppure `byref<'T>`, è inoltre necessario che il valore ottenere un puntatore a `mutable`.

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

Se si sta scrivendo solo il puntatore anziché leggerlo, è consigliabile usare `outref<'T>` invece di `byref<'T>`.

### <a name="inref-semantics"></a>Semantica Inref

Esaminare il codice seguente:

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

Semanticamente, ciò significa che i seguenti:

* Il titolare del `x` puntatore possa utilizzarlo solo per leggere il valore.
* Qualsiasi puntatore acquisito al `struct` campi annidati all'interno `SomeStruct` sono di tipo specificato `inref<_>`.

Si verifica quanto segue anche:

* Non vi è alcuna implicazione che gli altri thread o gli alias non hanno accesso in scrittura a `x`.
* Non vi è alcuna implicazione che `SomeStruct` non è modificabile in virtù della `x` in corso un `inref`.

Tuttavia, per F # tipi di valori che **vengono** modificabile, il `this` puntatore viene dedotto come un `inref`.

Tutte queste regole insieme significa che il titolare di un `inref` puntatore non può modificare il contenuto della memoria che puntano all'immediato.

### <a name="outref-semantics"></a>Semantica Outref

Lo scopo di `outref<'T>` consiste nell'indicare che il puntatore deve essere letto solo da. In modo imprevisto, `outref<'T>` consente la lettura sottostante valore malgrado il nome. Si tratta di garantire la compatibilità. A livello semantico `outref<'T>` non è diversa da `byref<'T>`.

### <a name="interop-with-c"></a>Interoperabilità con c# #

C# supporta le `in ref` e `out ref` parole chiave, oltre a `ref` restituisce. La tabella seguente illustra in che modo F # interpreta c# genera di cosa:

|Costrutto di linguaggio c#|F # deduce|
|------------|---------|
|`ref` Valore restituito|`outref<'T>`|
|`ref readonly` Valore restituito|`inref<'T>`|
|`in ref` Parametro|`inref<'T>`|
|`out ref` Parametro|`outref<'T>`|

Nella tabella seguente mostra F # genera di cosa:

|Costrutto F #|Costrutto generato|
|------------|-----------------|
|`inref<'T>` argomento|`[In]` attributo nell'argomento|
|`inref<'T>` restituire|`modreq` attributo sul valore|
|`inref<'T>` in uno slot astratto o implementazione|`modreq` argomento o return|
|`outref<'T>` argomento|`[Out]` attributo nell'argomento|

### <a name="type-inference-and-overloading-rules"></a>L'inferenza del tipo e le regole di overload

Un `inref<'T>` tipo viene dedotto dal compilatore F # nei casi seguenti:

1. Un tipo restituito o parametro .NET con un `IsReadOnly` attributo.
2. Il `this` indicatore di misura su un tipo struct che nessun campo modificabile.
3. L'indirizzo di una posizione di memoria derivato da un altro `inref<_>` puntatore.

Quando un indirizzo implicito di un `inref` è stata posta, un overload con un argomento di tipo `SomeType` è preferibile a un overload con un argomento di tipo `inref<SomeType>`. Ad esempio:

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

In entrambi i casi, l'overload che accettano `System.DateTime` vengono risolte invece l'overload che accettano `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>Strutture di tipo ByRef

Oltre al `byref` / `inref` / `outref` trio, è possibile definire struct che possono rispettare `byref`-come la semantica. Questa operazione viene eseguita con il <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` non implica `Struct`. Entrambi devono essere presenti nel tipo.

Un "`byref`-ad esempio" struct in F # è un tipo di valore con associazione dello stack. Non viene allocato nell'heap gestito. Oggetto `byref`-come struct è utile per la programmazione ad alte prestazioni, come viene applicato con set di controlli accurati su durata e di non acquisizione. Le regole sono:

* Possono essere utilizzati come parametri di funzione, i parametri dei metodi, variabili locali, metodo viene restituito.
* Essi non può essere statico o istanza i membri di una classe o struct normali.
* Non è possibile acquisire da qualsiasi costrutto di chiusura (`async` metodi o espressioni lambda).
* Non possono essere utilizzati come un parametro generico.

Quest'ultimo punto è essenziale per la programmazione in F # pipeline stile come `|>` è una funzione generica che Parametrizza relativi tipi di input. Questa restrizione può essere assoluta per `|>` in futuro, perché è in linea e non esegue tutte le chiamate a funzioni generiche non inline nel relativo corpo.

Anche se queste regole limitano molto fortemente utilizzo, a tale scopo per soddisfare la promessa di high performance computing in modo sicuro.

## <a name="byref-returns"></a>Valori restituiti ByRef

Valori restituiti byref da funzioni F # o i membri possono essere generati e utilizzati. Quando si utilizza un `byref`-metodo di restituzione, il valore è dereferenziato in modo implicito. Ad esempio:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Per evitare il dereferenziazione implicito, ad esempio passando un riferimento tramite più chiamate concatenate, usano `&x` (dove `x` è il valore).

È anche possibile assegnare direttamente a una restituzione `byref`. Si consideri il seguente programma (elevata imperativo):

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

## <a name="scoping-for-byrefs"></a>Definizione dell'ambito per i tipi ByRef

Oggetto `let`-valore associato non può avere il proprio riferimento superano l'ambito in cui è stato definito. Ad esempio, di seguito non è consentito:

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

Ciò impedisce all'utente di ottenere risultati diversi a seconda se esegue la compilazione con ottimizzazioni attiva o disattiva.
