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
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="2dcc3-102">\<aggiungere > di \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2dcc3-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="2dcc3-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="2dcc3-104">Se un comportamento dell'endpoint contiene [ \<](clientcredentials.md) un elemento ClientCredentials >, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="2dcc3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2dcc3-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="2dcc3-106">\<comportamenti > </span><span class="sxs-lookup"><span data-stu-id="2dcc3-106">\<behaviors></span></span>\
<span data-ttu-id="2dcc3-107">comportamento della \<sezione endpointBehaviors > </span><span class="sxs-lookup"><span data-stu-id="2dcc3-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="2dcc3-108">\<clientCredentials > </span><span class="sxs-lookup"><span data-stu-id="2dcc3-108">\<clientCredentials></span></span>\
<span data-ttu-id="2dcc3-109">\<issuedToken > </span><span class="sxs-lookup"><span data-stu-id="2dcc3-109">\<issuedToken></span></span>\
<span data-ttu-id="2dcc3-110">\<Elemento > issuerChannelBehaviors </span><span class="sxs-lookup"><span data-stu-id="2dcc3-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="2dcc3-111">\<add></span><span class="sxs-lookup"><span data-stu-id="2dcc3-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="2dcc3-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2dcc3-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2dcc3-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2dcc3-113">Attributes and Elements</span></span>

<span data-ttu-id="2dcc3-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="2dcc3-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="2dcc3-115">Attributes</span></span>

|<span data-ttu-id="2dcc3-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="2dcc3-116">Attribute</span></span>|<span data-ttu-id="2dcc3-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2dcc3-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2dcc3-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="2dcc3-118">issuerAddress</span></span>|<span data-ttu-id="2dcc3-119">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="2dcc3-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="2dcc3-120">behaviorConfiguration</span></span>|<span data-ttu-id="2dcc3-121">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2dcc3-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2dcc3-122">Child Elements</span></span>

<span data-ttu-id="2dcc3-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2dcc3-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2dcc3-124">Parent Elements</span></span>

|<span data-ttu-id="2dcc3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2dcc3-125">Element</span></span>|<span data-ttu-id="2dcc3-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2dcc3-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2dcc3-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="2dcc3-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="2dcc3-128">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2dcc3-129">Note</span><span class="sxs-lookup"><span data-stu-id="2dcc3-129">Remarks</span></span>

<span data-ttu-id="2dcc3-130">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="2dcc3-131">`behaviorConfiguration`punta a un comportamento dell'endpoint utilizzato dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token emessi dai servizi token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2dcc3-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dcc3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dcc3-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="2dcc3-133">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="2dcc3-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="2dcc3-134">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2dcc3-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2dcc3-135">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="2dcc3-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2dcc3-136">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="2dcc3-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2dcc3-137">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="2dcc3-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2dcc3-138">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="2dcc3-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="2dcc3-139">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="2dcc3-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="2dcc3-140">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="2dcc3-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="2dcc3-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="2dcc3-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
