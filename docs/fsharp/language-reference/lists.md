---
title: Elenchi (F#)
description: 'Informazioni sugli elenchi di F #, una serie ordinata e non modificabile di elementi dello stesso tipo.'
ms.date: 05/16/2016
ms.openlocfilehash: 60e7edb56bdf498e3ba51aff028d8564eb68d0f1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47109858"
---
# <a name="lists"></a><span data-ttu-id="f0d06-103">Elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-103">Lists</span></span>

> [!NOTE]
<span data-ttu-id="f0d06-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="f0d06-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f0d06-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f0d06-106">Un elenco in F# è una serie ordinata e non modificabile di elementi dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-106">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="f0d06-107">Per eseguire operazioni di base sugli elenchi, usare le funzioni nel [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="f0d06-107">To perform basic operations on lists, use the functions in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="f0d06-108">Creazione e inizializzazione di elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-108">Creating and Initializing Lists</span></span>

<span data-ttu-id="f0d06-109">È possibile definire un elenco elencando in modo esplicito gli elementi, separati da punti e virgola e racchiusi tra parentesi quadre, come mostrato nella riga di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0d06-109">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="f0d06-110">È anche possibile inserire interruzioni di riga tra gli elementi e in questo caso i punti e virgola sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-110">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="f0d06-111">La sintassi precedente può agevolare la lettura del codice in caso di espressioni di inizializzazione degli elementi più lunghe o se si desidera includere un commento per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-111">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="f0d06-112">In genere, tutti gli elementi dell'elenco devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-112">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="f0d06-113">Fanno eccezione gli elenchi in cui gli elementi vengono specificati come tipi di base. Gli elementi di tali elenchi possono essere tipi derivati.</span><span class="sxs-lookup"><span data-stu-id="f0d06-113">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="f0d06-114">Sono pertanto accettabili gli elementi seguenti, poiché sia `Button` che `CheckBox` derivano da `Control`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-114">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="f0d06-115">È anche possibile definire gli elementi dell'elenco usando un intervallo indicato da numeri interi separati dall'operatore di intervallo (`..`), come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0d06-115">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="f0d06-116">Un elenco vuoto viene specificato da una coppia di parentesi quadre al cui interno non è presente alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-116">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="f0d06-117">È possibile anche usare un'espressione sequenza per creare un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-117">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="f0d06-118">Visualizzare [espressioni di sequenza](sequences.md#sequence-expressions) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="f0d06-118">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="f0d06-119">Ad esempio, il codice seguente crea un elenco di quadrati di numeri interi compresi tra 1 e 10.</span><span class="sxs-lookup"><span data-stu-id="f0d06-119">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="f0d06-120">Operatori per l'uso di elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-120">Operators for Working with Lists</span></span>

<span data-ttu-id="f0d06-121">È possibile associare elementi a un elenco usando l'operatore `::` (cons).</span><span class="sxs-lookup"><span data-stu-id="f0d06-121">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="f0d06-122">Se `list1` è `[2; 3; 4]`, il codice seguente crea `list2` come `[100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-122">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="f0d06-123">È possibile concatenare gli elenchi con tipi compatibili usando l'operatore `@`, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0d06-123">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="f0d06-124">Se `list1` è `[2; 3; 4]` e `list2` è `[100; 2; 3; 4 ]`, questo codice crea `list3` come `[2; 3; 4; 100; 2; 3; 4]`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-124">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4 ]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="f0d06-125">Sono disponibili nelle funzioni per l'esecuzione di operazioni sugli elenchi di [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="f0d06-125">Functions for performing operations on lists are available in the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span>

<span data-ttu-id="f0d06-126">Poiché gli elenchi in F# non sono modificabili, qualsiasi operazione di modifica comporta la generazione di nuovi elenchi anziché la modifica di quelli esistenti.</span><span class="sxs-lookup"><span data-stu-id="f0d06-126">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="f0d06-127">Gli elenchi in F # vengono implementati come elenchi collegati singolarmente, ovvero le operazioni che accedono solo all'elemento head dell'elenco sono o (1) e l'accesso all'elemento è O (*n*).</span><span class="sxs-lookup"><span data-stu-id="f0d06-127">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="f0d06-128">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f0d06-128">Properties</span></span>

<span data-ttu-id="f0d06-129">Il tipo di elenco supporta le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0d06-129">The list type supports the following properties:</span></span>

|<span data-ttu-id="f0d06-130">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f0d06-130">Property</span></span>|<span data-ttu-id="f0d06-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="f0d06-131">Type</span></span>|<span data-ttu-id="f0d06-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0d06-132">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="f0d06-133">Head</span><span class="sxs-lookup"><span data-stu-id="f0d06-133">Head</span></span>](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740)|`'T`|<span data-ttu-id="f0d06-134">Primo elemento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-134">The first element.</span></span>|
|[<span data-ttu-id="f0d06-135">vuota</span><span class="sxs-lookup"><span data-stu-id="f0d06-135">Empty</span></span>](https://msdn.microsoft.com/library/44406ecb-1918-4d32-b32a-ca1f69840386)|`'T list`|<span data-ttu-id="f0d06-136">Proprietà statica che restituisce un elenco vuoto del tipo appropriato.</span><span class="sxs-lookup"><span data-stu-id="f0d06-136">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="f0d06-137">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="f0d06-137">IsEmpty</span></span>](https://msdn.microsoft.com/library/3ba087b2-2fc2-406d-b10a-cff6a19322da)|`bool`|<span data-ttu-id="f0d06-138">`true` se nell'elenco non sono presenti elementi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-138">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="f0d06-139">Item</span><span class="sxs-lookup"><span data-stu-id="f0d06-139">Item</span></span>](https://msdn.microsoft.com/library/bdb2553a-0e54-4ff8-baed-ab1aac8f5dae)|`'T`|<span data-ttu-id="f0d06-140">Elemento in corrispondenza dell'indice specificato (a base zero).</span><span class="sxs-lookup"><span data-stu-id="f0d06-140">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="f0d06-141">Lunghezza</span><span class="sxs-lookup"><span data-stu-id="f0d06-141">Length</span></span>](https://msdn.microsoft.com/library/25f715c8-9daa-4c4d-a6c7-26772f9dab4d)|`int`|<span data-ttu-id="f0d06-142">Numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-142">The number of elements.</span></span>|
|[<span data-ttu-id="f0d06-143">Della parte finale del</span><span class="sxs-lookup"><span data-stu-id="f0d06-143">Tail</span></span>](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91)|`'T list`|<span data-ttu-id="f0d06-144">Elenco senza il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-144">The list without the first element.</span></span>|
<span data-ttu-id="f0d06-145">Di seguito sono riportati alcuni esempi per l'uso di queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0d06-145">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="f0d06-146">Uso degli elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-146">Using Lists</span></span>

<span data-ttu-id="f0d06-147">L'uso degli elenchi nella programmazione consente di eseguire operazioni complesse con una piccola quantità di codice.</span><span class="sxs-lookup"><span data-stu-id="f0d06-147">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="f0d06-148">Questa sezione descrive le operazioni comuni sugli elenchi, fondamentali ai fini della programmazione funzionale.</span><span class="sxs-lookup"><span data-stu-id="f0d06-148">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="f0d06-149">Ricorsione con elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-149">Recursion with Lists</span></span>

<span data-ttu-id="f0d06-150">Gli elenchi sono particolarmente adatti per le tecniche di programmazione ricorsive.</span><span class="sxs-lookup"><span data-stu-id="f0d06-150">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="f0d06-151">Nel caso di un'operazione da eseguire su ogni elemento di un elenco,</span><span class="sxs-lookup"><span data-stu-id="f0d06-151">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="f0d06-152">è possibile operare in modo ricorsivo sull'elemento head dell'elenco e quindi passare all'elemento tail, ovvero un elenco di dimensioni ridotte costituito dall'elenco originale senza il primo elemento, per poi tornare al livello successivo di ricorsione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-152">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="f0d06-153">Per scrivere una funzione ricorsiva di questo tipo, è necessario usare l'operatore cons (`::`) nei criteri di ricerca, per separare l'elemento head dell'elenco dall'elemento tail.</span><span class="sxs-lookup"><span data-stu-id="f0d06-153">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="f0d06-154">L'esempio di codice seguente illustra come usare i criteri di ricerca per implementare una funzione ricorsiva che esegue le operazioni su un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-154">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="f0d06-155">Il codice precedente è ideale per elenchi di piccole dimensioni, ma con gli elenchi di grandi dimensione potrebbe verificarsi un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="f0d06-155">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="f0d06-156">Il codice seguente migliora questo tipo di codice mediante un argomento dell'accumulatore, una tecnica standard per l'uso di funzioni ricorsive.</span><span class="sxs-lookup"><span data-stu-id="f0d06-156">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="f0d06-157">L'uso dell'argomento accumulatore rende ricorsivo la funzione tail, risparmiando spazio nello stack.</span><span class="sxs-lookup"><span data-stu-id="f0d06-157">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="f0d06-158">`RemoveAllMultiples` è una funzione ricorsiva che accetta due elenchi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-158">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="f0d06-159">Il primo elenco contiene i numeri di cui verranno rimossi i multipli e il secondo è l'elenco da cui rimuovere i numeri.</span><span class="sxs-lookup"><span data-stu-id="f0d06-159">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="f0d06-160">Il codice nell'esempio seguente usa questa funzione ricorsiva per eliminare tutti i numeri non primi da un elenco, restituendo come risultato un elenco di numeri primi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-160">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="f0d06-161">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-161">The output is as follows:</span></span>

```
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="f0d06-162">Funzioni di modulo</span><span class="sxs-lookup"><span data-stu-id="f0d06-162">Module Functions</span></span>

<span data-ttu-id="f0d06-163">Il [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) fornisce funzioni che gli elementi di un elenco di accesso.</span><span class="sxs-lookup"><span data-stu-id="f0d06-163">The [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788) provides functions that access the elements of a list.</span></span> <span data-ttu-id="f0d06-164">L'elemento head è il più veloce e più semplice a cui accedere.</span><span class="sxs-lookup"><span data-stu-id="f0d06-164">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="f0d06-165">Usare la proprietà [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) o alla funzione module [List. head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span><span class="sxs-lookup"><span data-stu-id="f0d06-165">Use the property [Head](https://msdn.microsoft.com/library/5f9414fd-6bdb-470a-8b72-40016db30740) or the module function [List.head](https://msdn.microsoft.com/library/22514cc5-0511-498b-a2cc-837b688a6da2).</span></span> <span data-ttu-id="f0d06-166">Della parte finale di un elenco è possibile accedere usando il [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) proprietà o il [List. tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f0d06-166">You can access the tail of a list by using the [Tail](https://msdn.microsoft.com/library/2a6f8eb9-dc32-41aa-8b62-2baffaface91) property or the [List.tail](https://msdn.microsoft.com/library/da0a0638-4420-4571-84b6-d09ae601f601) function.</span></span> <span data-ttu-id="f0d06-167">Per trovare un elemento in base all'indice, usare il [List. nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f0d06-167">To find an element by index, use the [List.nth](https://msdn.microsoft.com/library/1f717d57-89be-4007-a971-9cf5a28d83b1) function.</span></span> <span data-ttu-id="f0d06-168">`List.nth` attraversa l'elenco</span><span class="sxs-lookup"><span data-stu-id="f0d06-168">`List.nth` traverses the list.</span></span> <span data-ttu-id="f0d06-169">Pertanto, è O (*n*).</span><span class="sxs-lookup"><span data-stu-id="f0d06-169">Therefore, it is O(*n*).</span></span> <span data-ttu-id="f0d06-170">Se il codice usa `List.nth` in modo frequente, è opportuno considerare l'uso di una matrice anziché di un elenco</span><span class="sxs-lookup"><span data-stu-id="f0d06-170">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="f0d06-171">L'accesso agli elementi nelle matrici è O(1).</span><span class="sxs-lookup"><span data-stu-id="f0d06-171">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="f0d06-172">Operazioni booleane sugli elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-172">Boolean Operations on Lists</span></span>

<span data-ttu-id="f0d06-173">Il [List. isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) funzione determina se un elenco contiene tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-173">The [List.isEmpty](https://msdn.microsoft.com/library/a7941d44-9e92-427c-b806-c378f4558107) function determines whether a list has any elements.</span></span>

<span data-ttu-id="f0d06-174">Il [List. exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) funzione si applica un valore booleano test agli elementi di un elenco e restituisce `true` se un elemento qualsiasi soddisfa il test.</span><span class="sxs-lookup"><span data-stu-id="f0d06-174">The [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="f0d06-175">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) è simile ma opera su coppie consecutive di elementi in due elenchi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-175">[List.exists2](https://msdn.microsoft.com/library/7532b39e-3f4f-4534-a60b-d7721dc6fa7e) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="f0d06-176">Il codice seguente illustra l'uso di `List.exists`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-176">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="f0d06-177">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-177">The output is as follows:</span></span>

```
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="f0d06-178">L'esempio seguente illustra l'uso di `List.exists2`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-178">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="f0d06-179">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-179">The output is as follows:</span></span>

```
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="f0d06-180">È possibile usare [forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) se si vuole verificare se tutti gli elementi di un elenco soddisfano una condizione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-180">You can use [List.forall](https://msdn.microsoft.com/library/e11a5233-d612-40ac-833b-d5cf496900b7) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="f0d06-181">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-181">The output is as follows:</span></span>

```
true
false
```

<span data-ttu-id="f0d06-182">Analogamente, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determina se tutti gli elementi nelle posizioni corrispondenti dei due elenchi soddisfano un'espressione booleana che coinvolge ogni coppia di elementi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-182">Similarly, [List.forall2](https://msdn.microsoft.com/library/bb611f02-8277-48f5-9af3-6194ae27d07e) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="f0d06-183">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-183">The output is as follows:</span></span>

```
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="f0d06-184">Operazioni di ordinamento sugli elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-184">Sort Operations on Lists</span></span>

<span data-ttu-id="f0d06-185">Il [List. Sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List. sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), e [List. sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) funzioni ordinare gli elenchi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-185">The [List.sort](https://msdn.microsoft.com/library/17f1030e-aa7e-41dd-94ea-72cb6c04fd3d), [List.sortBy](https://msdn.microsoft.com/library/955bfc5f-ad9c-4f2d-a7ab-91e43eb21359), and [List.sortWith](https://msdn.microsoft.com/library/1d806a54-9166-4198-906d-15101f7916c7) functions sort lists.</span></span> <span data-ttu-id="f0d06-186">La funzione di ordinamento determina quali funzioni usare tra le tre indicate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f0d06-186">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="f0d06-187">`List.sort` usa il confronto generico predefinito.</span><span class="sxs-lookup"><span data-stu-id="f0d06-187">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="f0d06-188">Il confronto generico usa gli operatori globali basati sulla funzione di confronto generico per confrontare i valori.</span><span class="sxs-lookup"><span data-stu-id="f0d06-188">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="f0d06-189">È perfettamente compatibile con un'ampia gamma di tipi di elemento, ad esempio tipi numerici semplici, tuple, record, unioni discriminate, elenchi, matrici e qualsiasi tipo che implementa `System.IComparable`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-189">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="f0d06-190">Per i tipi che implementano `System.IComparable`, il confronto generico usa la funzione `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-190">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="f0d06-191">Il confronto generico usa anche le stringhe, ma adotta un ordinamento indipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f0d06-191">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="f0d06-192">Non è opportuno usare il confronto generico sui tipi non supportati, ad esempio i tipi di funzione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-192">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="f0d06-193">Le prestazioni del confronto generico predefinito risultano inoltre ottimali per i tipi strutturati di piccole dimensioni, mentre per i tipi strutturati di grandi dimensioni, che devono essere confrontati e ordinati con frequenza, provare a implementare `System.IComparable` e a fornire un'implementazione efficiente del metodo `System.IComparable.CompareTo()`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-193">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="f0d06-194">`List.sortBy` accetta una funzione che restituisce un valore usato come criterio di ordinamento e `List.sortWith` accetta una funzione di confronto come argomento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-194">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="f0d06-195">Queste ultime due funzioni risultano utili nel caso in cui vengano usati tipi che non supportano il confronto oppure se il confronto richiede una semantica più complessa, come nel caso di stringhe dipendenti dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f0d06-195">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="f0d06-196">L'esempio seguente illustra l'uso di `List.sort`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-196">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="f0d06-197">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-197">The output is as follows:</span></span>

```
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="f0d06-198">L'esempio seguente illustra l'uso di `List.sortBy`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-198">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="f0d06-199">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-199">The output is as follows:</span></span>

```
[1; -2; 4; 5; 8]
```

<span data-ttu-id="f0d06-200">L'esempio seguente illustra l'uso di `List.sortWith`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-200">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="f0d06-201">In questo esempio, la funzione di confronto personalizzato `compareWidgets` viene usata per confrontare in primo luogo un campo di un tipo personalizzato, quindi un altro campo, se i valori del primo campo sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f0d06-201">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="f0d06-202">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-202">The output is as follows:</span></span>

```
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="f0d06-203">Operazioni di ricerca sugli elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-203">Search Operations on Lists</span></span>

<span data-ttu-id="f0d06-204">Per gli elenchi sono supportate numerose operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="f0d06-204">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="f0d06-205">La più semplice, [List. Find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), consente di trovare il primo elemento che corrisponde a una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-205">The simplest, [List.find](https://msdn.microsoft.com/library/0594593e-9c75-44c1-8f5a-a37b2e561c06), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="f0d06-206">L'esempio di codice seguente illustra l'uso di `List.find` per trovare il primo numero divisibile per 5 in un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-206">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="f0d06-207">Il risultato è 5.</span><span class="sxs-lookup"><span data-stu-id="f0d06-207">The result is 5.</span></span>

<span data-ttu-id="f0d06-208">Se gli elementi devono essere trasformati prima di tutto, chiamare [Pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), che accetta una funzione che restituisce un'opzione e cerca la prima opzione valore che è `Some(x)`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-208">If the elements must be transformed first, call [List.pick](https://msdn.microsoft.com/library/0430b515-7fe4-49a1-a616-d2286d8b08b2), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="f0d06-209">Anziché restituire l'elemento, `List.pick` restituisce il risultato `x`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-209">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="f0d06-210">Se non viene trovato alcun elemento corrispondente, `List.pick` genera un'eccezione `System.Collections.Generic.KeyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-210">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="f0d06-211">Il codice seguente illustra l'uso di `List.pick`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-211">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="f0d06-212">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-212">The output is as follows:</span></span>

```
"b"
```

<span data-ttu-id="f0d06-213">Un altro gruppo di operazioni di ricerca [List. tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) e funzioni correlate, restituiscono un valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-213">Another group of search operations, [List.tryFind](https://msdn.microsoft.com/library/37f4532e-9fd0-4802-8bbd-e1aa2380287d) and related functions, return an option value.</span></span> <span data-ttu-id="f0d06-214">La funzione `List.tryFind` restituisce il primo elemento di un elenco che soddisfa una condizione se tale elemento è presente e il valore di opzione `None` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f0d06-214">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="f0d06-215">La variazione [List. tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) restituisce l'indice dell'elemento, se ne viene trovato, anziché l'elemento stesso.</span><span class="sxs-lookup"><span data-stu-id="f0d06-215">The variation [List.tryFindIndex](https://msdn.microsoft.com/library/5e31968c-c3d3-43d2-859a-0526825895ec) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="f0d06-216">Queste funzioni vengono illustrate nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0d06-216">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="f0d06-217">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-217">The output is as follows:</span></span>

```
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="f0d06-218">Operazioni aritmetiche sugli elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-218">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="f0d06-219">Operazioni aritmetiche comuni, ad esempio somma e Media sono integrate le [modulo List](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span><span class="sxs-lookup"><span data-stu-id="f0d06-219">Common arithmetic operations such as sum and average are built into the [List module](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788).</span></span> <span data-ttu-id="f0d06-220">Per lavorare con [List. Sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), il tipo di elemento di elenco deve supportare il `+` operatore e hanno un valore pari a zero.</span><span class="sxs-lookup"><span data-stu-id="f0d06-220">To work with [List.sum](https://msdn.microsoft.com/library/54d47fe3-5ecf-4883-beb5-e915342a17f9), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="f0d06-221">Tutti i tipi aritmetici incorporati soddisfano queste condizioni.</span><span class="sxs-lookup"><span data-stu-id="f0d06-221">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="f0d06-222">Per rivolgersi [Average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), il tipo di elemento deve supportare la divisione senza resto, esclusi i tipi integrali ma consente tipi a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="f0d06-222">To work with [List.average](https://msdn.microsoft.com/library/2b9a627b-106d-4548-8c4c-ab5058b8f8e1), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="f0d06-223">Il [List. sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) e [List. averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) funzioni accettano una funzione come parametro, i risultati della funzione vengono utilizzati per calcolare i valori per la somma o Media.</span><span class="sxs-lookup"><span data-stu-id="f0d06-223">The [List.sumBy](https://msdn.microsoft.com/library/b7623389-0fe1-4762-9c67-51079903ab7d) and [List.averageBy](https://msdn.microsoft.com/library/936cc9ec-62af-464d-8726-7999c2f48403) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="f0d06-224">Il codice seguente illustra l'uso di `List.sum`, `List.sumBy` e `List.average`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-224">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="f0d06-225">L'output è `1.000000`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-225">The output is `1.000000`.</span></span>

<span data-ttu-id="f0d06-226">Il codice seguente illustra l'uso di `List.averageBy`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-226">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="f0d06-227">L'output è `5.5`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-227">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="f0d06-228">Elenchi e tuple</span><span class="sxs-lookup"><span data-stu-id="f0d06-228">Lists and Tuples</span></span>

<span data-ttu-id="f0d06-229">Gli elenchi che contengono tuple possono essere modificati da funzioni di compressione e decompressione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-229">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="f0d06-230">Queste funzioni combinano due elenchi di valori singoli in un elenco di tuple o separano un elenco di tuple in due elenchi di valori singoli.</span><span class="sxs-lookup"><span data-stu-id="f0d06-230">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="f0d06-231">La più semplice [List. zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) funzione accetta due elenchi di elementi singoli e produce un unico elenco di coppie di tuple.</span><span class="sxs-lookup"><span data-stu-id="f0d06-231">The simplest [List.zip](https://msdn.microsoft.com/library/3028d790-8f48-4c94-bf08-b058bec3689c) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="f0d06-232">Un'altra versione, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), accetta tre elenchi di elementi singoli e produce un unico elenco di tuple con tre elementi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-232">Another version, [List.zip3](https://msdn.microsoft.com/library/003cc28e-0de3-4d99-89ed-cb19028e3c5b), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="f0d06-233">L'esempio di codice seguente illustra l'uso di `List.zip`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-233">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="f0d06-234">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-234">The output is as follows:</span></span>

```
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="f0d06-235">L'esempio di codice seguente illustra l'uso di `List.zip3`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-235">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="f0d06-236">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-236">The output is as follows:</span></span>

```
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="f0d06-237">Le versioni, decompresse corrispondenti [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) e [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), accettano elenchi di tuple e restituiscono elenchi in una tupla, in cui il primo elenco contiene tutti gli elementi che sono state inserite primi di ogni tupla e il secondo elenco contiene il secondo elemento di ogni tupla e così via.</span><span class="sxs-lookup"><span data-stu-id="f0d06-237">The corresponding unzip versions, [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21) and [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="f0d06-238">Esempio di codice seguente illustra l'uso del [List. unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span><span class="sxs-lookup"><span data-stu-id="f0d06-238">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="f0d06-239">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-239">The output is as follows:</span></span>

```
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="f0d06-240">Esempio di codice seguente illustra l'uso del [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span><span class="sxs-lookup"><span data-stu-id="f0d06-240">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="f0d06-241">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-241">The output is as follows:</span></span>

```
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="f0d06-242">Operazioni sugli elementi dell'elenco</span><span class="sxs-lookup"><span data-stu-id="f0d06-242">Operating on List Elements</span></span>

<span data-ttu-id="f0d06-243">F# supporta un'ampia gamma di operazioni sugli elementi di un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-243">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="f0d06-244">È la più semplice [List. iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), che consente di chiamare una funzione su ogni elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-244">The simplest is [List.iter](https://msdn.microsoft.com/library/f778d075-81a9-4994-af60-cddcc53a201f), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="f0d06-245">Includono le variazioni [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), che consente di eseguire un'operazione su elementi di due elenchi, [List. iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), che è simile a `List.iter` ad eccezione del fatto che l'indice di ogni elemento viene passato come un argomento della funzione che viene chiamata per ogni elemento, e [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), ovvero una combinazione delle funzionalità del `List.iter2` e `List.iteri`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-245">Variations include [List.iter2](https://msdn.microsoft.com/library/ea3b7761-916c-4016-9bd8-651124c98b40), which enables you to perform an operation on elements of two lists, [List.iteri](https://msdn.microsoft.com/library/6dd21ae6-5c00-41cd-8306-821e513d8f60), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://msdn.microsoft.com/library/9658d740-9be5-4bf7-b663-c8ab2b3e196c), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="f0d06-246">Queste funzioni vengono illustrate nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f0d06-246">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="f0d06-247">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-247">The output is as follows:</span></span>

```
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="f0d06-248">Un'altra funzione usata di frequente che trasforma gli elementi dell'elenco viene [Map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), che consente di applicare una funzione a ogni elemento di un elenco e di inserire tutti i risultati in un nuovo elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-248">Another frequently used function that transforms list elements is [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="f0d06-249">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) e [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) sono variazioni che accettano più elenchi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-249">[List.map2](https://msdn.microsoft.com/library/5f48cce7-6eaf-4e54-8996-2b04d3c31e57) and [List.map3](https://msdn.microsoft.com/library/dd9fb190-6980-4537-be96-5645a64908f8) are variations that take multiple lists.</span></span> <span data-ttu-id="f0d06-250">È anche possibile usare [List. MAPI](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) e [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), se, oltre all'elemento, è necessario passare l'indice di ogni elemento di funzione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-250">You can also use [List.mapi](https://msdn.microsoft.com/library/284b9234-3d26-409b-b328-ac79638d9e14) and [List.mapi2](https://msdn.microsoft.com/library/680643af-233c-40a3-82f2-43d5af27ec49), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="f0d06-251">L'unica differenza tra `List.mapi2` e `List.mapi` consiste nel fatto che `List.mapi2` usa due elenchi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-251">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="f0d06-252">L'esempio seguente illustra [Map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span><span class="sxs-lookup"><span data-stu-id="f0d06-252">The following example illustrates [List.map](https://msdn.microsoft.com/library/c6b49c99-d4f3-4ba3-b1d0-85a312683dc6).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="f0d06-253">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-253">The output is as follows:</span></span>

```
[2; 3; 4]
```

<span data-ttu-id="f0d06-254">L'esempio seguente illustra l'uso di `List.map2`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-254">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="f0d06-255">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-255">The output is as follows:</span></span>

```
[5; 7; 9]
```

<span data-ttu-id="f0d06-256">L'esempio seguente illustra l'uso di `List.map3`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-256">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="f0d06-257">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-257">The output is as follows:</span></span>

```
[7; 10; 13]
```

<span data-ttu-id="f0d06-258">L'esempio seguente illustra l'uso di `List.mapi`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-258">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="f0d06-259">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-259">The output is as follows:</span></span>

```
[1; 3; 5]
```

<span data-ttu-id="f0d06-260">L'esempio seguente illustra l'uso di `List.mapi2`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-260">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="f0d06-261">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-261">The output is as follows:</span></span>

```
[0; 7; 18]
```

<span data-ttu-id="f0d06-262">[List. Collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) è simile a `List.map`, ad eccezione del fatto che ogni elemento produce un elenco e tutti questi elenchi vengono concatenati in un elenco finale.</span><span class="sxs-lookup"><span data-stu-id="f0d06-262">[List.collect](https://msdn.microsoft.com/library/cd08bbc7-a3b9-40ab-8c20-4e85ec84664f) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="f0d06-263">Nel codice seguente ogni elemento dell'elenco genera tre numeri,</span><span class="sxs-lookup"><span data-stu-id="f0d06-263">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="f0d06-264">che vengono raccolti in un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-264">These are all collected into one list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="f0d06-265">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-265">The output is as follows:</span></span>

```
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="f0d06-266">È anche possibile usare [List. Filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), che accetta una condizione booleana e produce un nuovo elenco costituito solo da elementi che soddisfano la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="f0d06-266">You can also use [List.filter](https://msdn.microsoft.com/library/11a8c926-547b-44dd-bbae-98d44f3dd248), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="f0d06-267">L'elenco risultante è `[2; 4; 6]`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-267">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="f0d06-268">Una combinazione di mapping e filtro [List. choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) consente di trasformare e selezionare gli elementi nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-268">A combination of map and filter, [List.choose](https://msdn.microsoft.com/library/2e21d3fb-ce35-4824-8a57-c4404616093d) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="f0d06-269">`List.choose` applica una funzione che restituisce un'opzione a ogni elemento di un elenco e restituisce un nuovo elenco dei risultati per gli elementi quando la funzione restituisce il valore di opzione `Some`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-269">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="f0d06-270">Il codice seguente illustra l'uso di `List.choose` per selezionare parole in lettere maiuscole da un elenco di parole.</span><span class="sxs-lookup"><span data-stu-id="f0d06-270">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="f0d06-271">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f0d06-271">The output is as follows:</span></span>

```
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="f0d06-272">Operazioni su più elenchi</span><span class="sxs-lookup"><span data-stu-id="f0d06-272">Operating on Multiple Lists</span></span>

<span data-ttu-id="f0d06-273">Gli elenchi possono essere uniti.</span><span class="sxs-lookup"><span data-stu-id="f0d06-273">Lists can be joined together.</span></span> <span data-ttu-id="f0d06-274">Per unire due elenchi, usare [List. Append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span><span class="sxs-lookup"><span data-stu-id="f0d06-274">To join two lists into one, use [List.append](https://msdn.microsoft.com/library/2954da80-3f4a-4a4b-9371-794645c03426).</span></span> <span data-ttu-id="f0d06-275">Per unire più di due elenchi, usare [Concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span><span class="sxs-lookup"><span data-stu-id="f0d06-275">To join more than two lists, use [List.concat](https://msdn.microsoft.com/library/c5afd433-8764-4ea8-a6a8-937fb4d77c4c).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="f0d06-276">Operazioni di riduzione e analisi</span><span class="sxs-lookup"><span data-stu-id="f0d06-276">Fold and Scan Operations</span></span>

<span data-ttu-id="f0d06-277">Alcune operazioni sugli elenchi comportano interdipendenze tra tutti gli elementi di un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-277">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="f0d06-278">Le operazioni di riduzione e analisi sono analoghe `List.iter` e `List.map` che si richiama una funzione su ogni elemento, ma queste operazioni forniscono un parametro aggiuntivo, denominato il *accumulatore* che trasmette informazioni il calcolo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-278">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="f0d06-279">Usare `List.fold` per eseguire un calcolo in un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-279">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="f0d06-280">Esempio di codice seguente illustra l'uso del [List. fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) per eseguire diverse operazioni.</span><span class="sxs-lookup"><span data-stu-id="f0d06-280">The following code example demonstrates the use of [List.fold](https://msdn.microsoft.com/library/c272779e-bae7-4983-8d7f-16b345bb33a0) to perform various operations.</span></span>

<span data-ttu-id="f0d06-281">L'elenco viene attraversato. L'accumulatore `acc` è un valore passato contestualmente all'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-281">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="f0d06-282">Il primo argomento accetta l'accumulatore e l'elemento dell'elenco e restituisce il risultato provvisorio del calcolo per l'elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-282">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="f0d06-283">Il secondo argomento è il valore iniziale dell'accumulatore.</span><span class="sxs-lookup"><span data-stu-id="f0d06-283">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="f0d06-284">Le versioni di queste funzioni che contengono una cifra nel nome della funzione consentono di eseguire operazioni su più di un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-284">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="f0d06-285">Ad esempio, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) esegue calcoli su due elenchi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-285">For example, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) performs computations on two lists.</span></span>

<span data-ttu-id="f0d06-286">L'esempio seguente illustra l'uso di `List.fold2`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-286">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="f0d06-287">`List.fold` e [List. scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differiscono in quanto `List.fold` restituisce il valore finale del parametro aggiuntivo, ma `List.scan` restituisce l'elenco dei valori intermedi (insieme al valore finale) del parametro aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-287">`List.fold` and [List.scan](https://msdn.microsoft.com/library/21f636db-885c-4a72-970e-e3841f33a1b8) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="f0d06-288">Ognuna di queste funzioni include una variazione inversa, ad esempio, [foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), che differisce nell'ordine in cui l'elenco viene attraversato e l'ordine degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="f0d06-288">Each of these functions includes a reverse variation, for example, [List.foldBack](https://msdn.microsoft.com/library/b9a58e66-efe1-445f-a90c-ac9ffb9d40c7), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="f0d06-289">È inoltre `List.fold` e `List.foldBack` hanno varianti [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) e [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), che accettano due elenchi di uguale lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f0d06-289">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://msdn.microsoft.com/library/6cfcd043-a65d-4423-805a-2ab234cb5343) and [List.foldBack2](https://msdn.microsoft.com/library/56371d3e-5271-4183-9e8c-15a02eda9aa2), that take two lists of equal length.</span></span> <span data-ttu-id="f0d06-290">La funzione eseguita su ogni elemento può usare elementi corrispondenti di entrambi gli elenchi per eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="f0d06-290">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="f0d06-291">I tipi di elementi dei due elenchi possono essere diversi, come nell'esempio seguente, in cui un elenco contiene importi di transazioni per un conto bancario e l'altro contiene il tipo di transazione (deposito o prelievo).</span><span class="sxs-lookup"><span data-stu-id="f0d06-291">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="f0d06-292">Per un calcolo quale una somma, `List.fold` e `List.foldBack` producono lo stesso effetto, poiché il risultato non dipende dall'ordine di attraversamento.</span><span class="sxs-lookup"><span data-stu-id="f0d06-292">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="f0d06-293">Nell'esempio seguente viene usato `List.foldBack` per aggiungere gli elementi a un elenco.</span><span class="sxs-lookup"><span data-stu-id="f0d06-293">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="f0d06-294">Per l'esempio seguente viene nuovamente usato il conto bancario precedente.</span><span class="sxs-lookup"><span data-stu-id="f0d06-294">The following example returns to the bank account example.</span></span> <span data-ttu-id="f0d06-295">Questa volta viene aggiunto un nuovo tipo di transazione: il calcolo degli interessi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-295">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="f0d06-296">Il saldo finale dipende ora dall'ordine delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="f0d06-296">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="f0d06-297">La funzione [reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) un'operazione simile `List.fold` e `List.scan`, ad eccezione del fatto che anziché passare un accumulatore separato, `List.reduce` accetta una funzione che accetta due argomenti del tipo di elemento anziché solo uno e uno di questi argomenti funge da accumulatore, ovvero archivia il risultato intermedio del calcolo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-297">The function [List.reduce](https://msdn.microsoft.com/library/048e1f95-691b-49cb-bb99-fb85f68f3d8b) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="f0d06-298">`List.reduce` esegue innanzitutto le operazioni sui primi due elementi dell'elenco, quindi usa il risultato dell'operazione insieme all'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-298">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="f0d06-299">Poiché nessun accumulatore separato ha un proprio tipo, `List.reduce` può essere usato al posto di `List.fold` solo se l'accumulatore e il tipo di elemento hanno lo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="f0d06-299">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="f0d06-300">Il codice seguente illustra l'uso di `List.reduce`.</span><span class="sxs-lookup"><span data-stu-id="f0d06-300">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="f0d06-301">`List.reduce` genera un'eccezione se l'elenco fornito non contiene elementi.</span><span class="sxs-lookup"><span data-stu-id="f0d06-301">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="f0d06-302">Nel codice seguente per la prima chiamata all'espressione lambda vengono forniti gli argomenti 2 e 4, quindi la chiamata restituisce 6. Per la chiamata successiva vengono forniti gli argomenti 6 e 10, pertanto il risultato è 16.</span><span class="sxs-lookup"><span data-stu-id="f0d06-302">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="f0d06-303">Conversione tra elenchi e altri tipi di raccolta</span><span class="sxs-lookup"><span data-stu-id="f0d06-303">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="f0d06-304">Il modulo `List` fornisce funzioni per la conversione da e verso sequenze e matrici.</span><span class="sxs-lookup"><span data-stu-id="f0d06-304">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="f0d06-305">Per eseguire la conversione da o verso una sequenza, usare [List. toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) oppure [List. ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span><span class="sxs-lookup"><span data-stu-id="f0d06-305">To convert to or from a sequence, use [List.toSeq](https://msdn.microsoft.com/library/7024be4b-ee70-43cc-8d0a-e6564a4ff7c0) or [List.ofSeq](https://msdn.microsoft.com/library/74ab9289-4a59-4433-92eb-3f662d7f7db0).</span></span> <span data-ttu-id="f0d06-306">Per eseguire la conversione da o verso una matrice, usare [List. toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) oppure [List. ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span><span class="sxs-lookup"><span data-stu-id="f0d06-306">To convert to or from an array, use [List.toArray](https://msdn.microsoft.com/library/ac87dd82-a0cd-40b3-b1fa-dd3168134547) or [List.ofArray](https://msdn.microsoft.com/library/f4bddc26-8c8f-4307-a6d7-a49dceb97032).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="f0d06-307">Operazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="f0d06-307">Additional Operations</span></span>

<span data-ttu-id="f0d06-308">Per informazioni su altre operazioni sugli elenchi, vedere l'argomento di riferimento della libreria [modulo Collections. List](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="f0d06-308">For information about additional operations on lists, see the library reference topic [Collections.List Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.list-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0d06-309">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0d06-309">See also</span></span>

- [<span data-ttu-id="f0d06-310">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f0d06-310">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f0d06-311">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="f0d06-311">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="f0d06-312">Sequenze</span><span class="sxs-lookup"><span data-stu-id="f0d06-312">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="f0d06-313">Array</span><span class="sxs-lookup"><span data-stu-id="f0d06-313">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="f0d06-314">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f0d06-314">Options</span></span>](options.md)
