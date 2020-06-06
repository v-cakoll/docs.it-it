---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152504"
---
# \<system.identityModel.services>
Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
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
|[\<federationConfiguration>](federationconfiguration.md)|Contiene le impostazioni che configurano i <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> moduli HTTP (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam).|  
  
### <a name="parent-elements"></a>Elementi padre  
 nessuno  
  
## <a name="remarks"></a>Osservazioni  
 Aggiungere una `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per specificare le impostazioni per Sam e WSFAM.  
  
> [!IMPORTANT]
> Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, il gestore delle autorizzazioni delle attestazioni ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) e i criteri usati per prendere decisioni di autorizzazione vengono configurati tramite un `<identityConfiguration>` elemento a cui viene fatto riferimento in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione. Per ulteriori informazioni, vedere la **sezione Osservazioni** sotto l' [\<federationConfiguration>](federationconfiguration.md) elemento.  
  
 La `<system.identityModel.services>` sezione è rappresentata dalla <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> classe. La raccolta di `<federationConfiguration>` elementi figlio configurati nella sezione è rappresentata dalla <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> classe.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato come aggiungere una `<system.identityModel.services>` sezione a un file di configurazione. È necessario innanzitutto aggiungere dichiarazioni di sezione per la `<system.identityModel.services>` sezione e le `<system.identityModel>` sezioni. Quando si aggiunge una `<system.identityModel.services>` sezione, è inoltre necessario aggiungere una dichiarazione per la `<system.identityModel>` sezione per assicurarsi che, `<identityConfiguration>` se necessario, una sezione predefinita possa essere creata dal runtime. Una volta aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata nell' `<system.identityModel.services>` elemento.  
  
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
