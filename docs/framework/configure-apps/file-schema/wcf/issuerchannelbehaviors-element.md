---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7cbd50daa82b0ca937a1bba93786545898b03c8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58890475"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="9dc40-102">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="9dc40-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="9dc40-103">Contiene una raccolta di comportamenti dell'endpoint client Windows Communication Foundation (WCF) (definita nella configurazione) da utilizzare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="9dc40-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="9dc40-104">I comportamenti definiti non possono includere [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="9dc40-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="9dc40-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dc40-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9dc40-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9dc40-106">Attributes and Elements</span></span>

<span data-ttu-id="9dc40-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9dc40-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9dc40-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="9dc40-108">Attributes</span></span>

<span data-ttu-id="9dc40-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9dc40-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9dc40-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9dc40-110">Child Elements</span></span>

|<span data-ttu-id="9dc40-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9dc40-111">Element</span></span>|<span data-ttu-id="9dc40-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dc40-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9dc40-113">\<add></span><span class="sxs-lookup"><span data-stu-id="9dc40-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="9dc40-114">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="9dc40-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9dc40-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9dc40-115">Parent Elements</span></span>

|<span data-ttu-id="9dc40-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9dc40-116">Element</span></span>|<span data-ttu-id="9dc40-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dc40-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9dc40-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="9dc40-118">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="9dc40-119">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="9dc40-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9dc40-120">Note</span><span class="sxs-lookup"><span data-stu-id="9dc40-120">Remarks</span></span>

<span data-ttu-id="9dc40-121">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="9dc40-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="9dc40-122">Ad esempio, se un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) elemento di comportamento deve essere incluso.</span><span class="sxs-lookup"><span data-stu-id="9dc40-122">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="9dc40-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dc40-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="9dc40-124">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="9dc40-124">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9dc40-125">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9dc40-125">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9dc40-126">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="9dc40-126">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="9dc40-127">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9dc40-127">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9dc40-128">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="9dc40-128">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="9dc40-129">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="9dc40-129">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="9dc40-130">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="9dc40-130">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="9dc40-131">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="9dc40-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
