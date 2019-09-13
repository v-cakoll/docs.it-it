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
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70893149"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="c57e1-102">\<Elemento > issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="c57e1-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="c57e1-103">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) (definiti nella configurazione) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="c57e1-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="c57e1-104">I comportamenti definiti non possono includere [ \<gli elementi ClientCredentials >](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="c57e1-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="c57e1-105">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-105">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="c57e1-106">&nbsp;&nbsp;[\<> System. serviceModel](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-106">&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)</span></span>\
<span data-ttu-id="c57e1-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<comportamenti >](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-107">&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)</span></span>\
<span data-ttu-id="c57e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> endpointBehaviors](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)</span></span>\
<span data-ttu-id="c57e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<comportamento >](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="c57e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> clientCredentials](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)</span></span>\
<span data-ttu-id="c57e1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<> issuedToken](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="c57e1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)</span></span>\
<span data-ttu-id="c57e1-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<> issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="c57e1-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="c57e1-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c57e1-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c57e1-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c57e1-114">Attributes and elements</span></span>

<span data-ttu-id="c57e1-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c57e1-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c57e1-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="c57e1-116">Attributes</span></span>

<span data-ttu-id="c57e1-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c57e1-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c57e1-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c57e1-118">Child elements</span></span>

|<span data-ttu-id="c57e1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c57e1-119">Element</span></span>|<span data-ttu-id="c57e1-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c57e1-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c57e1-121">\<add></span><span class="sxs-lookup"><span data-stu-id="c57e1-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="c57e1-122">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="c57e1-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c57e1-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c57e1-123">Parent elements</span></span>

|<span data-ttu-id="c57e1-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c57e1-124">Element</span></span>|<span data-ttu-id="c57e1-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="c57e1-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c57e1-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="c57e1-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="c57e1-127">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="c57e1-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c57e1-128">Note</span><span class="sxs-lookup"><span data-stu-id="c57e1-128">Remarks</span></span>

<span data-ttu-id="c57e1-129">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="c57e1-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="c57e1-130">Ad esempio, se è [ \<](datacontractserializer-element.md) necessario includere un elemento del comportamento > DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="c57e1-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="c57e1-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c57e1-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="c57e1-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="c57e1-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c57e1-133">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c57e1-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c57e1-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c57e1-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="c57e1-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="c57e1-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c57e1-136">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="c57e1-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c57e1-137">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="c57e1-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="c57e1-138">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="c57e1-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="c57e1-139">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="c57e1-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
