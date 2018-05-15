---
title: Protezione di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: 5dbd724f3a2f8febfc74719584f4d69cbf75b567
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="securing-workflow-services"></a><span data-ttu-id="ae98c-102">Protezione di servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ae98c-102">Securing Workflow Services</span></span>
<span data-ttu-id="ae98c-103">Nell'esempio di servizio flusso di lavoro protetto vengono illustrate le procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="ae98c-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="ae98c-104">Creazione di un servizio flusso di lavoro di base usando le attività <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="ae98c-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="ae98c-105">Utilizzo della configurazione di Windows Communication Foundation (WCF) per definire endpoint sicuri per l'utilizzo dal servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ae98c-105">Using Windows Communication Foundation (WCF) configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="ae98c-106">Creazione di richieste all'interno di criteri personalizzati e utilizzo di <xref:System.ServiceModel.ServiceAuthorizationManager> per convalidare richieste.</span><span class="sxs-lookup"><span data-stu-id="ae98c-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ae98c-107">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="ae98c-107">Demonstrates</span></span>  
 <span data-ttu-id="ae98c-108">Utilizzo della sicurezza WCF per proteggere la comunicazione tra client e servizio flusso di lavoro,con autorizzazione basata sulle attestazioni</span><span class="sxs-lookup"><span data-stu-id="ae98c-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ae98c-109">Discussione</span><span class="sxs-lookup"><span data-stu-id="ae98c-109">Discussion</span></span>  
 <span data-ttu-id="ae98c-110">In questo esempio illustra l'uso di infrastruttura di sicurezza WCF per proteggere un servizio flusso di lavoro esattamente come si farebbe con un normale servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="ae98c-110">This sample demonstrates the use of WCF security infrastructure to secure a workflow service just like you would with a normal WCF service.</span></span> <span data-ttu-id="ae98c-111">In particolare, viene usata una richiesta personalizzata per l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae98c-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="ae98c-112">In questo caso, viene usato <xref:System.ServiceModel.WSHttpBinding> e la sicurezza in modalità messaggio con credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="ae98c-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="ae98c-113">L'oggetto personalizzato <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) esegue il controllo del nome utente di Windows del client e di un carattere specifico.</span><span class="sxs-lookup"><span data-stu-id="ae98c-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="ae98c-114">Se tale carattere è presente, la richiesta viene creata e aggiunta a <xref:System.IdentityModel.Policy.EvaluationContext>.</span><span class="sxs-lookup"><span data-stu-id="ae98c-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="ae98c-115">In questo modo, i criteri personalizzati dichiarano che il client dispone di questo carattere nel nome utente.</span><span class="sxs-lookup"><span data-stu-id="ae98c-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="ae98c-116">È possibile eseguire query su questa richiesta per tutta la durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ae98c-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="ae98c-117">È possibile trovare il carattere in `Constants.cs`.</span><span class="sxs-lookup"><span data-stu-id="ae98c-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="ae98c-118">I criteri di autorizzazione cercano la richiesta in `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="ae98c-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="ae98c-119">Se viene trovata, viene restituito `true` e al flusso di lavoro è consentito procedere.</span><span class="sxs-lookup"><span data-stu-id="ae98c-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="ae98c-120">In caso contrario, viene restituito `false` che causa la restituzione al client di un messaggio 'Accesso negato'.</span><span class="sxs-lookup"><span data-stu-id="ae98c-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="ae98c-121">Nel contesto sono presenti altre richieste che possono essere esaminate in `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="ae98c-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="ae98c-122">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="ae98c-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="ae98c-123">Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="ae98c-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="ae98c-124">Caricare SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae98c-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="ae98c-125">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="ae98c-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="ae98c-126">Impostare il progetto Service come progetto di avvio per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ae98c-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="ae98c-127">Per avviare l'esempio senza debug, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ae98c-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="ae98c-128">Impostare il progetto Client come progetto di avvio per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ae98c-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="ae98c-129">Premere CTRL+F5 per avviare l'esempio senza debug.</span><span class="sxs-lookup"><span data-stu-id="ae98c-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae98c-130">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ae98c-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ae98c-131">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ae98c-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ae98c-132">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="ae98c-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ae98c-133">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ae98c-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
