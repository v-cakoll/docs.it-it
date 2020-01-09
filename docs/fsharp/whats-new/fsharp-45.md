---
title: Novità di F# 4,5- F# Guida
description: Ottenere una panoramica delle nuove funzionalità disponibili in F# 4,5.
ms.date: 11/27/2019
ms.openlocfilehash: b699165125d345ad783b24da8a0a994cba72d4ba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715694"
---
# <a name="whats-new-in-f-45"></a>Novità di F# 4,5

F#4,5 aggiunge più miglioramenti al F# linguaggio. Molte di queste funzionalità sono state aggiunte insieme per consentire di scrivere codice efficiente in F# garantendo al tempo stesso la sicurezza del codice. In questo modo si aggiungono alcuni concetti al linguaggio e una quantità significativa di analisi del compilatore quando si usano questi costrutti.

## <a name="get-started"></a>Attività iniziali

F#4,5 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio. Per ulteriori informazioni, [vedere Introduzione F# ](../get-started/index.md) a.

## <a name="span-and-byref-like-structs"></a>Struct di span e di tipo ByRef

Il tipo di <xref:System.Span%601> introdotto in .NET Core consente di rappresentare i buffer in memoria in modo fortemente tipizzato, che ora è consentito in F# a partire da F# 4,5. Nell'esempio seguente viene illustrato come è possibile riutilizzare una funzione che opera su un <xref:System.Span%601> con diverse rappresentazioni del buffer:

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

Un aspetto importante è che span e altri struct di [tipo ByRef](../language-reference/structures.md#byreflike-structs) hanno un'analisi statica molto rigida eseguita dal compilatore che limitano l'utilizzo in modi che potrebbero risultare imprevisti. Questo è il compromesso fondamentale tra prestazioni, espressività e sicurezza introdotta in F# 4,5.

## <a name="revamped-byrefs"></a>ByRef rinnovati

Prima del F# 4,5, le [ByRef](../language-reference/byrefs.md) in F# non erano sicure e non erano valide per numerose applicazioni. Sono stati risolti i problemi di sonorità relativi F# ai byref in 4,5 e viene applicata la stessa analisi statica eseguita per gli struct span e di tipo ByRef.

### <a name="inreft-and-outreft"></a>inref < t > e outref <' t >

Per rappresentare la nozione di un puntatore gestito di sola lettura, di sola scrittura e di lettura/scrittura F# , 4,5 introduce i tipi di `inref<'T>``outref<'T>` per rappresentare rispettivamente i puntatori di sola lettura e di sola scrittura. Ognuna con una semantica diversa. Ad esempio, non è possibile scrivere in un `inref<'T>`:

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

Per impostazione predefinita, l'inferenza del tipo dedurrà i puntatori gestiti come `inref<'T>` essere in linea con la F# natura non modificabile del codice, a meno che un elemento non sia già stato dichiarato come modificabile. Per rendere scrivibile un elemento, è necessario dichiarare un tipo come `mutable` prima di passare il relativo indirizzo a una funzione o a un membro che lo manipola. Per ulteriori informazioni, vedere [ByRef](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Struct di sola lettura

A partire F# da 4,5, è possibile aggiungere annotazioni a uno struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> di questo tipo:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Ciò impedisce di dichiarare un membro modificabile nello struct e di emettere metadati che consentono F# e C# di considerarli come ReadOnly quando vengono utilizzati da un assembly. Per altre informazioni, vedere [struct](../language-reference/structures.md#readonly-structs)di sola lettura.

## <a name="void-pointers"></a>Puntatori void

Il tipo di `voidptr` viene aggiunto F# a 4,5, così come le funzioni seguenti:

* `NativePtr.ofVoidPtr` convertire un puntatore void in un puntatore int nativo
* `NativePtr.toVoidPtr` convertire un puntatore int nativo in un puntatore void

Questa operazione è utile quando si interopera con un componente nativo che utilizza i puntatori void.

## <a name="the-match-keyword"></a>Parola chiave `match!`

La parola chiave `match!` ottimizza i criteri di ricerca all'interno di un'espressione di calcolo:

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

Quando si combinano i tipi in cui è possibile ereditare da un altro oggetto all'interno delle espressioni array, List e Sequence, è necessario eseguire il cast di tutti i tipi derivati nel tipo padre con `:>` o `upcast`. Questo aspetto è ora rilassato, illustrato di seguito:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Rilassamento dei rientri per le espressioni di matrici ed elenchi

Prima del F# 4,5, era necessario rientrare eccessivamente le espressioni di matrici ed elenchi quando venivano passati come argomenti alle chiamate al metodo. Questa operazione non è più necessaria:

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
