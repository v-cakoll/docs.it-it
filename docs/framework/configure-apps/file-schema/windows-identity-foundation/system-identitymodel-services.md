---
title: '&lt;IdentityModel&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757047"
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;IdentityModel&gt;
Sezione di configurazione per l'autenticazione tramite il protocollo WS-Federation.  
  
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
 Nessuno  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene le impostazioni che configurano il <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) e <xref:System.IdentityModel.Services.SessionAuthenticationModule> moduli HTTP (SAM).|  
  
### <a name="parent-elements"></a>Elementi padre  
 Nessuno  
  
## <a name="remarks"></a>Note  
 Aggiungere un `<system.identityModel.services>` sezione al file di configurazione dell'applicazione per fornire le impostazioni per le WSFAM SAM.  
  
> [!IMPORTANT]
>  Quando si utilizza il <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, la gestione di autorizzazione delle attestazioni (<xref:System.Security.Claims.ClaimsAuthorizationManager>) e criteri che consentono di prendere decisioni di autorizzazione vengono configurati mediante un `<identityConfiguration>` elemento a cui fa riferimento in modo implicito o esplicito da un `<federationConfiguration>` elemento in questa sezione. Per ulteriori informazioni, vedere il **osservazioni** sotto il [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 Il `<system.identityModel.services>` sezione è rappresentata dalla <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> classe. La raccolta di figlio `<federationConfiguration>` elementi configurati nella sezione è rappresentato dalla <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> classe.  
  
## <a name="example"></a>Esempio  
 Il codice XML seguente viene illustrato come aggiungere un `<system.identityModel.services>` sezione in un file di configurazione. È innanzitutto necessario aggiungere le dichiarazioni della sezione per entrambi i `<system.identityModel.services>` sezione e `<system.identityModel>` sezioni. (Quando si aggiunge un `<system.identityModel.services>` sezione, è necessario aggiungere una dichiarazione per il `<system.identityModel>` sezione per garantire che un valore predefinito `<identityConfiguration>` sezione possa essere creata dal runtime se necessario.) Dopo che sono state aggiunte le dichiarazioni di sezione, è possibile configurare le impostazioni di autenticazione federata sotto il `<system.identityModel.services>` elemento.  
  
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
