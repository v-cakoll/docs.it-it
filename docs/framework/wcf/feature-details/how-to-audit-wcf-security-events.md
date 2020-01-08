---
title: 'Procedura: controllare gli eventi di sicurezza di Windows Communication Foundation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 7071aaf88346ee217226632501ebd6c82cfc1cb8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346753"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a>Procedura: controllare gli eventi di sicurezza di Windows Communication Foundation
Windows Communication Foundation (WCF) consente di registrare gli eventi di sicurezza nel registro eventi di Windows, che possono essere visualizzati tramite la Visualizzatore eventi di Windows. In questo argomento viene illustrato come configurare un'applicazione in modo che registri eventi di sicurezza. Per ulteriori informazioni sul controllo WCF, vedere [controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
### <a name="to-audit-security-events-in-code"></a>Per controllare gli eventi di sicurezza nel codice  
  
1. Specificare il percorso del registro di controllo. A questo scopo, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> della classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> su uno dei valori dell'enumerazione <xref:System.ServiceModel.AuditLogLocation>, come illustrato nel codice seguente.  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     L'enumerazione <xref:System.ServiceModel.AuditLogLocation> dispone di tre valori: `Application`, `Security`o `Default`. Il valore specifica uno dei log visibili nel Visualizzatore eventi, il registro protezione o il registro applicazioni. Se si usa il valore `Default`, il log effettivo dipenderà dal sistema operativo su cui è in esecuzione l'applicazione. Se il controllo è attivato e il percorso del log non viene specificato, verrà usato, per impostazione predefinita, il registro `Security`, per le piattaforme che supportano la scrittura nel registro protezione, altrimenti verrà usato il registro `Application`. Per impostazione predefinita, solo Windows Server 2003 e Windows Vista supportano la scrittura nel registro di sicurezza.  
  
2. Impostare i tipi di eventi da controllare. È possibile controllare simultaneamente eventi a livello di servizio o eventi di autorizzazione a livello di messaggio. A questo scopo, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> su uno dei valori dell'enumerazione <xref:System.ServiceModel.AuditLevel>, come illustrato nel codice seguente.  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. Specificare se esporre o meno gli errori all'applicazione relativamente agli eventi di controllo del log. Impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true` o `false`, come illustrato nel codice seguente.  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     La proprietà `SuppressAuditFailure` predefinita è `true`, in modo che l'errore da controllare non influenzi l'applicazione. In caso contrario, viene generata un'eccezione. Per ogni controllo riuscito viene scritta una traccia dettagliata. Per ogni errore da controllare, la traccia viene scritta a livello errore.  
  
4. Eliminare la classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> esistente dalla raccolta dei comportamenti trovati nella descrizione di una classe <xref:System.ServiceModel.ServiceHost>. La raccolta dei comportamenti è accessibile tramite la proprietà <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, che a sua volta è accessibile dalla proprietà <xref:System.ServiceModel.ServiceHostBase.Description%2A>. Aggiungere quindi la nuova classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> alla stessa raccolta, come illustrato nel codice seguente.  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a>Per impostare il controllo nella configurazione  
  
1. Per configurare il controllo nella configurazione, aggiungere un [\<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento alla sezione [\<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) del file Web. config. Aggiungere quindi un elemento [\<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) e impostare i vari attributi, come illustrato nell'esempio seguente.  
  
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
  
2. È necessario specificare il comportamento del servizio, come illustrato nell'esempio seguente.  
  
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
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene creata un'istanza della classe <xref:System.ServiceModel.ServiceHost> e viene aggiunta una nuova classe <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> alla raccolta dei comportamenti.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Se si imposta la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true`, viene evitata la visualizzazione di qualsiasi errore per generare controlli di sicurezza (se la proprietà viene impostata su `false`, viene generata un'eccezione). Tuttavia, se si Abilita la seguente proprietà di **impostazione di sicurezza locale** di Windows, un errore di generazione di eventi di controllo causerà l'arresto immediato di Windows:  
  
 **Controllo: arrestare immediatamente il sistema se non è possibile registrare i controlli di sicurezza**  
  
 Per impostare la proprietà, aprire la finestra di dialogo **impostazioni di sicurezza locali** . In **impostazioni di sicurezza**fare clic su **criteri locali**. Fare quindi clic su **Opzioni di sicurezza**.  
  
 Se la proprietà <xref:System.ServiceModel.AuditLogLocation> è impostata su <xref:System.ServiceModel.AuditLogLocation.Security> e l' **accesso agli oggetti di controllo** non è impostato nei criteri di **sicurezza locali**, gli eventi di controllo non verranno scritti nel registro di sicurezza. Si noti che non viene restituito alcun errore, ma non vengono scritte voci di controllo nel registro protezione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [Controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
