---
title: Comportamento di controllo dei servizi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0e7e85ac2aa5be9614946418f0df676ea1cb7dd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="service-auditing-behavior"></a><span data-ttu-id="b4e4c-102">Comportamento di controllo dei servizi</span><span class="sxs-lookup"><span data-stu-id="b4e4c-102">Service Auditing Behavior</span></span>
<span data-ttu-id="b4e4c-103">Questo esempio illustra come usare <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> per abilitare il controllo degli eventi di sicurezza durante le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-103">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span> <span data-ttu-id="b4e4c-104">Questo esempio è basato sul [Introduzione](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="b4e4c-105">Il servizio e client sono stati configurati utilizzando il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-105">The service and client have been configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="b4e4c-106">Il `mode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) è stata impostata su `Message` e `clientCredentialType` è stata impostata su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="b4e4c-107">In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4e4c-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b4e4c-109">Il file di configurazione del servizio utilizza l'elemento `serviceSecurityAudit` per configurare il controllo.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-109">The service configuration file uses the `serviceSecurityAudit` element to configure auditing.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="b4e4c-110">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-110">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b4e4c-111">Premere INVIO nella finestra della console per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-111">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="b4e4c-112">I log di controllo risultanti possono essere visualizzati eseguendo il Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-112">The resulting audit logs can be seen by running the Event Viewer.</span></span> <span data-ttu-id="b4e4c-113">Per impostazione predefinita, in Windows XP gli eventi di controllo possono essere visualizzati nel registro applicazioni, mentre in Windows Server 2003 e Windows Vista gli eventi di controllo possono essere visti nel registro sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-113">By default, on Windows XP the audit events can be seen in the Application Log while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="b4e4c-114">In Windows Server 2008 e Windows 7 è possibile visualizzare gli eventi di controllo nei registri applicazioni e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-114">On Windows Server 2008 and Windows 7, the audit events can be seen in the Applications and Services logs.</span></span> <span data-ttu-id="b4e4c-115">Il percorso di eventi di controllo può essere specificato impostando il `auditLogLocation` attributo "Application" o "Security".</span><span class="sxs-lookup"><span data-stu-id="b4e4c-115">The location of audit events can be specified by setting the `auditLogLocation` attribute to "Application" or "Security".</span></span> <span data-ttu-id="b4e4c-116">Per ulteriori informazioni, vedere [come: eventi di protezione controllo](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-116">For more information, see [How to: Audit Security Events](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="b4e4c-117">Se gli eventi vengono scritti nel registro sicurezza, il valore di LocalSecurityPolicy per l'abilitazione dell'accesso all'oggetto deve essere impostato per "Success" e "Failure".</span><span class="sxs-lookup"><span data-stu-id="b4e4c-117">If the events are written in the Security Log the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="b4e4c-118">Nel registro eventi l'origine degli eventi di controllo corrisponde a "ServiceModel Audit 3.0.0.0".</span><span class="sxs-lookup"><span data-stu-id="b4e4c-118">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="b4e4c-119">Record di controllo di autenticazione messaggi hanno una categoria "Messageauthentication", mentre i record di controllo di autorizzazione del servizio hanno una categoria "ServiceAuthorization".</span><span class="sxs-lookup"><span data-stu-id="b4e4c-119">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of "ServiceAuthorization".</span></span>  
  
 <span data-ttu-id="b4e4c-120">Gli eventi di controllo dell'autenticazione dei messaggi analizzano se il messaggio è stato manomesso, se è scaduto e se il client può essere autenticato presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-120">Message authentication audit events cover whether the message was tampered with, whether the message has expired, and whether the client can authenticate to the service.</span></span> <span data-ttu-id="b4e4c-121">Tali eventi forniscono inoltre informazioni sull'esito positivo o meno dell'autenticazione nonché l'identità del client e dell'endpoint a cui è stato inviato il messaggio insieme all'azione associata a quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-121">They provide information about whether the authentication succeeded or failed along with the identity of the client, and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="b4e4c-122">Gli eventi di controllo dell'autorizzazione del servizio analizzano la decisione di autorizzazione adottata dalla gestione autorizzazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-122">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="b4e4c-123">Tali eventi forniscono inoltre informazioni sull'esito positivo o meno dell'autorizzazione nonché l'identità del client, l'endpoint al quale è stato inviato il messaggio, l'azione associata al messaggio, l'identificatore del contesto di autorizzazione generato dal messaggio in arrivo e il tipo di gestione autorizzazioni che ha preso la decisione relativa all'accesso.</span><span class="sxs-lookup"><span data-stu-id="b4e4c-123">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message, and the type of the authorization manager that made the access decision.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b4e4c-124">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b4e4c-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b4e4c-125">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b4e4c-126">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b4e4c-127">Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b4e4c-127">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e4c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4e4c-128">See Also</span></span>  
 [<span data-ttu-id="b4e4c-129">Il controllo</span><span class="sxs-lookup"><span data-stu-id="b4e4c-129">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [<span data-ttu-id="b4e4c-130">Procedura: controllare gli eventi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b4e4c-130">How to: Audit Security Events</span></span>](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
