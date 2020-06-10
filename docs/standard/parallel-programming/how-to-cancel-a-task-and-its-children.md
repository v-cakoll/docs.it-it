---
title: "Procedura: Annullare un'attività e i relativi figli"
description: Vedere esempi di come annullare un'attività e i relativi elementi figlio in .NET. Gli esempi illustrano i passaggi della creazione di un'attività annullabile, fino alla nota che l'attività è stata annullata.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
ms.openlocfilehash: 66daf00680b65aace1ce6367761e3ed81596d33b
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662680"
---
# <a name="how-to-cancel-a-task-and-its-children"></a><span data-ttu-id="ee416-104">Procedura: Annullare un'attività e i relativi figli</span><span class="sxs-lookup"><span data-stu-id="ee416-104">How to: Cancel a Task and Its Children</span></span>
<span data-ttu-id="ee416-105">Questi esempi mostrano come eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ee416-105">These examples show how to perform the following tasks:</span></span>  
  
1. <span data-ttu-id="ee416-106">Creare e avviare un'attività annullabile.</span><span class="sxs-lookup"><span data-stu-id="ee416-106">Create and start a cancelable task.</span></span>  
  
2. <span data-ttu-id="ee416-107">Passare un token di annullamento al delegato dell'utente e, facoltativamente, all'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ee416-107">Pass a cancellation token to your user delegate and optionally to the task instance.</span></span>  
  
3. <span data-ttu-id="ee416-108">Rilevare e rispondere alla richiesta di annullamento nel delegato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ee416-108">Notice and respond to the cancellation request in your user delegate.</span></span>  
  
4. <span data-ttu-id="ee416-109">Facoltativamente, indicare nel thread chiamante che l'attività è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="ee416-109">Optionally notice on the calling thread that the task was canceled.</span></span>  
  
 <span data-ttu-id="ee416-110">Il thread chiamante non forza la fine dell'attività, ma segnala solo che è richiesto l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee416-110">The calling thread does not forcibly end the task; it only signals that cancellation is requested.</span></span> <span data-ttu-id="ee416-111">Se l'attività è già in esecuzione, è responsabilità del delegato dell'utente rilevare la richiesta e rispondervi nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="ee416-111">If the task is already running, it is up to the user delegate to notice the request and respond appropriately.</span></span> <span data-ttu-id="ee416-112">Se l'annullamento viene richiesto prima dell'esecuzione dell'attività, il delegato dell'utente non viene mai eseguito e l'oggetto attività passa allo stato annullato.</span><span class="sxs-lookup"><span data-stu-id="ee416-112">If cancellation is requested before the task runs, then the user delegate is never executed and the task object transitions into the Canceled state.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee416-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee416-113">Example</span></span>  
 <span data-ttu-id="ee416-114">Questo esempio mostra come terminare un'attività <xref:System.Threading.Tasks.Task> e i relativi elementi figlio in risposta a una richiesta di annullamento.</span><span class="sxs-lookup"><span data-stu-id="ee416-114">This example shows how to terminate a <xref:System.Threading.Tasks.Task> and its children in response to a cancellation request.</span></span> <span data-ttu-id="ee416-115">Viene inoltre mostrato che quando un delegato dell'utente viene terminato generando un oggetto <xref:System.Threading.Tasks.TaskCanceledException>, tramite il thread chiamante è possibile utilizzare facoltativamente il metodo <xref:System.Threading.Tasks.Task.Wait%2A> o il metodo <xref:System.Threading.Tasks.Task.WaitAll%2A> per attendere il completamento delle attività.</span><span class="sxs-lookup"><span data-stu-id="ee416-115">It also shows that when a user delegate terminates by throwing a <xref:System.Threading.Tasks.TaskCanceledException>, the calling thread can optionally use the <xref:System.Threading.Tasks.Task.Wait%2A> method or <xref:System.Threading.Tasks.Task.WaitAll%2A> method to wait for the tasks to finish.</span></span> <span data-ttu-id="ee416-116">In questo caso, è necessario utilizzare un blocco `try/catch` per gestire le eccezioni nel thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="ee416-116">In this case, you must use a `try/catch` block to handle the exceptions on the calling thread.</span></span>  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <span data-ttu-id="ee416-117">La classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> è completamente integrata con il modello di annullamento basato sui tipi <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> e <xref:System.Threading.CancellationToken?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee416-117">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class is fully integrated with the cancellation model that is based on the <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> and <xref:System.Threading.CancellationToken?displayProperty=nameWithType> types.</span></span> <span data-ttu-id="ee416-118">Per altre informazioni, vedere [Annullamento in thread gestiti](../threading/cancellation-in-managed-threads.md) e [Annullamento delle attività](task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="ee416-118">For more information, see [Cancellation in Managed Threads](../threading/cancellation-in-managed-threads.md) and [Task Cancellation](task-cancellation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee416-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee416-119">See also</span></span>

- <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>
- <xref:System.Threading.CancellationToken?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [<span data-ttu-id="ee416-120">Programmazione asincrona basata su attività</span><span class="sxs-lookup"><span data-stu-id="ee416-120">Task-based Asynchronous Programming</span></span>](task-based-asynchronous-programming.md)
- [<span data-ttu-id="ee416-121">Attività figlio connesse e disconnesse</span><span class="sxs-lookup"><span data-stu-id="ee416-121">Attached and Detached Child Tasks</span></span>](attached-and-detached-child-tasks.md)
- [<span data-ttu-id="ee416-122">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="ee416-122">Lambda Expressions in PLINQ and TPL</span></span>](lambda-expressions-in-plinq-and-tpl.md)
