---
title: Gestione dell'istanza sospesa
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f5073e9de217637141d7e3c9d70bb6a0b7a9cd0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="suspended-instance-management"></a><span data-ttu-id="02347-102">Gestione dell'istanza sospesa</span><span class="sxs-lookup"><span data-stu-id="02347-102">Suspended Instance Management</span></span>
<span data-ttu-id="02347-103">In questo esempio viene illustrato come gestire le istanze del flusso di lavoro che sono state sospese.</span><span class="sxs-lookup"><span data-stu-id="02347-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="02347-104">L'azione predefinita per l'oggetto <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è `AbandonAndSuspend`.</span><span class="sxs-lookup"><span data-stu-id="02347-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="02347-105">Pertanto, per impostazione predefinita, le eccezioni non gestite generate da un'istanza del flusso di lavoro ospitata nell'oggetto <xref:System.ServiceModel.WorkflowServiceHost> comporteranno l'eliminazione dell'istanza dalla memoria (abbandonata) e la versione durevole/persistente dell'istanza sarà contrassegnata come sospesa.</span><span class="sxs-lookup"><span data-stu-id="02347-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="02347-106">Non sarà possibile eseguire un'istanza del flusso di lavoro sospesa finché non viene annullata la sospensione.</span><span class="sxs-lookup"><span data-stu-id="02347-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>  
  
 <span data-ttu-id="02347-107">Nell'esempio viene illustrata l'implementazione di un'utilità della riga di comando per eseguire query per le istanze sospese e viene mostrato come consentire all'utente di riprendere o terminare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="02347-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="02347-108">In questo esempio, un servizio flusso di lavoro genera intenzionalmente un'eccezione, comportandone la sospensione.</span><span class="sxs-lookup"><span data-stu-id="02347-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="02347-109">L'utilità della riga di comando può essere quindi usata per eseguire query per l'istanza e, successivamente, per riprendere o terminare l'istanza.</span><span class="sxs-lookup"><span data-stu-id="02347-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="02347-110">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="02347-110">Demonstrates</span></span>  
 <span data-ttu-id="02347-111"><xref:System.ServiceModel.WorkflowServiceHost> con <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> e <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="02347-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="02347-112">Discussione</span><span class="sxs-lookup"><span data-stu-id="02347-112">Discussion</span></span>  
 <span data-ttu-id="02347-113">L'utilità della riga di comando implementata in questo esempio è specifica per l'implementazione dell'archivio di istanze SQL fornito con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02347-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="02347-114">Se si dispone di un'implementazione personalizzata dell'archivio di istanze, è possibile adattare questa utilità sostituendo le implementazioni `WorkflowInstanceCommand` dell'esempio con le implementazioni specifiche dell'archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="02347-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>  
  
 <span data-ttu-id="02347-115">L'implementazione fornita esegue direttamente i comandi SQL nell'archivio di istanze SQL per elencare le istanze sospese e si basa su un oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> aggiunto all'oggetto <xref:System.ServiceModel.WorkflowServiceHost> per riprendere o terminare le istanze.</span><span class="sxs-lookup"><span data-stu-id="02347-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="02347-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="02347-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="02347-117">Per questo esempio è necessario aver abilitato i seguenti componenti di Windows:</span><span class="sxs-lookup"><span data-stu-id="02347-117">This sample requires that the following Windows components are enabled:</span></span>  
  
    1.  <span data-ttu-id="02347-118">Microsoft Message Queue (MSMQ) Server</span><span class="sxs-lookup"><span data-stu-id="02347-118">Microsoft Message Queues (MSMQ) Server</span></span>  
  
    2.  <span data-ttu-id="02347-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="02347-119">SQL Server Express</span></span>  
  
2.  <span data-ttu-id="02347-120">Impostare il database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02347-120">Set up the SQL Server database.</span></span>  
  
    1.  <span data-ttu-id="02347-121">Da un [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] prompt dei comandi, eseguire "setup.cmd" dalla directory di esempio SuspendedInstanceManagement, che esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02347-121">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>  
  
        1.  <span data-ttu-id="02347-122">Creare un database di persistenza tramite SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="02347-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="02347-123">Se il database di persistenza è già presente, viene eliminato e ricreato</span><span class="sxs-lookup"><span data-stu-id="02347-123">If the persistence database already exists, then it is dropped and re-created</span></span>  
  
        2.  <span data-ttu-id="02347-124">Impostare il database per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="02347-124">Sets up the database for persistence.</span></span>  
  
        3.  <span data-ttu-id="02347-125">Aggiungere IIS APPPOOL\DefaultAppPool e NT AUTHORITY\Network Service al ruolo InstanceStoreUsers definito durante l'impostazione del database per la persistenza.</span><span class="sxs-lookup"><span data-stu-id="02347-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>  
  
