---
title: Ritardo durevole in XAMLX
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45521453"
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="2d217-102">Ritardo durevole in XAMLX</span><span class="sxs-lookup"><span data-stu-id="2d217-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="2d217-103">In questo esempio viene illustrato come usare un ritardo durevole, ovvero un ritardo che rende persistente il flusso di lavoro in un dispositivo durevole durante il ritardo.</span><span class="sxs-lookup"><span data-stu-id="2d217-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d217-104">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2d217-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2d217-105">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2d217-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2d217-106">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2d217-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2d217-107">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2d217-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="2d217-108">Discussione</span><span class="sxs-lookup"><span data-stu-id="2d217-108">Discussion</span></span>  
 <span data-ttu-id="2d217-109">Il flusso di lavoro di esempio contiene due messaggi in un file locale separati da un ritardo.</span><span class="sxs-lookup"><span data-stu-id="2d217-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="2d217-110">Quando viene attivato il ritardo, il flusso di lavoro viene scaricato e attende 5 secondi nell'archivio di istanze del flusso di lavoro prima di essere ricaricato in memoria.</span><span class="sxs-lookup"><span data-stu-id="2d217-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="2d217-111">Il file con estensione xamlx è un servizio del flusso di lavoro ospitata in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d217-111">The .xamlx file is a workflow service that is hosted in Visual Studio.</span></span> <span data-ttu-id="2d217-112">Visual Studio utilizza Cassini che usa un servizio del flusso di lavoro host per ospitare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2d217-112">Visual Studio uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="2d217-113">Oltre a ospitare il flusso di lavoro, l'host del servizio flusso di lavoro gestisce le istanze del flusso di lavoro caricandole e scaricandole.</span><span class="sxs-lookup"><span data-stu-id="2d217-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="2d217-114">Per avviare un'istanza della definizione di Windows Workflow Foundation (WF) (nell'host del servizio del flusso di lavoro), impostare un client che invia un messaggio per il <xref:System.ServiceModel.Activities.Receive> attività nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2d217-114">To start an instance of the Windows Workflow Foundation (WF) definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="2d217-115">Questo oggetto <xref:System.ServiceModel.Activities.Receive> dispone della proprietà <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> impostata su `true` in modo che possa creare una nuova istanza del flusso di lavoro dopo aver ricevuto un messaggio.</span><span class="sxs-lookup"><span data-stu-id="2d217-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="2d217-116">Durante l'inizializzazione, viene aggiunto un comportamento di scaricamento di istanze al file di configurazione che specifica all'host del servizio flusso di lavoro il punto in cui scaricare un'istanza nell'archivio di persistenza (database).</span><span class="sxs-lookup"><span data-stu-id="2d217-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="2d217-117">Per questo esempio, scarica immediatamente l'istanza dopo che il flusso di lavoro diventa inattivo (quando viene attivato il ritardo).</span><span class="sxs-lookup"><span data-stu-id="2d217-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2d217-118">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="2d217-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="2d217-119">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d217-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="2d217-120">Passare alla cartella DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="2d217-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="2d217-121">Eseguire Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="2d217-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="2d217-122">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] come amministratore.</span><span class="sxs-lookup"><span data-stu-id="2d217-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="2d217-123">Aprire il file della soluzione DurableDelayXamlx.sln.</span><span class="sxs-lookup"><span data-stu-id="2d217-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="2d217-124">Nelle **Esplora soluzioni**, la soluzione e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2d217-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="2d217-125">Selezionare **progetti di avvio multipli** e impostare entrambi i progetti **avviare**.</span><span class="sxs-lookup"><span data-stu-id="2d217-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="2d217-126">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="2d217-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="2d217-127">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="2d217-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="2d217-128">Per disinstallare l'esempio</span><span class="sxs-lookup"><span data-stu-id="2d217-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="2d217-129">Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d217-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="2d217-130">Passare alla cartella DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="2d217-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="2d217-131">Eseguire Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="2d217-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d217-132">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2d217-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2d217-133">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2d217-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2d217-134">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2d217-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2d217-135">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2d217-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
