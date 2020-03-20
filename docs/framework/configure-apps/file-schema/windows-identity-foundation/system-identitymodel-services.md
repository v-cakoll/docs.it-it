---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152504"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.  
  
[**\<>di configurazione**](../configuration-element.md)\
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
  
### <a name="attributes"></a>Attributes  
 nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<>di configurazione](federationconfiguration.md)|Contiene le impostazioni <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> che configurano i <xref:System.IdentityModel.Services.SessionAuthenticationModule> moduli HTTP (WSFAM) e SAM.|  
  
### <a name="parent-elements"></a>Elementi padre  
 nessuno  
  
## <a name="remarks"></a>Osservazioni  
 Aggiungere `<system.identityModel.services>` una sezione al file di configurazione dell'applicazione per fornire le impostazioni per SAM e WSFAM.  
  
> [!IMPORTANT]
> Quando si <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> utilizza <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la classe o per fornire il controllo di<xref:System.Security.Claims.ClaimsAuthorizationManager>accesso basato sulle attestazioni nel codice, `<identityConfiguration>` il gestore di autorizzazioni delle `<federationConfiguration>` attestazioni ( ) e i criteri utilizzati per prendere decisioni di autorizzazione vengono configurati tramite un elemento a cui viene fatto riferimento in modo implicito o esplicito da un elemento di questa sezione. Per altre informazioni, vedere le **osservazioni** nell'elemento [ \<federationConfiguration>.](federationconfiguration.md)  
  
 La `<system.identityModel.services>` sezione è <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> rappresentata dalla classe . La raccolta `<federationConfiguration>` di elementi figlio configurati nella <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> sezione è rappresentata dalla classe .  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente `<system.identityModel.services>` viene illustrato come aggiungere una sezione a un file di configurazione. È innanzitutto necessario aggiungere le `<system.identityModel.services>` dichiarazioni `<system.identityModel>` di sezione per la sezione e le sezioni. Quando si aggiunge `<system.identityModel.services>` una sezione, è inoltre `<system.identityModel>` necessario aggiungere una `<identityConfiguration>` dichiarazione per la sezione per garantire che una sezione predefinita possa essere creata dal runtime, se necessario. Dopo aver aggiunto le dichiarazioni di sezione, è `<system.identityModel.services>` possibile configurare le impostazioni di autenticazione federata sotto l'elemento.  
  
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
