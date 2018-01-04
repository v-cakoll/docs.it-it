---
title: Esposizione e richiamo di ActivityAction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4285718ef1829e9432957278d5ca7959e32e4511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="ccd9e-102">Esposizione e richiamo di ActivityAction</span><span class="sxs-lookup"><span data-stu-id="ccd9e-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="ccd9e-103">In questo esempio viene illustrato come sviluppare un'attività personalizzata che dispone di un oggetto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="ccd9e-104">Viene inoltre illustrato come usare questa attività fornendo un'implementazione dell'oggetto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="ccd9e-105">Un <xref:System.Activities.ActivityAction> consente all'autore di attività di esporre "problemi di sicurezza" con firme specifiche in cui l'utente di attività può associare un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="ccd9e-106">Ad esempio, il <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` attività (che agisce su una raccolta di elementi) dispone di un <xref:System.Activities.ActivityAction> che consente all'utente di attività associare un comportamento che agisce sull'elemento di iterazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ccd9e-107">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ccd9e-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ccd9e-108">Aprire il **ActivityAction.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccd9e-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ccd9e-109">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ccd9e-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ccd9e-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ccd9e-112">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccd9e-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ccd9e-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ccd9e-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`