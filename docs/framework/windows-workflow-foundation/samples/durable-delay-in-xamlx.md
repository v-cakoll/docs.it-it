---
title: Ritardo durevole in XAMLX
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff5eb09acea16ac125fac5d9e3ed875c9095e1c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="6afc5-102">Ritardo durevole in XAMLX</span><span class="sxs-lookup"><span data-stu-id="6afc5-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="6afc5-103">In questo esempio viene illustrato come usare un ritardo durevole, ovvero un ritardo che rende persistente il flusso di lavoro in un dispositivo durevole durante il ritardo.</span><span class="sxs-lookup"><span data-stu-id="6afc5-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6afc5-104">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6afc5-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6afc5-105">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6afc5-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6afc5-106">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6afc5-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6afc5-107">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6afc5-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="6afc5-108">Discussione</span><span class="sxs-lookup"><span data-stu-id="6afc5-108">Discussion</span></span>  
 <span data-ttu-id="6afc5-109">Il flusso di lavoro di esempio contiene due messaggi in un file locale separati da un ritardo.</span><span class="sxs-lookup"><span data-stu-id="6afc5-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="6afc5-110">Quando viene attivato il ritardo, il flusso di lavoro viene scaricato e attende 5 secondi nell'archivio di istanze del flusso di lavoro prima di essere ricaricato in memoria.</span><span class="sxs-lookup"><span data-stu-id="6afc5-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="6afc5-111">Il file con estensione xamlx è un servizio flusso di lavoro ospitato in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6afc5-111">The .xamlx file is a workflow service that is hosted in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="6afc5-112">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] viene usato Cassini che usa un host del servizio del flusso di lavoro per ospitare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6afc5-112">[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="6afc5-113">Oltre a ospitare il flusso di lavoro, l'host del servizio flusso di lavoro gestisce le istanze del flusso di lavoro caricandole e scaricandole.</span><span class="sxs-lookup"><span data-stu-id="6afc5-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="6afc5-114">Per avviare un'istanza della definizione di [!INCLUDE[wf](../../../../includes/wf-md.md)] (nell'host del servizio flusso di lavoro), impostare un client che invia un messaggio all'attività <xref:System.ServiceModel.Activities.Receive> nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6afc5-114">To start an instance of the [!INCLUDE[wf](../../../../includes/wf-md.md)] definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="6afc5-115">Questo oggetto <xref:System.ServiceModel.Activities.Receive> dispone della proprietà <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> impostata su `true` in modo che possa creare una nuova istanza del flusso di lavoro dopo aver ricevuto un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6afc5-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="6afc5-116">Durante l'inizializzazione, viene aggiunto un comportamento di scaricamento di istanze al file di configurazione che specifica all'host del servizio flusso di lavoro il punto in cui scaricare un'istanza nell'archivio di persistenza (database).</span><span class="sxs-lookup"><span data-stu-id="6afc5-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="6afc5-117">Per questo esempio, scarica immediatamente l'istanza dopo che il flusso di lavoro diventa inattivo (quando viene attivato il ritardo).</span><span class="sxs-lookup"><span data-stu-id="6afc5-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6afc5-118">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="6afc5-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="6afc5-119">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6afc5-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="6afc5-120">Passare alla cartella DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="6afc5-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="6afc5-121">Eseguire Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="6afc5-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="6afc5-122">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] come amministratore.</span><span class="sxs-lookup"><span data-stu-id="6afc5-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="6afc5-123">Aprire il file della soluzione DurableDelayXamlx.sln.</span><span class="sxs-lookup"><span data-stu-id="6afc5-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="6afc5-124">In **Esplora**, la soluzione e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6afc5-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="6afc5-125">Selezionare **più progetti di avvio** e impostare entrambi i progetti **avviare**.</span><span class="sxs-lookup"><span data-stu-id="6afc5-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="6afc5-126">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="6afc5-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="6afc5-127">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="6afc5-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="6afc5-128">Per disinstallare l'esempio</span><span class="sxs-lookup"><span data-stu-id="6afc5-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="6afc5-129">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6afc5-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="6afc5-130">Passare alla cartella DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="6afc5-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="6afc5-131">Eseguire Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="6afc5-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6afc5-132">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6afc5-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6afc5-133">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="6afc5-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6afc5-134">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6afc5-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6afc5-135">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="6afc5-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
