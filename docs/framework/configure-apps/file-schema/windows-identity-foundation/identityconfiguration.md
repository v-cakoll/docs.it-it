---
title: '&lt;identityConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5070d9e886b8f5a8a0abf27593d40df8b5281267
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
Specifica le impostazioni di identità a livello di servizio.  
  
 \<system.identityModel>  
\<identityConfiguration>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Il nome della sezione di configurazione di identità. È possibile utilizzare questo nome per fare riferimento a una sezione di configurazione specifico. Se non `name` attributo viene specificato, la sezione definisce la configurazione predefinita. La configurazione predefinita viene sempre utilizzata per gli scenari di federazione passiva. Per ulteriori informazioni, vedere il [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.|  
|saveBootstrapContext|Specifica se i token di bootstrap devono essere inclusi nel token di sessione. Il valore può inoltre essere impostato su una raccolta di gestore del token impostando il `saveBootstrapContext` attributo la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento. Il valore impostato per la raccolta del gestore dei token sostituisce il valore impostato nel servizio.|  
|maximumClockSkew|Oggetto <xref:System.TimeSpan> che specifica l'inclinazione di clock massima. Controlla lo sfasamento dei segnali di clock massima per le operazioni di scadenza, ad esempio convalida l'ora di scadenza di una sessione di accesso. Il valore predefinito è 5 minuti, "00: 05:00". Per ulteriori informazioni su come specificare <xref:System.TimeSpan> valori, vedere [valori Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Lo sfasamento dei segnali di clock massima può essere impostato anche in una raccolta di gestore del token impostando il `maximumClockSkew` attributo la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento. Il valore impostato per la raccolta del gestore dei token sostituisce il valore impostato nel servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<memorizza nella cache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra le cache usate per i token di sessione e il rilevamento riproduzione token. È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza. Facoltativo.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controlla le impostazioni che utilizzano gestori di token per convalidare i certificati. È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza. Facoltativo.|  
|[\<claimsAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso. Facoltativo.|  
|[\<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Registra un gestore autorizzazioni attestazioni per le attestazioni in ingresso. Facoltativo.|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Specifica il set di attestazioni necessarie per i token di sicurezza in ingresso. Facoltativo.|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Specifica una raccolta di gestori di token di sicurezza. È possibile specificare zero o più raccolte di gestori di token di sicurezza. Facoltativo.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Abilita rilevamento riproduzione token e specifica l'ora di scadenza per i token. È possibile specificare a livello di servizio o in una raccolta di gestore del token di sicurezza. Facoltativo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<System. IdentityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Fornisce la configurazione per l'attivazione di opzioni di Windows Identity Foundation (WIF) nelle applicazioni.|  
  
## <a name="remarks"></a>Note  
 Più identità è possibile definire configurazioni, ognuna con un nome univoco. Il comportamento è come segue:  
  
1.  Se non `<identityConfiguration>` viene specificato alcun elemento. Una configurazione di identità predefinita viene creata in fase di esecuzione e popolata con i valori predefiniti.  
  
2.  Se un singolo `<identityConfiguration>` viene specificato alcun elemento. Si tratta della configurazione di identità predefinito. Non è importante se è denominato o senza nome.  
  
3.  Se più `<identityConfiguration>` gli elementi vengono specificati. L'elemento senza nome specifica la configurazione di identità predefinita. È consigliabile che quando si specificano più `<identityConfiguration>` elementi, uno di essi deve essere senza nome.  
  
> [!WARNING]
>  Se si specificano più `<identityConfiguration>` elementi, uno di essi deve essere senza nome. L'elemento senza nome sarà la configurazione di identità predefinita.  
  
 Alcune delle impostazioni specificate nel `<identityConfiguration>` elemento può essere sottoposta a override dalle impostazioni in una raccolta di gestore del token di sicurezza o mediante le impostazioni di gestori di token di sicurezza.  
  
> [!IMPORTANT]
>  Quando si utilizza il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, la configurazione di identità a cui fa riferimento il `<federationConfiguration>` elemento consente di configurare i criteri viene utilizzato per rendere e la gestione di autorizzazioni di attestazioni decisioni di autorizzazione. Questo è true, anche negli scenari che non sono passivi scenari Web, ad esempio applicazioni di Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, il [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento (e criteri elementi figlio, se presente) della configurazione dell'identità a cui fa riferimento sono le uniche impostazioni applicate. Tutte le altre impostazioni vengono ignorate. Per ulteriori informazioni, vedere il [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 Il `<identityConfiguration>` elemento è rappresentato dalla <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> classe. Una sezione di configurazione di identità è rappresentata dalla <xref:System.IdentityModel.Configuration.IdentityConfiguration> classe.  
  
> [!IMPORTANT]
>  Specificare i seguenti elementi come elementi figlio del `<identityConfiguration>` deprecato, anche se il comportamento è ancora supportato per compatibilità con le versioni precedenti. Questi elementi, dovrebbe invece essere specificati sotto la [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento.  
>   
>  -   [\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una configurazione di identità, denominata "alternateConfiguration". La configurazione di identità specifica le impostazioni predefinite.  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
