---
title: Novità di F . 4.5 - Guida di F
description: Ottenere una panoramica delle nuove funzionalità disponibili in F .
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186127"
---
# <a name="whats-new-in-f-45"></a>Novità di F .

Il linguaggio F . Molte di queste funzionalità sono state aggiunte insieme per consentire di scrivere codice efficiente in F , garantendo al contempo che questo codice sia sicuro. In questo modo significa aggiungere alcuni concetti al linguaggio e una quantità significativa di analisi del compilatore quando si utilizzano questi costrutti.

## <a name="get-started"></a>Introduzione

Il linguaggio F . 4.5 è disponibile in tutte le distribuzioni di .NET Core e negli strumenti di Visual Studio. Per altre informazioni, [iniziare a usare F.](../get-started/index.md)

## <a name="span-and-byref-like-structs"></a>Span e struct simili a byref

Il <xref:System.Span%601> tipo introdotto in .NET Core consente di rappresentare i buffer in memoria in modo fortemente tipizzato, che è ora consentito in F , a partire da F . L'esempio seguente mostra come riutilizzare una <xref:System.Span%601> funzione che opera su un con diverse rappresentazioni del buffer:The following example shows how you can re-use a function operating on a with different buffer representations:

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

Un aspetto importante è che Span e altri struct di [tipo byref](../language-reference/structures.md#byreflike-structs) hanno un'analisi statica molto rigida eseguita dal compilatore che ne limitano l'utilizzo in modi imprevisti. Questo è il compromesso fondamentale tra prestazioni, espressività e sicurezza che viene introdotto in F .

## <a name="revamped-byrefs"></a>Rinnovato darefs

Prima della versione 4.5, [i Byref](../language-reference/byrefs.md) in F , erano non sicuri e non sono stati validi per numerose applicazioni. Problemi di solidità intorno byrefs sono stati risolti in F .

### <a name="inreft-and-outreft"></a>inref<'T> e outref<'T>

Per rappresentare la nozione di puntatore gestito di sola lettura, di sola scrittura `inref<'T>` `outref<'T>` e di lettura/scrittura, in Fè 4.5 vengono introdotti rispettivamente i tipi , per rappresentare puntatori di sola lettura e di sola scrittura. Ognuno ha una semantica diversa. Ad esempio, non è `inref<'T>`possibile scrivere in un:

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

Per impostazione predefinita, l'inferenza `inref<'T>` del tipo dedurrà i puntatori gestiti come in linea con la natura non modificabile del codice F , a meno che qualcosa non sia già stato dichiarato modificabile. Per rendere un elemento scrivibile, è necessario `mutable` dichiarare un tipo come prima di passare il relativo indirizzo a una funzione o membro che lo modifica. Per ulteriori informazioni, vedere [Byrefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Strutture Readonly

A partire da F . <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Ciò impedisce di dichiarare un membro modificabile nella struttura e genera metadati che consentono a F e C , di considerarlo come readonly quando utilizzato da un assembly. Per ulteriori informazioni, consultate [Structs ReadOnly](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Puntatori Void

Il `voidptr` tipo viene aggiunto a F .

* `NativePtr.ofVoidPtr`per convertire un puntatore void in un puntatore int nativo
* `NativePtr.toVoidPtr`per convertire un puntatore int nativo in un puntatore void

Ciò è utile quando si interagisce con un componente nativo che utilizza puntatori void.

## <a name="the-match-keyword"></a>Parola chiave `match!`

La `match!` parola chiave migliora la corrispondenza dei criteri di ricerca all'interno di un'espressione di calcolo:The keyword enhances pattern matching when inside a computation expression:

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

Ciò consente di abbreviare il codice che spesso comporta la combinazione di opzioni (o altri tipi) con espressioni di calcolo, ad esempio async. Per saperne di più, vedi [match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Requisiti di upcast rilassati nelle espressioni di matrice, elenco e sequenza

La combinazione di tipi in cui uno può ereditare da un'altra all'interno di espressioni `:>` `upcast`di matrice, elenco e sequenza ha tradizionalmente richiesto l'upcast di qualsiasi tipo derivato al relativo tipo padre con o . Questo è ora rilassato, dimostrato come segue:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Rilassamento del rientro per le espressioni di matrice ed elenco

Prima della versione 4.5 di F, era necessario applicare un rientro eccessivo alle espressioni di matrice ed elenco quando vengono passate come argomenti alle chiamate al metodo. Questo non è più necessario:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
