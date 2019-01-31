---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: befa74f02ccb0dde4448f36c0698feebaf6201ce
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286403"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Consente di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) quando si usa federated authentication tramite il protocollo WS-Federation. Consente di configurare il <xref:System.Security.Claims.ClaimsAuthorizationManager> quando si usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
  
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
|name|Il nome di questo elemento di configurazione di federazione. Questo attributo fornisce principalmente un punto di estendibilità per i protocolli future. Facoltativo.|  
|identityConfigurationName|Il nome della sezione di configurazione di identità come specificato in un' [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento da utilizzare. Se questo attributo viene omesso, viene utilizzata la sezione di configurazione di identità predefinito. Facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Consente di configurare il gestore di cookie usato da SAM. Facoltativo.|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura il certificato utilizzato per crittografare e decrittografare i token. Facoltativo.|  
|[\<wsFederation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Consente di configurare il modulo di autenticazione WS-Federation (WSFAM). Facoltativo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Sezione di configurazione per l'autenticazione usando il protocollo WS-Federation.|  
  
## <a name="remarks"></a>Note  
 Il \<federationConfiguration > elemento offre impostazioni in due scenari diversi:  
  
-   Quando si usa WS-Federation in un'applicazione Web passiva, l'elemento contiene impostazioni che consentono di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Fa inoltre riferimento la configurazione di identità da usare per configurare i gestori di token di sicurezza e i certificati e i componenti, ad esempio il gestore di autorizzazione delle attestazioni e il gestore di autenticazione delle attestazioni.  
  
-   Quando si usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire un controllo di accesso basato sulle attestazioni nel codice, l'elemento fa riferimento la configurazione di identità che consente di configurare il gestore di autorizzazione delle attestazioni e i criteri utilizzati per rendere l'autorizzazione decisioni. Questo è true, anche negli scenari che non sono gli scenari passivi Web; ad esempio, le applicazioni di Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, il [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento (e gli elementi di criteri figlio, se presente) della configurazione dell'identità a cui fanno riferimento le `<federationConfiguration>` elemento le uniche impostazioni vengono applicate. Tutti gli altri vengono ignorati.  
  
 Indipendentemente dallo scenario, il runtime carica la configurazione predefinita di federazione. Il comportamento viene definito come segue:  
  
1.  Se è presente alcun `<federationConfiguration>` elemento presenta, il runtime crea una configurazione di federazione e lo popola con i valori predefiniti. Questa configurazione di federazione predefinita farà riferimento la configurazione di identità predefinito.  
  
2.  Se un singolo `<federationConfiguration>` elemento è presente, si tratta della configurazione di federazione predefinito indipendentemente dal fatto è definito o meno. Se relativo `identityConfiguration` attributo è specificato, la configurazione di identità denominata viene fatto riferimento; in caso contrario, fa riferimento la configurazione di identità predefinito.  
  
3.  Se un oggetto senza nome `<federationConfiguration>` elemento è presente, è la configurazione predefinita di federazione. Se relativo `identityConfiguration` attributo è specificato, la configurazione di identità denominata viene fatto riferimento; in caso contrario, fa riferimento la configurazione di identità predefinito.  
  
4.  Se più denominata `<federationConfiguration>` elementi siano presenti e senza nome `<federationConfiguration>` elemento è presente, viene generata un'eccezione.  
  
 In genere, una sola `<federationConfiguration>` sezione è definita. In questa sezione è la configurazione predefinita di federazione. È possibile specificare più, denominati in modo univoco `<federationConfiguration>` elementi; tuttavia, in questo caso, se si vuole caricare una configurazione di federazione diverso da quello senza nome, è necessario fornire un gestore per il. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> evento e impostare il <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> proprietà all'interno del gestore per un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto inizializzata con i valori appropriati `<federationConfiguration>` elemento nel file di configurazione.  
  
 Il `<federationConfiguration>` elemento è rappresentato dal <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> classe. L'oggetto di configurazione stesso è rappresentato dal <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> classe. Un unico <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> istanza è nastavit il <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà e fornisce una configurazione federata per l'applicazione.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato un `<federationConfiguration>` elemento che specifica le impostazioni per il WSFAM e specifica che il gestore di cookie predefinito (un'istanza del <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe) essere usato da SAM.  
  
> [!WARNING]
>  In questo esempio, il gestore di cookie né WSFAM deve usare HTTPS. Infatti il `requireHttps` dell'attributo sul `<wsFederation>` elemento e il `requireSsl` attributo il `<cookieHandlerElement>` sono `false`. Queste impostazioni non sono consigliate per la maggior parte degli ambienti di produzione, come si può costituire un rischio di sicurezza.  
  
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
- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
