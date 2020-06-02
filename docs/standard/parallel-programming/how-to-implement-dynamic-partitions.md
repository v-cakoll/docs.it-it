---
title: 'Procedura: Implementare partizioni dinamiche'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 197e71cf4f00c98891e58e5f72974c0ec407e6ce
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288446"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="223d2-102">Procedura: Implementare partizioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="223d2-102">How to: Implement Dynamic Partitions</span></span>

<span data-ttu-id="223d2-103">L'esempio seguente mostra come implementare un oggetto <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizzato che implementa il partizionamento dinamico e che può essere usato da determinati overload <xref:System.Threading.Tasks.Parallel.ForEach%2A> e da PLINQ.</span><span class="sxs-lookup"><span data-stu-id="223d2-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="223d2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="223d2-104">Example</span></span>

<span data-ttu-id="223d2-105">Ogni volta che una partizione chiama <xref:System.Collections.IEnumerator.MoveNext%2A> nell'enumeratore, l'enumeratore fornisce la partizione con un elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="223d2-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="223d2-106">Nel caso di PLINQ e di <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partizione è un'istanza <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="223d2-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="223d2-107">Poiché le richieste vengono eseguite contemporaneamente su più thread, l'accesso all'indice corrente è sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="223d2-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

<span data-ttu-id="223d2-108">Questo è un esempio di partizionamento in blocchi, con ogni blocco costituito da un elemento.</span><span class="sxs-lookup"><span data-stu-id="223d2-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="223d2-109">Fornendo più elementi per volta, è possibile ridurre il conflitto sul blocco e ottenere in teoria prestazioni più veloci.</span><span class="sxs-lookup"><span data-stu-id="223d2-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="223d2-110">A un certo punto, tuttavia, blocchi più grandi potrebbero richiedere logica di bilanciamento del carico aggiuntiva per mantenere occupati tutti i thread fino al completamento del lavoro.</span><span class="sxs-lookup"><span data-stu-id="223d2-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223d2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="223d2-111">See also</span></span>

* [<span data-ttu-id="223d2-112">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="223d2-112">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
* [<span data-ttu-id="223d2-113">Procedura: Implementare un partitioner per il partizionamento statico</span><span class="sxs-lookup"><span data-stu-id="223d2-113">How to: Implement a Partitioner for Static Partitioning</span></span>](how-to-implement-a-partitioner-for-static-partitioning.md)
