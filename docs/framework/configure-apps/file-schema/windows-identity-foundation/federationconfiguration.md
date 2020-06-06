---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152736"
---
# \<federationConfiguration>
Configura <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) quando si utilizza l'autenticazione federata tramite il protocollo WS-Federation. Configura <xref:System.Security.Claims.ClaimsAuthorizationManager> quando si utilizza la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe o per fornire il controllo degli accessi in base alle attestazioni.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**  
  
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
|name|Nome di questo elemento di configurazione della federazione. Questo attributo fornisce principalmente un punto di estendibilità per i protocolli futuri. Facoltativa.|  
|identityConfigurationName|Nome della sezione di configurazione dell'identità come specificato in un [\<identityConfiguration>](identityconfiguration.md) elemento da usare. Se questo attributo non viene specificato, viene utilizzata la sezione di configurazione predefinita dell'identità. Facoltativa.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura il gestore di cookie usato da SAM. Facoltativa.|  
|[\<serviceCertificate>](servicecertificate.md)|Configura il certificato usato per crittografare e decrittografare i token. Facoltativa.|  
|[\<wsFederation>](wsfederation.md)|Configura il modulo di autenticazione WS-Federation (WSFAM). Facoltativa.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.|  
  
## <a name="remarks"></a>Commenti  
 L' \<federationConfiguration> elemento fornisce le impostazioni in due scenari diversi:  
  
- Quando si usa WS-Federation in un'applicazione Web passiva, l'elemento contiene le impostazioni che configurano <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam). Fa anche riferimento alla configurazione dell'identità da usare per configurare i gestori e i certificati dei token di sicurezza e i componenti come gestione autorizzazioni delle attestazioni e il gestore di autenticazione delle attestazioni.  
  
- Quando si usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe o per fornire il controllo degli accessi in base alle attestazioni nel codice, l'elemento fa riferimento alla configurazione di identità che configura il gestore delle autorizzazioni delle attestazioni e i criteri usati per prendere decisioni di autorizzazione. Questo vale anche negli scenari che non sono scenari Web passivi; ad esempio, Windows Communication Foundation applicazioni (WCF) o un'applicazione che non è basata sul Web. Se l'applicazione non è un'applicazione Web passiva, l' [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) elemento (e i relativi elementi figlio, se presenti) della configurazione di identità a cui fa riferimento l' `<federationConfiguration>` elemento sono le uniche impostazioni applicate. Tutti gli altri vengono ignorati.  
  
 Indipendentemente dallo scenario, il runtime carica la configurazione della federazione predefinita. Il comportamento è definito nel modo seguente:  
  
1. Se non è `<federationConfiguration>` presente alcun elemento, il runtime crea una configurazione di Federazione e la popola con i valori predefiniti. Questa configurazione di federazione predefinita fa riferimento alla configurazione predefinita dell'identità.  
  
2. Se `<federationConfiguration>` è presente un singolo elemento, è la configurazione della federazione predefinita, indipendentemente dal fatto che sia denominato o senza nome. Se `identityConfiguration` viene specificato il relativo attributo, viene fatto riferimento alla configurazione di identità denominata. in caso contrario, viene fatto riferimento alla configurazione di identità predefinita.  
  
3. Se `<federationConfiguration>` è presente un elemento senza nome, è la configurazione della federazione predefinita. Se `identityConfiguration` viene specificato il relativo attributo, viene fatto riferimento alla configurazione di identità denominata. in caso contrario, viene fatto riferimento alla configurazione di identità predefinita.  
  
4. Se sono presenti più elementi denominati `<federationConfiguration>` e non `<federationConfiguration>` è presente alcun elemento senza nome, viene generata un'eccezione.  
  
 In genere, `<federationConfiguration>` viene definita una sola sezione. Questa sezione è la configurazione della federazione predefinita. È possibile specificare più elementi denominati in modo univoco. `<federationConfiguration>` in questo caso, tuttavia, se si desidera caricare una configurazione di Federazione diversa da quella senza nome, è necessario fornire un gestore per. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>e impostare la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> proprietà all'interno del gestore su un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> oggetto inizializzato con i valori dell' `<federationConfiguration>` elemento appropriato nel file di configurazione.  
  
 L' `<federationConfiguration>` elemento è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> classe. L'oggetto di configurazione stesso è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> classe. Una singola <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> istanza viene impostata sulla <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> proprietà e fornisce la configurazione federata per l'applicazione.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato un `<federationConfiguration>` elemento che specifica le impostazioni per WSFAM e specifica che il gestore di cookie predefinito (un'istanza della <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe) verrà utilizzato da Sam.  
  
> [!WARNING]
> In questo esempio non sono necessari né il gestore di cookie né WSFAM per usare HTTPS. Questo è dovuto al fatto `requireHttps` che l'attributo nell' `<wsFederation>` elemento e l' `requireSsl` attributo in `<cookieHandlerElement>` sono `false` . Queste impostazioni non sono consigliate per la maggior parte degli ambienti di produzione perché possono presentare un rischio per la sicurezza.  
  
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
