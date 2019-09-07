---
title: <add> di <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398325"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="3226f-102">\<aggiungere > di \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3226f-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="3226f-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="3226f-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="3226f-104">Se un comportamento dell'endpoint contiene un [ \<elemento ClientCredentials >](clientcredentials.md) , verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3226f-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="3226f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3226f-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3226f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3226f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="3226f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="3226f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="3226f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedToken**](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="3226f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuerChannelBehaviors**](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="3226f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="3226f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="3226f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="3226f-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3226f-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3226f-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3226f-115">Attributes and Elements</span></span>

<span data-ttu-id="3226f-116">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3226f-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="3226f-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="3226f-117">Attributes</span></span>

|<span data-ttu-id="3226f-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="3226f-118">Attribute</span></span>|<span data-ttu-id="3226f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3226f-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3226f-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="3226f-120">issuerAddress</span></span>|<span data-ttu-id="3226f-121">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="3226f-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="3226f-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3226f-122">behaviorConfiguration</span></span>|<span data-ttu-id="3226f-123">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3226f-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3226f-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3226f-124">Child Elements</span></span>

<span data-ttu-id="3226f-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3226f-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3226f-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3226f-126">Parent Elements</span></span>

|<span data-ttu-id="3226f-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="3226f-127">Element</span></span>|<span data-ttu-id="3226f-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3226f-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3226f-129">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3226f-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="3226f-130">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="3226f-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3226f-131">Note</span><span class="sxs-lookup"><span data-stu-id="3226f-131">Remarks</span></span>

<span data-ttu-id="3226f-132">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="3226f-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="3226f-133">`behaviorConfiguration`punta a un comportamento dell'endpoint utilizzato dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token emessi dai servizi token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3226f-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="3226f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3226f-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="3226f-135">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="3226f-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3226f-136">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3226f-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3226f-137">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="3226f-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3226f-138">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="3226f-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3226f-139">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="3226f-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="3226f-140">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="3226f-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3226f-141">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="3226f-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="3226f-142">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="3226f-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3226f-143">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3226f-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
