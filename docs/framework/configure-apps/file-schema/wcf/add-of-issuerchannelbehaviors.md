---
title: <add> di <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398325"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="1e0d1-102">\<add> di \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="1e0d1-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="1e0d1-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="1e0d1-104">Se un qualsiasi comportamento dell'endpoint contiene un [\<clientCredentials>](clientcredentials.md) elemento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="1e0d1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e0d1-105">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1e0d1-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1e0d1-106">Attributes and Elements</span></span>

<span data-ttu-id="1e0d1-107">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-107">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="1e0d1-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="1e0d1-108">Attributes</span></span>

|<span data-ttu-id="1e0d1-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="1e0d1-109">Attribute</span></span>|<span data-ttu-id="1e0d1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e0d1-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="1e0d1-111">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="1e0d1-111">issuerAddress</span></span>|<span data-ttu-id="1e0d1-112">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-112">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="1e0d1-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="1e0d1-113">behaviorConfiguration</span></span>|<span data-ttu-id="1e0d1-114">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-114">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1e0d1-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1e0d1-115">Child Elements</span></span>

<span data-ttu-id="1e0d1-116">No.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1e0d1-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1e0d1-117">Parent Elements</span></span>

|<span data-ttu-id="1e0d1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e0d1-118">Element</span></span>|<span data-ttu-id="1e0d1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e0d1-119">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="1e0d1-120">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-120">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1e0d1-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="1e0d1-121">Remarks</span></span>

<span data-ttu-id="1e0d1-122">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-122">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="1e0d1-123">`behaviorConfiguration`punta a un comportamento dell'endpoint utilizzato dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token emessi dai servizi token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1e0d1-123">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e0d1-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1e0d1-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="1e0d1-125">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="1e0d1-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1e0d1-126">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e0d1-126">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1e0d1-127">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="1e0d1-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1e0d1-128">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="1e0d1-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1e0d1-129">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="1e0d1-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="1e0d1-130">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="1e0d1-130">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="1e0d1-131">Procedura: configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="1e0d1-131">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="1e0d1-132">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="1e0d1-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
