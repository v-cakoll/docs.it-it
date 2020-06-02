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
ms.openlocfilehash: 4983cafb9d4a72262dc7a6a6c37fab23937b3274
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288082"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="1edb2-102">Procedura: Aumentare la velocità di corpi di ciclo di dimensioni ridotte</span><span class="sxs-lookup"><span data-stu-id="1edb2-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="1edb2-103">La velocità dei cicli <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> con un corpo di dimensioni ridotte può risultare minore rispetto alla velocità dei cicli sequenziali equivalenti, come il ciclo [for](../../csharp/language-reference/keywords/for.md) in C# e il ciclo [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1edb2-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="1edb2-104">La minore velocità è dovuta all'overhead necessario per eseguire il partizionamento dei dati e al costo associato alla chiamata di un delegato a ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="1edb2-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="1edb2-105">Per gestire tali scenari, la classe <xref:System.Collections.Concurrent.Partitioner> fornisce il metodo <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> che consente di fornire un ciclo sequenziale per il corpo del delegato in modo che il delegato venga richiamato soltanto una volta per partizione, anziché una volta per iterazione.</span><span class="sxs-lookup"><span data-stu-id="1edb2-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="1edb2-106">Per altre informazioni, vedere [Partitioner personalizzati per PLINQ e TPL](custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="1edb2-106">For more information, see [Custom Partitioners for PLINQ and TPL](custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1edb2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="1edb2-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="1edb2-108">L'approccio descritto in questo esempio è utile quando il ciclo esegue una quantità minima di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1edb2-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="1edb2-109">Quando il lavoro diventa più dispendioso in termini di calcolo, l'uso di un ciclo <xref:System.Threading.Tasks.Parallel.For%2A> o <xref:System.Threading.Tasks.Parallel.ForEach%2A> con il partitioner predefinito offrirà probabilmente prestazioni simili o migliori.</span><span class="sxs-lookup"><span data-stu-id="1edb2-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edb2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1edb2-110">See also</span></span>

- [<span data-ttu-id="1edb2-111">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="1edb2-111">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="1edb2-112">Partitioner personalizzati per PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="1edb2-112">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="1edb2-113">Iteratori (C#)</span><span class="sxs-lookup"><span data-stu-id="1edb2-113">Iterators (C#)</span></span>](../../csharp/programming-guide/concepts/iterators.md)
- <span data-ttu-id="1edb2-114">[Iteratori [Visual Basic]](../../visual-basic/programming-guide/concepts/iterators.md)</span><span class="sxs-lookup"><span data-stu-id="1edb2-114">[Iterators (Visual Basic)](../../visual-basic/programming-guide/concepts/iterators.md)</span></span>
- [<span data-ttu-id="1edb2-115">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="1edb2-115">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
