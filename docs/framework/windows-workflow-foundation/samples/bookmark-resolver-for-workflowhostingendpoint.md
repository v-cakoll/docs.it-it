---
title: Risolver di segnalibri per WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 4676b3c624a7ba1539a7a12ed38c286f688dcf9f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344299"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a><span data-ttu-id="b1af2-102">Risolver di segnalibri per WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="b1af2-102">Bookmark Resolver for WorkflowHostingEndpoint</span></span>
<span data-ttu-id="b1af2-103">In questo esempio viene illustrato come usare l'oggetto <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con l'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> per creare istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b1af2-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b1af2-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="b1af2-104">Demonstrates</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint><span data-ttu-id="b1af2-105">,</span><span class="sxs-lookup"><span data-stu-id="b1af2-105">,</span></span> <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a><span data-ttu-id="b1af2-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="b1af2-106">Discussion</span></span>  
 <span data-ttu-id="b1af2-107">In questo esempio viene usato <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per creare istanze del flusso di lavoro ospitate usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b1af2-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create workflow instances hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> <span data-ttu-id="b1af2-108">è un punto di estendibilità per <xref:System.ServiceModel.Activities.WorkflowServiceHost> che può essere utilizzato negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1af2-108">is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="b1af2-109">Creazione di nuove istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b1af2-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="b1af2-110">Ripresa di segnalibri nell'istanza del flusso di lavoro ospitata in un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b1af2-110">Resuming bookmarks on workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="b1af2-111">L'endpoint di esempio incluso espone un contratto che fornisce operazioni per creare un flusso di lavoro e restituisce l'ID istanza o crea un'istanza con un ID specifico.</span><span class="sxs-lookup"><span data-stu-id="b1af2-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and returns the instance ID or creates an instance with a specific ID.</span></span> <span data-ttu-id="b1af2-112">L'applicazione console di esempio crea un'istanza <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definizione di flusso di lavoro e aggiunge un oggetto `CreationEndpoint` all'host.</span><span class="sxs-lookup"><span data-stu-id="b1af2-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a workflow definition and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="b1af2-113">Successivamente chiama l'operazione `Create` nell'endpoint per creare una nuova istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b1af2-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b1af2-114">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b1af2-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b1af2-115">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="b1af2-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="b1af2-116">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b1af2-116">Run the application.</span></span> <span data-ttu-id="b1af2-117">Nella console `CreationEndpoint` viene visualizzato un messaggio che include l'ID istanza quando viene creata l'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b1af2-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="b1af2-118">Il messaggio "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="b1af2-118">The message "Hello World!"</span></span> <span data-ttu-id="b1af2-119">viene stampato dall'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b1af2-119">is printed by the workflow instance.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1af2-120">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b1af2-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b1af2-121">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b1af2-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b1af2-122">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b1af2-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b1af2-123">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b1af2-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
