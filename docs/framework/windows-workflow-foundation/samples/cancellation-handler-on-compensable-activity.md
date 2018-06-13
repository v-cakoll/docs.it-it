---
title: Gestore di annullamento nell'attività compensabile
ms.date: 03/30/2017
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
ms.openlocfilehash: ce4d67b26a2b4c6a9b507715b48e75e328c5b100
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515001"
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="30b2f-102">Gestore di annullamento nell'attività compensabile</span><span class="sxs-lookup"><span data-stu-id="30b2f-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="30b2f-103">In questo esempio viene illustrato l'uso di un gestore di annullamento in un oggetto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="30b2f-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="30b2f-104">Nell'esempio sono disponibili due scenari in cui viene illustrato l'uso dell'annullamento dell'oggetto <xref:System.Activities.Statements.CompensableActivity>. Nel primo scenario è inclusa un'attività compensabile radice che contiene tre attività compensabili figlio.</span><span class="sxs-lookup"><span data-stu-id="30b2f-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="30b2f-105">Le due attività figlio completano correttamente l'esecuzione dei relativi corpi delle attività.</span><span class="sxs-lookup"><span data-stu-id="30b2f-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="30b2f-106">Quando viene eseguito il corpo della terza attività figlio, viene rilevata un'eccezione gestita annullando l'elaborazione della terza attività, dopo che viene attivato l'annullamento dell'attività radice.</span><span class="sxs-lookup"><span data-stu-id="30b2f-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="30b2f-107">La logica nell'attività radice in questo esempio consiste nel compensare le altre due attività figlio che vengono completate precedentemente.</span><span class="sxs-lookup"><span data-stu-id="30b2f-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="30b2f-108">Nel secondo scenario viene illustrata l'esecuzione di un oggetto <xref:System.Activities.Statements.TryCatch> in parallelo con un oggetto <xref:System.Activities.Statements.Delay> che termina prima del ramo <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="30b2f-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="30b2f-109">La condizione di completamento viene impostata su `true` una volta terminato il primo ramo, determinando l'annullamento dell'altro ramo.</span><span class="sxs-lookup"><span data-stu-id="30b2f-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="30b2f-110">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="30b2f-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="30b2f-111">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire CompensationCancellation.sln.</span><span class="sxs-lookup"><span data-stu-id="30b2f-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="30b2f-112">Compilare l'esempio premendo CTRL + MAIUSC + B o selezionare "Compila soluzione" dal menu Compila.</span><span class="sxs-lookup"><span data-stu-id="30b2f-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="30b2f-113">Eseguire l'esempio premendo F5 o selezionare "Avvia debug" dal menu Debug.</span><span class="sxs-lookup"><span data-stu-id="30b2f-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="30b2f-114">In alternativa, è possibile premere Ctrl+F5 o selezionare "Avvia senza eseguire debug" dal menu Debug.</span><span class="sxs-lookup"><span data-stu-id="30b2f-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30b2f-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="30b2f-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="30b2f-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="30b2f-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="30b2f-117">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="30b2f-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="30b2f-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="30b2f-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`