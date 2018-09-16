---
title: Esempio di CompensableActivity
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 3bf1d120cd700830a98f53495f7e9989ffec73db
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45678256"
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="1636f-102">Esempio di CompensableActivity</span><span class="sxs-lookup"><span data-stu-id="1636f-102">Compensable Activity Sample</span></span>
<span data-ttu-id="1636f-103">In questo esempio viene illustrato come usare l'attività `CompensableActivity` per definire il lavoro da eseguire per un'azione specificata durante la normale esecuzione e il lavoro che è necessario eseguire per compensare tale azione, se necessario in un secondo tempo.</span><span class="sxs-lookup"><span data-stu-id="1636f-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="1636f-104">La prima parte dell'esempio viene illustrato come unità di lavoro compensabile possono essere definite in Windows Workflow Foundation (WF) usando un `CompensableActivity` attività e come vengono eseguiti in un'esecuzione riuscita.</span><span class="sxs-lookup"><span data-stu-id="1636f-104">The first part of the sample shows how units of compensable work can be defined in Windows Workflow Foundation (WF) using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="1636f-105">Nella seconda parte dell'esempio viene illustrato in che modo le stesse unità di lavoro compensabile eseguono automaticamente la compensazione quando viene rilevato un evento imprevisto e l'istanza del flusso di lavoro viene annullata.</span><span class="sxs-lookup"><span data-stu-id="1636f-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1636f-106">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="1636f-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1636f-107">Tramite Visual Studio 2010 aprire CompensableActivity.sln.</span><span class="sxs-lookup"><span data-stu-id="1636f-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="1636f-108">Premere CTRL+MAIUSC+B per compilare la soluzione,</span><span class="sxs-lookup"><span data-stu-id="1636f-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1636f-109">Eseguire l'applicazione premendo F5.</span><span class="sxs-lookup"><span data-stu-id="1636f-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1636f-110">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1636f-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1636f-111">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1636f-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1636f-112">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="1636f-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1636f-113">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1636f-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`