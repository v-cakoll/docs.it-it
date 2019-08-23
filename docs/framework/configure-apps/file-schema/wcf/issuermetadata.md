---
title: <issuerMetadata>
ms.date: 03/30/2017
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
ms.openlocfilehash: bf512c427637ca65a7271ec8300a373a38632108
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913513"
---
# <a name="issuermetadata"></a>\<issuerMetadata>
\<system.serviceModel>  
\<Binding >  
\<wsFederationHttpBinding>  
\<binding>  
\<security>  
\<> messaggi  
\<issuerMetadata>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<issuerMetadata address="String">
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
</issuerMetadata>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|Address|Attributo `string` obbligatorio.<br /><br /> Specifica l'indirizzo dell'endpoint. L'indirizzo deve essere un URI assoluto. Il valore predefinito è una stringa vuota.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<intestazioni >](headers-element.md)|Raccolte di intestazioni di indirizzo.|  
|[\<identity>](identity.md)|Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<> messaggi](message-element-of-wsfederationhttpbinding.md)|Definisce le impostazioni per la sicurezza a livello di messaggio per l' [ \<elemento wsFederationHttpBinding >](wsfederationhttpbinding.md) .|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Funzionalità di sicurezza con associazioni personalizzate](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
