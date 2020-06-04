---
title: Ottimizzazione dell'applicazione Async
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: e33f86177a3680d41ec04842dbc120713a48f61c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396649"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="532f9-102">Ottimizzazione dell'applicazione Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="532f9-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="532f9-103">È possibile rendere più precise e flessibili le applicazioni asincrone usando le proprietà e i metodi resi disponibili dal tipo <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="532f9-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="532f9-104">Gli argomenti di questa sezione mostrano esempi che usano <xref:System.Threading.CancellationToken> e metodi `Task` importanti, ad esempio <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="532f9-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="532f9-105">Usando `WhenAny` e `WhenAll`, è possibile avviare più attività e attenderne il completamento da una singola attività di monitoraggio in modo più facile.</span><span class="sxs-lookup"><span data-stu-id="532f9-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
- <span data-ttu-id="532f9-106">`WhenAny` restituisce un'attività completata quando una qualsiasi attività in una raccolta viene completata.</span><span class="sxs-lookup"><span data-stu-id="532f9-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="532f9-107">Per esempi che usano `WhenAny` , vedere [annullare le attività asincrone rimanenti dopo che ne è stata completata una (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)e [avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="532f9-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
- <span data-ttu-id="532f9-108">`WhenAll` restituisce un'attività completata quando tutte le attività in una raccolta vengono completate.</span><span class="sxs-lookup"><span data-stu-id="532f9-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="532f9-109">Per ulteriori informazioni e un esempio di utilizzo `WhenAll` di, vedere [procedura: estendere la procedura dettagliata asincrona tramite Task. WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="532f9-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="532f9-110">Questa sezione presenta i seguenti esempi.</span><span class="sxs-lookup"><span data-stu-id="532f9-110">This section includes the following examples.</span></span>  
  
- <span data-ttu-id="532f9-111">[Annullare un'attività asincrona o un elenco di attività (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="532f9-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
- [<span data-ttu-id="532f9-112">Annullare attività asincrone dopo un periodo di tempo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="532f9-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](cancel-async-tasks-after-a-period-of-time.md)  
  
- [<span data-ttu-id="532f9-113">Annullare le attività asincrone rimanenti dopo che ne è stata completata una(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="532f9-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](cancel-remaining-async-tasks-after-one-is-complete.md)  
  
- [<span data-ttu-id="532f9-114">Avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="532f9-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
> <span data-ttu-id="532f9-115">Per eseguire gli esempi, è necessario avere installato Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive nel computer.</span><span class="sxs-lookup"><span data-stu-id="532f9-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="532f9-116">I progetti creano un'interfaccia utente che contiene un pulsante che consente di avviare il processo e un pulsante che consente di annullarlo, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="532f9-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="532f9-117">I pulsanti sono denominati `startButton` e `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="532f9-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="532f9-118">![Finestra WPF con pulsante Annulla](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Finestra di dialogo con un pulsante avvia e arresta")</span><span class="sxs-lookup"><span data-stu-id="532f9-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="532f9-119">È possibile scaricare i progetti completi di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="532f9-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532f9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="532f9-120">See also</span></span>

- [<span data-ttu-id="532f9-121">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="532f9-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](index.md)
