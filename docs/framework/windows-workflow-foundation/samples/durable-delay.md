---
title: Ritardo durevole
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 2a7692e28d60232913ae5d11a90025e59664c0e5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406576"
---
# <a name="durable-delay"></a><span data-ttu-id="9873f-102">Ritardo durevole</span><span class="sxs-lookup"><span data-stu-id="9873f-102">Durable Delay</span></span>
<span data-ttu-id="9873f-103">In questo esempio viene illustrato come usare un ritardo durevole, ovvero un ritardo che rende persistente il flusso di lavoro in un dispositivo durevole durante il ritardo.</span><span class="sxs-lookup"><span data-stu-id="9873f-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="9873f-104">Il flusso di lavoro di esempio contiene due messaggi alla console separati da un ritardo.</span><span class="sxs-lookup"><span data-stu-id="9873f-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="9873f-105">Quando viene attivato il ritardo, il flusso di lavoro viene scaricato e attende 5 secondi nell'archivio di istanze del flusso di lavoro prima di essere ricaricato in memoria.</span><span class="sxs-lookup"><span data-stu-id="9873f-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="9873f-106">Dettagli del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9873f-106">Workflow Details</span></span>  
 <span data-ttu-id="9873f-107">Oltre a ospitare il flusso di lavoro, l'host del servizio flusso di lavoro gestisce le istanze del flusso di lavoro caricandole e scaricandole.</span><span class="sxs-lookup"><span data-stu-id="9873f-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="9873f-108">Per avviare un'istanza della definizione di flusso di lavoro, nell'esempio viene impostato un proxy che invia un messaggio all'attività <xref:System.ServiceModel.Activities.Receive> nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9873f-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="9873f-109">La proprietà <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> è impostata su `true`, consentendo la creazione di una nuova istanza del flusso di lavoro dopo la ricezione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="9873f-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="9873f-110">Nell'elenco seguente viene fornita una descrizione dettagliata della configurazione del servizio flusso di lavoro durante l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="9873f-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="9873f-111">Crea un host del servizio con un indirizzo (http://localhost:8080/Client).</span><span class="sxs-lookup"><span data-stu-id="9873f-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="9873f-112">Crea un endpoint nell'host del servizio per abilitare la comunicazione con l'attività <xref:System.ServiceModel.Activities.Receive> nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9873f-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="9873f-113">Configura un archivio di istanze SQL.</span><span class="sxs-lookup"><span data-stu-id="9873f-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="9873f-114">Aggiunge un comportamento di scaricamento di istanze che specifica le condizioni in base alle quali l'host del servizio flusso di lavoro deve scaricare un'istanza del flusso di lavoro nell'archivio di persistenza SQL.</span><span class="sxs-lookup"><span data-stu-id="9873f-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="9873f-115">Per questo esempio, scarica immediatamente l'istanza dopo che il flusso di lavoro diventa inattivo (quando viene attivato il ritardo).</span><span class="sxs-lookup"><span data-stu-id="9873f-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="9873f-116">Crea il proxy che invia un messaggio all'attività <xref:System.ServiceModel.Activities.Receive> nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9873f-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9873f-117">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="9873f-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="9873f-118">Impostare il database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="9873f-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="9873f-119">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9873f-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="9873f-120">Passare al [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4. X\\).</span><span class="sxs-lookup"><span data-stu-id="9873f-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="9873f-121">Modificare il file WorkflowManagementService.exe.config e aggiungere la stringa di connessione seguente nell'elemento <`database`>.</span><span class="sxs-lookup"><span data-stu-id="9873f-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="9873f-122">Passare alla directory DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="9873f-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="9873f-123">Eseguire Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="9873f-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="9873f-124">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con autorizzazioni elevate facendo clic con il [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icona e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9873f-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="9873f-125">Aprire il file della soluzione Delay.sln.</span><span class="sxs-lookup"><span data-stu-id="9873f-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="9873f-126">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="9873f-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="9873f-127">Premere CTRL+F5 per eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="9873f-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="9873f-128">Per disinstallare l'esempio</span><span class="sxs-lookup"><span data-stu-id="9873f-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="9873f-129">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9873f-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="9873f-130">Passare alla directory DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="9873f-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="9873f-131">Eseguire Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="9873f-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9873f-132">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9873f-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9873f-133">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9873f-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9873f-134">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="9873f-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9873f-135">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9873f-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`