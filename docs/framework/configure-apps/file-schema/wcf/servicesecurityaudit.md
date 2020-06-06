---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 10888f26053014ffb1fec49d1dfe87c7fd09ab54
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399584"
---
# \<serviceSecurityAudit>
Specifica impostazioni che abilitano controllo di eventi di sicurezza durante le operazioni del servizio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|auditLogLocation|Specifica il percorso del registro di controllo. I valori validi sono i seguenti:<br /><br /> -Default: gli eventi di sicurezza vengono scritti nel registro applicazioni in Windows XP e nel registro eventi in Windows Server 2003 e Windows Vista.<br />-Application: gli eventi di controllo vengono scritti nel registro eventi dell'applicazione.<br />-Security: gli eventi di controllo vengono scritti nel registro eventi di protezione.<br /><br /> Il valore predefinito è Default. Per altre informazioni, vedere <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel log di controllo.<br /><br /> Le applicazioni devono ricevere notifiche per errori di scrittura nel registro di controllo. Se l'applicazione non è progettata per gestire errori di controllo, è necessario usare questo attributo per eliminare errori di scrittura nel registro di controllo.<br /><br /> Se l'attributo è `true`, le eccezioni diverse da OutOfMemoryException, StackOverFlowException, ThreadAbortException e ArgumentException che sono il risultato di tentativi di scrivere eventi di controllo vengono gestite dal sistema e non vengono propagate all'applicazione. Se questo attributo è `false`, tutte le eccezioni che sono il risultato di tentativi di scrivere eventi di controllo vengono passate all'applicazione.<br /><br /> Il valore predefinito è `true`.|  
|serviceAuthorizationAuditLevel|Specifica i tipi di eventi di autorizzazione registrati nel registro di controllo. I valori validi sono i seguenti:<br /><br /> -None: non viene eseguito alcun controllo degli eventi di autorizzazione del servizio.<br />-Success: vengono controllati solo gli eventi di autorizzazione del servizio riusciti.<br />-Errore: vengono controllati solo gli eventi di autorizzazione del servizio non riuscito.<br />-SuccessOrFailure: vengono controllati gli eventi di autorizzazione del servizio con esito positivo e negativo.<br /><br /> Il valore predefinito è None (Nessuna). Per altre informazioni, vedere <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Specifica il tipo di eventi di controllo di autenticazione dei messaggi registrati. I valori validi sono i seguenti:<br /><br /> -None: non viene generato alcun evento di controllo.<br />-Success: vengono registrate solo le operazioni di sicurezza con esito positivo (convalida completa, inclusi convalida della firma del messaggio, crittografia e convalida del token).<br />-Errore: vengono registrati solo gli eventi di errore.<br />-SuccessOrFailure: vengono registrati gli eventi di esito positivo e negativo.<br /><br /> Il valore predefinito è None (Nessuna). Per altre informazioni, vedere <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Commenti  
 Questo elemento di configurazione viene utilizzato per controllare gli eventi di autenticazione di Windows Communication Foundation (WCF). Quando il controllo è attivato, è possibile controllare tentativi di autenticazione riusciti o con errori (o entrambi). Gli eventi vengono scritti in uno di tre registri eventi (applicazione, sicurezza o predefinito) in base alla versione del sistema operativo. I registri eventi possono essere tutti visualizzati con il Visualizzatore eventi di Windows.  
  
 Per un esempio dettagliato dell'uso di questo elemento di configurazione, vedere [comportamento di controllo dei servizi](../../../wcf/samples/service-auditing-behavior.md).  
  
 Per impostazione predefinita, in Windows XP gli eventi di controllo possono essere visualizzati nel Registro applicazioni, mentre in Windows Server 2003 e Windows Vista gli eventi di controllo possono essere visti nel Registro di sicurezza. Il percorso degli eventi di controllo può essere specificato impostando l'attributo `auditLogLocation` su 'Application' o 'Security'. Per altre informazioni, vedere [procedura: controllare gli eventi di sicurezza](../../../wcf/feature-details/how-to-audit-wcf-security-events.md). Se gli eventi vengono scritti nel registro di sicurezza, è necessario impostare LocalSecurityPolicy-> abilitare l'accesso agli oggetti per "success" e "Failure".  
  
 Nel registro eventi l'origine degli eventi di controllo corrisponde a "ServiceModel Audit 3.0.0.0". I record di controllo di autenticazione dei messaggi hanno una categoria "MessageAuthentication", mentre i record di controllo di autorizzazione del servizio hanno una categoria "ServiceAuthorization".  
  
 Gli eventi di controllo di autenticazione dei messaggi analizzano se il messaggio è stato manomesso, se è scaduto e se il client può essere autenticato presso il servizio. Forniscono informazioni sull'esito positivo o meno dell'autenticazione insieme all'identità del client e dell'endpoint a cui è stato inviato il messaggio a insieme all'azione associata al messaggio.  
  
 Gli eventi di controllo dell'autorizzazione del servizio analizzano la decisione di autorizzazione adottata dalla gestione autorizzazioni del servizio. Forniscono informazioni sull'esito positivo o negativo dell'autorizzazione con l'identità del client, l'endpoint a cui è stato inviato il messaggio, l'azione associata al messaggio, l'identificatore del contesto di autorizzazione generato dal messaggio in arrivo e il tipo di gestione autorizzazioni che ha effettuato la decisione di accesso.  
  
## <a name="example"></a>Esempio  
  
```xml  
<system.serviceModel>
  <behaviors>
    <serviceBehaviors>
      <behavior name="NewBehavior">
        <serviceSecurityAudit auditLogLocation="Application"
                              suppressAuditFailure="true"
                              serviceAuthorizationAuditLevel="Success"
                              messageAuthenticationAuditLevel="Success" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Controllo](../../../wcf/feature-details/auditing-security-events.md)
- [Procedura: controllare gli eventi di sicurezza](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [Comportamento di controllo dei servizi](../../../wcf/samples/service-auditing-behavior.md)
