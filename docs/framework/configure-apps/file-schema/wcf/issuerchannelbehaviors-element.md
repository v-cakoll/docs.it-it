---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929934"
---
# <a name="issuerchannelbehaviors-element"></a>\<Elemento > issuerChannelBehaviors

Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) (definiti nella configurazione) da utilizzare durante la comunicazione con i servizi del token del servizio specificati. I comportamenti definiti non possono includere [ \<](clientcredentials.md) gli elementi ClientCredentials >.

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

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

Nessuno.

### <a name="child-elements"></a>Elementi figlio

|Elemento|DESCRIZIONE|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|Aggiunge un comportamento alla raccolta.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|Specifica un token personalizzato usato per autenticare un client presso un servizio.|

## <a name="remarks"></a>Note

Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`, Ad esempio, se è [ \<](datacontractserializer-element.md) necessario includere un elemento del comportamento > DataContractSerializer.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Identità del servizio e autenticazione](../../../wcf/feature-details/service-identity-and-authentication.md)
- [Comportamenti di sicurezza](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Protezione di client](../../../wcf/securing-clients.md)
- [Procedura: Creazione di un client federato](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedura: Configurare un'autorità emittente locale](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federazione e token rilasciati](../../../wcf/feature-details/federation-and-issued-tokens.md)
