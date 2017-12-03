---
title: Ottenere WorkflowInstanceId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e8794be83a80882e2e249c0f774697f6174d0b8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="get-workflowinstanceid"></a><span data-ttu-id="089c1-102">Ottenere WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="089c1-102">Get WorkflowInstanceId</span></span>
<span data-ttu-id="089c1-103">In questo esempio viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="089c1-103">This sample demonstrates how to use the custom activity, `GetWorkflowInstanceId` to return the workflow instance ID.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="089c1-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="089c1-104">Demonstrates</span></span>  
 <span data-ttu-id="089c1-105">Sviluppo dell'attività personalizzata, come accedere all'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="089c1-105">Custom activity development, how to access the workflow instance.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="089c1-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="089c1-106">Discussion</span></span>  
 <span data-ttu-id="089c1-107">L'acquisizione dell'ID istanza di un flusso di lavoro in esecuzione richiede che venga scritto codice.</span><span class="sxs-lookup"><span data-stu-id="089c1-107">Getting the instance ID of a running workflow requires writing code.</span></span> <span data-ttu-id="089c1-108">Se si desidera scrivere un flusso di lavoro completamente dichiarativo, è necessaria un'attività che possa restituire l'ID istanza del flusso di lavoro in modo che sia possibile fare riferimento all'attività nel flusso di lavoro per fornire una creazione di flussi di lavoro completamente dichiarativa.</span><span class="sxs-lookup"><span data-stu-id="089c1-108">If you want to write a fully-declarative workflow, then you need an activity that can return the workflow instance ID so that the activity can be referenced in the workflow to provide a fully-declarative workflow authoring experience.</span></span> <span data-ttu-id="089c1-109">Molti scenari richiedono l'accesso all'ID istanza: alcuni esempi sono per la registrazione o il controllo degli scopi o per eseguire la correlazione a livello di applicazione fornendo di nuovo l'ID istanza a un client per l'associazione futura (ad esempio, tramite questa attività in un'attività SendReply).</span><span class="sxs-lookup"><span data-stu-id="089c1-109">Many scenarios require access to the instance ID: a few examples are for logging or auditing purposes or for doing application-level correlation by providing the instance ID back to a client for future association (for example, by using this activity inside a SendReply activity).</span></span>  
  
 <span data-ttu-id="089c1-110">L'oggetto `GetWorkflowInstanceId` viene implementato come oggetto <xref:System.Activities.CodeActivity%601> perché deve restituire un valore di tipo <xref:System.Guid> e deve disporre dell'accesso all'oggetto <xref:System.Activities.CodeActivityContext> per l'acquisizione dell'ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="089c1-110">`GetWorkflowInstanceId` is implemented as a <xref:System.Activities.CodeActivity%601> because it must return a value of type <xref:System.Guid>, and it must have access to the <xref:System.Activities.CodeActivityContext> for getting the workflow’s instance ID.</span></span> <span data-ttu-id="089c1-111">L'implementazione è abbastanza semplice.</span><span class="sxs-lookup"><span data-stu-id="089c1-111">Its implementation is fairly basic.</span></span>  
  
```  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
protected override Guid Execute(CodeActivityContext context)  
        {  
            return context.WorkflowInstanceId;  
        }  
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="089c1-112">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="089c1-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="089c1-113">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="089c1-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="089c1-114">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="089c1-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="089c1-115">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="089c1-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
