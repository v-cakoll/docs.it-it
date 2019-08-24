---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: c4dbb31bb7961f0d33df9d1faee8fe36ecb520a3
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988325"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Configura (WSFAM) e (Sam) quando si utilizza l'autenticazione federata tramite il protocollo WS-Federation. <xref:System.IdentityModel.Services.SessionAuthenticationModule> <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Configura quando si <xref:System.Security.Claims.ClaimsAuthorizationManager> utilizza la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe o per fornire il controllo degli accessi in base alle attestazioni.  
  
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
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|name|Nome di questo elemento di configurazione della Federazione. Questo attributo fornisce principalmente un punto di estendibilità per i protocolli futuri. facoltativo.|  
|identityConfigurationName|Nome della sezione di configurazione dell'identità come specificato in un [ \<> elemento IdentityConfiguration](identityconfiguration.md) da utilizzare. Se questo attributo non viene specificato, viene utilizzata la sezione di configurazione predefinita dell'identità. facoltativo.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura il gestore di cookie usato da SAM. facoltativo.|  
|[\<serviceCertificate>](servicecertificate.md)|Configura il certificato usato per crittografare e decrittografare i token. facoltativo.|  
|[\<wsFederation>](wsfederation.md)|Configura il modulo di autenticazione WS-Federation (WSFAM). facoltativo.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.|  
  
## <a name="remarks"></a>Note  
 L' \<elemento > federationConfiguration fornisce le impostazioni in due scenari diversi:  
  
- Quando si usa WS-Federation in un'applicazione Web passiva, l'elemento contiene le impostazioni che <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> configurano (WSFAM <xref:System.IdentityModel.Services.SessionAuthenticationModule> ) e (Sam). Fa anche riferimento alla configurazione dell'identità da usare per configurare i gestori e i certificati dei token di sicurezza e i componenti come gestione autorizzazioni delle attestazioni e il gestore di autenticazione delle attestazioni.  
  
- Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe o per fornire il controllo degli accessi in base alle attestazioni nel codice, l'elemento fa riferimento alla configurazione di identità che configura il gestore delle autorizzazioni per le attestazioni e i criteri usati per eseguire l'autorizzazione. decisioni. Questo vale anche negli scenari che non sono scenari Web passivi; ad esempio, Windows Communication Foundation applicazioni (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, l' [ \<elemento > ClaimsAuthorizationManager](claimsauthorizationmanager.md) (e i relativi elementi figlio, se presenti) della configurazione di identità a cui fa riferimento `<federationConfiguration>` l'elemento sono le uniche impostazioni. applicato. Tutti gli altri vengono ignorati.  
  
 Indipendentemente dallo scenario, il runtime carica la configurazione della federazione predefinita. Il comportamento è definito nel modo seguente:  
  
1. Se non è presente `<federationConfiguration>` alcun elemento, il runtime crea una configurazione di Federazione e la popola con i valori predefiniti. Questa configurazione di federazione predefinita fa riferimento alla configurazione predefinita dell'identità.  
  
2. Se è presente `<federationConfiguration>` un singolo elemento, è la configurazione della federazione predefinita, indipendentemente dal fatto che sia denominato o senza nome. Se viene `identityConfiguration` specificato il relativo attributo, viene fatto riferimento alla configurazione di identità denominata. in caso contrario, viene fatto riferimento alla configurazione di identità predefinita.  
  
3. Se è presente un `<federationConfiguration>` elemento senza nome, è la configurazione della federazione predefinita. Se viene `identityConfiguration` specificato il relativo attributo, viene fatto riferimento alla configurazione di identità denominata. in caso contrario, viene fatto riferimento alla configurazione di identità predefinita.  
  
4. Se sono presenti `<federationConfiguration>` più elementi denominati e non è `<federationConfiguration>` presente alcun elemento senza nome, viene generata un'eccezione.  
  
 In genere, viene definita `<federationConfiguration>` una sola sezione. Questa sezione è la configurazione della federazione predefinita. È possibile specificare più elementi denominati `<federationConfiguration>` in modo univoco. in questo caso, tuttavia, se si desidera caricare una configurazione di Federazione diversa da quella senza nome, è necessario fornire un gestore per. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>e impostare la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> proprietà all'interno del gestore su un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto inizializzato con i valori dell' `<federationConfiguration>` elemento appropriato nel file di configurazione.  
  
 L' `<federationConfiguration>` elemento è rappresentato <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> dalla classe. L'oggetto di configurazione stesso è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> classe. Una singola <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> istanza viene impostata <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> sulla proprietà e fornisce la configurazione federata per l'applicazione.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene `<federationConfiguration>` illustrato un elemento che specifica le impostazioni per WSFAM e specifica che il gestore di cookie predefinito (un' <xref:System.IdentityModel.Services.ChunkedCookieHandler> istanza della classe) verrà utilizzato da Sam.  
  
> [!WARNING]
> In questo esempio non sono necessari né il gestore di cookie né WSFAM per usare HTTPS. Questo è dovuto al `requireHttps` fatto `<wsFederation>` `requireSsl` chel'`false`attributo nell'elemento e l'attributo in sono.`<cookieHandlerElement>` Queste impostazioni non sono consigliate per la maggior parte degli ambienti di produzione perché possono presentare un rischio per la sicurezza.  
  
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
- [\<identityConfiguration>](identityconfiguration.md)
