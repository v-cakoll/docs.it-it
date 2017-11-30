---
title: 'Procedura: specificare le opzioni di merge in PLINQ'
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="e07d6-102">Procedura: specificare le opzioni di merge in PLINQ</span><span class="sxs-lookup"><span data-stu-id="e07d6-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="e07d6-103">In questo esempio viene illustrato come specificare le opzioni di unione che verranno applicate a tutti gli operatori successivi in una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="e07d6-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="e07d6-104">Non è necessario impostare le opzioni di merge in modo esplicito, ma può migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e07d6-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="e07d6-105">Per ulteriori informazioni sulle opzioni di unione, vedere [opzioni di Merge in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="e07d6-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e07d6-106">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="e07d6-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="e07d6-107">Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="e07d6-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e07d6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e07d6-108">Example</span></span>  
 <span data-ttu-id="e07d6-109">Nell'esempio seguente viene illustrato il comportamento delle opzioni di unione in uno scenario di base che dispone di un'origine non ordinata e si applica una funzione dispendiosa a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="e07d6-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="e07d6-110">Nei casi in cui il <xref:System.Linq.ParallelMergeOptions.AutoBuffered> opzione comporta una latenza indesiderata prima viene restituito il primo elemento, provare il <xref:System.Linq.ParallelMergeOptions.NotBuffered> possibile produrre elementi di risultato più veloce ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="e07d6-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e07d6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e07d6-111">See Also</span></span>  
 <xref:System.Linq.ParallelMergeOptions>  
 [<span data-ttu-id="e07d6-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="e07d6-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
