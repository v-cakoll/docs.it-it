---
title: Comportamento di controllo dei servizi
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: bfe13146a7f7cdec648a82a34c34077ec5466809
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599932"
---
# <a name="service-auditing-behavior"></a>Comportamento di controllo dei servizi
Questo esempio illustra come usare <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> per abilitare il controllo degli eventi di sicurezza durante le operazioni del servizio. Questo esempio è basato sul [Introduzione](getting-started-sample.md). Il servizio e il client sono stati configurati utilizzando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . L' `mode` attributo di [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) è stato impostato su `Message` e `clientCredentialType` è stato impostato su `Windows` . In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il file di configurazione del servizio utilizza l'elemento `serviceSecurityAudit` per configurare il controllo.  
  
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
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra della console per arrestare il client.  
  
 I log di controllo risultanti possono essere visualizzati eseguendo il Visualizzatore eventi. Per impostazione predefinita, in Windows XP gli eventi di controllo possono essere visualizzati nel registro applicazioni, mentre in Windows Server 2003 e Windows Vista gli eventi di controllo possono essere visti nel registro sicurezza. In Windows Server 2008 e Windows 7 è possibile visualizzare gli eventi di controllo nei registri applicazioni e sicurezza. Il percorso degli eventi di controllo può essere specificato impostando l' `auditLogLocation` attributo su "Application" o "Security". Per altre informazioni, vedere [procedura: controllare gli eventi di sicurezza](../feature-details/how-to-audit-wcf-security-events.md). Se gli eventi vengono scritti nel registro di sicurezza, è necessario impostare LocalSecurityPolicy-> abilitare l'accesso agli oggetti per "success" e "Failure".  
  
 Nel registro eventi l'origine degli eventi di controllo corrisponde a "ServiceModel Audit 3.0.0.0". I record di controllo di autenticazione dei messaggi hanno una categoria "MessageAuthentication", mentre i record di controllo di autorizzazione del servizio hanno una categoria "ServiceAuthorization".  
  
 Gli eventi di controllo dell'autenticazione dei messaggi analizzano se il messaggio è stato manomesso, se è scaduto e se il client può essere autenticato presso il servizio. Tali eventi forniscono inoltre informazioni sull'esito positivo o meno dell'autenticazione nonché l'identità del client e dell'endpoint a cui è stato inviato il messaggio insieme all'azione associata a quest'ultimo.  
  
 Gli eventi di controllo dell'autorizzazione del servizio analizzano la decisione di autorizzazione adottata dalla gestione autorizzazioni del servizio. Tali eventi forniscono inoltre informazioni sull'esito positivo o meno dell'autorizzazione nonché l'identità del client, l'endpoint al quale è stato inviato il messaggio, l'azione associata al messaggio, l'identificatore del contesto di autorizzazione generato dal messaggio in arrivo e il tipo di gestione autorizzazioni che ha preso la decisione relativa all'accesso.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche

- [Controllo](../feature-details/auditing-security-events.md)
- [Procedura: controllare gli eventi di sicurezza](../feature-details/how-to-audit-wcf-security-events.md)
