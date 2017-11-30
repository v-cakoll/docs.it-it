---
title: 'Procedura: combinare query LINQ parallele e sequenziali'
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="4095e-102">Procedura: combinare query LINQ parallele e sequenziali</span><span class="sxs-lookup"><span data-stu-id="4095e-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="4095e-103">In questo esempio viene illustrato come utilizzare il <xref:System.Linq.ParallelEnumerable.AsSequential%2A> metodo per indicare a elaborare in modo sequenziale tutti gli operatori successivi nella query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4095e-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="4095e-104">Anche se è in genere inferiore a parallelo elaborazione sequenza, in alcuni casi è necessario ottenere risultati corretti.</span><span class="sxs-lookup"><span data-stu-id="4095e-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4095e-105">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="4095e-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="4095e-106">Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4095e-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4095e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4095e-107">Example</span></span>  
 <span data-ttu-id="4095e-108">Nell'esempio seguente viene illustrato uno scenario in cui <xref:System.Linq.ParallelEnumerable.AsSequential%2A> è obbligatorio, in particolare per conservare l'ordine è stata stabilita in una clausola della query precedente.</span><span class="sxs-lookup"><span data-stu-id="4095e-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4095e-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4095e-109">Compiling the Code</span></span>  
 <span data-ttu-id="4095e-110">Per compilare ed eseguire il codice, incollarlo il [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) del progetto, aggiungere una riga per chiamare il metodo dal `Main`, e premere F5.</span><span class="sxs-lookup"><span data-stu-id="4095e-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4095e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4095e-111">See Also</span></span>  
 [<span data-ttu-id="4095e-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4095e-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
