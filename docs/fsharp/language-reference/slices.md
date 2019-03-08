---
title: Le sezioni (F#)
description: Informazioni su come usare le sezioni esistente F# tipi di dati e come definire le proprie sezioni per altri tipi di dati.
ms.date: 01/22/2019
ms.openlocfilehash: 1d8bb029ad18c8853ab58888959967ed279fb368
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675277"
---
# <a name="slices"></a><span data-ttu-id="87826-103">Sezioni</span><span class="sxs-lookup"><span data-stu-id="87826-103">Slices</span></span>

<span data-ttu-id="87826-104">In F#, una sezione è un subset di un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="87826-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="87826-105">Per essere in grado di sfruttare una sezione di un tipo di dati, è necessario definire il tipo di dati un `GetSlice` metodo o in un [digitare estensione](type-extensions.md) vale a dire nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="87826-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="87826-106">Questo articolo illustra come eseguire sezioni di esistenti F# i tipi e come definirne uno proprio.</span><span class="sxs-lookup"><span data-stu-id="87826-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="87826-107">Le sezioni sono simili agli [indicizzatori](members/indexed-properties.md), ma anziché restituire un singolo valore dalla struttura di dati sottostante, consentono di produrre più sessioni.</span><span class="sxs-lookup"><span data-stu-id="87826-107">Slices are similar to [indexers](members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="87826-108">F#è attualmente il supporto intrinseco per il sezionamento stringhe, elenchi, matrici e matrici 2D.</span><span class="sxs-lookup"><span data-stu-id="87826-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="87826-109">Sezionamento di base con F# elenchi e matrici</span><span class="sxs-lookup"><span data-stu-id="87826-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="87826-110">I tipi di dati più comuni che vengono sezionati sono F# elenchi e matrici.</span><span class="sxs-lookup"><span data-stu-id="87826-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="87826-111">Nell'esempio seguente viene illustrato come eseguire questa operazione con elenchi:</span><span class="sxs-lookup"><span data-stu-id="87826-111">The following example demonstrates how to do this with lists:</span></span>

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

<span data-ttu-id="87826-112">Sezionamento delle matrici è esattamente come gli elenchi di sezionamento:</span><span class="sxs-lookup"><span data-stu-id="87826-112">Slicing arrays is just like slicing lists:</span></span>

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

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="87826-113">Sezionamento delle matrici multidimensionali</span><span class="sxs-lookup"><span data-stu-id="87826-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="87826-114">F#supporta matrici multidimensionali in di F# libreria di base.</span><span class="sxs-lookup"><span data-stu-id="87826-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="87826-115">Come con le matrici unidimensionali, sezioni di matrici multidimensionali possono anche essere utile.</span><span class="sxs-lookup"><span data-stu-id="87826-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="87826-116">Tuttavia, l'introduzione di altre quote impone una sintassi leggermente diversa in modo che sia possibile eseguire le sezioni di righe e colonne specifiche.</span><span class="sxs-lookup"><span data-stu-id="87826-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="87826-117">Negli esempi seguenti illustrano come eseguire il sezionamento una matrice 2D:</span><span class="sxs-lookup"><span data-stu-id="87826-117">The following examples demonstrate how to slice a 2D array:</span></span>

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

<span data-ttu-id="87826-118">Il F# libreria di base non definisce `GetSlice`per le matrici 3D.</span><span class="sxs-lookup"><span data-stu-id="87826-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="87826-119">Se si desidera sezionare quelli o ad altre matrici o più dimensioni, è necessario definire il `GetSlice` membro manualmente.</span><span class="sxs-lookup"><span data-stu-id="87826-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="87826-120">La definizione di intervalli di altre strutture di dati</span><span class="sxs-lookup"><span data-stu-id="87826-120">Defining slices for other data structures</span></span>

<span data-ttu-id="87826-121">Il F# libreria di base definisce le sezioni per un set limitato di tipi.</span><span class="sxs-lookup"><span data-stu-id="87826-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="87826-122">Se si vuole definire sezioni per più tipi di dati, è possibile farlo nella definizione del tipo stesso o in un'estensione del tipo.</span><span class="sxs-lookup"><span data-stu-id="87826-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="87826-123">Ad esempio, ecco come è possibile definire sezioni per la <xref:System.ArraySegment%601> classe per consentire la manipolazione dei dati utile:</span><span class="sxs-lookup"><span data-stu-id="87826-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="87826-124">Usare l'incorporamento per evitare la conversione boxing se è necessario</span><span class="sxs-lookup"><span data-stu-id="87826-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="87826-125">Se si siano definendo le sezioni per un tipo che è effettivamente uno struct, è consigliabile che si `inline` il `GetSlice` membro.</span><span class="sxs-lookup"><span data-stu-id="87826-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="87826-126">Il F# compilatore ottimizza gli argomenti facoltativi, come evitare allocazioni heap come risultato di sezionamento.</span><span class="sxs-lookup"><span data-stu-id="87826-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="87826-127">Ciò è particolarmente importante per i costrutti di sezionamento, ad esempio <xref:System.Span%601> che non possono essere allocati nell'heap.</span><span class="sxs-lookup"><span data-stu-id="87826-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="87826-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87826-128">See also</span></span>

- [<span data-ttu-id="87826-129">Proprietà indicizzate</span><span class="sxs-lookup"><span data-stu-id="87826-129">Indexed properties</span></span>](members/indexed-properties.md)
