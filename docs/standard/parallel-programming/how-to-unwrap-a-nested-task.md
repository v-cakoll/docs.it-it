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
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="80ae1-102">Procedura: annullare il wrapping di un'attività annidata</span><span class="sxs-lookup"><span data-stu-id="80ae1-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="80ae1-103">È possibile restituire un'attività da un metodo e attendere o continua da tale attività, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="80ae1-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="80ae1-104">Nell'esempio precedente, il <xref:System.Threading.Tasks.Task%601.Result%2A> proprietà è di tipo `string` (`String` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="80ae1-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="80ae1-105">Tuttavia, in alcuni scenari, è consigliabile creare un'attività all'interno di un'altra attività e quindi restituire l'attività annidata.</span><span class="sxs-lookup"><span data-stu-id="80ae1-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="80ae1-106">In questo caso, il `TResult` dell'attività contenitore è un'attività.</span><span class="sxs-lookup"><span data-stu-id="80ae1-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="80ae1-107">Nell'esempio seguente, la proprietà del risultato è un `Task<Task<string>>` in c# o `Task(Of Task(Of String))` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="80ae1-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="80ae1-108">Sebbene sia possibile scrivere codice per annullare il wrapping dell'attività esterna e recuperare l'attività originale e il relativo <xref:System.Threading.Tasks.Task%601.Result%2A> proprietà, tale codice non è più semplice la scrittura in quanto è necessario gestire le eccezioni, nonché le richieste di annullamento.</span><span class="sxs-lookup"><span data-stu-id="80ae1-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="80ae1-109">In questo caso, è consigliabile utilizzare uno del <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metodi di estensione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="80ae1-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="80ae1-110">Il <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metodi possono essere utilizzati per trasformare qualsiasi `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` in Visual Basic) per un `Task` o `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="80ae1-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="80ae1-111">La nuova attività completamente rappresenta l'attività annidata interna e include lo stato di annullamento e tutte le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="80ae1-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80ae1-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="80ae1-112">Example</span></span>  
 <span data-ttu-id="80ae1-113">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="80ae1-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="80ae1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80ae1-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="80ae1-115">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="80ae1-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
