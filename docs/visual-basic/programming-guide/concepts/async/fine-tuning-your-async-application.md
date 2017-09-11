---
title: Ottimizzazione dell&quot;applicazione Async (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e031c2e23430a62629424ee57a140a7d8da41777
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="82fe0-102">Ottimizzazione dell'applicazione Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82fe0-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="82fe0-103">È possibile aggiungere precisione e flessibilità alle applicazioni asincrone utilizzando i metodi e proprietà che la <xref:System.Threading.Tasks.Task>tipo rende disponibile.</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="82fe0-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="82fe0-104">Negli argomenti di questa sezione mostrano esempi che utilizzano <xref:System.Threading.CancellationToken>e importante `Task` metodi quali <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> </xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="82fe0-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="82fe0-105">Utilizzando `WhenAny` e `WhenAll`, è possibile avviare più attività e attendere il completamento da una singola attività di monitoraggio più facilmente.</span><span class="sxs-lookup"><span data-stu-id="82fe0-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="82fe0-106">`WhenAny`Restituisce un'attività che viene completata quando un'attività in una raccolta è stata completata.</span><span class="sxs-lookup"><span data-stu-id="82fe0-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="82fe0-107">Per esempi che utilizzano `WhenAny`, vedere [annullare attività asincrone rimanenti dopo una completa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)e [avviare più attività asincrone e processo li come essi completa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="82fe0-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="82fe0-108">`WhenAll`Restituisce un'attività che viene completata quando sono state completate tutte le attività in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="82fe0-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="82fe0-109">Per ulteriori informazioni e un esempio che utilizza `WhenAll`, vedere [procedura: estendere la Async Walkthrough da tramite Task. whenall (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="82fe0-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="82fe0-110">In questa sezione sono inclusi gli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="82fe0-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="82fe0-111">[Annullare un'attività asincrona o un elenco di attività (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="82fe0-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="82fe0-112">Annullare attività asincrone dopo un periodo di tempo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82fe0-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="82fe0-113">Annullare le attività asincrone rimanenti dopo che ne è completa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82fe0-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="82fe0-114">Avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82fe0-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="82fe0-115">Per eseguire gli esempi, è necessario disporre di Visual Studio 2012 o versione successiva e .NET Framework 4.5 o versioni successive installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="82fe0-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="82fe0-116">I progetti di creare un'interfaccia utente che contiene un pulsante che avvia il processo e un pulsante che consente di annullare, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="82fe0-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="82fe0-117">I pulsanti sono denominati `startButton` e `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="82fe0-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="82fe0-118">![Finestra WPF con pulsante Annulla](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "annullamento")</span><span class="sxs-lookup"><span data-stu-id="82fe0-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="82fe0-119">È possibile scaricare i progetti Windows Presentation Foundation (WPF) completa da [esempio asincrono: Fine ottimizzazione dell'applicazione](http://go.microsoft.com/fwlink/?LinkId=255046).</span><span class="sxs-lookup"><span data-stu-id="82fe0-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82fe0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82fe0-120">See Also</span></span>  
 [<span data-ttu-id="82fe0-121">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82fe0-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
