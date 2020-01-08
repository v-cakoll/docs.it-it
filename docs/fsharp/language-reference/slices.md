---
title: Sezioni
description: Viene illustrato come utilizzare le sezioni per i F# tipi di dati esistenti e come definire sezioni personalizzate per altri tipi di dati.
ms.date: 12/23/2019
ms.openlocfilehash: 3911139c7ce656043817eb23d30f3686555b6efe
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545110"
---
# <a name="slices"></a><span data-ttu-id="1ba62-103">Sezioni</span><span class="sxs-lookup"><span data-stu-id="1ba62-103">Slices</span></span>

<span data-ttu-id="1ba62-104">In F#una sezione è un subset di qualsiasi tipo di dati che dispone di un metodo di `GetSlice` nella definizione o in un'estensione del [tipo](type-extensions.md)nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="1ba62-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="1ba62-105">Viene in genere usato con F# matrici ed elenchi.</span><span class="sxs-lookup"><span data-stu-id="1ba62-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="1ba62-106">Questo articolo illustra come prendere sezioni da tipi esistenti F# e come definire sezioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1ba62-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="1ba62-107">Le sezioni sono simili agli [indicizzatori](./members/indexed-properties.md), ma anziché restituire un singolo valore dalla struttura dei dati sottostante, producono più di uno.</span><span class="sxs-lookup"><span data-stu-id="1ba62-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="1ba62-108">F#attualmente dispone del supporto intrinseco per sezionare stringhe, elenchi, matrici e matrici 2D.</span><span class="sxs-lookup"><span data-stu-id="1ba62-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="1ba62-109">Sezionamento di base F# con elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="1ba62-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="1ba62-110">I tipi di dati più comuni sezionati sono F# elenchi e matrici.</span><span class="sxs-lookup"><span data-stu-id="1ba62-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="1ba62-111">Nell'esempio seguente viene illustrato come eseguire questa operazione con gli elenchi:</span><span class="sxs-lookup"><span data-stu-id="1ba62-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="1ba62-112">Il sezionamento di matrici è analogo a quello degli elenchi di sezionamento:</span><span class="sxs-lookup"><span data-stu-id="1ba62-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="1ba62-113">Sezionamento di matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="1ba62-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="1ba62-114">F#supporta matrici multidimensionali nella libreria F# principale.</span><span class="sxs-lookup"><span data-stu-id="1ba62-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="1ba62-115">Come per le matrici unidimensionali, possono essere utili anche le sezioni di matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="1ba62-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="1ba62-116">Tuttavia, l'introduzione di dimensioni aggiuntive impone una sintassi leggermente diversa, in modo da poter eseguire sezioni di righe e colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="1ba62-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="1ba62-117">Gli esempi seguenti illustrano come sezionare una matrice 2D:</span><span class="sxs-lookup"><span data-stu-id="1ba62-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="1ba62-118">La F# libreria principale attualmente non definisce `GetSlice` per le matrici 3D.</span><span class="sxs-lookup"><span data-stu-id="1ba62-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="1ba62-119">Se si desidera sezionare matrici 3D o altre matrici di dimensioni maggiori, definire il membro `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="1ba62-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="1ba62-120">Definizione di sezioni per altre strutture di dati</span><span class="sxs-lookup"><span data-stu-id="1ba62-120">Defining slices for other data structures</span></span>

<span data-ttu-id="1ba62-121">La F# libreria principale definisce sezioni per un set limitato di tipi.</span><span class="sxs-lookup"><span data-stu-id="1ba62-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="1ba62-122">Se si desidera definire sezioni per più tipi di dati, è possibile eseguire questa operazione nella definizione del tipo o in un'estensione del tipo.</span><span class="sxs-lookup"><span data-stu-id="1ba62-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="1ba62-123">Ad esempio, di seguito viene illustrato come è possibile definire sezioni per la classe <xref:System.ArraySegment%601> per consentire una manipolazione dei dati semplice:</span><span class="sxs-lookup"><span data-stu-id="1ba62-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="1ba62-124">Utilizzare l'incorporamento per evitare la conversione boxing se necessario</span><span class="sxs-lookup"><span data-stu-id="1ba62-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="1ba62-125">Se si definiscono sezioni per un tipo che è effettivamente uno struct, è consigliabile `inline` il membro del `GetSlice`.</span><span class="sxs-lookup"><span data-stu-id="1ba62-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="1ba62-126">Il F# compilatore ottimizza gli argomenti facoltativi, evitando qualsiasi allocazione di heap in seguito all'sezionamento.</span><span class="sxs-lookup"><span data-stu-id="1ba62-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="1ba62-127">Questo è estremamente importante per i costrutti di sezionamento, ad esempio <xref:System.Span%601> che non possono essere allocati nell'heap.</span><span class="sxs-lookup"><span data-stu-id="1ba62-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member sp.GetSlice(startIdx, endIdx) =
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
printSpan sp.[1..2] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="1ba62-128">Le F# sezioni predefinite sono end-Inclusive</span><span class="sxs-lookup"><span data-stu-id="1ba62-128">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="1ba62-129">Tutte le sezioni intrinseche F# in sono end-Inclusive; ovvero, il limite superiore è incluso nella sezione.</span><span class="sxs-lookup"><span data-stu-id="1ba62-129">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="1ba62-130">Per una sezione specifica con indice iniziale `x` e indice finale `y`, la sezione risultante includerà il valore *YTH* .</span><span class="sxs-lookup"><span data-stu-id="1ba62-130">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a><span data-ttu-id="1ba62-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ba62-131">See also</span></span>

- [<span data-ttu-id="1ba62-132">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="1ba62-132">Indexed properties</span></span>](./members/indexed-properties.md)
