---
title: Esplorare intervalli di dati con indici e intervalli
description: Questa esercitazione avanzata descrive come esplorare i dati usando indici e intervalli per esaminare le sezioni di un set di dati sequenziale.
ms.date: 09/20/2019
ms.custom: mvc
ms.openlocfilehash: a879601e1358f72e80983992a3cd96ba1fb06a38
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71391960"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="fdba6-103">Indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="fdba6-103">Indices and ranges</span></span>

<span data-ttu-id="fdba6-104">Gli intervalli e gli indici forniscono una sintassi concisa per l'accesso a singoli elementi o intervalli in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="fdba6-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="fdba6-105">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="fdba6-105">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="fdba6-106">Usare la sintassi per gli intervalli in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="fdba6-106">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="fdba6-107">Comprendere le decisioni a livello di progettazione per l'inizio e la fine di ogni sequenza.</span><span class="sxs-lookup"><span data-stu-id="fdba6-107">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="fdba6-108">Analizzare gli scenari per i tipi <xref:System.Index> e <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="fdba6-108">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="fdba6-109">Supporto del linguaggio per indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="fdba6-109">Language support for indices and ranges</span></span>

<span data-ttu-id="fdba6-110">Questo supporto per il linguaggio si basa su due nuovi tipi e due nuovi operatori:</span><span class="sxs-lookup"><span data-stu-id="fdba6-110">This language support relies on two new types and two new operators:</span></span>

- <span data-ttu-id="fdba6-111"><xref:System.Index?displayProperty=nameWithType> rappresenta un indice in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="fdba6-111"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="fdba6-112">Indice dell'operatore `^`end, che specifica che un indice è relativo alla fine di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="fdba6-112">The index from end operator `^`, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="fdba6-113"><xref:System.Range?displayProperty=nameWithType> rappresenta un intervallo secondario di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="fdba6-113"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="fdba6-114">Operatore `..`Range, che specifica l'inizio e la fine di un intervallo come operandi.</span><span class="sxs-lookup"><span data-stu-id="fdba6-114">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="fdba6-115">Per iniziare, ecco come funzionano le regole per gli indici.</span><span class="sxs-lookup"><span data-stu-id="fdba6-115">Let's start with the rules for indices.</span></span> <span data-ttu-id="fdba6-116">Prendere in considerazione una matrice `sequence`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-116">Consider an array `sequence`.</span></span> <span data-ttu-id="fdba6-117">L'indice `0` è uguale a `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-117">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="fdba6-118">L'indice `^0` è uguale a `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-118">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="fdba6-119">Si noti che `sequence[^0]` genera un'eccezione, proprio come `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-119">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="fdba6-120">Per qualsiasi numero `n`, l'indice `^n` è uguale a `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-120">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

```csharp-interactive
string[] words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="fdba6-121">È possibile recuperare l'ultima parola con l'indice `^1`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-121">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="fdba6-122">Aggiungere il codice seguente sotto l'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="fdba6-122">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="fdba6-123">Un intervallo specifica *inizio* e *fine* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="fdba6-123">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="fdba6-124">Gli intervalli sono esclusivi, vale a dire che la *fine* non è inclusa nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="fdba6-124">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="fdba6-125">L'intervallo `[0..^0]` rappresenta l'intero intervallo, proprio come `[0..sequence.Length]` rappresenta l'intero intervallo.</span><span class="sxs-lookup"><span data-stu-id="fdba6-125">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="fdba6-126">Il codice seguente crea un intervallo secondario con le parole "quick", "brown" e "fox".</span><span class="sxs-lookup"><span data-stu-id="fdba6-126">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="fdba6-127">Include da `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-127">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="fdba6-128">L'elemento `words[4]` non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="fdba6-128">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="fdba6-129">Aggiungere il codice seguente allo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="fdba6-129">Add the following code to the same method.</span></span> <span data-ttu-id="fdba6-130">Copiarlo e incollarlo nella parte inferiore della finestra interattiva.</span><span class="sxs-lookup"><span data-stu-id="fdba6-130">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="fdba6-131">Il codice seguente crea un intervallo secondario con "lazy" e "dog".</span><span class="sxs-lookup"><span data-stu-id="fdba6-131">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="fdba6-132">Include `words[^2]` e `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-132">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="fdba6-133">L'indice finale `words[^0]` non viene incluso.</span><span class="sxs-lookup"><span data-stu-id="fdba6-133">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="fdba6-134">Aggiungere anche il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fdba6-134">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="fdba6-135">Gli esempi seguenti creano intervalli aperti alle estremità, per l'inizio, la fine o entrambe:</span><span class="sxs-lookup"><span data-stu-id="fdba6-135">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="fdba6-136">È anche possibile dichiarare gli intervalli o gli indici come variabili.</span><span class="sxs-lookup"><span data-stu-id="fdba6-136">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="fdba6-137">In seguito la variabile può essere usata all'interno dei caratteri `[` e `]`:</span><span class="sxs-lookup"><span data-stu-id="fdba6-137">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="fdba6-138">L'esempio seguente illustra molti dei motivi per cui sono state fatte tali scelte.</span><span class="sxs-lookup"><span data-stu-id="fdba6-138">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="fdba6-139">Modificare `x`, `y`, e `z` per provare combinazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="fdba6-139">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="fdba6-140">Durante le varie prove, usare valori per cui `x` è minore di `y` e `y` è minore di `z` per le combinazioni valide.</span><span class="sxs-lookup"><span data-stu-id="fdba6-140">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="fdba6-141">Aggiungere il codice seguente in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="fdba6-141">Add the following code in a new method.</span></span> <span data-ttu-id="fdba6-142">Provare combinazioni diverse:</span><span class="sxs-lookup"><span data-stu-id="fdba6-142">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="type-support-for-indices-and-ranges"></a><span data-ttu-id="fdba6-143">Supporto dei tipi per gli indici e gli intervalli</span><span class="sxs-lookup"><span data-stu-id="fdba6-143">Type support for indices and ranges</span></span>

