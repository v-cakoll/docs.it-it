---
title: 'Procedura: controllare gli eventi di sicurezza di Windows Communication Foundation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 186dd4a7fc2beae848e5cbd167a204352ee6ed4e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601296"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="aff2a-102">Procedura: controllare gli eventi di sicurezza di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="aff2a-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="aff2a-103">Windows Communication Foundation (WCF) consente di registrare gli eventi di sicurezza nel registro eventi di Windows, che possono essere visualizzati tramite la Visualizzatore eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="aff2a-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="aff2a-104">In questo argomento viene illustrato come configurare un'applicazione in modo che registri eventi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aff2a-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="aff2a-105">Per ulteriori informazioni sul controllo WCF, vedere [controllo](auditing-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="aff2a-105">For more information about WCF auditing, see [Auditing](auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="aff2a-106">Per controllare gli eventi di sicurezza nel codice</span><span class="sxs-lookup"><span data-stu-id="aff2a-106">To audit security events in code</span></span>  
  
1. <span data-ttu-id="aff2a-107">Specificare il percorso del registro di controllo.</span><span class="sxs-lookup"><span data-stu-id="aff2a-107">Specify the audit log location.</span></span> <span data-ttu-id="aff2a-108">A questo scopo, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> della classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> su uno dei valori dell'enumerazione <xref:System.ServiceModel.AuditLogLocation>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="aff2a-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="aff2a-109">L' <xref:System.ServiceModel.AuditLogLocation> enumerazione ha tre valori: `Application` , `Security` o `Default` .</span><span class="sxs-lookup"><span data-stu-id="aff2a-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="aff2a-110">Il valore specifica uno dei log visibili nel Visualizzatore eventi, il registro protezione o il registro applicazioni.</span><span class="sxs-lookup"><span data-stu-id="aff2a-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="aff2a-111">Se si usa il valore `Default`, il log effettivo dipenderà dal sistema operativo su cui è in esecuzione l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aff2a-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="aff2a-112">Se il controllo è attivato e il percorso del log non viene specificato, verrà usato, per impostazione predefinita, il registro `Security`, per le piattaforme che supportano la scrittura nel registro protezione, altrimenti verrà usato il registro `Application`.</span><span class="sxs-lookup"><span data-stu-id="aff2a-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="aff2a-113">Per impostazione predefinita, solo Windows Server 2003 e Windows Vista supportano la scrittura nel registro di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aff2a-113">Only Windows Server 2003 and Windows Vista support writing to the Security log by default.</span></span>  
  
2. <span data-ttu-id="aff2a-114">Impostare i tipi di eventi da controllare.</span><span class="sxs-lookup"><span data-stu-id="aff2a-114">Set up the types of events to audit.</span></span> <span data-ttu-id="aff2a-115">È possibile controllare simultaneamente eventi a livello di servizio o eventi di autorizzazione a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="aff2a-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="aff2a-116">A questo scopo, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> su uno dei valori dell'enumerazione <xref:System.ServiceModel.AuditLevel>, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="aff2a-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. <span data-ttu-id="aff2a-117">Specificare se esporre o meno gli errori all'applicazione relativamente agli eventi di controllo del log.</span><span class="sxs-lookup"><span data-stu-id="aff2a-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="aff2a-118">Impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true` o `false`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="aff2a-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="aff2a-119">La proprietà `SuppressAuditFailure` predefinita è `true`, in modo che l'errore da controllare non influenzi l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aff2a-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="aff2a-120">In caso contrario, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="aff2a-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="aff2a-121">Per ogni controllo riuscito viene scritta una traccia dettagliata.</span><span class="sxs-lookup"><span data-stu-id="aff2a-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="aff2a-122">Per ogni errore da controllare, la traccia viene scritta a livello errore.</span><span class="sxs-lookup"><span data-stu-id="aff2a-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4. <span data-ttu-id="aff2a-123">Eliminare la classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> esistente dalla raccolta dei comportamenti trovati nella descrizione di una classe <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="aff2a-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="aff2a-124">La raccolta dei comportamenti è accessibile tramite la proprietà <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, che a sua volta è accessibile dalla proprietà <xref:System.ServiceModel.ServiceHostBase.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="aff2a-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="aff2a-125">Aggiungere quindi la nuova classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> alla stessa raccolta, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="aff2a-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="aff2a-126">Per impostare il controllo nella configurazione</span><span class="sxs-lookup"><span data-stu-id="aff2a-126">To set up auditing in configuration</span></span>  
  
1. <span data-ttu-id="aff2a-127">Per impostare il controllo nella configurazione, aggiungere un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento alla [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) sezione del file Web. config.</span><span class="sxs-lookup"><span data-stu-id="aff2a-127">To set up auditing in configuration, add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="aff2a-128">Aggiungere quindi un [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) elemento e impostare i vari attributi, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="aff2a-128">Then add a [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
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
  
2. <span data-ttu-id="aff2a-129">È necessario specificare il comportamento del servizio, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="aff2a-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="aff2a-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="aff2a-130">Example</span></span>  
 <span data-ttu-id="aff2a-131">Nel codice seguente viene creata un'istanza della classe <xref:System.ServiceModel.ServiceHost> e viene aggiunta una nuova classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> alla raccolta dei comportamenti.</span><span class="sxs-lookup"><span data-stu-id="aff2a-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="aff2a-132">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aff2a-132">.NET Framework Security</span></span>  
 <span data-ttu-id="aff2a-133">Se si imposta la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true`, viene evitata la visualizzazione di qualsiasi errore per generare controlli di sicurezza (se la proprietà viene impostata su `false`, viene generata un'eccezione).</span><span class="sxs-lookup"><span data-stu-id="aff2a-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="aff2a-134">Tuttavia, se si Abilita la seguente proprietà di **impostazione di sicurezza locale** di Windows, un errore di generazione di eventi di controllo causerà l'arresto immediato di Windows:</span><span class="sxs-lookup"><span data-stu-id="aff2a-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="aff2a-135">**Controllo: arresto del sistema immediato se non è possibile registrare i controlli di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="aff2a-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="aff2a-136">Per impostare la proprietà, aprire la finestra di dialogo **impostazioni di sicurezza locali** .</span><span class="sxs-lookup"><span data-stu-id="aff2a-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="aff2a-137">In **impostazioni di sicurezza**fare clic su **criteri locali**.</span><span class="sxs-lookup"><span data-stu-id="aff2a-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="aff2a-138">Fare quindi clic su **Opzioni di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="aff2a-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="aff2a-139">Se la <xref:System.ServiceModel.AuditLogLocation> proprietà è impostata su <xref:System.ServiceModel.AuditLogLocation.Security> e l' **accesso agli oggetti di controllo** non è impostato nei criteri di **sicurezza locali**, gli eventi di controllo non verranno scritti nel registro di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aff2a-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="aff2a-140">Si noti che non viene restituito alcun errore, ma non vengono scritte voci di controllo nel registro protezione.</span><span class="sxs-lookup"><span data-stu-id="aff2a-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff2a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aff2a-141">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="aff2a-142">Controllo</span><span class="sxs-lookup"><span data-stu-id="aff2a-142">Auditing</span></span>](auditing-security-events.md)
