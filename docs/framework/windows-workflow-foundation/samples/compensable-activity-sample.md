---
title: Esempio di CompensableActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b8d7fb5650a8927016e0deebc07a68a8145496db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="3afe9-102">Esempio di CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="3afe9-102">Compensable Activity Sample</span></span>
<span data-ttu-id="3afe9-103">In questo esempio viene illustrato come usare l'attività `CompensableActivity` per definire il lavoro da eseguire per un'azione specificata durante la normale esecuzione e il lavoro che è necessario eseguire per compensare tale azione, se necessario in un secondo tempo.</span><span class="sxs-lookup"><span data-stu-id="3afe9-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="3afe9-104">Nella prima parte dell'esempio viene illustrato come possono essere definite unità di lavoro compensabile in [!INCLUDE[wf](../../../../includes/wf-md.md)] usando un'attività `CompensableActivity` e come vengono eseguiti in un'esecuzione riuscita.</span><span class="sxs-lookup"><span data-stu-id="3afe9-104">The first part of the sample shows how units of compensable work can be defined in [!INCLUDE[wf](../../../../includes/wf-md.md)] using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="3afe9-105">Nella seconda parte dell'esempio viene illustrato in che modo le stesse unità di lavoro compensabile eseguono automaticamente la compensazione quando viene rilevato un evento imprevisto e l'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="3afe9-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3afe9-106">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="3afe9-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3afe9-107">Tramite Visual Studio 2010 aprire CompensableActivity.sln.</span><span class="sxs-lookup"><span data-stu-id="3afe9-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="3afe9-108">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="3afe9-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="3afe9-109">Eseguire l'applicazione premendo F5.</span><span class="sxs-lookup"><span data-stu-id="3afe9-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3afe9-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3afe9-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3afe9-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3afe9-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3afe9-112">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3afe9-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3afe9-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3afe9-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`  
  
## <a name="see-also"></a><span data-ttu-id="3afe9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3afe9-114">See Also</span></span>
