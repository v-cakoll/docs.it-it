---
title: Controllo degli eventi di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- auditing security events [WCF]
ms.assetid: 5633f61c-a3c9-40dd-8070-1c373b66a716
ms.openlocfilehash: b130ed57ba086535122c8c8795c42863348870d0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597657"
---
# <a name="auditing-security-events"></a>Controllo degli eventi di sicurezza
Le applicazioni create con Windows Communication Foundation (WCF) possono registrare gli eventi di sicurezza (esito positivo, esito negativo o entrambi) con la funzionalità di controllo. Gli eventi vengono scritti nel registro eventi del sistema Windows e possono essere esaminati tramite il Visualizzatore eventi.  
  
 La funzionalità di controllo consente a un amministratore di individuare un attacco mentre è ancora in corso o quando è già avvenuto. Tale funzionalità consente inoltre agli sviluppatori di semplificare il debug dei problemi di sicurezza. Ad esempio, se per un errore nella configurazione dei criteri di autorizzazione o di verifica il sistema nega l'accesso a un utente autorizzato, uno sviluppatore può individuare e isolare rapidamente la causa di questo errore esaminando il registro eventi.  
  
 Per ulteriori informazioni sulla sicurezza di WCF, vedere [Cenni preliminari sulla sicurezza](security-overview.md). Per ulteriori informazioni sulla programmazione di WCF, vedere [Basic WCF Programming](../basic-wcf-programming.md).  
  
## <a name="audit-level-and-behavior"></a>Livelli e comportamenti di controllo  
 Esistono due livelli di controllo di sicurezza:  
  
- Livello Autorizzazione servizio, che prevede l'autorizzazione di un chiamante.  
  
- Livello del messaggio, in cui WCF verifica la validità del messaggio e autentica il chiamante.  
  
 È possibile verificare l'esito positivo o negativo di entrambi i livelli di controllo, noto come *comportamento di controllo*.  
  
## <a name="audit-log-location"></a>Posizione del registro di controllo  
 Dopo aver determinato un livello e un comportamento di controllo, è possibile specificare la posizione del registro di controllo. Sono disponibili tre opzioni: Predefinito, Applicazione e Protezione. Quando si specifica l'opzione Predefinito, la posizione effettiva del registro varia in base al sistema utilizzato e alla possibilità di quest'ultimo di supportare la scrittura nel registro di sicurezza. Per ulteriori informazioni, vedere la sezione "sistema operativo" più avanti in questo argomento.  
  
 Per scrivere nel registro protezione è necessario disporre del privilegio `SeAuditPrivilege`. Per impostazione predefinita, solo gli account Sistema locale e Servizio di rete dispongono di questo privilegio. Per gestire le funzioni del registro protezione `read` e `delete` è necessario disporre del privilegio `SeSecurityPrivilege`. Per impostazione predefinita, solo gli amministratori dispongono di questo privilegio.  
  
 Gli utenti autenticati possono invece leggere e scrivere nel registro applicazioni. Per impostazione predefinita, in Windows XP gli eventi di controllo vengono scritti nel registro applicazioni. Il registro applicazioni può inoltre contenere informazioni personali a cui tutti gli utenti autenticati sono in grado di accedere.  
  
## <a name="suppressing-audit-failures"></a>Soppressione degli errori di controllo  
 Durante il controllo è inoltre disponibile un'opzione che consente di sopprimere tutti gli errori di controllo. Per impostazione predefinita, gli errori di controllo non influiscono sulle applicazioni. Tuttavia, se occorre, è possibile impostare tale opzione su `false`. In questo modo, se si verifica un errore di controllo, viene generata un'eccezione.  
  
## <a name="programming-auditing"></a>Programmazione del controllo  
 Il comportamento di controllo può essere specificato a livello di programmazione o tramite configurazione.  
  
### <a name="auditing-classes"></a>Classi di controllo  
 Nella seguente tabella sono descritte le classi e le proprietà utilizzate per programmare un comportamento di controllo.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>|Consente di impostare le opzioni di controllo come comportamento di servizio.|  
