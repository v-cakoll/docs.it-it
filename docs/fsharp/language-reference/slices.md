---
title: Le sezioni (F#)
description: Informazioni su come usare le sezioni esistente F# tipi di dati e come definire le proprie sezioni per altri tipi di dati.
ms.date: 01/22/2019
ms.openlocfilehash: c204c6cbb195b33998b92dd940313a132ecc321d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746708"
---
# <a name="slices"></a>Sezioni

In F#, una sezione è un subset di un tipo di dati. Per essere in grado di sfruttare una sezione di un tipo di dati, è necessario definire il tipo di dati un `GetSlice` metodo o in un [digitare estensione](type-extensions.md) vale a dire nell'ambito. Questo articolo illustra come eseguire sezioni di esistenti F# i tipi e come definirne uno proprio.

Le sezioni sono simili agli [indicizzatori](members/indexed-properties.md), ma anziché restituire un singolo valore dalla struttura di dati sottostante, consentono di produrre più sessioni.

F#è attualmente il supporto intrinseco per il sezionamento stringhe, elenchi, matrici e matrici 2D.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Sezionamento di base con F# elenchi e matrici

I tipi di dati più comuni che vengono sezionati sono F# elenchi e matrici. Nell'esempio seguente viene illustrato come eseguire questa operazione con elenchi:

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

Sezionamento delle matrici è esattamente come gli elenchi di sezionamento:

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a>Sezionamento delle matrici multidimensionali

F#supporta matrici multidimensionali in di F# libreria di base. Come con le matrici unidimensionali, sezioni di matrici multidimensionali possono anche essere utile. Tuttavia, l'introduzione di altre quote impone una sintassi leggermente diversa in modo che sia possibile eseguire le sezioni di righe e colonne specifiche.

Negli esempi seguenti illustrano come eseguire il sezionamento una matrice 2D:

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twobyTwo
```

Il F# libreria di base non definisce `GetSlice`per le matrici 3D. Se si desidera sezionare quelli o ad altre matrici o più dimensioni, è necessario definire il `GetSlice` membro manualmente.

## <a name="defining-slices-for-other-data-structures"></a>La definizione di intervalli di altre strutture di dati

Il F# libreria di base definisce le sezioni per un set limitato di tipi. Se si vuole definire sezioni per più tipi di dati, è possibile farlo nella definizione del tipo stesso o in un'estensione del tipo.

Ad esempio, ecco come è possibile definire sezioni per la <xref:System.ArraySegment`1> classe per consentire la manipolazione dei dati utile:

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Usare l'incorporamento per evitare la conversione boxing se è necessario

Se si siano definendo le sezioni per un tipo che è effettivamente uno struct, è consigliabile che si `inline` il `GetSlice` membro. Il F# compilatore ottimizza gli argomenti facoltativi, come evitare allocazioni heap come risultato di sezionamento. Ciò è particolarmente importante per i costrutti di sezionamento, ad esempio <xref:System.Span`1> che non è possibile essere allocata nell'heap.

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a>Vedere anche

- [Proprietà indicizzate](members/indexed-properties.md)