---
title: 'Procedura: annullare un ciclo Parallel.For o ForEach'
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
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f82c5758e02b4beebf035fe8f43f856447855a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="242f7-102">Procedura: annullare un ciclo Parallel.For o ForEach</span><span class="sxs-lookup"><span data-stu-id="242f7-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="242f7-103">Il <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> metodi supportano l'annullamento tramite l'utilizzo di token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="242f7-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="242f7-104">Per ulteriori informazioni sull'annullamento in generale, vedere [annullamento](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="242f7-104">For more information about cancellation in general, see [Cancellation](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="242f7-105">In un ciclo parallelo, si fornisce il <xref:System.Threading.CancellationToken> al metodo di <xref:System.Threading.Tasks.ParallelOptions> parametro e quindi racchiudere la chiamata parallela in un blocco try-catch.</span><span class="sxs-lookup"><span data-stu-id="242f7-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="242f7-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="242f7-106">Example</span></span>  
 <span data-ttu-id="242f7-107">Nell'esempio seguente viene illustrato come annullare una chiamata a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="242f7-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="242f7-108">È possibile applicare lo stesso approccio a un <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> chiamare.</span><span class="sxs-lookup"><span data-stu-id="242f7-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="242f7-109">Se il token che segnala l'annullamento è lo stesso token specificato nel <xref:System.Threading.Tasks.ParallelOptions> istanza, quindi genera un singolo ciclo parallelo <xref:System.OperationCanceledException> al momento dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="242f7-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="242f7-110">Se altri token provochi l'annullamento, il ciclo genererà un <xref:System.AggregateException> con un <xref:System.OperationCanceledException> come InnerException.</span><span class="sxs-lookup"><span data-stu-id="242f7-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242f7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="242f7-111">See Also</span></span>  
 [<span data-ttu-id="242f7-112">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="242f7-112">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="242f7-113">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="242f7-113">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
