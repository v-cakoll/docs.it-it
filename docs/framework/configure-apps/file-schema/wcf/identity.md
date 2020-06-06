---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855145"
---
# \<identity>
L'elemento identity consente a uno sviluppatore di client di specificare in fase di progettazione l'identità prevista del servizio. Nel processo di handshake tra il client e il servizio, l'infrastruttura Windows Communication Foundation (WCF) garantirà che l'identità del servizio previsto corrisponda ai valori di questo elemento e possa quindi essere autenticata. Per altre informazioni, vedere [identità e autenticazione del servizio](../../../wcf/feature-details/service-identity-and-authentication.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|certificato|Specifica le impostazioni di un certificato X.509. L'elemento è di tipo <xref:System.ServiceModel.Configuration.CertificateElement>. Contiene un attributo stringa `encodedValue` che specifica il valore codificato da questo certificato.|  
|certificateReference|Specifica le impostazioni per la convalida del certificato X.509. L'elemento è di tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.|  
|dns|Specifica il DNS di un certificato X.509 usato per autenticare un servizio. Questo elemento contiene un attributo stringa `value` contenente l'identità effettiva.|  
|rsa|Specifica il valore del campo RSA di un certificato X.509 usato per autenticare un servizio presso un client. Questo elemento contiene un attributo stringa `value` contenente l'identità effettiva.|  
|servicePrincipalName|Specifica l'identità di un nome principale di servizio (SPN, Server Principal Name), ovvero il nome principale usato da un client per identificare in modo univoco un'istanza di un servizio. Questo elemento contiene un attributo stringa `value` contenente il nome principale effettivo. L'elemento è di tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.|  
|userPrincipalName|Specifica l'identità di un nome principale dell'utente (UPN, User Principal Name), ovvero il tipo di nome che un utente usa per accedere a una rete. Il nome dell'entità utente è costituito dal nome dell'oggetto utente utilizzato in Active Directory, seguito dal simbolo di chiocciola ( \@ ) e quindi, in genere, dal dominio Domain Name System padre. Ad esempio, Jeff nell'albero di dominio Fabrikam.com potrebbe avere il nome dell'entità utente [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .  Questo elemento contiene un attributo stringa `value` contenente il nome principale effettivo. L'elemento è di tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<custom>](custom.md)|Specifica un resolver peer personalizzato per un'associazione netPeerTcpBinding.|  
|[\<endpoint>](endpoint-element.md)|Configura gli endpoint di servizio.|  
|[\<endpoint>di\<client>](endpoint-of-client.md)|Configura gli endpoint del canale.|  
|[\<issuer>](issuer.md)|Specifica il servizio token di sicurezza del servizio federato.|  
|[\<issuerMetadata>](issuermetadata.md)|Specifica l'endpoint dei metadati del servizio token di sicurezza di un servizio federato.|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Definisce i parametri di un token emesso in un'associazione personalizzata.|  
|[\<localIssuer>](localissuer.md)|Specifica un servizio token di sicurezza locale.|  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Endpoint: indirizzi, associazioni e contratti](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
