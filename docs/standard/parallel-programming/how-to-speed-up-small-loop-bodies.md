---
title: 'Procedura: Aumentare la velocità di corpi di ciclo di dimensioni ridotte'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06af0e10080977800479ed5aa444c63bde2d371e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726455"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="11493-102">Procedura: Aumentare la velocità di corpi di ciclo di dimensioni ridotte</span><span class="sxs-lookup"><span data-stu-id="11493-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="11493-103">La velocità dei cicli <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> con un corpo di dimensioni ridotte può risultare minore rispetto alla velocità dei cicli sequenziali equivalenti, come il ciclo [for](~/docs/csharp/language-reference/keywords/for.md) in C# e il ciclo [For](https://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="11493-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](https://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="11493-104">La minore velocità è dovuta all'overhead necessario per eseguire il partizionamento dei dati e al costo associato alla chiamata di un delegato a ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="11493-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="11493-105">Per gestire tali scenari, la classe <xref:System.Collections.Concurrent.Partitioner> fornisce il metodo <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> che consente di fornire un ciclo sequenziale per il corpo del delegato in modo che il delegato venga richiamato soltanto una volta per partizione, anziché una volta per iterazione.</span><span class="sxs-lookup"><span data-stu-id="11493-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="11493-106">Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="11493-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11493-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="11493-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="11493-108">L'approccio descritto in questo esempio è utile quando il ciclo esegue una quantità minima di lavoro.</span><span class="sxs-lookup"><span data-stu-id="11493-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="11493-109">Quando il lavoro diventa più dispendioso in termini di calcolo, l'uso di un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con il partitioner predefinito offrirà probabilmente prestazioni simili o migliori.</span><span class="sxs-lookup"><span data-stu-id="11493-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11493-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11493-110">See also</span></span>

- [<span data-ttu-id="11493-111">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="11493-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="11493-112">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="11493-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="11493-113">Iteratori</span><span class="sxs-lookup"><span data-stu-id="11493-113">Iterators</span></span>](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
- [<span data-ttu-id="11493-114">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="11493-114">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
