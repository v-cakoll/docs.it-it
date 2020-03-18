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
ms.openlocfilehash: 4c04afb23a168a9cff60962bd5a75a65e3ebca4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73134190"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="29646-102">Procedura: combinare query LINQ parallele e sequenziali</span><span class="sxs-lookup"><span data-stu-id="29646-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="29646-103">Questo esempio mostra come usare il metodo <xref:System.Linq.ParallelEnumerable.AsSequential%2A> per indicare a PLINQ di elaborare tutti gli operatori successivi nella query in modo sequenziale.</span><span class="sxs-lookup"><span data-stu-id="29646-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="29646-104">Anche se l'elaborazione sequenziale è generalmente più lenta di quella parallela, a volte è necessaria per produrre risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="29646-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="29646-105">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="29646-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="29646-106">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="29646-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29646-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="29646-107">Example</span></span>  
 <span data-ttu-id="29646-108">L'esempio seguente mostra uno scenario in cui è necessario usare <xref:System.Linq.ParallelEnumerable.AsSequential%2A>, in particolare per mantenere l'ordinamento stabilito in una clausola precedente della query.</span><span class="sxs-lookup"><span data-stu-id="29646-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="29646-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="29646-109">Compiling the Code</span></span>  
 <span data-ttu-id="29646-110">Per compilare ed eseguire il codice, incollarlo nel progetto [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md), aggiungere una riga per chiamare il metodo da `Main` e quindi premere F5.</span><span class="sxs-lookup"><span data-stu-id="29646-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29646-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29646-111">See also</span></span>

- [<span data-ttu-id="29646-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="29646-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
