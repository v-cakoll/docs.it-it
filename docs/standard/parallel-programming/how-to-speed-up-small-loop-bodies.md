---
title: 'Procedura: aumentare la velocità di corpi di ciclo di dimensioni ridotte'
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
ms.openlocfilehash: bff41416dd2263c185cc94de045b2c8a26ea194d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581151"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="ab511-102">Procedura: aumentare la velocità di corpi di ciclo di dimensioni ridotte</span><span class="sxs-lookup"><span data-stu-id="ab511-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="ab511-103">La velocità dei cicli <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> con un corpo di dimensioni ridotte può risultare minore rispetto alla velocità dei cicli sequenziali equivalenti, come il ciclo [for](~/docs/csharp/language-reference/keywords/for.md) in C# e il ciclo [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab511-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](http://msdn.microsoft.com/library/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="ab511-104">La minore velocità è dovuta all'overhead necessario per eseguire il partizionamento dei dati e al costo associato alla chiamata di un delegato a ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="ab511-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="ab511-105">Per gestire tali scenari, la classe <xref:System.Collections.Concurrent.Partitioner> fornisce il metodo <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> che consente di fornire un ciclo sequenziale per il corpo del delegato in modo che il delegato venga richiamato soltanto una volta per partizione, anziché una volta per iterazione.</span><span class="sxs-lookup"><span data-stu-id="ab511-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="ab511-106">Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="ab511-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab511-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab511-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="ab511-108">L'approccio descritto in questo esempio è utile quando il ciclo esegue una quantità minima di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ab511-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="ab511-109">Quando il lavoro diventa più dispendioso in termini di calcolo, l'uso di un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con il partitioner predefinito offrirà probabilmente prestazioni simili o migliori.</span><span class="sxs-lookup"><span data-stu-id="ab511-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab511-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab511-110">See Also</span></span>  
 [<span data-ttu-id="ab511-111">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="ab511-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="ab511-112">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="ab511-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="ab511-113">Iteratori</span><span class="sxs-lookup"><span data-stu-id="ab511-113">Iterators</span></span>](https://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="ab511-114">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="ab511-114">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
