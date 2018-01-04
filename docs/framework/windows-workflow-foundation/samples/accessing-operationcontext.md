---
title: Accesso a OperationContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ca0290f658dfc5e34ec7e1e1be228213c521ce0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-operationcontext"></a><span data-ttu-id="414eb-102">Accesso a OperationContext</span><span class="sxs-lookup"><span data-stu-id="414eb-102">Accessing OperationContext</span></span>
<span data-ttu-id="414eb-103">Questo esempio viene illustrato come l'attività di messaggistica (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.Send>) può essere utilizzato con un'attività di ambiti personalizzata per accedere <xref:System.ServiceModel.OperationContext.Current%2A> e allegare o recuperare un'intestazione di messaggio personalizzata all'interno di un messaggio in ingresso o in uscita.</span><span class="sxs-lookup"><span data-stu-id="414eb-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.Send>) can be used with a custom scope activity to access <xref:System.ServiceModel.OperationContext.Current%2A> and attach or retrieve a custom message header within an outgoing or incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="414eb-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="414eb-104">Demonstrates</span></span>  
 <span data-ttu-id="414eb-105">Attività di messaggistica, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span><span class="sxs-lookup"><span data-stu-id="414eb-105">Messaging Activities, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="414eb-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="414eb-106">Discussion</span></span>  
 <span data-ttu-id="414eb-107">In questo esempio viene illustrato come usare punti di estensibilità (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) nelle attività di messaggistica per accedere a <xref:System.ServiceModel.OperationContext.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="414eb-107">This sample shows how to use extensibility points (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in the messaging activities to access <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="414eb-108">I callback vengono registrati all'interno dell'esecuzione del flusso di lavoro come un'implementazione di <xref:System.Activities.IExecutionProperty> raccolta dalle attività della messaggistica durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="414eb-108">The callbacks are registered within the workflow runtime as an implementation of <xref:System.Activities.IExecutionProperty> that is picked up by the messaging activities upon execution.</span></span> <span data-ttu-id="414eb-109">Qualsiasi attività di messaggistica nello stesso ambito di tale implementazione <xref:System.Activities.IExecutionProperty> risulta interessata.</span><span class="sxs-lookup"><span data-stu-id="414eb-109">Any messaging activity in the same scope as that <xref:System.Activities.IExecutionProperty> implementation is affected.</span></span> <span data-ttu-id="414eb-110">In particolare, questo esempio usa un'attività di ambiti personalizzata per applicare il comportamento di callback.</span><span class="sxs-lookup"><span data-stu-id="414eb-110">In particular, this sample uses a custom scope activity to enforce the callback behavior.</span></span> <span data-ttu-id="414eb-111"><xref:System.ServiceModel.Activities.ISendMessageCallback> viene usato nel flusso di lavoro client per includere l'oggetto <xref:System.Activities.WorkflowApplication.Id%2A> del flusso di lavoro come <xref:System.ServiceModel.Channels.MessageHeader> in uscita.</span><span class="sxs-lookup"><span data-stu-id="414eb-111">The <xref:System.ServiceModel.Activities.ISendMessageCallback> is used in the client workflow to include the workflow’s <xref:System.Activities.WorkflowApplication.Id%2A> as an outgoing <xref:System.ServiceModel.Channels.MessageHeader>.</span></span> <span data-ttu-id="414eb-112">Questa intestazione viene quindi scelta nel servizio usando <xref:System.ServiceModel.Activities.IReceiveMessageCallback> e il valore dell'intestazione viene stampato nella console.</span><span class="sxs-lookup"><span data-stu-id="414eb-112">This header is then picked up in the service using the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> and the value of the header is printed out to the console.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="414eb-113">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="414eb-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="414eb-114">In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP.</span><span class="sxs-lookup"><span data-stu-id="414eb-114">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="414eb-115">Eseguire questa procedura elenchi ACL di URL di esempio, appropriata deve essere aggiunto (vedere [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) per informazioni dettagliate), eseguendo Visual Studio come amministratore o eseguendo il comando seguente in un prompt dei comandi con privilegi elevati per aggiungere gli ACL appropriati.</span><span class="sxs-lookup"><span data-stu-id="414eb-115">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="414eb-116">Assicurarsi che vengono sostituiti il dominio e il nome utente.</span><span class="sxs-lookup"><span data-stu-id="414eb-116">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  <span data-ttu-id="414eb-117">Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="414eb-117">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1.  <span data-ttu-id="414eb-118">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="414eb-118">Build the solution.</span></span>  
  
    2.  <span data-ttu-id="414eb-119">Impostare più progetti di avvio facendo clic sulla soluzione e selezionando **Imposta progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="414eb-119">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span>  
  
    3.  <span data-ttu-id="414eb-120">Aggiungere **servizio** e **Client** (in tale ordine) come più progetti di avvio.</span><span class="sxs-lookup"><span data-stu-id="414eb-120">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    4.  <span data-ttu-id="414eb-121">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="414eb-121">Run the application.</span></span> <span data-ttu-id="414eb-122">Nella console client viene visualizzato un flusso di lavoro che viene eseguito due volte e nella finestra Servizio è visualizzato l'ID istanza di tali flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="414eb-122">The client console shows a workflow running twice and the Service window shows the instance ID of those workflows.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="414eb-123">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="414eb-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="414eb-124">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="414eb-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="414eb-125">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="414eb-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="414eb-126">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="414eb-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
