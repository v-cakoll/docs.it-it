---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: bef061c5c982fb0e740f889336a3b334bc19225e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943664"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.  
  
 \<system.identityModel.services>  
  
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
 Nessuna  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene le impostazioni che configurano i <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> moduli HTTP (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> e (Sam).|  
  
### <a name="parent-elements"></a>Elementi padre  
 Nessuna  
  
## <a name="remarks"></a>Note  
 Aggiungere una `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per specificare le impostazioni per Sam e WSFAM.  
  
> [!IMPORTANT]
> Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, il<xref:System.Security.Claims.ClaimsAuthorizationManager>gestore delle autorizzazioni delle attestazioni () e il criterio usato per prendere `<identityConfiguration>` decisioni di autorizzazione vengono configurati tramite un elemento a cui viene fatto riferimento in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione. Per ulteriori informazioni, vedere la **sezione Osservazioni** sotto l' [ \<elemento federationConfiguration >](federationconfiguration.md) .  
  
 La `<system.identityModel.services>` sezione è rappresentata <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> dalla classe. La raccolta di elementi `<federationConfiguration>` figlio configurati nella sezione è rappresentata <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> dalla classe.  
  
## <a name="example"></a>Esempio  
 Nel codice XML seguente viene illustrato come aggiungere `<system.identityModel.services>` una sezione a un file di configurazione. È necessario innanzitutto aggiungere dichiarazioni di sezione per la `<system.identityModel.services>` sezione e le `<system.identityModel>` sezioni. Quando si aggiunge una `<system.identityModel.services>` sezione, è inoltre necessario aggiungere una dichiarazione per la `<system.identityModel>` sezione per assicurarsi che, se necessario `<identityConfiguration>` , una sezione predefinita possa essere creata dal runtime. Una volta aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata nell' `<system.identityModel.services>` elemento.  
  
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
