---
title: Esplorare intervalli di dati con indici e intervalli
description: Questa esercitazione avanzata descrive come esplorare i dati usando indici e intervalli per esaminare le sezioni di un set di dati sequenziale.
ms.date: 04/19/2019
ms.custom: mvc
ms.openlocfilehash: d53f32bcb310d4859cea67a742ac0e2c4be5d942
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70105779"
---
# <a name="indices-and-ranges"></a><span data-ttu-id="19d9b-103">Indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="19d9b-103">Indices and ranges</span></span>

<span data-ttu-id="19d9b-104">Gli intervalli e gli indici offrono una sintassi concisa per accedere a elementi singoli o a intervalli secondari in un oggetto <xref:System.Array>, <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="19d9b-104">Ranges and indices provide a succinct syntax for accessing single elements or ranges in an <xref:System.Array>, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="19d9b-105">Queste funzionalità offrono una sintassi più concisa e chiara per accedere a elementi singoli o a intervalli di elementi in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="19d9b-105">These features enable more concise, clear syntax to access single elements or ranges of elements in a sequence.</span></span>

<span data-ttu-id="19d9b-106">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="19d9b-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="19d9b-107">Usare la sintassi per gli intervalli in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="19d9b-107">Use the syntax for ranges in a sequence.</span></span>
> - <span data-ttu-id="19d9b-108">Comprendere le decisioni a livello di progettazione per l'inizio e la fine di ogni sequenza.</span><span class="sxs-lookup"><span data-stu-id="19d9b-108">Understand the design decisions for the start and end of each sequence.</span></span>
> - <span data-ttu-id="19d9b-109">Analizzare gli scenari per i tipi <xref:System.Index> e <xref:System.Range>.</span><span class="sxs-lookup"><span data-stu-id="19d9b-109">Learn scenarios for the <xref:System.Index> and <xref:System.Range> types.</span></span>

## <a name="language-support-for-indices-and-ranges"></a><span data-ttu-id="19d9b-110">Supporto del linguaggio per indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="19d9b-110">Language support for indices and ranges</span></span>

<span data-ttu-id="19d9b-111">Questo supporto del linguaggio si basa su due nuovi tipi e due nuovi operatori.</span><span class="sxs-lookup"><span data-stu-id="19d9b-111">This language support relies on two new types and two new operators.</span></span>
- <span data-ttu-id="19d9b-112"><xref:System.Index?displayProperty=nameWithType> rappresenta un indice in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="19d9b-112"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="19d9b-113">L'operatore `^`, che specifica che un indice è relativo alla fine di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="19d9b-113">The `^` operator, which specifies that an index is relative to the end of a sequence.</span></span>
- <span data-ttu-id="19d9b-114"><xref:System.Range?displayProperty=nameWithType> rappresenta un intervallo secondario di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="19d9b-114"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="19d9b-115">L'operatore Range (`..`), che specifica l'inizio e fine di un intervallo come operandi.</span><span class="sxs-lookup"><span data-stu-id="19d9b-115">The Range operator (`..`), which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="19d9b-116">Per iniziare, ecco come funzionano le regole per gli indici.</span><span class="sxs-lookup"><span data-stu-id="19d9b-116">Let's start with the rules for indices.</span></span> <span data-ttu-id="19d9b-117">Prendere in considerazione una matrice `sequence`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-117">Consider an array `sequence`.</span></span> <span data-ttu-id="19d9b-118">L'indice `0` è uguale a `sequence[0]`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-118">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="19d9b-119">L'indice `^0` è uguale a `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-119">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="19d9b-120">Si noti che `sequence[^0]` genera un'eccezione, proprio come `sequence[sequence.Length]`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-120">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="19d9b-121">Per qualsiasi numero `n`, l'indice `^n` è uguale a `sequence[sequence.Length - n]`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-121">For any number `n`, the index `^n` is the same as `sequence[sequence.Length - n]`.</span></span>

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

<span data-ttu-id="19d9b-122">È possibile recuperare l'ultima parola con l'indice `^1`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-122">You can retrieve the last word with the `^1` index.</span></span> <span data-ttu-id="19d9b-123">Aggiungere il codice seguente sotto l'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="19d9b-123">Add the following code below the initialization:</span></span>

[!code-csharp[LastIndex](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastIndex)]

<span data-ttu-id="19d9b-124">Un intervallo specifica *inizio* e *fine* di un intervallo.</span><span class="sxs-lookup"><span data-stu-id="19d9b-124">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="19d9b-125">Gli intervalli sono esclusivi, vale a dire che la *fine* non è inclusa nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="19d9b-125">Ranges are exclusive, meaning the *end* is not included in the range.</span></span> <span data-ttu-id="19d9b-126">L'intervallo `[0..^0]` rappresenta l'intero intervallo, proprio come `[0..sequence.Length]` rappresenta l'intero intervallo.</span><span class="sxs-lookup"><span data-stu-id="19d9b-126">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span> 

