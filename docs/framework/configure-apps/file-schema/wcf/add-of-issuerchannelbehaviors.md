---
title: <add> di <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920118"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<aggiungere > di \<issuerChannelBehaviors >

Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.

> [!NOTE]
> Se un comportamento dell'endpoint contiene [ \<](clientcredentials.md) un elemento ClientCredentials >, verrà generata un'eccezione.

\<system.ServiceModel>\
\<comportamenti > \
comportamento della \<sezione endpointBehaviors > \
\<clientCredentials > \
\<issuedToken > \
\<Elemento > issuerChannelBehaviors \
\<add>

## <a name="syntax"></a>Sintassi

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|issuerAddress|URI dell'emittente del token di sicurezza con cui comunicare.|
|behaviorConfiguration|Nome di un comportamento di endpoint definito nello stesso file di configurazione.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.|

## <a name="remarks"></a>Note

`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare. `behaviorConfiguration`punta a un comportamento dell'endpoint utilizzato dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token emessi dai servizi token di sicurezza.

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
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
