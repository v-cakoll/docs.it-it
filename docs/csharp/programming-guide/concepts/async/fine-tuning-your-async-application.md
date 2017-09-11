---
title: Ottimizzazione dell'applicazione asincrona (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7afcdb28fbe10d5aa33dd2704d264ffd716af5d6
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="e1ea0-102">Ottimizzazione dell'applicazione asincrona (C#)</span><span class="sxs-lookup"><span data-stu-id="e1ea0-102">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="e1ea0-103">È possibile rendere più precise e flessibili le applicazioni asincrone usando le proprietà e i metodi resi disponibili dal tipo <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="e1ea0-104">Gli argomenti di questa sezione mostrano esempi che usano <xref:System.Threading.CancellationToken> e metodi `Task` importanti, ad esempio <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="e1ea0-105">Usando `WhenAny` e `WhenAll`, è possibile avviare più attività e attenderne il completamento da una singola attività di monitoraggio in modo più facile.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="e1ea0-106">`WhenAny` restituisce un'attività completata quando una qualsiasi attività in una raccolta viene completata.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="e1ea0-107">Per esempi che usano `WhenAny`, vedere [Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) e [Avviare più attività asincrone ed elaborarle quando vengono completate (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="e1ea0-107">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="e1ea0-108">`WhenAll` restituisce un'attività completata quando tutte le attività in una raccolta vengono completate.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="e1ea0-109">Per altre informazioni e un esempio che usa `WhenAll`, vedere [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (C#)).</span><span class="sxs-lookup"><span data-stu-id="e1ea0-109">For more information and an example that uses `WhenAll`, see [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="e1ea0-110">Questa sezione presenta i seguenti esempi.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="e1ea0-111">[Annullare un'attività asincrona o un elenco di attività (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="e1ea0-111">[Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="e1ea0-112">Annullare attività asincrone dopo un periodo di tempo (C#)</span><span class="sxs-lookup"><span data-stu-id="e1ea0-112">Cancel Async Tasks after a Period of Time (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="e1ea0-113">Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)</span><span class="sxs-lookup"><span data-stu-id="e1ea0-113">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="e1ea0-114">Avviare più attività asincrone ed elaborarle quando vengono completate (C#)</span><span class="sxs-lookup"><span data-stu-id="e1ea0-114">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="e1ea0-115">Per eseguire gli esempi, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="e1ea0-116">I progetti creano un'interfaccia utente che contiene un pulsante che consente di avviare il processo e un pulsante che consente di annullarlo, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="e1ea0-117">I pulsanti sono denominati `startButton` e `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="e1ea0-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="e1ea0-118">![Finestra WPF con pulsante Annulla](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Annullamento")</span><span class="sxs-lookup"><span data-stu-id="e1ea0-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="e1ea0-119">È possibile scaricare i progetti completi di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="e1ea0-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ea0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1ea0-120">See Also</span></span>  
 [<span data-ttu-id="e1ea0-121">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="e1ea0-121">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)

