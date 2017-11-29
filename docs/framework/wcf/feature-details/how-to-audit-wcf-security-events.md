---
title: 'Procedura: controllare gli eventi di sicurezza di Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
caps.latest.revision: "19"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 67fca1af6a9e1fdd35051e8b289679677a0abd6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="7138b-102">Procedura: controllare gli eventi di sicurezza di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7138b-102">How to: Audit Windows Communication Foundation Security Events</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="7138b-103"> consente di registrarsi eventi di sicurezza nel registro eventi di Windows, che può essere visualizzato usando il Visualizzatore eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="7138b-103"> allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="7138b-104">In questo argomento viene illustrato come configurare un'applicazione in modo che registri eventi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7138b-104">This topic explains how to set up an application so that it logs security events.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7138b-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controllo, vedere [controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="7138b-105"> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auditing, see [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="7138b-106">Per controllare gli eventi di sicurezza nel codice</span><span class="sxs-lookup"><span data-stu-id="7138b-106">To audit security events in code</span></span>  
  
1.  <span data-ttu-id="7138b-107">Specificare il percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="7138b-107">Specify the audit log location.</span></span> <span data-ttu-id="7138b-108">A questo scopo, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> della classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> su uno dei valori dell'enumerazione <xref:System.ServiceModel.AuditLogLocation>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7138b-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="7138b-109">Il <xref:System.ServiceModel.AuditLogLocation> enumerazione dispone di tre valori: `Application`, `Security`, o `Default`.</span><span class="sxs-lookup"><span data-stu-id="7138b-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="7138b-110">Il valore specifica uno dei log visibili nel Visualizzatore eventi, il registro protezione o il registro applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7138b-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="7138b-111">Se si usa il valore `Default`, il log effettivo dipenderà dal sistema operativo su cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7138b-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="7138b-112">Se il controllo è attivato e il percorso del log non viene specificato, verrà usato, per impostazione predefinita, il registro `Security`, per le piattaforme che supportano la scrittura nel registro protezione, altrimenti verrà usato il registro `Application`.</span><span class="sxs-lookup"><span data-stu-id="7138b-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="7138b-113">Solo [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wv](../../../../includes/wv-md.md)] supportano la scrittura nel registro protezione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7138b-113">Only [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] and [!INCLUDE[wv](../../../../includes/wv-md.md)] support writing to the Security log by default.</span></span>  
  
2.  <span data-ttu-id="7138b-114">Impostare i tipi di eventi da controllare.</span><span class="sxs-lookup"><span data-stu-id="7138b-114">Set up the types of events to audit.</span></span> <span data-ttu-id="7138b-115">È possibile controllare simultaneamente eventi a livello di servizio o eventi di autorizzazione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="7138b-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="7138b-116">A questo scopo, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> su uno dei valori dell'enumerazione <xref:System.ServiceModel.AuditLevel>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7138b-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3.  <span data-ttu-id="7138b-117">Specificare se esporre o meno gli errori all'applicazione relativamente agli eventi di controllo del log.</span><span class="sxs-lookup"><span data-stu-id="7138b-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="7138b-118">Impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true` o `false`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7138b-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="7138b-119">La proprietà `SuppressAuditFailure` predefinita è `true`, in modo che l'errore da controllare non influenzi l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7138b-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="7138b-120">In caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7138b-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="7138b-121">Per ogni controllo riuscito viene scritta una traccia dettagliata.</span><span class="sxs-lookup"><span data-stu-id="7138b-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="7138b-122">Per ogni errore da controllare, la traccia viene scritta a livello errore.</span><span class="sxs-lookup"><span data-stu-id="7138b-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4.  <span data-ttu-id="7138b-123">Eliminare la classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> esistente dalla raccolta dei comportamenti trovati nella descrizione di una classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7138b-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7138b-124">La raccolta dei comportamenti è accessibile tramite la proprietà <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, che a sua volta è accessibile dalla proprietà <xref:System.ServiceModel.ServiceHostBase.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="7138b-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="7138b-125">Aggiungere quindi la nuova classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> alla stessa raccolta, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7138b-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="7138b-126">Per impostare il controllo nella configurazione</span><span class="sxs-lookup"><span data-stu-id="7138b-126">To set up auditing in configuration</span></span>  
  
1.  <span data-ttu-id="7138b-127">Per impostare il controllo nella configurazione, aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento per il [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) sezione del file Web. config.</span><span class="sxs-lookup"><span data-stu-id="7138b-127">To set up auditing in configuration, add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="7138b-128">Aggiungere quindi una [ \<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) elemento e impostare i vari attributi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7138b-128">Then add a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"   
                serviceAuthorizationAuditLevel="None"   
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2.  <span data-ttu-id="7138b-129">È necessario specificare il comportamento del servizio, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7138b-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"   
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"   
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="7138b-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="7138b-130">Example</span></span>  
 <span data-ttu-id="7138b-131">Nel codice seguente viene creata un'istanza della classe <xref:System.ServiceModel.ServiceHost> e viene aggiunta una nuova classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> alla raccolta dei comportamenti.</span><span class="sxs-lookup"><span data-stu-id="7138b-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="7138b-132">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7138b-132">.NET Framework Security</span></span>  
 <span data-ttu-id="7138b-133">Se si imposta la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true`, viene evitata la visualizzazione di qualsiasi errore per generare controlli di sicurezza (se la proprietà viene impostata su `false`, viene generata un'eccezione).</span><span class="sxs-lookup"><span data-stu-id="7138b-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="7138b-134">Tuttavia, se si abilita le seguenti finestre **impostazioni di sicurezza locali**proprietà, un errore per generare eventi di controllo causerà Windows arrestare immediatamente:</span><span class="sxs-lookup"><span data-stu-id="7138b-134">However, if you enable the following Windows **Local Security Setting**property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="7138b-135">**Controllo: Arresto del sistema immediato se non è possibile registrare i controlli di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="7138b-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="7138b-136">Per impostare la proprietà, aprire il **impostazioni protezione locale** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7138b-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="7138b-137">In **le impostazioni di sicurezza**, fare clic su **criteri locali**.</span><span class="sxs-lookup"><span data-stu-id="7138b-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="7138b-138">Quindi fare clic su **opzioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="7138b-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="7138b-139">Se il <xref:System.ServiceModel.AuditLogLocation> è impostata su <xref:System.ServiceModel.AuditLogLocation.Security> e **Controlla accesso agli oggetti** non è impostata **criteri di sicurezza locali**, gli eventi di controllo non vengono scritti nel Registro di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7138b-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="7138b-140">Si noti che non viene restituito alcun errore, ma non vengono scritte voci di controllo nel registro protezione.</span><span class="sxs-lookup"><span data-stu-id="7138b-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7138b-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7138b-141">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 <xref:System.ServiceModel.AuditLogLocation>  
 [<span data-ttu-id="7138b-142">Il controllo</span><span class="sxs-lookup"><span data-stu-id="7138b-142">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
