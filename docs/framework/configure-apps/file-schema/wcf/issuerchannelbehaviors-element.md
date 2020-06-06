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
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="b116b-102">\<issuerChannelBehaviors> Elemento</span><span class="sxs-lookup"><span data-stu-id="b116b-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="b116b-103">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) (definiti nella configurazione) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="b116b-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="b116b-104">I comportamenti definiti non possono includere [\<clientCredentials>](clientcredentials.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="b116b-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a><span data-ttu-id="b116b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b116b-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b116b-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b116b-106">Attributes and elements</span></span>

<span data-ttu-id="b116b-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b116b-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b116b-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="b116b-108">Attributes</span></span>

<span data-ttu-id="b116b-109">No.</span><span class="sxs-lookup"><span data-stu-id="b116b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b116b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b116b-110">Child elements</span></span>

|<span data-ttu-id="b116b-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b116b-111">Element</span></span>|<span data-ttu-id="b116b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b116b-112">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="b116b-113">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="b116b-113">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b116b-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b116b-114">Parent elements</span></span>

|<span data-ttu-id="b116b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b116b-115">Element</span></span>|<span data-ttu-id="b116b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b116b-116">Description</span></span>|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="b116b-117">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="b116b-117">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b116b-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="b116b-118">Remarks</span></span>

<span data-ttu-id="b116b-119">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="b116b-119">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="b116b-120">Ad esempio, se [\<dataContractSerializer>](datacontractserializer-element.md) è necessario includere un elemento Behavior.</span><span class="sxs-lookup"><span data-stu-id="b116b-120">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="b116b-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="b116b-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="b116b-122">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="b116b-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b116b-123">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b116b-123">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b116b-124">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="b116b-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b116b-125">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="b116b-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b116b-126">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="b116b-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="b116b-127">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="b116b-127">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="b116b-128">Procedura: configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="b116b-128">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="b116b-129">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="b116b-129">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
