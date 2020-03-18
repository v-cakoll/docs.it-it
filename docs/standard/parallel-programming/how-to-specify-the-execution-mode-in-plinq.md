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
ms.openlocfilehash: c602aba6e18f80b007b15cd61dfd2b48a36dd2c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139250"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="f21c1-102">Procedura: specificare la modalità di esecuzione in PLINQ</span><span class="sxs-lookup"><span data-stu-id="f21c1-102">How to: Specify the Execution Mode in PLINQ</span></span>
<span data-ttu-id="f21c1-103">Questo esempio mostra come forzare PLINQ a ignorare l'euristica predefinita e parallelizzare una query indipendentemente dalla relativa forma.</span><span class="sxs-lookup"><span data-stu-id="f21c1-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="f21c1-104">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="f21c1-104">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="f21c1-105">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="f21c1-105">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f21c1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f21c1-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="f21c1-107">PLINQ è progettato per sfruttare le opportunità di parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="f21c1-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="f21c1-108">Tuttavia, l'esecuzione parallela non è vantaggiosa per tutte le query.</span><span class="sxs-lookup"><span data-stu-id="f21c1-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="f21c1-109">Quando una query contiene un delegato utente singolo che esegue operazioni minime, ad esempio, risulta in genere più veloce l'esecuzione sequenziale.</span><span class="sxs-lookup"><span data-stu-id="f21c1-109">For example, when a query contains a single user delegate that does very little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="f21c1-110">Il motivo è che il sovraccarico correlato all'abilitazione dell'esecuzione parallela è superiore all'aumento di velocità ottenuto.</span><span class="sxs-lookup"><span data-stu-id="f21c1-110">This is because the overhead involved in enabling parallelizing execution is more expensive than the speedup that is obtained.</span></span> <span data-ttu-id="f21c1-111">PLINQ pertanto non parallelizza automaticamente ogni query.</span><span class="sxs-lookup"><span data-stu-id="f21c1-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="f21c1-112">Esamina prima di tutto la forma della query e i vari operatori inclusi.</span><span class="sxs-lookup"><span data-stu-id="f21c1-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="f21c1-113">In base a questa analisi, in modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza.</span><span class="sxs-lookup"><span data-stu-id="f21c1-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="f21c1-114">In alcuni casi, tuttavia, l'utente potrebbe avere più informazioni sulla query rispetto a quelle che PLINQ è in grado di determinare dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="f21c1-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="f21c1-115">Si potrebbe ad esempio sapere che un delegato è molto costoso e che la parallelizzazione offre sicuramente vantaggi per la query.</span><span class="sxs-lookup"><span data-stu-id="f21c1-115">For example, you may know that a delegate is very expensive, and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="f21c1-116">In questi casi, è possibile usare il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> e specificare il valore <xref:System.Linq.ParallelExecutionMode.ForceParallelism> per indicare a PLINQ di eseguire sempre la query in parallelo.</span><span class="sxs-lookup"><span data-stu-id="f21c1-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f21c1-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f21c1-117">Compiling the Code</span></span>  
 <span data-ttu-id="f21c1-118">Tagliare e incollare questo codice nell'[esempio di dati PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) e chiamare il metodo da `Main`.</span><span class="sxs-lookup"><span data-stu-id="f21c1-118">Cut and paste this code into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21c1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f21c1-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="f21c1-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="f21c1-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
