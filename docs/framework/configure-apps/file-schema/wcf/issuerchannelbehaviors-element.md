---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 3386a287d577681b67bd3ad54a75b0276e29da1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357248"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="ee5ea-102">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="ee5ea-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="ee5ea-103">Contiene una raccolta di comportamenti dell'endpoint client Windows Communication Foundation (WCF) (definita nella configurazione) da utilizzare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="ee5ea-104">I comportamenti definiti non possono includere [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

<span data-ttu-id="ee5ea-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="ee5ea-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="ee5ea-106">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="ee5ea-106">\<behaviors>\\</span></span>
<span data-ttu-id="ee5ea-107">section\ endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="ee5ea-107">endpointBehaviors section\\</span></span>
<span data-ttu-id="ee5ea-108">\<behavior>\\</span><span class="sxs-lookup"><span data-stu-id="ee5ea-108">\<behavior>\\</span></span>
<span data-ttu-id="ee5ea-109">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="ee5ea-109">\<clientCredentials>\\</span></span>
<span data-ttu-id="ee5ea-110">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="ee5ea-110">\<issuedToken>\\</span></span>
<span data-ttu-id="ee5ea-111">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="ee5ea-111">\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="ee5ea-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee5ea-112">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee5ea-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ee5ea-113">Attributes and Elements</span></span>

<span data-ttu-id="ee5ea-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ee5ea-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="ee5ea-115">Attributes</span></span>

<span data-ttu-id="ee5ea-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-116">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ee5ea-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ee5ea-117">Child Elements</span></span>

|<span data-ttu-id="ee5ea-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee5ea-118">Element</span></span>|<span data-ttu-id="ee5ea-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee5ea-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee5ea-120">\<add></span><span class="sxs-lookup"><span data-stu-id="ee5ea-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="ee5ea-121">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-121">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ee5ea-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ee5ea-122">Parent Elements</span></span>

|<span data-ttu-id="ee5ea-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee5ea-123">Element</span></span>|<span data-ttu-id="ee5ea-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee5ea-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ee5ea-125">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="ee5ea-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="ee5ea-126">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-126">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ee5ea-127">Note</span><span class="sxs-lookup"><span data-stu-id="ee5ea-127">Remarks</span></span>

<span data-ttu-id="ee5ea-128">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="ee5ea-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="ee5ea-129">Ad esempio, se un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) elemento di comportamento deve essere incluso.</span><span class="sxs-lookup"><span data-stu-id="ee5ea-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee5ea-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee5ea-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="ee5ea-131">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="ee5ea-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ee5ea-132">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee5ea-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ee5ea-133">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="ee5ea-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ee5ea-134">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="ee5ea-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ee5ea-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="ee5ea-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="ee5ea-136">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="ee5ea-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ee5ea-137">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="ee5ea-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="ee5ea-138">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="ee5ea-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
