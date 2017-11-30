---
title: "Procedura: specificare la modalità di esecuzione in PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 745ceae9832582c7b66a56075d128f9cf1c8ff69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="7d6d8-102">Procedura: specificare la modalità di esecuzione in PLINQ</span><span class="sxs-lookup"><span data-stu-id="7d6d8-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="7d6d8-103">In questo esempio viene illustrato come forzare PLINQ per ignorare le proprie regole euristiche predefinite e la parallelizzazione di una query indipendentemente dalla forma della query.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7d6d8-104">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="7d6d8-105">Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7d6d8-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d6d8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d6d8-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="7d6d8-107">PLINQ è progettato per sfruttare le opportunità di parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="7d6d8-108">Tuttavia, non tutte le query trarre vantaggio dall'esecuzione parallela.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="7d6d8-109">Ad esempio, quando una query contiene un delegato di singolo utente che esegue un intervento minimo, eseguirà la query in genere più veloce in sequenza.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="7d6d8-110">In questo modo l'overhead necessario per consentire l'esecuzione parallela rappresenta uno è più costoso di un aumento di velocità ottenuti.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="7d6d8-111">Pertanto, PLINQ non parallelizza automaticamente tutte le query.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="7d6d8-112">Viene innanzitutto esaminato la forma di query e i vari operatori che lo compongono.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="7d6d8-113">In base a questa analisi, nella modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="7d6d8-114">Tuttavia, in alcuni casi è possibile conoscere più query di PLINQ è in grado di determinare dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="7d6d8-115">Ad esempio, si potrebbe sapere che un delegato è molto costoso e che la query verrà sicuramente sfruttano la parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="7d6d8-116">In questi casi, è possibile utilizzare il <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> (metodo) e specificare il <xref:System.Linq.ParallelExecutionMode.ForceParallelism> valore per indicare alla query vengono eseguite sempre come parallelo PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d6d8-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7d6d8-117">Compiling the Code</span></span>  
 <span data-ttu-id="7d6d8-118">Tagliare e incollare questo codice nel [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) e chiamare il metodo da `Main`.</span><span class="sxs-lookup"><span data-stu-id="7d6d8-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d6d8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d6d8-119">See Also</span></span>  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>  
 [<span data-ttu-id="7d6d8-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="7d6d8-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
