---
title: 'Procedura: implementare partizioni dinamiche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2d46264113cb4c961f6c4b971b5986bdd9eb6a7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44180972"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="d0a22-102">Procedura: implementare partizioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="d0a22-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="d0a22-103">L'esempio seguente mostra come implementare un oggetto <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizzato che implementa il partizionamento dinamico e che può essere usato da determinati overload <xref:System.Threading.Tasks.Parallel.ForEach%2A> e da PLINQ.</span><span class="sxs-lookup"><span data-stu-id="d0a22-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0a22-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0a22-104">Example</span></span>  
 <span data-ttu-id="d0a22-105">Ogni volta che una partizione chiama <xref:System.Collections.IEnumerator.MoveNext%2A> nell'enumeratore, l'enumeratore fornisce la partizione con un elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0a22-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="d0a22-106">Nel caso di PLINQ e di <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partizione è un'istanza <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="d0a22-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="d0a22-107">Poiché le richieste vengono eseguite contemporaneamente su più thread, l'accesso all'indice corrente è sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="d0a22-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="d0a22-108">Questo è un esempio di partizionamento in blocchi, con ogni blocco costituito da un elemento.</span><span class="sxs-lookup"><span data-stu-id="d0a22-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="d0a22-109">Fornendo più elementi per volta, è possibile ridurre il conflitto sul blocco e ottenere in teoria prestazioni più veloci.</span><span class="sxs-lookup"><span data-stu-id="d0a22-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="d0a22-110">A un certo punto, tuttavia, blocchi più grandi potrebbero richiedere logica di bilanciamento del carico aggiuntiva per mantenere occupati tutti i thread fino al completamento del lavoro.</span><span class="sxs-lookup"><span data-stu-id="d0a22-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a22-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0a22-111">See also</span></span>

- [<span data-ttu-id="d0a22-112">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="d0a22-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
- [<span data-ttu-id="d0a22-113">Procedura: Implementare un partitioner per il partizionamento statico</span><span class="sxs-lookup"><span data-stu-id="d0a22-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
