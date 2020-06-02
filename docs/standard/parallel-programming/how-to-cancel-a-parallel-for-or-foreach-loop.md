---
title: 'Procedura: Annullare un ciclo Parallel.For o ForEach'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: d29137127dd47844f8f08d3ac689cf2827d9efe2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288225"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a><span data-ttu-id="b0ca2-102">Procedura: Annullare un ciclo Parallel.For o ForEach</span><span class="sxs-lookup"><span data-stu-id="b0ca2-102">How to: Cancel a Parallel.For or ForEach Loop</span></span>
<span data-ttu-id="b0ca2-103">I metodi <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> supportano l'annullamento tramite l'uso di token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> methods support cancellation through the use of cancellation tokens.</span></span> <span data-ttu-id="b0ca2-104">Per altre informazioni generali sull'annullamento, vedere [Annullamento](../threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="b0ca2-104">For more information about cancellation in general, see [Cancellation](../threading/cancellation-in-managed-threads.md).</span></span> <span data-ttu-id="b0ca2-105">In un ciclo parallelo è necessario fornire <xref:System.Threading.CancellationToken> al metodo nel parametro <xref:System.Threading.Tasks.ParallelOptions> e quindi racchiudere la chiamata parallela in un blocco Try-Catch.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-105">In a parallel loop, you supply the <xref:System.Threading.CancellationToken> to the method in the <xref:System.Threading.Tasks.ParallelOptions> parameter and then enclose the parallel call in a try-catch block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0ca2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0ca2-106">Example</span></span>  
 <span data-ttu-id="b0ca2-107">L'esempio seguente mostra come annullare una chiamata a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-107">The following example shows how to cancel a call to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b0ca2-108">È possibile applicare lo stesso approccio a una chiamata <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-108">You can apply the same approach to a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> call.</span></span>  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 <span data-ttu-id="b0ca2-109">Se il token che segnala l'annullamento è lo stesso token specificato nell'istanza <xref:System.Threading.Tasks.ParallelOptions>, il ciclo parallelo genera un'unica eccezione <xref:System.OperationCanceledException> al momento dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-109">If the token that signals the cancellation is the same token that is specified in the <xref:System.Threading.Tasks.ParallelOptions> instance, then the parallel loop will throw a single <xref:System.OperationCanceledException> on cancellation.</span></span> <span data-ttu-id="b0ca2-110">Se altri token provocano l'annullamento, il ciclo genererà un'eccezione <xref:System.AggregateException> con <xref:System.OperationCanceledException> come InnerException.</span><span class="sxs-lookup"><span data-stu-id="b0ca2-110">If some other token causes cancellation, the loop will throw an <xref:System.AggregateException> with an <xref:System.OperationCanceledException> as an InnerException.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ca2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0ca2-111">See also</span></span>

- [<span data-ttu-id="b0ca2-112">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="b0ca2-112">Data Parallelism</span></span>](data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="b0ca2-113">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="b0ca2-113">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