<span data-ttu-id="fdba6-144">Se un tipo fornisce un [indicizzatore](../programming-guide/indexers/index.md) con un parametro <xref:System.Index> o <xref:System.Range>, supporta in modo esplicito gli indici o gli intervalli rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="fdba6-144">If a type provides an [indexer](../programming-guide/indexers/index.md) with an <xref:System.Index> or <xref:System.Range> parameter, it explicitly supports indices or ranges respectively.</span></span>

<span data-ttu-id="fdba6-145">Un tipo può essere **conteggiato** se dispone di una proprietà denominata `Length` o `Count` con un getter accessibile e un tipo restituito `int`.</span><span class="sxs-lookup"><span data-stu-id="fdba6-145">A type is **countable** if it has a property named `Length` or `Count` with an accessible getter and a return type of `int`.</span></span> <span data-ttu-id="fdba6-146">Un tipo conteggiabile che non supporta in modo esplicito gli indici o gli intervalli può fornire un supporto implicito.</span><span class="sxs-lookup"><span data-stu-id="fdba6-146">A countable type that doesn't explicitly support indices or ranges may provide an implicit support for them.</span></span> <span data-ttu-id="fdba6-147">Per ulteriori informazioni, vedere le sezioni supporto implicito degli [indici](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) e [supporto per intervalli impliciti](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) della [Nota relativa alla proposta di funzionalità](~/_csharplang/proposals/csharp-8.0/ranges.md).</span><span class="sxs-lookup"><span data-stu-id="fdba6-147">For more information, see the [Implicit Index support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-index-support) and [Implicit Range support](~/_csharplang/proposals/csharp-8.0/ranges.md#implicit-range-support) sections of the [feature proposal note](~/_csharplang/proposals/csharp-8.0/ranges.md).</span></span>

<span data-ttu-id="fdba6-148">I tipi .NET seguenti, ad esempio, supportano sia gli indici che gli intervalli: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601> e <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="fdba6-148">For example, the following .NET types support both indices and ranges: <xref:System.Array>, <xref:System.String>, <xref:System.Span%601>, and <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="fdba6-149">Il <xref:System.Collections.Generic.List%601> supporta gli indici, ma non supporta gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="fdba6-149">The <xref:System.Collections.Generic.List%601> supports indices but doesn't support ranges.</span></span>

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="fdba6-150">Scenari per gli indici e gli intervalli</span><span class="sxs-lookup"><span data-stu-id="fdba6-150">Scenarios for indices and ranges</span></span>

<span data-ttu-id="fdba6-151">Quando si vuole analizzare un intervallo secondario di un'intera sequenza, si usano spesso intervalli e indici.</span><span class="sxs-lookup"><span data-stu-id="fdba6-151">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="fdba6-152">La nuova sintassi è più chiara e consente di capire meglio la funzione dell'intervallo secondario.</span><span class="sxs-lookup"><span data-stu-id="fdba6-152">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="fdba6-153">La funzione locale `MovingAverage` accetta un <xref:System.Range> come argomento.</span><span class="sxs-lookup"><span data-stu-id="fdba6-153">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="fdba6-154">In seguito il metodo enumera solo quell'intervallo durante il calcolo dei valori minimo e massimo e della media.</span><span class="sxs-lookup"><span data-stu-id="fdba6-154">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="fdba6-155">Provare a includere il codice seguente nel progetto:</span><span class="sxs-lookup"><span data-stu-id="fdba6-155">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="fdba6-156">È possibile scaricare il codice completo dal repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="fdba6-156">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