3.  <span data-ttu-id="02347-126">Impostare la coda del servizio.</span><span class="sxs-lookup"><span data-stu-id="02347-126">Set up the service queue.</span></span>  
  
    1.  <span data-ttu-id="02347-127">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], fare doppio clic su di **SampleWorkflowApp** sul progetto e scegliere **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="02347-127">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>  
  
    2.  <span data-ttu-id="02347-128">Compilare ed eseguire SampleWorkflowApp premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="02347-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="02347-129">In questo modo verrà creata la coda richiesta.</span><span class="sxs-lookup"><span data-stu-id="02347-129">This will create the required queue.</span></span>  
  
    3.  <span data-ttu-id="02347-130">Premere **invio** per arrestare SampleWorkflowApp.</span><span class="sxs-lookup"><span data-stu-id="02347-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>  
  
    4.  <span data-ttu-id="02347-131">Aprire la console Gestione computer eseguendo Compmgmt.msc da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="02347-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>  
  
    5.  <span data-ttu-id="02347-132">Espandere **servizi e applicazioni**, **Accodamento**, **code Private**.</span><span class="sxs-lookup"><span data-stu-id="02347-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    6.  <span data-ttu-id="02347-133">Fare clic destro la **ReceiveTx** coda e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="02347-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>  
  
    7.  <span data-ttu-id="02347-134">Selezionare il **sicurezza** scheda e consentono **Everyone** disporre delle autorizzazioni per **Ricevi messaggio**, **Visualizza il messaggio**, e  **Invia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="02347-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>  
  
4.  <span data-ttu-id="02347-135">A questo punto, eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="02347-135">Now, run the sample.</span></span>  
  
    1.  <span data-ttu-id="02347-136">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], eseguire nuovamente il progetto SampleWorkflowApp senza debug premendo **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="02347-136">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="02347-137">Nella finestra della console saranno stampati due indirizzi endpoint: uno per l'endpoint dell'applicazione e l'altro per l'oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="02347-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="02347-138">Viene quindi creata un'istanza del flusso di lavoro e i record di rilevamento per tale istanza saranno visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="02347-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="02347-139">L'istanza del flusso di lavoro genererà un'eccezione che comporterà la sospensione e l'interruzione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="02347-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>  
  
    2.  <span data-ttu-id="02347-140">L'utilità della riga di comando può essere quindi usata per eseguire ulteriori azioni in qualsiasi istanza.</span><span class="sxs-lookup"><span data-stu-id="02347-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="02347-141">Di seguito è riportata la sintassi per gli argomenti della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="02347-141">The syntax for command line arguments is as follows::</span></span>  
  
         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`  
  
         <span data-ttu-id="02347-142">I comandi supportati sono: `Query`, `Resume` e `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="02347-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="02347-143">L'opzione InstanceId è richiesta solo per le operazioni `Resume` e `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="02347-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="02347-144">Per eseguire la pulizia (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="02347-144">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="02347-145">Aprire la console Gestione computer eseguendo Compmgmt.msc da un prompt dei comandi di `vs2010`.</span><span class="sxs-lookup"><span data-stu-id="02347-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>  
  
2.  <span data-ttu-id="02347-146">Espandere **servizi e applicazioni**, **Accodamento**, **code Private**.</span><span class="sxs-lookup"><span data-stu-id="02347-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="02347-147">Eliminare il **ReceiveTx** coda.</span><span class="sxs-lookup"><span data-stu-id="02347-147">Delete the **ReceiveTx** queue.</span></span>  
  
4.  <span data-ttu-id="02347-148">Per rimuovere il database di persistenza, eseguire cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="02347-148">To remove the persistence database, run cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02347-149">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="02347-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="02347-150">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="02347-150">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="02347-151">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02347-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="02347-152">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="02347-152">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
