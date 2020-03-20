---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152736"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Configura (WSFAM) e <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) quando si utilizza l'autenticazione federata tramite il protocollo WS-Federation. Configura l'oggetto <xref:System.Security.Claims.ClaimsAuthorizationManager> <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> quando <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> si utilizza la classe o per fornire il controllo di accesso basato sulle attestazioni.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>di configurazione**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Nome di questo elemento di configurazione della federazione. Questo attributo fornisce principalmente un punto di estendibilità per i protocolli futuri. Facoltativa.|  
|identitàNomeConfigurazione|Nome della sezione di configurazione dell'identità come specificato in un [ \<](identityconfiguration.md) elemento identityConfiguration>da utilizzare. Se questo attributo non viene specificato, viene utilizzata la sezione di configurazione dell'identità predefinita. Facoltativa.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>cookieHandler](cookiehandler.md)|Configura il gestore di cookie utilizzato dal SAM. Facoltativa.|  
|[\<>serviceCertificate](servicecertificate.md)|Configura il certificato utilizzato per crittografare e decrittografare i token. Facoltativa.|  
|[\<>wsFederazione](wsfederation.md)|Configura il modulo di autenticazione WS-Federation (WSFAM). Facoltativa.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.|  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento> federationConfiguration fornisce le impostazioni in due scenari diversi:The \<federationConfiguration> element provides settings in two different scenarios:  
  
- Quando si utilizza WS-Federation in un'applicazione Web <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> passiva, l'elemento <xref:System.IdentityModel.Services.SessionAuthenticationModule> contiene le impostazioni che configurano (WSFAM) e (SAM). Fa inoltre riferimento alla configurazione dell'identità da utilizzare per configurare i gestori di token di sicurezza e i certificati e componenti come il gestore di autorizzazioni delle attestazioni e il gestore di autenticazione delle attestazioni.  
  
- Quando si <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la classe o per fornire il controllo di accesso basato sulle attestazioni nel codice, l'elemento fa riferimento alla configurazione dell'identità che configura il gestore di autorizzazioni delle attestazioni e i criteri usati per prendere decisioni di autorizzazione. Questo è vero, anche in scenari che non sono scenari Web passivi; ad esempio, applicazioni Windows Communication Foundation (WCF) o un'applicazione non basata sul Web. Se l'applicazione non è un'applicazione Web passiva, l'elemento `<federationConfiguration>` [ \<>claimsAuthorizationManager](claimsauthorizationmanager.md) (e i relativi elementi dei criteri figlio, se presenti) della configurazione dell'identità a cui fa riferimento l'elemento sono le uniche impostazioni applicate. Tutti gli altri vengono ignorati.  
  
 Indipendentemente dallo scenario, il runtime carica la configurazione di federazione predefinita. Il comportamento è definito come segue:  
  
1. Se non `<federationConfiguration>` è presente alcun elemento, il runtime crea una configurazione di federazione e la popola con i valori predefiniti. Questa configurazione di federazione predefinita farà riferimento alla configurazione dell'identità predefinita.  
  
2. Se è `<federationConfiguration>` presente un singolo elemento, è la configurazione di federazione predefinita indipendentemente dal fatto che sia denominato o senza nome. Se `identityConfiguration` viene specificato il relativo attributo, viene fatto riferimento alla configurazione dell'identità denominata; in caso contrario, viene fatto riferimento alla configurazione dell'identità predefinita.  
  
3. Se è `<federationConfiguration>` presente un elemento senza nome, è la configurazione di federazione predefinita. Se `identityConfiguration` viene specificato il relativo attributo, viene fatto riferimento alla configurazione dell'identità denominata; in caso contrario, viene fatto riferimento alla configurazione dell'identità predefinita.  
  
4. Se sono `<federationConfiguration>` presenti più elementi `<federationConfiguration>` denominati e non è presente alcun elemento senza nome, viene generata un'eccezione.  
  
 In genere, `<federationConfiguration>` viene definita una sola sezione. Questa sezione è la configurazione di federazione predefinita. È possibile specificare più `<federationConfiguration>` elementi con nome univoco; Tuttavia, in questo caso, se si desidera caricare una configurazione di federazione diversa da quella senza nome, è necessario fornire un gestore per il. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>evento e <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> impostare la proprietà <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> all'interno del gestore su un oggetto inizializzato con i valori dell'elemento appropriato `<federationConfiguration>` nel file di configurazione.  
  
 L'elemento `<federationConfiguration>` è <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> rappresentato dalla classe . L'oggetto di configurazione <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> stesso è rappresentato dalla classe . Una <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> singola istanza viene <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> impostata sulla proprietà e fornisce la configurazione federata per l'applicazione.  
  
## <a name="example"></a>Esempio  
 Nel codice XML `<federationConfiguration>` seguente viene illustrato un elemento che specifica le impostazioni per WSFAM e specifica che il gestore di cookie predefinito (un'istanza della <xref:System.IdentityModel.Services.ChunkedCookieHandler> classe) deve essere utilizzato dal SAM.  
  
> [!WARNING]
> In questo esempio, né il gestore di cookie né WSFAM sono tenuti a utilizzare HTTPS. Ciò è `requireHttps` dovuto `<wsFederation>` al fatto `requireSsl` che `<cookieHandlerElement>` l'attributo sull'elemento e l'attributo sull'oggetto sono `false`. Queste impostazioni non sono consigliate per la maggior parte degli ambienti di produzione in quanto potrebbero rappresentare un rischio per la sicurezza.  
  
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
- [\<>di identitàConfigurazione](identityconfiguration.md)
