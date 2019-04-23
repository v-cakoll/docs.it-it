---
title: <issuer>
ms.date: 03/30/2017
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
ms.openlocfilehash: 37d935287fa7dfba640c39071295fd660f4db7c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160823"
---
# <a name="issuer"></a>\<issuer>
Specifica il servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<wsFederationHttpBinding>  
\<binding>  
\<security>  
\<messaggio >  
\<issuer>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuer address="Uri">
  <headers>
    <add name="String"
         namespace="String" />
  </headers>
  <identity>
    <certificate encodedValue="String" />
    <certificateReference findValue="String"
                          isChainIncluded="Boolean"
                          storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                          storeLocation="LocalMachine/CurrentUser"
                          x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
    <dns value="String" />
    <rsa value="String" />
    <servicePrincipalName value="String" />
    <usePrincipalName value="String" />
  </identity>
</issuer>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|indirizzo|Stringa obbligatoria. URL del servizio STS.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Raccolta delle intestazioni di indirizzi per gli endpoint che il generatore può creare.|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Quando si usa un token emesso, specifica le impostazioni che consentono al client di autenticare il server.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<messaggio >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|Definisce le impostazioni per la sicurezza a livello di messaggio per il [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elemento.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Funzionalità di sicurezza con associazioni personalizzate](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
