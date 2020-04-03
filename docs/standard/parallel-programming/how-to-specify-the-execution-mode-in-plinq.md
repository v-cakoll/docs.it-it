---
title: 'Procedura: specificare la modalità di esecuzione in PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: f035dbcd5091d81a3cce3b9e9e683d836fe84bb7
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635818"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="be1a9-102">Procedura: specificare la modalità di esecuzione in PLINQ</span><span class="sxs-lookup"><span data-stu-id="be1a9-102">How to: Specify the Execution Mode in PLINQ</span></span>

<span data-ttu-id="be1a9-103">Questo esempio mostra come forzare PLINQ a ignorare l'euristica predefinita e parallelizzare una query indipendentemente dalla relativa forma.</span><span class="sxs-lookup"><span data-stu-id="be1a9-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be1a9-104">Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente della query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="be1a9-104">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="be1a9-105">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="be1a9-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be1a9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="be1a9-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="be1a9-107">PLINQ è progettato per sfruttare le opportunità di parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="be1a9-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="be1a9-108">Tuttavia, l'esecuzione parallela non è vantaggiosa per tutte le query.</span><span class="sxs-lookup"><span data-stu-id="be1a9-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="be1a9-109">Ad esempio, quando una query contiene un singolo delegato utente che esegue poco lavoro, la query verrà in genere eseguita più velocemente in sequenza.</span><span class="sxs-lookup"><span data-stu-id="be1a9-109">For example, when a query contains a single user delegate that does little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="be1a9-110">L'esecuzione sequenziale è più veloce perché l'overhead implicato nell'abilitazione della parallelizzazione dell'esecuzione è più costoso della velocità ottenuta.</span><span class="sxs-lookup"><span data-stu-id="be1a9-110">Sequential execution is faster because the overhead involved in enabling parallelizing execution is more expensive than the speedup that's obtained.</span></span> <span data-ttu-id="be1a9-111">PLINQ pertanto non parallelizza automaticamente ogni query.</span><span class="sxs-lookup"><span data-stu-id="be1a9-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="be1a9-112">Esamina prima di tutto la forma della query e i vari operatori inclusi.</span><span class="sxs-lookup"><span data-stu-id="be1a9-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="be1a9-113">In base a questa analisi, in modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza.</span><span class="sxs-lookup"><span data-stu-id="be1a9-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="be1a9-114">In alcuni casi, tuttavia, l'utente potrebbe avere più informazioni sulla query rispetto a quelle che PLINQ è in grado di determinare dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="be1a9-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="be1a9-115">Ad esempio, è possibile sapere che un delegato è costoso e che la query trarrà sicuramente vantaggio dalla parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="be1a9-115">For example, you may know that a delegate is expensive and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="be1a9-116">In questi casi, è possibile usare il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> e specificare il valore <xref:System.Linq.ParallelExecutionMode.ForceParallelism> per indicare a PLINQ di eseguire sempre la query in parallelo.</span><span class="sxs-lookup"><span data-stu-id="be1a9-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be1a9-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="be1a9-117">Compiling the Code</span></span>  
 <span data-ttu-id="be1a9-118">Tagliare e incollare questo codice nell'[esempio di dati PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) e chiamare il metodo da `Main`.</span><span class="sxs-lookup"><span data-stu-id="be1a9-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1a9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be1a9-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="be1a9-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="be1a9-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
