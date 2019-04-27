---
title: <add> di <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673615"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="c03de-102">\<aggiungere > di \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c03de-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="c03de-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="c03de-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="c03de-104">Se qualsiasi comportamento dell'endpoint contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c03de-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="c03de-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="c03de-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="c03de-106">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="c03de-106">\<behaviors>\\</span></span>
<span data-ttu-id="c03de-107">sezione endpointBehaviors \<comportamento > \\</span><span class="sxs-lookup"><span data-stu-id="c03de-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="c03de-108">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="c03de-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="c03de-109">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="c03de-109">\<issuedToken>\\</span></span>
<span data-ttu-id="c03de-110">\<issuerChannelBehaviors > Element\\</span><span class="sxs-lookup"><span data-stu-id="c03de-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="c03de-111">\<add></span><span class="sxs-lookup"><span data-stu-id="c03de-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="c03de-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c03de-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c03de-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c03de-113">Attributes and Elements</span></span>

<span data-ttu-id="c03de-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c03de-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="c03de-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="c03de-115">Attributes</span></span>

|<span data-ttu-id="c03de-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="c03de-116">Attribute</span></span>|<span data-ttu-id="c03de-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c03de-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="c03de-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="c03de-118">issuerAddress</span></span>|<span data-ttu-id="c03de-119">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="c03de-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="c03de-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c03de-120">behaviorConfiguration</span></span>|<span data-ttu-id="c03de-121">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c03de-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c03de-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c03de-122">Child Elements</span></span>

<span data-ttu-id="c03de-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c03de-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c03de-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c03de-124">Parent Elements</span></span>

|<span data-ttu-id="c03de-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="c03de-125">Element</span></span>|<span data-ttu-id="c03de-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c03de-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c03de-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="c03de-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="c03de-128">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="c03de-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c03de-129">Note</span><span class="sxs-lookup"><span data-stu-id="c03de-129">Remarks</span></span>

<span data-ttu-id="c03de-130">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="c03de-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="c03de-131">`behaviorConfiguration` punta a un comportamento dell'endpoint utilizzati dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token rilasciati dal servizio Token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c03de-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="c03de-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c03de-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="c03de-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c03de-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c03de-134">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c03de-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c03de-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c03de-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c03de-136">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="c03de-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c03de-137">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="c03de-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="c03de-138">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="c03de-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="c03de-139">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="c03de-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="c03de-140">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c03de-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c03de-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="c03de-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
