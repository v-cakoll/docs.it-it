---
title: 'Procedura: Annullare un ciclo Parallel.For o ForEach'
description: Annullare un ciclo Parallel. for o Parallel. ForEach in .NET fornendo un oggetto token di annullamento al metodo nel parametro ParallelOptions.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to cancel
- parallel for loops, how to cancel
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
ms.openlocfilehash: 0a22794f3c45e685a80d36a42ecd849461936c7b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769002"
---
# <a name="how-to-cancel-a-parallelfor-or-foreach-loop"></a>Procedura: Annullare un ciclo Parallel.For o ForEach
I metodi <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> supportano l'annullamento tramite l'uso di token di annullamento. Per altre informazioni generali sull'annullamento, vedere [Annullamento](../threading/cancellation-in-managed-threads.md). In un ciclo parallelo è necessario fornire <xref:System.Threading.CancellationToken> al metodo nel parametro <xref:System.Threading.Tasks.ParallelOptions> e quindi racchiudere la chiamata parallela in un blocco Try-Catch.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come annullare una chiamata a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. È possibile applicare lo stesso approccio a una chiamata <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Se il token che segnala l'annullamento è lo stesso token specificato nell'istanza <xref:System.Threading.Tasks.ParallelOptions>, il ciclo parallelo genera un'unica eccezione <xref:System.OperationCanceledException> al momento dell'annullamento. Se altri token provocano l'annullamento, il ciclo genererà un'eccezione <xref:System.AggregateException> con <xref:System.OperationCanceledException> come InnerException.  
  
## <a name="see-also"></a>Vedere anche

- [Parallelismo dei dati](data-parallelism-task-parallel-library.md)
- [Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md)