|<xref:System.ServiceModel.AuditLogLocation>|Enumerazione che consente di specificare la posizione del registro in cui scrivere. I valori possibili sono Predefinito, Applicazione e Protezione. Quando si seleziona Predefinito, il sistema operativo determina la posizione effettiva del registro. Per ulteriori informazioni, vedere la sezione "Scelta fra registro eventi Applicazione o Protezione" del presente argomento.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A>|Specifica il livello Messaggio utilizzato per i controlli a livello di messaggio. Sono disponibili le opzioni `None`, `Failure`, `Success`, e `SuccessOrFailure`.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A>|Specifica il livello Autorizzazione servizio utilizzato per i controlli a livello di servizio. Sono disponibili le opzioni `None`, `Failure`, `Success`, e `SuccessOrFailure`.|  
|<xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A>|Specifica la modalità di elaborazione della richiesta del client quando un controllo ha esito negativo. Ciò ad esempio si verifica quando il servizio tenta di scrivere nel registro protezione senza tuttavia disporre del privilegio `SeAuditPrivilege`. Il valore predefinito `true` indica che gli errori vengono ignorati e che la richiesta del client viene elaborata normalmente.|  
  
 Per un esempio di configurazione di un'applicazione per la registrazione degli eventi di controllo, vedere [procedura: controllare gli eventi di sicurezza](how-to-audit-wcf-security-events.md).  
  
### <a name="configuration"></a>Configurazione  
 È anche possibile usare la configurazione per specificare il comportamento di controllo aggiungendo un oggetto [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md) in [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) . È necessario aggiungere l'elemento in un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) come illustrato nel codice seguente.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <behavior>  
        <!-- auditLogLocation="Application" or "Security" -->  
        <serviceSecurityAudit  
                  auditLogLocation="Application"  
                  suppressAuditFailure="true"  
                  serviceAuthorizationAuditLevel="Failure"  
                  messageAuthenticationAuditLevel="SuccessOrFailure" />
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Se il controllo è attivo e non è stata specificata alcuna posizione `auditLogLocation`, la posizione predefinita del registro è "Protezione" se la piattaforma supporta la scrittura in tale registro. In caso contrario, tale posizione è "Applicazione". Solo i sistemi operativi Windows Server 2003 e Windows Vista supportano la scrittura nel registro di sicurezza. Per ulteriori informazioni, vedere la sezione "sistema operativo" più avanti in questo argomento.  
  
## <a name="security-considerations"></a>Considerazioni relative alla sicurezza  
 Un utente malintenzionato a conoscenza del fatto che il controllo è attivo può inviare messaggi non validi che comportano la scrittura di voci di controllo. Ciò comporta a sua volta la generazione di errori nel sistema di controllo. Per ridurre questo problema, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true` e usare le proprietà del Visualizzatore eventi per controllare il comportamento di controllo.  
  
 Gli eventi di controllo scritti nel registro applicazioni in Windows XP sono visibili a tutti gli utenti autenticati.  
  
## <a name="choosing-between-application-and-security-event-logs"></a>Scelta fra registro eventi Applicazione o Protezione  
 Nelle tabelle seguenti sono fornite informazioni per scegliere se eseguire la registrazione nel registro eventi Applicazione o nel registro eventi Protezione.  
  
#### <a name="operating-system"></a>Sistema operativo  
  
|Sistema|Registro applicazioni|Registro di sicurezza|  
|------------|---------------------|------------------|  
|Windows XP SP2 o versione successiva|Supportato|Non supportate|  
|Windows Server 2003 SP1 e Windows Vista|Supportato|Il contesto del thread deve disporre del privilegio `SeAuditPrivilege`|  
  
#### <a name="other-factors"></a>Altri fattori  
 Oltre al sistema operativo, nella tabella seguente sono descritte le altre impostazioni che controllano l'attivazione della registrazione.  
  
|Fattore|Registro applicazioni|Registro di sicurezza|  
|------------|---------------------|------------------|  
|Gestione dei criteri di controllo|Non applicabile.|Insieme alla configurazione, il registro protezione viene controllato anche in base ai criteri LSA (Local Security Authority, autorità di sicurezza locale). È inoltre necessario attivare la categoria "Controlla accesso agli oggetti".|  
|Esperienza utente predefinita|Tutti gli utenti autenticati possono scrivere nel registro applicazioni. Di conseguenza, per i processi delle applicazioni non è necessario eseguire alcun passaggio aggiuntivo di autorizzazione.|Il processo dell'applicazione (ovvero il relativo contesto) deve disporre del privilegio `SeAuditPrivilege`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [Panoramica della sicurezza](security-overview.md)
- [Programmazione WCF di base](../basic-wcf-programming.md)
- [Procedura: controllare gli eventi di sicurezza](how-to-audit-wcf-security-events.md)
- [\<serviceSecurityAudit>](../../configure-apps/file-schema/wcf/servicesecurityaudit.md)
- [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
