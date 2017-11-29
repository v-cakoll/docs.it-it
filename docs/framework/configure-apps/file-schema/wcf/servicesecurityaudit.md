---
title: '&lt;serviceSecurityAudit&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f0c708c19761f6086e1b5c2fdd15904c76fe3de9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicesecurityauditgt"></a>&lt;serviceSecurityAudit&gt;
Specifica impostazioni che abilitano controllo di eventi di sicurezza durante le operazioni del servizio.  
  
 \<System. ServiceModel >  
\<i comportamenti >  
\<serviceBehaviors >  
\<comportamento >  
\<serviceSecurityAudit >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessAndFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessAndFailure"  
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
|serviceAuthorizationAuditLevel|Specifica i tipi di eventi di autorizzazione registrati nel registro di controllo. Di seguito vengono elencati i valori validi:<br /><br /> -None: Autorizzazione eventi del servizio viene eseguito alcun controllo.<br />-Operazione riuscita: Vengono controllati solo gli eventi di autorizzazione del servizio ha esito positivo.<br />-Errore: Vengono controllati solo eventi di autorizzazione del servizio errori.<br />-SuccessAndFailure: Entrambi vengono controllati gli eventi di autorizzazione servizio esito positivo e negativo.<br /><br /> Il valore predefinito è None. Per altre informazioni, vedere <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Specifica il tipo di eventi di controllo di autenticazione dei messaggi registrati. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessun evento di controllo viene generato.<br />-Operazione riuscita: Vengono registrati solo gli eventi di sicurezza riusciti (convalida completa inclusa la convalida della firma di messaggi, cifra e convalida dei token).<br />-Errore: Vengono registrati solo gli eventi di errore.<br />-SuccessAndFailure: Entrambi vengono registrati gli eventi di esito positivo e negativo.<br /><br /> Il valore predefinito è None. Per altre informazioni, vedere <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione viene usato per controllare gli eventi di autenticazione di [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]. Quando il controllo è attivato, è possibile controllare tentativi di autenticazione riusciti o con errori (o entrambi). Gli eventi vengono scritti in uno di tre registri eventi (applicazione, sicurezza o predefinito) in base alla versione del sistema operativo. I registri eventi possono essere tutti visualizzati con il Visualizzatore eventi di Windows.  
  
 Per un esempio dettagliato dell'utilizzo di questo elemento di configurazione, vedere [il comportamento di controllo del servizio](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).  
  
 Per impostazione predefinita, in Windows XP gli eventi di controllo possono essere visualizzati nel Registro applicazioni, mentre in Windows Server 2003 e Windows Vista gli eventi di controllo possono essere visti nel Registro di sicurezza. Il percorso degli eventi di controllo può essere specificato impostando l'attributo `auditLogLocation` su 'Application' o 'Security'. Per ulteriori informazioni, vedere [come: eventi di protezione controllo](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Se gli eventi vengono scritti nel Registro di sicurezza, LocalSecurityPolicy per l'abilitazione dell'accesso all'oggetto deve essere impostato per "Success" e "Failure".  
  
 Nel registro eventi l'origine degli eventi di controllo corrisponde a "ServiceModel Audit 3.0.0.0". I record di controllo di autenticazione dei messaggi hanno una categoria "MessageAuthentication", mentre i record di controllo di autorizzazione del servizio hanno una categoria "ServiceAuthorization".  
  
 Gli eventi di controllo di autenticazione dei messaggi analizzano se il messaggio è stato manomesso, se è scaduto e se il client può essere autenticato presso il servizio. Forniscono informazioni sull'esito positivo o meno dell'autenticazione insieme all'identità del client e dell'endpoint a cui è stato inviato il messaggio a insieme all'azione associata al messaggio.  
  
 Gli eventi di controllo dell'autorizzazione del servizio analizzano la decisione di autorizzazione adottata dalla gestione autorizzazioni del servizio. Forniscono informazioni sull'esito positivo o meno dell'autorizzazione insieme all'identità del client, l'endpoint al quale è stato inviato il messaggio, l'azione associata al messaggio, l'identificatore del contesto di autorizzazione che è stato generato dal messaggio in arrivo e il tipo di gestione autorizzazioni che ha eseguito la decisione dell'accesso.  
  
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
 [Il controllo](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Procedura: controllare gli eventi di sicurezza](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [Comportamento di controllo del servizio](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)
