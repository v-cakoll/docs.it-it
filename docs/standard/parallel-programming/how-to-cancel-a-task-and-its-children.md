---
title: "Procedura: Annullare un'attività e i relativi figli"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: ca6b5f10840d935aa45cb660da86685d1c90554b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290032"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="6b49e-102">Procedura: Annullare un'attività e i relativi figli</span><span class="sxs-lookup"><span data-stu-id="6b49e-102">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="6b49e-103">Questi esempi mostrano come eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b49e-103">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="6b49e-104">Creare e avviare un'attività annullabile.</span><span class="sxs-lookup"><span data-stu-id="6b49e-104">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="6b49e-105">Passare un token di annullamento al delegato dell'utente e, facoltativamente, all'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6b49e-105">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="6b49e-106">Rilevare e rispondere alla richiesta di annullamento nel delegato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6b49e-106">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="6b49e-107">Facoltativamente, indicare nel thread chiamante che l'attività è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="6b49e-107">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="6b49e-108">Il thread chiamante non forza la fine dell'attività, ma segnala solo che è richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="6b49e-108">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="6b49e-109">Se l'attività è già in esecuzione, è responsabilità del delegato dell'utente rilevare la richiesta e rispondervi nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6b49e-109">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="6b49e-110">Se l'annullamento viene richiesto prima dell'esecuzione dell'attività, il delegato dell'utente non viene mai eseguito e l'oggetto attività passa allo stato annullato.</span><span class="sxs-lookup"><span data-stu-id="6b49e-110">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b49e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b49e-111">Example</span></span>  
 <span data-ttu-id="6b49e-112">Questo esempio mostra come terminare un'attività <xref:System.Threading.Tasks.Task> e i relativi elementi figlio in risposta a una richiesta di annullamento.</span><span class="sxs-lookup"><span data-stu-id="6b49e-112">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="6b49e-113">Viene inoltre mostrato che quando un delegato dell'utente viene terminato generando un oggetto <xref:System.Threading.Tasks.TaskCanceledException>, tramite il thread chiamante è possibile utilizzare facoltativamente il metodo <xref:System.Threading.Tasks.Task.Wait%2A> o il metodo <xref:System.Threading.Tasks.Task.WaitAll%2A> per attendere il completamento delle attività.</span><span class="sxs-lookup"><span data-stu-id="6b49e-113">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="6b49e-114">In questo caso, è necessario utilizzare un blocco `try/catch` per gestire le eccezioni nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="6b49e-114">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="6b49e-115">La classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> è completamente integrata con il modello di annullamento basato sui tipi <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> e <xref:System.Threading.CancellationToken?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6b49e-115">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="6b49e-116">Per altre informazioni, vedere [Annullamento in thread gestiti](../threading/cancellation-in-managed-threads.md) e [Annullamento delle attività](task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="6b49e-116">For more information, see [Cancellation in Managed Threads](../threading/cancellation-in-managed-threads.md) and [Task Cancellation](task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b49e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b49e-117">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="6b49e-118">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="6b49e-118">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="6b49e-119">Attività figlio connesse e disconnesse</span><span class="sxs-lookup"><span data-stu-id="6b49e-119">Attached and Detached Child Tasks</span></span>](attached-and-detached-child-tasks.md)
- [<span data-ttu-id="6b49e-120">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="6b49e-120">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
