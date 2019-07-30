---
title: Sezioni (F#)
description: Informazioni su come usare le sezioni per i tipi F# di dati esistenti e su come definire sezioni personalizzate per altri tipi di dati.
ms.date: 01/22/2019
ms.openlocfilehash: 3067982c2b4249312c7e9365bbfb994be840911d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627141"
---
# <a name="slices"></a>Sezioni

In F#una sezione è un subset di un tipo di dati. Per poter eseguire una sezione da un tipo di dati, il tipo di dati deve definire un `GetSlice` metodo o un'estensione del [tipo](type-extensions.md) nell'ambito. Questo articolo illustra come prendere le sezioni dai tipi esistenti F# e come definirne di personalizzate.

Le sezioni sono simili agli [indicizzatori](./members/indexed-properties.md), ma anziché restituire un singolo valore dalla struttura dei dati sottostante, producono più di uno.

F#attualmente dispone del supporto intrinseco per sezionare stringhe, elenchi, matrici e matrici 2D.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Sezionamento di base F# con elenchi e matrici

I tipi di dati più comuni sezionati sono F# elenchi e matrici. Nell'esempio seguente viene illustrato come eseguire questa operazione con gli elenchi:

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

Il sezionamento di matrici è analogo a quello degli elenchi di sezionamento:

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

## <a name="slicing-multidimensional-arrays"></a>Sezionamento di matrici multidimensionali

F#supporta matrici multidimensionali nella libreria F# principale. Come per le matrici unidimensionali, possono essere utili anche le sezioni di matrici multidimensionali. Tuttavia, l'introduzione di dimensioni aggiuntive impone una sintassi leggermente diversa, in modo da poter eseguire sezioni di righe e colonne specifiche.

Gli esempi seguenti illustrano come sezionare una matrice 2D:

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
printfn "%A" twoByTwo
```

La F# libreria principale non definisce `GetSlice`per le matrici 3D. Se si desidera sezionare tali matrici o altre matrici di dimensioni maggiori, è necessario definire il `GetSlice` membro manualmente.

## <a name="defining-slices-for-other-data-structures"></a>Definizione di sezioni per altre strutture di dati

La F# libreria principale definisce sezioni per un set limitato di tipi. Se si desidera definire sezioni per più tipi di dati, è possibile eseguire questa operazione nella definizione del tipo o in un'estensione del tipo.

Ad esempio, di seguito viene illustrato come definire le sezioni per la <xref:System.ArraySegment%601> classe per consentire una manipolazione dei dati semplice:

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Utilizzare l'incorporamento per evitare la conversione boxing se necessario

Se si definiscono sezioni per un tipo che è effettivamente uno struct, è consigliabile `inline` usare il `GetSlice` membro. Il F# compilatore ottimizza gli argomenti facoltativi, evitando qualsiasi allocazione di heap in seguito all'sezionamento. Questo è estremamente importante per i costrutti di sezionamento, <xref:System.Span%601> ad esempio, che non possono essere allocati nell'heap.

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

- [Proprietà indicizzate](./members/indexed-properties.md)
