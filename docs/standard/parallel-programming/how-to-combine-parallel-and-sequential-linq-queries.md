---
title: 'Procedura: Combinare query LINQ parallele e sequenziali'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 2bdf074bc2977dc501e0726a52e825c89828565f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289538"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="c7384-102">Procedura: Combinare query LINQ parallele e sequenziali</span><span class="sxs-lookup"><span data-stu-id="c7384-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>

<span data-ttu-id="c7384-103">Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A> per indicare a PLINQ di elaborare tutti gli operatori successivi nella query in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="c7384-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="c7384-104">Anche se l'elaborazione sequenziale è spesso più lenta di quella parallela, a volte è necessario produrre risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="c7384-104">Although sequential processing is often slower than parallel, sometimes it's necessary to produce correct results.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7384-105">Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="c7384-105">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="c7384-106">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="c7384-106">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7384-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7384-107">Example</span></span>  
 <span data-ttu-id="c7384-108">L'esempio seguente mostra uno scenario in cui è necessario usare <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, in particolare per mantenere l'ordinamento stabilito in una clausola precedente della query.</span><span class="sxs-lookup"><span data-stu-id="c7384-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7384-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c7384-109">Compiling the Code</span></span>  
 <span data-ttu-id="c7384-110">Per compilare ed eseguire il codice, incollarlo nel progetto [PLINQ Data Sample](plinq-data-sample.md) , aggiungere una riga per chiamare il metodo da `Main` e premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="c7384-110">To compile and run this code, paste it into the [PLINQ Data Sample](plinq-data-sample.md) project, add a line to call the method from `Main`, and press **F5**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7384-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7384-111">See also</span></span>

- [<span data-ttu-id="c7384-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="c7384-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
