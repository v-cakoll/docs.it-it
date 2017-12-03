---
title: Protezione di servizi flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cd7620186ed51110a32e251d5239c85bb90e0f0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="securing-workflow-services"></a><span data-ttu-id="18c89-102">Protezione di servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="18c89-102">Securing Workflow Services</span></span>
<span data-ttu-id="18c89-103">Nell'esempio di servizio flusso di lavoro protetto vengono illustrate le procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="18c89-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="18c89-104">Creazione di un servizio flusso di lavoro di base usando le attività <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="18c89-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="18c89-105">Utilizzo della configurazione [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per definire endpoint sicuri per l'uso dal servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="18c89-105">Using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="18c89-106">Creazione di richieste all'interno di criteri personalizzati e utilizzo di <xref:System.ServiceModel.ServiceAuthorizationManager> per convalidare richieste.</span><span class="sxs-lookup"><span data-stu-id="18c89-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="18c89-107">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="18c89-107">Demonstrates</span></span>  
 <span data-ttu-id="18c89-108">Utilizzo della sicurezza WCF per proteggere la comunicazione tra client e servizio flusso di lavoro,con autorizzazione basata sulle attestazioni</span><span class="sxs-lookup"><span data-stu-id="18c89-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="18c89-109">Discussione</span><span class="sxs-lookup"><span data-stu-id="18c89-109">Discussion</span></span>  
 <span data-ttu-id="18c89-110">In questo esempio viene illustrato l'uso dell'infrastruttura di sicurezza di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per proteggere un servizio flusso di lavoro con la stessa modalità di con un normale servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18c89-110">This sample demonstrates the use of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security infrastructure to secure a workflow service just like you would with a normal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="18c89-111">In particolare, viene usata una richiesta personalizzata per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="18c89-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="18c89-112">In questo caso, viene usato <xref:System.ServiceModel.WSHttpBinding> e la sicurezza in modalità messaggio con credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="18c89-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="18c89-113">L'oggetto personalizzato <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) esegue il controllo del nome utente di Windows del client e di un carattere specifico.</span><span class="sxs-lookup"><span data-stu-id="18c89-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="18c89-114">Se tale carattere è presente, la richiesta viene creata e aggiunta a <xref:System.IdentityModel.Policy.EvaluationContext>.</span><span class="sxs-lookup"><span data-stu-id="18c89-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="18c89-115">In questo modo, i criteri personalizzati dichiarano che il client dispone di questo carattere nel nome utente.</span><span class="sxs-lookup"><span data-stu-id="18c89-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="18c89-116">È possibile eseguire query su questa richiesta per tutta la durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="18c89-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="18c89-117">È possibile trovare il carattere in `Constants.cs`.</span><span class="sxs-lookup"><span data-stu-id="18c89-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="18c89-118">I criteri di autorizzazione cercano la richiesta in `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="18c89-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="18c89-119">Se viene trovata, viene restituito `true` e al flusso di lavoro è consentito procedere.</span><span class="sxs-lookup"><span data-stu-id="18c89-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="18c89-120">In caso contrario, viene restituito `false` che causa la restituzione al client di un messaggio 'Accesso negato'.</span><span class="sxs-lookup"><span data-stu-id="18c89-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="18c89-121">Nel contesto sono presenti altre richieste che possono essere esaminate in `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="18c89-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="18c89-122">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="18c89-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="18c89-123">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="18c89-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="18c89-124">Caricare SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18c89-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="18c89-125">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="18c89-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="18c89-126">Impostare il progetto Service come progetto di avvio per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="18c89-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="18c89-127">Per avviare l'esempio senza debug, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="18c89-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="18c89-128">Impostare il progetto Client come progetto di avvio per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="18c89-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="18c89-129">Premere CTRL+F5 per avviare l'esempio senza debug.</span><span class="sxs-lookup"><span data-stu-id="18c89-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="18c89-130">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="18c89-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="18c89-131">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="18c89-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="18c89-132">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18c89-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="18c89-133">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="18c89-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