<span data-ttu-id="19d9b-127">Il codice seguente crea un intervallo secondario con le parole "quick", "brown" e "fox".</span><span class="sxs-lookup"><span data-stu-id="19d9b-127">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="19d9b-128">Include da `words[1]` a `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-128">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="19d9b-129">L'elemento `words[4]` non è compreso nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="19d9b-129">The element `words[4]` isn't in the range.</span></span> <span data-ttu-id="19d9b-130">Aggiungere il codice seguente allo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="19d9b-130">Add the following code to the same method.</span></span> <span data-ttu-id="19d9b-131">Copiarlo e incollarlo nella parte inferiore della finestra interattiva.</span><span class="sxs-lookup"><span data-stu-id="19d9b-131">Copy and paste it at the bottom of the interactive window.</span></span>

[!code-csharp[Range](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Range)]

<span data-ttu-id="19d9b-132">Il codice seguente crea un intervallo secondario con "lazy" e "dog".</span><span class="sxs-lookup"><span data-stu-id="19d9b-132">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="19d9b-133">Include `words[^2]` e `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="19d9b-133">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="19d9b-134">L'indice finale `words[^0]` non viene incluso.</span><span class="sxs-lookup"><span data-stu-id="19d9b-134">The end index `words[^0]` isn't included.</span></span> <span data-ttu-id="19d9b-135">Aggiungere anche il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="19d9b-135">Add the following code as well:</span></span>

[!code-csharp[LastRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_LastRange)]

<span data-ttu-id="19d9b-136">Gli esempi seguenti creano intervalli aperti alle estremità, per l'inizio, la fine o entrambe:</span><span class="sxs-lookup"><span data-stu-id="19d9b-136">The following examples create ranges that are open ended for the start, end, or both:</span></span>

[!code-csharp[PartialRange](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_PartialRanges)]

<span data-ttu-id="19d9b-137">È anche possibile dichiarare gli intervalli o gli indici come variabili.</span><span class="sxs-lookup"><span data-stu-id="19d9b-137">You can also declare ranges or indices as variables.</span></span> <span data-ttu-id="19d9b-138">In seguito la variabile può essere usata all'interno dei caratteri `[` e `]`:</span><span class="sxs-lookup"><span data-stu-id="19d9b-138">The variable can then be used inside the `[` and `]` characters:</span></span>

[!code-csharp[IndexRangeTypes](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_RangeIndexTypes)]

<span data-ttu-id="19d9b-139">L'esempio seguente illustra molti dei motivi per cui sono state fatte tali scelte.</span><span class="sxs-lookup"><span data-stu-id="19d9b-139">The following sample shows many of the reasons for those choices.</span></span> <span data-ttu-id="19d9b-140">Modificare `x`, `y`, e `z` per provare combinazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="19d9b-140">Modify `x`, `y`, and `z` to try different combinations.</span></span> <span data-ttu-id="19d9b-141">Durante le varie prove, usare valori per cui `x` è minore di `y` e `y` è minore di `z` per le combinazioni valide.</span><span class="sxs-lookup"><span data-stu-id="19d9b-141">When you experiment, use values where `x` is less than `y`, and `y` is less than `z` for valid combinations.</span></span> <span data-ttu-id="19d9b-142">Aggiungere il codice seguente in un nuovo metodo.</span><span class="sxs-lookup"><span data-stu-id="19d9b-142">Add the following code in a new method.</span></span> <span data-ttu-id="19d9b-143">Provare combinazioni diverse:</span><span class="sxs-lookup"><span data-stu-id="19d9b-143">Try different combinations:</span></span>

[!code-csharp[SemanticsExamples](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_Semantics)]

## <a name="scenarios-for-indices-and-ranges"></a><span data-ttu-id="19d9b-144">Scenari per indici e intervalli</span><span class="sxs-lookup"><span data-stu-id="19d9b-144">Scenarios for Indices and Ranges</span></span>

<span data-ttu-id="19d9b-145">Quando si vuole analizzare un intervallo secondario di un'intera sequenza, si usano spesso intervalli e indici.</span><span class="sxs-lookup"><span data-stu-id="19d9b-145">You'll often use ranges and indices when you want to perform some analysis on subrange of an entire sequence.</span></span> <span data-ttu-id="19d9b-146">La nuova sintassi è più chiara e consente di capire meglio la funzione dell'intervallo secondario.</span><span class="sxs-lookup"><span data-stu-id="19d9b-146">The new syntax is clearer in reading exactly what subrange is involved.</span></span> <span data-ttu-id="19d9b-147">La funzione locale `MovingAverage` accetta un <xref:System.Range> come argomento.</span><span class="sxs-lookup"><span data-stu-id="19d9b-147">The local function `MovingAverage` takes a <xref:System.Range> as its argument.</span></span> <span data-ttu-id="19d9b-148">In seguito il metodo enumera solo quell'intervallo durante il calcolo dei valori minimo e massimo e della media.</span><span class="sxs-lookup"><span data-stu-id="19d9b-148">The method then enumerates just that range when calculating the min, max, and average.</span></span> <span data-ttu-id="19d9b-149">Provare a includere il codice seguente nel progetto:</span><span class="sxs-lookup"><span data-stu-id="19d9b-149">Try the following code in your project:</span></span>

[!code-csharp[MovingAverages](~/samples/csharp/tutorials/RangesIndexes/IndicesAndRanges.cs#IndicesAndRanges_MovingAverage)]

<span data-ttu-id="19d9b-150">È possibile scaricare il codice completo dal repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes).</span><span class="sxs-lookup"><span data-stu-id="19d9b-150">You can download the completed code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/RangesIndexes) repository.</span></span>
