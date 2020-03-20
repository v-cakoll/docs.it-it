---
title: Segnalibro di ripresa WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: d393a26dd29624765e01b139e818de8a41f73e06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182734"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="6c625-102">Segnalibro di ripresa WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="6c625-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="6c625-103">In questo esempio viene illustrato come usare l'oggetto <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con l'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> per creare istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6c625-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="6c625-104">Dimostra</span><span class="sxs-lookup"><span data-stu-id="6c625-104">Demonstrates</span></span>  
 <span data-ttu-id="6c625-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="6c625-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="6c625-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="6c625-106">Discussion</span></span>  
 <span data-ttu-id="6c625-107">In questo esempio viene usato <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per creare un'istanza del flusso di lavoro ospitata usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6c625-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="6c625-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> è un punto di estensibilità per <xref:System.ServiceModel.Activities.WorkflowServiceHost> che può essere usato negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c625-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
- <span data-ttu-id="6c625-109">Creazione di nuove istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6c625-109">Creating new workflow instances.</span></span>  
  
- <span data-ttu-id="6c625-110">Ripresa di segnalibri in un'istanza del flusso di lavoro ospitata in un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="6c625-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="6c625-111">L'endpoint di esempio incluso espone un contratto che fornisce operazioni per creare un flusso di lavoro e restituire l'ID istanza o per creare un'istanza con un ID specifico.</span><span class="sxs-lookup"><span data-stu-id="6c625-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="6c625-112">L'applicazione console di esempio crea un'istanza <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definizione di flusso di lavoro di base e aggiunge un oggetto `CreationEndpoint` all'host.</span><span class="sxs-lookup"><span data-stu-id="6c625-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="6c625-113">Successivamente chiama l'operazione `Create` nell'endpoint per creare una nuova istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6c625-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6c625-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="6c625-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6c625-115">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="6c625-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="6c625-116">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6c625-116">Run the application.</span></span> <span data-ttu-id="6c625-117">Nella console `CreationEndpoint` viene visualizzato un messaggio che include l'ID istanza quando viene creata l'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6c625-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="6c625-118">Il messaggio "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6c625-118">The message "Hello World!"</span></span> <span data-ttu-id="6c625-119">viene stampato dal flusso di lavoro al completamento della ripresa del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="6c625-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6c625-120">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6c625-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c625-121">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6c625-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6c625-122">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6c625-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c625-123">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6c625-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
