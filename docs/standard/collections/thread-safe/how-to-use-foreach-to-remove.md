---
title: 'Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b0f0ed30ae5192ed8a8f069d591855857bd2fa49
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a><span data-ttu-id="9cbe6-102">Procedura: utilizzare ForEach per rimuovere elementi in un oggetto BlockingCollection</span><span class="sxs-lookup"><span data-stu-id="9cbe6-102">How to: Use ForEach to Remove Items in a BlockingCollection</span></span>
<span data-ttu-id="9cbe6-103">Oltre a estrarre elementi da un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> e <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, è anche possibile usare [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) per rimuovere gli elementi finché l'aggiunta viene completata e la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-103">In addition to taking items from a <xref:System.Collections.Concurrent.BlockingCollection%601> by using the <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> method, you can also use a [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) in Visual Basic) to remove items until adding is completed and the collection is empty.</span></span> <span data-ttu-id="9cbe6-104">Questa operazione viene definita *enumerazione mutante* o *enumerazione di consumo* perché, a differenza di un ciclo `foreach` tipico (`For Each`), questo enumeratore modifica la raccolta di origine rimuovendo elementi.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-104">This is called a *mutating enumeration* or *consuming enumeration* because, unlike a typical `foreach` (`For Each`) loop, this enumerator modifies the source collection by removing items.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cbe6-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9cbe6-105">Example</span></span>  
 <span data-ttu-id="9cbe6-106">L'esempio seguente illustra come rimuovere tutti gli elementi di un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601> usando un ciclo `foreach` (`For Each`).</span><span class="sxs-lookup"><span data-stu-id="9cbe6-106">The following example shows how to remove all the items in a <xref:System.Collections.Concurrent.BlockingCollection%601> by using a `foreach` (`For Each`) loop.</span></span>  
  
 <span data-ttu-id="9cbe6-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span><span class="sxs-lookup"><span data-stu-id="9cbe6-107">[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)] [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]</span></span>  
  
 <span data-ttu-id="9cbe6-108">Questo esempio usa un ciclo `foreach` con il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> nel thread di consumo, che rimuove ogni elemento dalla raccolta mentre viene enumerato.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-108">This example uses a `foreach` loop with the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> method in the consuming thread, which causes each item to be removed from the collection as it is enumerated.</span></span> <span data-ttu-id="9cbe6-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limita il numero massimo di elementi presenti nella raccolta in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-109"><xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limits the maximum number of items that are in the collection at any time.</span></span> <span data-ttu-id="9cbe6-110">Tale enumerazione della raccolta blocca il thread consumer se non sono disponibili elementi o se la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-110">Enumerating the collection in this way blocks the consumer thread if no items are available or if the collection is empty.</span></span> <span data-ttu-id="9cbe6-111">In questo esempio il blocco non rappresenta un problema perché il thread producer aggiunge elementi più velocemente di quanto possano essere usati.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-111">In this example blocking is not a concern because the producer thread adds items faster than they can be consumed.</span></span>  
  
 <span data-ttu-id="9cbe6-112">Non esiste alcuna garanzia che gli elementi vengano enumerati nello stesso ordine in cui sono stati aggiunti dai thread producer.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-112">There is no guarantee that the items are enumerated in the same order in which they are added by the producer threads.</span></span>  
  
 <span data-ttu-id="9cbe6-113">Per enumerare la raccolta senza modificarla, usare `foreach` (`For Each`) senza il metodo <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-113">To enumerate the collection without modifying it, just use `foreach` (`For Each`) without the <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A> method.</span></span> <span data-ttu-id="9cbe6-114">Tuttavia, è importante tenere presente che questo tipo di enumerazione rappresenta uno snapshot della raccolta in un momento preciso.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-114">However, it is important to understand that this kind of enumeration represents a snapshot of the collection at a precise point in time.</span></span> <span data-ttu-id="9cbe6-115">Se altri thread aggiungono o rimuovono elementi contemporaneamente mentre si esegue il ciclo, il ciclo potrebbe non rappresentare lo stato effettivo della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9cbe6-115">If other threads are adding or removing items concurrently while you are executing the loop, then the loop might not represent the actual state of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbe6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cbe6-116">See Also</span></span>  
 <span data-ttu-id="9cbe6-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9cbe6-117"><xref:System.Collections.Concurrent?displayProperty=fullName></span></span>   
 [<span data-ttu-id="9cbe6-118">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="9cbe6-118">Parallel Programming</span></span>](../../../../docs/standard/parallel-programming/index.md)

