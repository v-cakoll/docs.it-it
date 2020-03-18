---
title: "Procedura: annullare il wrapping di un'attività annidata"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
ms.openlocfilehash: c72654a2bc21035fe706d76018bb163d8ba01ee8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106899"
---
# <a name="how-to-unwrap-a-nested-task"></a>Procedura: annullare il wrapping di un'attività annidata
È possibile restituire un'attività da un metodo e quindi attendere o continuare da tale attività, come illustrato nell'esempio seguente:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 Nell'esempio precedente la proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è di tipo `string` (`String` in Visual Basic).  
  
 In alcuni scenari, tuttavia, è consigliabile creare un'attività all'interno di un'altra attività e quindi restituire l'attività annidata. In questo caso, l'oggetto `TResult` dell'attività contenitore è esso stesso un'attività. Nell'esempio seguente la proprietà Result è di tipo `Task<Task<string>>` in C# o `Task(Of Task(Of String))` in Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Anche se è possibile scrivere codice per annullare il wrapping dell'attività esterna e recuperare l'attività originale e la relativa proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>, tale codice non è semplice da scrivere perché è necessario gestire le eccezioni e anche le richieste di annullamento. In questo caso, è consigliabile usare uno dei metodi di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, come illustrato nell'esempio seguente.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 I metodi <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> possono essere usati per trasformare qualsiasi oggetto `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` in Visual Basic) in un oggetto `Task` o `Task<TResult>` (`Task(Of TResult)` in Visual Basic). La nuova attività rappresenta completamente l'attività annidata interna e include lo stato di annullamento e tutte le eccezioni.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come usare i metodi di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>
- [Programmazione asincrona basata su attivitàTask-based Asynchronous Programming](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
