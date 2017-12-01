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
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Procedura: annullare un ciclo Parallel.For o ForEach
Il <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> metodi supportano l'annullamento tramite l'utilizzo di token di annullamento. Per ulteriori informazioni sull'annullamento in generale, vedere [annullamento](../../../docs/standard/threading/cancellation-in-managed-threads.md). In un ciclo parallelo, si fornisce il <xref:System.Threading.CancellationToken> al metodo di <xref:System.Threading.Tasks.ParallelOptions> parametro e quindi racchiudere la chiamata parallela in un blocco try-catch.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come annullare una chiamata a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. È possibile applicare lo stesso approccio a un <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> chiamare.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Se il token che segnala l'annullamento è lo stesso token specificato nel <xref:System.Threading.Tasks.ParallelOptions> istanza, quindi genera un singolo ciclo parallelo <xref:System.OperationCanceledException> al momento dell'annullamento. Se altri token provochi l'annullamento, il ciclo genererà un <xref:System.AggregateException> con un <xref:System.OperationCanceledException> come InnerException.  
  
## <a name="see-also"></a>Vedere anche  
 [Parallelismo dei dati](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
