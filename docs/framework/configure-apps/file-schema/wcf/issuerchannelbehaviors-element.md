---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70893149"
---
# <a name="issuerchannelbehaviors-element"></a>\<issuerChannelBehaviors> Elemento

Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) (definiti nella configurazione) da utilizzare durante la comunicazione con i servizi del token del servizio specificati. I comportamenti definiti non possono includere [\<clientCredentials>](clientcredentials.md) elementi.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a>Sintassi

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

No.

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|Aggiunge un comportamento alla raccolta.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|Specifica un token personalizzato usato per autenticare un client presso un servizio.|

## <a name="remarks"></a>Commenti

Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`, Ad esempio, se [\<dataContractSerializer>](datacontractserializer-element.md) è necessario includere un elemento Behavior.

## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Procedura: creare un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedura: configurare un emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federazione e token emessi](../../../wcf/feature-details/federation-and-issued-tokens.md)
