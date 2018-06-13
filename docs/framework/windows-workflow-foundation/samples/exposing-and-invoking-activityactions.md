---
title: Esposizione e richiamo di ActivityAction
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 2d369ec4b028b047ce02016dd511c1c088b46a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513152"
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="658d5-102">Esposizione e richiamo di ActivityAction</span><span class="sxs-lookup"><span data-stu-id="658d5-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="658d5-103">In questo esempio viene illustrato come sviluppare un'attività personalizzata che dispone di un oggetto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="658d5-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="658d5-104">Viene inoltre illustrato come usare questa attività fornendo un'implementazione dell'oggetto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="658d5-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="658d5-105">Un <xref:System.Activities.ActivityAction> consente all'autore di attività di esporre "problemi di sicurezza" con firme specifiche in cui l'utente di attività può associare un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="658d5-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="658d5-106">Ad esempio, il <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` attività (che agisce su una raccolta di elementi) dispone di un <xref:System.Activities.ActivityAction> che consente all'utente di attività associare un comportamento che agisce sull'elemento di iterazione corrente.</span><span class="sxs-lookup"><span data-stu-id="658d5-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="658d5-107">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="658d5-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="658d5-108">Aprire il **ActivityAction.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="658d5-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="658d5-109">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="658d5-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="658d5-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="658d5-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="658d5-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="658d5-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="658d5-112">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="658d5-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="658d5-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="658d5-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`