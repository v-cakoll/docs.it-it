---
title: '&lt;IdentityModel&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: c7261d20ae2379ad33679cadecdef484f2afdecf
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47402617"
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;IdentityModel&gt;
Sezione di configurazione per l'autenticazione usando il protocollo WS-Federation.  
  
 \<IdentityModel >  
  
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
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che consentono di configurare il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e il <xref:System.IdentityModel.Services.SessionAuthenticationModule> moduli HTTP (SAM).|  
  
### <a name="parent-elements"></a>Elementi padre  
 nessuno  
  
## <a name="remarks"></a>Note  
 Aggiungere un `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per fornire le impostazioni per il SAM e WSFAM.  
  
> [!IMPORTANT]
>  Quando si usa il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, il gestore di autorizzazione delle attestazioni (<xref:System.Security.Claims.ClaimsAuthorizationManager>) e i criteri utilizzati per prendere decisioni di autorizzazione vengono configurate mediante un `<identityConfiguration>` elemento che fa in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione. Per altre informazioni, vedere la **osservazioni** sotto il [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 Il `<system.identityModel.services>` sezione è rappresentata dal <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> classe. La raccolta di figlio `<federationConfiguration>` rappresentato da configurati nella sezione elementi di <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> classe.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come aggiungere un `<system.identityModel.services>` sezione in un file di configurazione. È innanzitutto necessario aggiungere le dichiarazioni della sezione sia per il `<system.identityModel.services>` sezione e `<system.identityModel>` sezioni. (Quando si aggiunge un `<system.identityModel.services>` sezione, è necessario aggiungere anche una dichiarazione per il `<system.identityModel>` sezione per garantire che un valore predefinito `<identityConfiguration>` sezione possa essere creata dal runtime se necessario.) Dopo che sono state aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata sotto il `<system.identityModel.services>` elemento.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
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
  
</configuration>  
```
