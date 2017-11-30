---
title: 'Procedura: implementare partizioni dinamiche'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="96d2b-102">Procedura: implementare partizioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="96d2b-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="96d2b-103">Nell'esempio seguente viene illustrato come implementare un oggetto personalizzato <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> che implementa il partizionamento dinamico e può essere utilizzato da determinati overload <xref:System.Threading.Tasks.Parallel.ForEach%2A> e da PLINQ.</span><span class="sxs-lookup"><span data-stu-id="96d2b-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96d2b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="96d2b-104">Example</span></span>  
 <span data-ttu-id="96d2b-105">Ogni volta che una partizione chiama <xref:System.Collections.IEnumerator.MoveNext%2A> sull'enumeratore, l'enumeratore fornisce la partizione di un elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="96d2b-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="96d2b-106">Nel caso di PLINQ e <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partizione è un <xref:System.Threading.Tasks.Task> istanza.</span><span class="sxs-lookup"><span data-stu-id="96d2b-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="96d2b-107">Poiché le richieste vengono eseguite contemporaneamente su più thread, l'accesso all'indice corrente è sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="96d2b-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="96d2b-108">Questo è un esempio di partizionamento, con ogni blocco costituito da un elemento di blocco.</span><span class="sxs-lookup"><span data-stu-id="96d2b-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="96d2b-109">Fornendo più elementi alla volta, è possibile ridurre la contesa sul blocco e realizzare teoricamente prestazioni più veloci.</span><span class="sxs-lookup"><span data-stu-id="96d2b-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="96d2b-110">A un certo punto blocchi più grandi potrebbero tuttavia richiedere logica aggiuntiva di bilanciamento del carico per mantenere tutti i thread occupato fino al completamento di tutto il lavoro.</span><span class="sxs-lookup"><span data-stu-id="96d2b-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d2b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96d2b-111">See Also</span></span>  
 [<span data-ttu-id="96d2b-112">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="96d2b-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="96d2b-113">Procedura: Implementare un partitioner per il partizionamento statico</span><span class="sxs-lookup"><span data-stu-id="96d2b-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
