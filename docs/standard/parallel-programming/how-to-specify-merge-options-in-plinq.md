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
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59ffff3019f10874bd2df977b80d46e903d13613
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="7aff1-102">Procedura: specificare le opzioni di merge in PLINQ</span><span class="sxs-lookup"><span data-stu-id="7aff1-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="7aff1-103">Questo esempio mostra come specificare le opzioni di merge che verranno applicate a tutti gli operatori successivi in una query PLINQ.</span><span class="sxs-lookup"><span data-stu-id="7aff1-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="7aff1-104">Non è necessario impostare le opzioni di merge in modo esplicito, ma facendolo è possibile migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7aff1-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="7aff1-105">Per altre informazioni sulle opzioni di merge, vedere [Opzioni di merge in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7aff1-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7aff1-106">Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente.</span><span class="sxs-lookup"><span data-stu-id="7aff1-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="7aff1-107">Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="7aff1-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aff1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7aff1-108">Example</span></span>  
 <span data-ttu-id="7aff1-109">L'esempio seguente illustra il comportamento delle opzioni di merge in uno scenario di base che ha un'origine non ordinata e applica una funzione complessa a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="7aff1-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="7aff1-110">Nei casi in cui l'opzione <xref:System.Linq.ParallelMergeOptions.AutoBuffered> comporta una latenza indesiderata prima della restituzione del primo elemento, provare a usare l'opzione <xref:System.Linq.ParallelMergeOptions.NotBuffered> per restituire gli elementi del risultato in modo più rapido e semplice.</span><span class="sxs-lookup"><span data-stu-id="7aff1-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aff1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7aff1-111">See Also</span></span>  
 <xref:System.Linq.ParallelMergeOptions>  
 [<span data-ttu-id="7aff1-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="7aff1-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
