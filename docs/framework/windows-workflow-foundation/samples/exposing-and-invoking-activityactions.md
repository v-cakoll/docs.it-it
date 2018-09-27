---
title: Esposizione e richiamo di ActivityAction
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 99207c33d82ec9028da2355cc792c366dc5e0cc6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47398563"
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="01452-102">Esposizione e richiamo di ActivityAction</span><span class="sxs-lookup"><span data-stu-id="01452-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="01452-103">In questo esempio viene illustrato come sviluppare un'attività personalizzata che dispone di un oggetto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="01452-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="01452-104">Viene inoltre illustrato come usare questa attività fornendo un'implementazione dell'oggetto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="01452-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="01452-105">Un <xref:System.Activities.ActivityAction> consente a un autore di attività di esporre "buchi" con le firme specifiche in cui l'utente di attività può collegare un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="01452-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="01452-106">Ad esempio, l'attività <xref:System.Activities.Statements.ForEach%601> (che agisce su una raccolta di elementi) dispone di un oggetto <xref:System.Activities.ActivityAction> che consente all'utente di attività di associare un comportamento che agisce sull'elemento di iterazione corrente.</span><span class="sxs-lookup"><span data-stu-id="01452-106">For example, the <xref:System.Activities.Statements.ForEach%601> activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="01452-107">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="01452-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="01452-108">Aprire il **ActivityAction** nella soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01452-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="01452-109">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="01452-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01452-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="01452-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="01452-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="01452-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="01452-112">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="01452-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="01452-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="01452-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`