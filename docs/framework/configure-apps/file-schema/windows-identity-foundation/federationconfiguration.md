---
title: '&lt;federationConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0014e0224221cd5143709ba0a5b38f10e457b494
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
Configura il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) quando si utilizza l'autenticazione tramite il protocollo WS-Federation di federazione. Configura il <xref:System.Security.Claims.ClaimsAuthorizationManager> quando si utilizza il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni.  
  
 \<System >  
\<federationConfiguration >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Il nome di questo elemento di configurazione della federazione. Questo attributo principalmente fornisce un punto di estensibilità per protocolli future. Facoltativo.|  
|identityConfigurationName|Il nome della sezione di configurazione di identità come specificato in un [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento da utilizzare. Se questo attributo viene omesso, viene utilizzata la sezione di configurazione di identità predefinito. Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Consente di configurare il gestore di cookie utilizzato per il modulo SAM. Facoltativo.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Consente di configurare il certificato utilizzato per crittografare e decrittografare i token. Facoltativo.|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Configura il modulo di autenticazione WS-Federation (WSFAM). Facoltativo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.|  
  
## <a name="remarks"></a>Note  
 Il \<federationConfiguration > elemento offre impostazioni in due scenari diversi:  
  
-   Quando si utilizza WS-Federation in un'applicazione Web passiva, l'elemento contiene le impostazioni che configurano il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Fa inoltre la configurazione di identità da utilizzare per configurare i gestori di token di sicurezza e i certificati e i componenti come la gestione di autorizzazione delle attestazioni e il gestore di autenticazione delle attestazioni.  
  
-   Quando si utilizza il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire un controllo di accesso basato sulle attestazioni nel codice, l'elemento fa riferimento la configurazione di identità che consente di configurare i criteri viene utilizzato per rendere l'autorizzazione e la gestione di autorizzazioni di attestazioni decisioni. Questo è true, anche negli scenari che non sono scenari Web passivi. ad esempio, applicazioni Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, il [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento (e criteri elementi figlio, se presente) della configurazione dell'identità a cui fa riferimento il `<federationConfiguration>` elemento le uniche impostazioni vengono applicate. Tutti gli altri vengono ignorati.  
  
 Indipendentemente dallo scenario, il runtime carica la configurazione predefinita della federazione. Il comportamento viene definito come segue:  
  
1.  Se è presente alcun `<federationConfiguration>` elemento presente, il runtime crea una configurazione di federazione e popolarla con i valori predefiniti. La configurazione di identità predefinita farà riferimento a questa configurazione di federazione predefinita.  
  
2.  Se un singolo `<federationConfiguration>` elemento è presente, è la configurazione della federazione predefinito indipendentemente dal fatto è denominato o senza nome. Se il relativo `identityConfiguration` attributo viene specificato, la configurazione di identità denominati viene fatto riferimento; in caso contrario, cui fa riferimento la configurazione di identità predefinita.  
  
3.  Se un oggetto senza nome `<federationConfiguration>` elemento è presente, è la configurazione predefinita della federazione. Se il relativo `identityConfiguration` attributo viene specificato, la configurazione di identità denominati viene fatto riferimento; in caso contrario, cui fa riferimento la configurazione di identità predefinita.  
  
4.  Se più denominato `<federationConfiguration>` elementi siano presenti e non denominati `<federationConfiguration>` elemento è presente, viene generata un'eccezione.  
  
 In genere, una sola `<federationConfiguration>` sezione è definita. In questa sezione è la configurazione predefinita della federazione. È possibile specificare più, in modo univoco denominato `<federationConfiguration>` elementi; tuttavia, in questo caso, se si desidera caricare una configurazione di federazione diverso da quello senza nome, è necessario fornire un gestore per il. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>eventi e impostare il <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> proprietà all'interno del gestore per un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto inizializzata con i valori appropriati `<federationConfiguration>` elemento nel file di configurazione.  
  
 Il `<federationConfiguration>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> classe. L'oggetto di configurazione è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> classe. Un singolo <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> istanza è impostata sul <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà e fornisce configurazione federato per l'applicazione.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato un `<federationConfiguration>` elemento che specifica le impostazioni per il WSFAM e specifica che il gestore di cookie predefinito (un'istanza del <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe) utilizzabile per il modulo SAM.  
  
> [!WARNING]
>  In questo esempio, il gestore di cookie né WSFAM deve utilizzare HTTPS. In questo modo il `requireHttps` attributo il `<wsFederation>` elemento e `requireSsl` attributo il `<cookieHandlerElement>` sono `false`. Queste impostazioni non sono consigliate per la maggior parte degli ambienti di produzione in cui potrebbe presentano un rischio per la sicurezza.  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"   
      issuer="http://localhost:15839/wsFederationSTS/Issue"   
      realm="http://localhost:50969/" reply="http://localhost:50969/"   
      requireHttps="false"   
      signOutReply="http://localhost:50969/SignedOutPage.html"   
      signOutQueryString="Param1=value2&Param2=value2"   
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
