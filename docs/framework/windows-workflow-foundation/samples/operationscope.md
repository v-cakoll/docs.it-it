---
title: OperationScope
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3bf92d7a726a53c5d625f31b0386e11c941cdde9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="operationscope"></a><span data-ttu-id="5dee3-102">OperationScope</span><span class="sxs-lookup"><span data-stu-id="5dee3-102">OperationScope</span></span>
<span data-ttu-id="5dee3-103">In questo esempio viene illustrato come è possibile usare le attività di messaggistica, <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply> per esporre un'attività personalizzata esistente come operazione in un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5dee3-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="5dee3-104">Questo esempio include una nuova attività personalizzata chiamata `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="5dee3-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="5dee3-105">È destinata a facilitare lo sviluppo di un servizio flusso di lavoro consentendo agli utenti di creare separatamente il corpo delle operazioni come attività personalizzate ed esponendole quindi facilmente come operazioni del servizio tramite l'attività `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="5dee3-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="5dee3-106">Ad esempio, un'attività `Add` personalizzata che accetta due argomenti `in` e restituisce un argomento `out` potrebbe essere esposta come un'operazione `Add` nel servizio flusso di lavoro rilasciandolo in `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="5dee3-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="5dee3-107">Il funzionamento dell'ambito si basa sul controllo dell'attività fornita come corpo.</span><span class="sxs-lookup"><span data-stu-id="5dee3-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="5dee3-108">Gli eventuali argomenti `in` non associati vengono considerati come input dal messaggio in arrivo.</span><span class="sxs-lookup"><span data-stu-id="5dee3-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="5dee3-109">Tutti gli argomenti `out`, indipendentemente che siano associati, sono considerati come output nel messaggio di risposta successivo.</span><span class="sxs-lookup"><span data-stu-id="5dee3-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="5dee3-110">Il nome dell'operazione esposto viene rilevato dal nome visualizzato dell'attività `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="5dee3-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="5dee3-111">Come risultato finale viene eseguito il wrapping dell'attività del corpo in un oggetto <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply> con i parametri dei messaggi associati agli argomenti dell'attività.</span><span class="sxs-lookup"><span data-stu-id="5dee3-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="5dee3-112">In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP.</span><span class="sxs-lookup"><span data-stu-id="5dee3-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="5dee3-113">Per l'esecuzione, è necessario aggiungere ACL di URL appropriati.</span><span class="sxs-lookup"><span data-stu-id="5dee3-113">To run, proper URL ACLs must be added.</span></span> <span data-ttu-id="5dee3-114">Per altre informazioni, vedere [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span><span class="sxs-lookup"><span data-stu-id="5dee3-114">For more information, see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="5dee3-115">Eseguire il comando seguente in un prompt dei comandi con privilegi elevati consente di aggiungere gli elenchi ACL appropriati (assicurarsi che il dominio e il nome utente vengono sostituiti con dominio %\\% UserName %).</span><span class="sxs-lookup"><span data-stu-id="5dee3-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="5dee3-116">**netsh http aggiungere urlacl url =http://+:8000/ utente = % dominio %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="5dee3-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="5dee3-117">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="5dee3-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="5dee3-118">Aprire la soluzione OperationScope.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dee3-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="5dee3-119">Impostare più progetti di avvio facendo clic sulla soluzione in Esplora soluzioni e selezionando **Imposta progetti di avvio**.</span><span class="sxs-lookup"><span data-stu-id="5dee3-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="5dee3-120">Aggiungere Scenario e Scenario_Client (in tale ordine) come più progetti di avvio.</span><span class="sxs-lookup"><span data-stu-id="5dee3-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="5dee3-121">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="5dee3-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="5dee3-122">Questo passaggio è necessario per visualizzare il flusso di lavoro BankService.xaml a causa dell'attività personalizzata `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="5dee3-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="5dee3-123">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5dee3-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="5dee3-124">La console Scenario_Client richiede l'input e l'output corrispondente viene visualizzato nella console di Scenario.</span><span class="sxs-lookup"><span data-stu-id="5dee3-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5dee3-125">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="5dee3-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5dee3-126">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="5dee3-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5dee3-127">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5dee3-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5dee3-128">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="5dee3-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`