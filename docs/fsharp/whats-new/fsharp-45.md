---
title: 'Novità di F # 4,5-Guida a F #'
description: 'Ottenere una panoramica delle nuove funzionalità disponibili in F # 4,5.'
ms.date: 11/27/2019
ms.openlocfilehash: 2c978c66a4bf231398508cbc1cbb8839228ea8e9
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202360"
---
# <a name="whats-new-in-f-45"></a>Novità di F # 4,5

F # 4,5 aggiunge più miglioramenti al linguaggio F #. Molte di queste funzionalità sono state aggiunte insieme per consentire di scrivere codice efficiente in F # garantendo al tempo stesso che il codice sia sicuro. In questo modo si aggiungono alcuni concetti al linguaggio e una quantità significativa di analisi del compilatore quando si usano questi costrutti.

## <a name="get-started"></a>Introduzione

F # 4,5 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio. Per altre informazioni, [vedere Introduzione a F #](../get-started/index.md) .

## <a name="span-and-byref-like-structs"></a>Struct di span e di tipo ByRef

Il <xref:System.Span%601> tipo introdotto in .NET Core consente di rappresentare i buffer in memoria in modo fortemente tipizzato, che ora è consentito in f # a partire da f # 4,5. Nell'esempio seguente viene illustrato come è possibile riutilizzare una funzione che opera su un oggetto <xref:System.Span%601> con diverse rappresentazioni del buffer:

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

Un aspetto importante è che span e altri struct di [tipo ByRef](../language-reference/structures.md#byreflike-structs) hanno un'analisi statica molto rigida eseguita dal compilatore che limitano l'utilizzo in modi che potrebbero risultare imprevisti. Questo è il compromesso fondamentale tra prestazioni, espressività e sicurezza introdotte in F # 4,5.

## <a name="revamped-byrefs"></a>ByRef rinnovati

Nelle versioni precedenti a F # 4,5, le [ByRef](../language-reference/byrefs.md) in f # non erano sicure e non erano valide per numerose applicazioni. Sono stati risolti i problemi di sonorità relativi ai ByRef in F # 4,5 ed è stata applicata la stessa analisi statica eseguita per gli struct di tipo span e ByRef.

### <a name="inreft-and-outreft"></a>inref< t> e outref<' t>

Per rappresentare la nozione di un puntatore gestito di sola lettura, di sola scrittura e di lettura/scrittura, F # 4,5 introduce `inref<'T>` i `outref<'T>` tipi, rispettivamente per rappresentare i puntatori di sola lettura e di sola scrittura. Ognuna con una semantica diversa. Ad esempio, non è possibile scrivere in un `inref<'T>` :

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

Per impostazione predefinita, l'inferenza del tipo dedurrà i puntatori gestiti come `inref<'T>` in linea con la natura non modificabile del codice F #, a meno che un elemento non sia già stato dichiarato come modificabile. Per rendere scrivibile un elemento, è necessario dichiarare un tipo come `mutable` prima di passare il relativo indirizzo a una funzione o a un membro che lo manipola. Per ulteriori informazioni, vedere [ByRef](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Struct di sola lettura

A partire da F # 4,5, è possibile aggiungere annotazioni a uno struct con l' <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> esempio seguente:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Ciò impedisce di dichiarare un membro modificabile nello struct e di emettere metadati che consentono a F # e C# di considerarlo come ReadOnly quando viene utilizzato da un assembly. Per altre informazioni, vedere [struct](../language-reference/structures.md#readonly-structs)di sola lettura.

## <a name="void-pointers"></a>Puntatori void

Il `voidptr` tipo viene aggiunto a F # 4,5, così come le funzioni seguenti:

* `NativePtr.ofVoidPtr`per convertire un puntatore void in un puntatore int nativo
* `NativePtr.toVoidPtr`per convertire un puntatore int nativo in un puntatore void

Questa operazione è utile quando si interopera con un componente nativo che utilizza i puntatori void.

## <a name="the-match-keyword"></a>Parola chiave `match!`

La `match!` parola chiave migliora i criteri di ricerca all'interno di un'espressione di calcolo:

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

In questo modo è possibile abbreviare il codice che spesso include opzioni di combinazione, o altri tipi, con espressioni di calcolo come Async. Per altre informazioni, vedere [match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Requisiti di multicast più rilassati nelle espressioni array, List e Sequence

Quando si combinano i tipi in cui è possibile ereditare da un altro oggetto all'interno delle espressioni array, List e Sequence, è necessario eseguire il cast di qualsiasi tipo derivato al relativo tipo padre con `:>` o `upcast` . Questo aspetto è ora rilassato, illustrato di seguito:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Rilassamento dei rientri per le espressioni di matrici ed elenchi

Prima di F # 4,5, era necessario rientrare eccessivamente le espressioni di matrici ed elenchi quando venivano passati come argomenti alle chiamate al metodo. Questa operazione non è più necessaria:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
