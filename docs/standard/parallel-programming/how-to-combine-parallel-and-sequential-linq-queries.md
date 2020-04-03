---
title: 'Procedura: combinare query LINQ parallele e sequenziali'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 074714b1152c8804ee1e747104dbaf47f4645546
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635862"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="0f0df-102">Procedura: combinare query LINQ parallele e sequenziali</span><span class="sxs-lookup"><span data-stu-id="0f0df-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>

<span data-ttu-id="0f0df-103">Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A> per indicare a PLINQ di elaborare tutti gli operatori successivi nella query in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="0f0df-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="0f0df-104">Anche se l'elaborazione sequenziale è spesso più lenta del parallelo, a volte è necessario produrre risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="0f0df-104">Although sequential processing is often slower than parallel, sometimes it's necessary to produce correct results.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f0df-105">Questo esempio ha lo scopo di illustrare l'utilizzo e potrebbe non essere eseguito più velocemente della query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="0f0df-105">This example is intended to demonstrate usage and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="0f0df-106">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="0f0df-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f0df-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f0df-107">Example</span></span>  
 <span data-ttu-id="0f0df-108">L'esempio seguente mostra uno scenario in cui è necessario usare <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, in particolare per mantenere l'ordinamento stabilito in una clausola precedente della query.</span><span class="sxs-lookup"><span data-stu-id="0f0df-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f0df-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0f0df-109">Compiling the Code</span></span>  
 <span data-ttu-id="0f0df-110">Per compilare ed eseguire questo codice, incollarlo nel progetto [PLINQ Data Sample,](../../../docs/standard/parallel-programming/plinq-data-sample.md) aggiungere una riga per chiamare il metodo da `Main`e premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="0f0df-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press **F5**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0df-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f0df-111">See also</span></span>

- [<span data-ttu-id="0f0df-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="0f0df-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
