---
title: "Procedura: annullare il wrapping di un'attività annidata"
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>Procedura: annullare il wrapping di un'attività annidata
È possibile restituire un'attività da un metodo e attendere o continua da tale attività, come illustrato nell'esempio seguente:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 Nell'esempio precedente, il <xref:System.Threading.Tasks.Task%601.Result%2A> proprietà è di tipo `string` (`String` in Visual Basic).  
  
 Tuttavia, in alcuni scenari, è consigliabile creare un'attività all'interno di un'altra attività e quindi restituire l'attività annidata. In questo caso, il `TResult` dell'attività contenitore è un'attività. Nell'esempio seguente, la proprietà del risultato è un `Task<Task<string>>` in c# o `Task(Of Task(Of String))` in Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Sebbene sia possibile scrivere codice per annullare il wrapping dell'attività esterna e recuperare l'attività originale e il relativo <xref:System.Threading.Tasks.Task%601.Result%2A> proprietà, tale codice non è più semplice la scrittura in quanto è necessario gestire le eccezioni, nonché le richieste di annullamento. In questo caso, è consigliabile utilizzare uno del <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metodi di estensione, come illustrato nell'esempio seguente.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Il <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metodi possono essere utilizzati per trasformare qualsiasi `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` in Visual Basic) per un `Task` o `Task<TResult>` (`Task(Of TResult)` in Visual Basic). La nuova attività completamente rappresenta l'attività annidata interna e include lo stato di annullamento e tutte le eccezioni.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metodi di estensione.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [Programmazione asincrona basata su attività](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
