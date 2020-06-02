---
title: 'Procedura: Specificare la modalità di esecuzione in PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: 39ccde003b60ac9cbcff7ab824103a9cf37cc453
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288095"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a><span data-ttu-id="5c86a-102">Procedura: Specificare la modalità di esecuzione in PLINQ</span><span class="sxs-lookup"><span data-stu-id="5c86a-102">How to: Specify the Execution Mode in PLINQ</span></span>

<span data-ttu-id="5c86a-103">Questo esempio mostra come forzare PLINQ a ignorare l'euristica predefinita e parallelizzare una query indipendentemente dalla relativa forma.</span><span class="sxs-lookup"><span data-stu-id="5c86a-103">This example shows how to force PLINQ to bypass its default heuristics and parallelize a query regardless of the query's shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c86a-104">Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="5c86a-104">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="5c86a-105">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="5c86a-105">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c86a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c86a-106">Example</span></span>  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 <span data-ttu-id="5c86a-107">PLINQ è progettato per sfruttare le opportunità di parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c86a-107">PLINQ is designed to exploit opportunities for parallelization.</span></span> <span data-ttu-id="5c86a-108">Tuttavia, l'esecuzione parallela non è vantaggiosa per tutte le query.</span><span class="sxs-lookup"><span data-stu-id="5c86a-108">However, not all queries benefit from parallel execution.</span></span> <span data-ttu-id="5c86a-109">Se, ad esempio, una query contiene un solo delegato utente che non funziona, la query viene in genere eseguita più velocemente in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="5c86a-109">For example, when a query contains a single user delegate that does little work, the query will usually run faster sequentially.</span></span> <span data-ttu-id="5c86a-110">L'esecuzione sequenziale è più veloce perché l'overhead richiesto per l'abilitazione dell'esecuzione di parallelizzazione è più costoso rispetto all'aumento di velocità ottenuto.</span><span class="sxs-lookup"><span data-stu-id="5c86a-110">Sequential execution is faster because the overhead involved in enabling parallelizing execution is more expensive than the speedup that's obtained.</span></span> <span data-ttu-id="5c86a-111">PLINQ pertanto non parallelizza automaticamente ogni query.</span><span class="sxs-lookup"><span data-stu-id="5c86a-111">Therefore, PLINQ does not automatically parallelize every query.</span></span> <span data-ttu-id="5c86a-112">Esamina prima di tutto la forma della query e i vari operatori inclusi.</span><span class="sxs-lookup"><span data-stu-id="5c86a-112">It first examines the shape of the query and the various operators that comprise it.</span></span> <span data-ttu-id="5c86a-113">In base a questa analisi, in modalità di esecuzione predefinita PLINQ può decidere di eseguire alcune o tutte le query in sequenza.</span><span class="sxs-lookup"><span data-stu-id="5c86a-113">Based on this analysis, PLINQ in the default execution mode may decide to execute some or all of the query sequentially.</span></span> <span data-ttu-id="5c86a-114">In alcuni casi, tuttavia, l'utente potrebbe avere più informazioni sulla query rispetto a quelle che PLINQ è in grado di determinare dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="5c86a-114">However, in some cases you may know more about your query than PLINQ is able to determine from its analysis.</span></span> <span data-ttu-id="5c86a-115">È ad esempio possibile che un delegato sia dispendioso e che la query possa trarre vantaggio dalla parallelizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c86a-115">For example, you may know that a delegate is expensive and that the query will definitely benefit from parallelization.</span></span> <span data-ttu-id="5c86a-116">In questi casi, è possibile usare il metodo <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> e specificare il valore <xref:System.Linq.ParallelExecutionMode.ForceParallelism> per indicare a PLINQ di eseguire sempre la query in parallelo.</span><span class="sxs-lookup"><span data-stu-id="5c86a-116">In such cases, you can use the <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> method and specify the <xref:System.Linq.ParallelExecutionMode.ForceParallelism> value to instruct PLINQ to always run the query as parallel.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c86a-117">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5c86a-117">Compiling the Code</span></span>  
 <span data-ttu-id="5c86a-118">Tagliare e incollare questo codice nell'[esempio di dati PLINQ](plinq-data-sample.md) e chiamare il metodo da `Main`.</span><span class="sxs-lookup"><span data-stu-id="5c86a-118">Cut and paste this code into the [PLINQ Data Sample](plinq-data-sample.md) and call the method from `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c86a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c86a-119">See also</span></span>

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [<span data-ttu-id="5c86a-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="5c86a-120">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
