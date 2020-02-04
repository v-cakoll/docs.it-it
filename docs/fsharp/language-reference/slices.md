---
title: Sezioni
description: Viene illustrato come utilizzare le sezioni per i F# tipi di dati esistenti e come definire sezioni personalizzate per altri tipi di dati.
ms.date: 12/23/2019
ms.openlocfilehash: 928005f2c63ffe099bb64e11ed29bb625e0a54c6
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980379"
---
# <a name="slices"></a>Sezioni

In F#una sezione è un subset di qualsiasi tipo di dati che dispone di un metodo di `GetSlice` nella definizione o in un'estensione del [tipo](type-extensions.md)nell'ambito. Viene in genere usato con F# matrici ed elenchi. Questo articolo illustra come prendere sezioni da tipi esistenti F# e come definire sezioni personalizzate.

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

La F# libreria principale attualmente non definisce `GetSlice` per le matrici 3D. Se si desidera sezionare matrici 3D o altre matrici di dimensioni maggiori, definire il membro `GetSlice`.

## <a name="defining-slices-for-other-data-structures"></a>Definizione di sezioni per altre strutture di dati

La F# libreria principale definisce sezioni per un set limitato di tipi. Se si desidera definire sezioni per più tipi di dati, è possibile eseguire questa operazione nella definizione del tipo o in un'estensione del tipo.

Ad esempio, di seguito viene illustrato come è possibile definire sezioni per la classe <xref:System.ArraySegment%601> per consentire una manipolazione dei dati semplice:

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Utilizzare l'incorporamento per evitare la conversione boxing se necessario

Se si definiscono sezioni per un tipo che è effettivamente uno struct, è consigliabile `inline` il membro del `GetSlice`. Il F# compilatore ottimizza gli argomenti facoltativi, evitando qualsiasi allocazione di heap in seguito all'sezionamento. Questo è estremamente importante per i costrutti di sezionamento, ad esempio <xref:System.Span%601> che non possono essere allocati nell'heap.

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a>Le F# sezioni predefinite sono end-Inclusive

Tutte le sezioni intrinseche F# in sono end-Inclusive; ovvero, il limite superiore è incluso nella sezione. Per una sezione specifica con indice iniziale `x` e indice finale `y`, la sezione risultante includerà il valore *YTH* .

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a>Vedere anche

- [Proprietà indicizzate](./members/indexed-properties.md)
