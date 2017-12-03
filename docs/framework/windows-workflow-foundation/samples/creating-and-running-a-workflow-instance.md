---
title: Creazione ed esecuzione di un'istanza del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b25acebfaf6df68ac3163a5ef4bcb235077139cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="3adc6-102">Creazione ed esecuzione di un'istanza del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="3adc6-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="3adc6-103">In questo esempio viene illustrato come eseguire un'istanza del flusso di lavoro,</span><span class="sxs-lookup"><span data-stu-id="3adc6-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="3adc6-104">sia in modo sincrono che asincrono.</span><span class="sxs-lookup"><span data-stu-id="3adc6-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3adc6-105">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="3adc6-105">Demonstrates</span></span>  
 <span data-ttu-id="3adc6-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="3adc6-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3adc6-107">Discussione</span><span class="sxs-lookup"><span data-stu-id="3adc6-107">Discussion</span></span>  
 <span data-ttu-id="3adc6-108">Nella prima parte dell'esempio viene usato <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="3adc6-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="3adc6-109">Si tratta della modalità di base per eseguire un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3adc6-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="3adc6-110">I flussi di lavoro eseguiti con <xref:System.Activities.WorkflowInvoker.Invoke%2A> possono esserlo solo in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="3adc6-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="3adc6-111">Nella seconda parte dell'esempio viene usata la classe <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="3adc6-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="3adc6-112"><xref:System.Activities.WorkflowApplication> consente un maggiore controllo su ogni istanza, inclusa la possibilità di interagire con il flusso di lavoro in esecuzione ed eseguirlo in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="3adc6-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3adc6-113">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3adc6-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3adc6-114">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3adc6-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3adc6-115">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3adc6-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3adc6-116">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3adc6-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="3adc6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3adc6-117">See Also</span></span>  
 [<span data-ttu-id="3adc6-118">Uso di WorkflowInvoker e WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="3adc6-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
