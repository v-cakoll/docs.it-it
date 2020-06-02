---
title: "Procedura: Annullare il wrapping di un'attività annidata"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
ms.openlocfilehash: 9a69fa42da41ee4a071a6571042fd96fb5a009d2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288030"
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="98421-102">Procedura: Annullare il wrapping di un'attività annidata</span><span class="sxs-lookup"><span data-stu-id="98421-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="98421-103">È possibile restituire un'attività da un metodo e quindi attendere o continuare da tale attività, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="98421-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="98421-104">Nell'esempio precedente la proprietà <xref:System.Threading.Tasks.Task%601.Result%2A> è di tipo `string` (`String` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="98421-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="98421-105">In alcuni scenari, tuttavia, è consigliabile creare un'attività all'interno di un'altra attività e quindi restituire l'attività annidata.</span><span class="sxs-lookup"><span data-stu-id="98421-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="98421-106">In questo caso, l'oggetto `TResult` dell'attività contenitore è esso stesso un'attività.</span><span class="sxs-lookup"><span data-stu-id="98421-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="98421-107">Nell'esempio seguente la proprietà Result è di tipo `Task<Task<string>>` in C# o `Task(Of Task(Of String))` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="98421-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="98421-108">Anche se è possibile scrivere codice per annullare il wrapping dell'attività esterna e recuperare l'attività originale e la relativa proprietà <xref:System.Threading.Tasks.Task%601.Result%2A>, tale codice non è semplice da scrivere perché è necessario gestire le eccezioni e anche le richieste di annullamento.</span><span class="sxs-lookup"><span data-stu-id="98421-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="98421-109">In questo caso, è consigliabile usare uno dei metodi di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="98421-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="98421-110">I metodi <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> possono essere usati per trasformare qualsiasi oggetto `Task<Task>` o `Task<Task<TResult>>` (`Task(Of Task)` o `Task(Of Task(Of TResult))` in Visual Basic) in un oggetto `Task` o `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="98421-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="98421-111">La nuova attività rappresenta completamente l'attività annidata interna e include lo stato di annullamento e tutte le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="98421-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98421-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="98421-112">Example</span></span>  
 <span data-ttu-id="98421-113">L'esempio seguente illustra come usare i metodi di estensione <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="98421-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="98421-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98421-114">See also</span></span>

- <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>
- [<span data-ttu-id="98421-115">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="98421-115">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
