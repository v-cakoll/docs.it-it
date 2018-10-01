---
title: Ottimizzazione dell'applicazione asincrona (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: 23557c0c920fbd858e9bdf8ae629bd5ef5f0355b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47197929"
---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="21e66-102">Ottimizzazione dell'applicazione asincrona (C#)</span><span class="sxs-lookup"><span data-stu-id="21e66-102">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="21e66-103">È possibile rendere più precise e flessibili le applicazioni asincrone usando le proprietà e i metodi resi disponibili dal tipo <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="21e66-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="21e66-104">Gli argomenti di questa sezione mostrano esempi che usano <xref:System.Threading.CancellationToken> e metodi `Task` importanti, ad esempio <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="21e66-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="21e66-105">Usando `WhenAny` e `WhenAll`, è possibile avviare più attività e attenderne il completamento da una singola attività di monitoraggio in modo più facile.</span><span class="sxs-lookup"><span data-stu-id="21e66-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="21e66-106">`WhenAny` restituisce un'attività completata quando una qualsiasi attività in una raccolta viene completata.</span><span class="sxs-lookup"><span data-stu-id="21e66-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="21e66-107">Per esempi che usano `WhenAny`, vedere [Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) e [Avviare più attività asincrone ed elaborarle quando vengono completate (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="21e66-107">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="21e66-108">`WhenAll` restituisce un'attività completata quando tutte le attività in una raccolta vengono completate.</span><span class="sxs-lookup"><span data-stu-id="21e66-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="21e66-109">Per altre informazioni e un esempio che usa `WhenAll`, vedere [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md) (Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (C#)).</span><span class="sxs-lookup"><span data-stu-id="21e66-109">For more information and an example that uses `WhenAll`, see [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="21e66-110">Questa sezione presenta i seguenti esempi.</span><span class="sxs-lookup"><span data-stu-id="21e66-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="21e66-111">[Annullare un'attività asincrona o un elenco di attività (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="21e66-111">[Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="21e66-112">Annullare attività asincrone dopo un periodo di tempo (C#)</span><span class="sxs-lookup"><span data-stu-id="21e66-112">Cancel Async Tasks after a Period of Time (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="21e66-113">Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)</span><span class="sxs-lookup"><span data-stu-id="21e66-113">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="21e66-114">Avviare più attività asincrone ed elaborarle quando vengono completate (C#)</span><span class="sxs-lookup"><span data-stu-id="21e66-114">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="21e66-115">Per eseguire gli esempi, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="21e66-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="21e66-116">I progetti creano un'interfaccia utente che contiene un pulsante che consente di avviare il processo e un pulsante che consente di annullarlo, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="21e66-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="21e66-117">I pulsanti sono denominati `startButton` e `cancelButton`.</span><span class="sxs-lookup"><span data-stu-id="21e66-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="21e66-118">![Finestra WPF con pulsante Annulla](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Annullamento")</span><span class="sxs-lookup"><span data-stu-id="21e66-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="21e66-119">È possibile scaricare i progetti completi di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).</span><span class="sxs-lookup"><span data-stu-id="21e66-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e66-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e66-120">See Also</span></span>

- [<span data-ttu-id="21e66-121">Programmazione asincrona con async e await (C#)</span><span class="sxs-lookup"><span data-stu-id="21e66-121">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)
