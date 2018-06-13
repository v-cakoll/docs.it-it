---
title: '&lt;serviceSecurityAudit&gt;'
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 293cd3118ace2e073933e4c124664c775902e7d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751181"
---
# <a name="ltservicesecurityauditgt"></a>&lt;serviceSecurityAudit&gt;
Specifica impostazioni che abilitano controllo di eventi di sicurezza durante le operazioni del servizio.  
  
 \<system.ServiceModel>  
\<i comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<serviceSecurityAudit>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessOrFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|auditLogLocation|Specifica il percorso del registro di controllo. Di seguito vengono elencati i valori validi:<br /><br /> -Default: Gli eventi di sicurezza vengono scritti nel registro applicazioni in Windows XP e nel registro eventi in Windows Server 2003 e Windows Vista.<br />-Applicazione: Eventi di controllo vengono scritti nel Log eventi dell'applicazione.<br />-Security: Gli eventi di controllo vengono scritti nel registro eventi di sicurezza.<br /><br /> Il valore predefinito è Default. Per altre informazioni, vedere <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel log di controllo.<br /><br /> Le applicazioni devono ricevere notifiche per errori di scrittura nel registro di controllo. Se l'applicazione non è progettata per gestire errori di controllo, è necessario usare questo attributo per eliminare errori di scrittura nel registro di controllo.<br /><br /> Se l'attributo è `true`, le eccezioni diverse da OutOfMemoryException, StackOverFlowException, ThreadAbortException e ArgumentException che sono il risultato di tentativi di scrivere eventi di controllo vengono gestite dal sistema e non vengono propagate all'applicazione. Se questo attributo è `false`, tutte le eccezioni che sono il risultato di tentativi di scrivere eventi di controllo vengono passate all'applicazione.<br /><br /> Il valore predefinito è `true`.|  
|serviceAuthorizationAuditLevel|Specifica i tipi di eventi di autorizzazione registrati nel registro di controllo. Di seguito vengono elencati i valori validi:<br /><br /> -None: Autorizzazione eventi del servizio viene eseguito alcun controllo.<br />-Operazione riuscita: Vengono controllati solo gli eventi di autorizzazione del servizio ha esito positivo.<br />-Errore: Vengono controllati solo eventi di autorizzazione del servizio errori.<br />-SuccessOrFailure: Entrambi gli eventi di autorizzazione servizio esito positivo e negativo sono controllati.<br /><br /> Il valore predefinito è None. Per altre informazioni, vedere <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Specifica il tipo di eventi di controllo di autenticazione dei messaggi registrati. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessun evento di controllo viene generato.<br />-Operazione riuscita: Vengono registrati solo gli eventi di sicurezza riusciti (convalida completa inclusa la convalida della firma di messaggi, cifra e convalida dei token).<br />-Errore: Vengono registrati solo gli eventi di errore.<br />-SuccessOrFailure: Entrambi vengono registrati gli eventi di esito positivo e negativo.<br /><br /> Il valore predefinito è None. Per altre informazioni, vedere <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione viene utilizzato per controllare gli eventi di autenticazione di Windows Communication Foundation (WCF). Quando il controllo è attivato, è possibile controllare tentativi di autenticazione riusciti o con errori (o entrambi). Gli eventi vengono scritti in uno di tre registri eventi (applicazione, sicurezza o predefinito) in base alla versione del sistema operativo. I registri eventi possono essere tutti visualizzati con il Visualizzatore eventi di Windows.  
  
 Per un esempio dettagliato dell'utilizzo di questo elemento di configurazione, vedere [il comportamento di controllo del servizio](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).  
  
 Per impostazione predefinita, in Windows XP gli eventi di controllo possono essere visualizzati nel Registro applicazioni, mentre in Windows Server 2003 e Windows Vista gli eventi di controllo possono essere visti nel Registro di sicurezza. Il percorso degli eventi di controllo può essere specificato impostando l'attributo `auditLogLocation` su 'Application' o 'Security'. Per ulteriori informazioni, vedere [come: eventi di protezione controllo](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Se gli eventi vengono scritti nel Registro di sicurezza, LocalSecurityPolicy per l'abilitazione dell'accesso all'oggetto deve essere impostato per "Success" e "Failure".  
  
 Nel registro eventi l'origine degli eventi di controllo corrisponde a "ServiceModel Audit 3.0.0.0". I record di controllo di autenticazione dei messaggi hanno una categoria "MessageAuthentication", mentre i record di controllo di autorizzazione del servizio hanno una categoria "ServiceAuthorization".  
  
 Gli eventi di controllo di autenticazione dei messaggi analizzano se il messaggio è stato manomesso, se è scaduto e se il client può essere autenticato presso il servizio. Forniscono informazioni sull'esito positivo o meno dell'autenticazione insieme all'identità del client e dell'endpoint a cui è stato inviato il messaggio a insieme all'azione associata al messaggio.  
  
 Gli eventi di controllo dell'autorizzazione del servizio analizzano la decisione di autorizzazione adottata dalla gestione autorizzazioni del servizio. Forniscono informazioni sull'eventuale autorizzazione ha avuto esito positivo o non è riuscita con l'identità del client, l'endpoint del messaggio è stato inviato, l'azione associata al messaggio, l'identificatore del contesto di autorizzazione che è stato generato dal messaggio in arrivo e il tipo di gestione autorizzazioni che ha preso la decisione di accesso.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.serviceModel>  
   <serviceBehaviors>  
      <behavior name="NewBehavior">  
         <serviceSecurityAudit auditLogLocation="Application"   
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"   
             messageAuthenticationAuditLevel="Success" />  
      </behavior>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Controllo](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Procedura: Controllare gli eventi di sicurezza](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [Comportamento di controllo dei servizi](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)
