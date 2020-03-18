---
title: 'Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: f9a858dea74be63634f887c4204aefa8ac338ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75711233"
---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="ce694-102">Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="ce694-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>

<span data-ttu-id="ce694-103">Oltre a estrarre elementi da un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, è anche possibile usare [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) per rimuovere gli elementi finché l'aggiunta viene completata e la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="ce694-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="ce694-104">Questa operazione viene definita *enumerazione mutante* o *enumerazione di consumo* perché, a differenza di un ciclo `foreach` tipico (`For Each`), questo enumeratore modifica la raccolta di origine rimuovendo elementi.</span><span class="sxs-lookup"><span data-stu-id="ce694-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>

## <a name="example"></a><span data-ttu-id="ce694-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce694-105">Example</span></span>

<span data-ttu-id="ce694-106">L'esempio seguente illustra come rimuovere tutti gli elementi di un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando un ciclo `foreach` (`For Each`).</span><span class="sxs-lookup"><span data-stu-id="ce694-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

<span data-ttu-id="ce694-107">Questo esempio usa un ciclo `foreach` con il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> nel thread di consumo, che rimuove ogni elemento dalla raccolta mentre viene enumerato.</span><span class="sxs-lookup"><span data-stu-id="ce694-107">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="ce694-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limita il numero massimo di elementi presenti nella raccolta in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ce694-108"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="ce694-109">Tale enumerazione della raccolta blocca il thread consumer se non sono disponibili elementi o se la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="ce694-109">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="ce694-110">In questo esempio il blocco non rappresenta un problema perché il thread producer aggiunge elementi più velocemente di quanto possano essere usati.</span><span class="sxs-lookup"><span data-stu-id="ce694-110">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>

<span data-ttu-id="ce694-111">Non esiste alcuna garanzia che gli elementi vengano enumerati nello stesso ordine in cui sono stati aggiunti dai thread producer.</span><span class="sxs-lookup"><span data-stu-id="ce694-111">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>

<span data-ttu-id="ce694-112">Per enumerare la raccolta senza modificarla, usare `foreach` (`For Each`) senza il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce694-112">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="ce694-113">Tuttavia, è importante tenere presente che questo tipo di enumerazione rappresenta uno snapshot della raccolta in un momento preciso.</span><span class="sxs-lookup"><span data-stu-id="ce694-113">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="ce694-114">Se altri thread aggiungono o rimuovono elementi contemporaneamente mentre si esegue il ciclo, il ciclo potrebbe non rappresentare lo stato effettivo della raccolta.</span><span class="sxs-lookup"><span data-stu-id="ce694-114">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce694-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce694-115">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="ce694-116">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="ce694-116">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)
