---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 2c0e0d8d041565edd25c4b2c2802bfd2a589b4f7
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397907"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="fc285-102">\<Elemento > issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="fc285-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="fc285-103">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) (definiti nella configurazione) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="fc285-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="fc285-104">I comportamenti definiti non possono includere [ \<gli elementi ClientCredentials >](clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="fc285-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="fc285-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc285-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fc285-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="fc285-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="fc285-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="fc285-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="fc285-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedToken**](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="fc285-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="fc285-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerChannelBehaviors**</span><span class="sxs-lookup"><span data-stu-id="fc285-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerChannelBehaviors>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="fc285-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc285-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fc285-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fc285-114">Attributes and Elements</span></span>

<span data-ttu-id="fc285-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fc285-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fc285-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="fc285-116">Attributes</span></span>

<span data-ttu-id="fc285-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fc285-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fc285-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fc285-118">Child Elements</span></span>

|<span data-ttu-id="fc285-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc285-119">Element</span></span>|<span data-ttu-id="fc285-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc285-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fc285-121">\<add></span><span class="sxs-lookup"><span data-stu-id="fc285-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="fc285-122">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="fc285-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="fc285-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fc285-123">Parent Elements</span></span>

|<span data-ttu-id="fc285-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc285-124">Element</span></span>|<span data-ttu-id="fc285-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc285-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fc285-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="fc285-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="fc285-127">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="fc285-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fc285-128">Note</span><span class="sxs-lookup"><span data-stu-id="fc285-128">Remarks</span></span>

<span data-ttu-id="fc285-129">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="fc285-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="fc285-130">Ad esempio, se è [ \<](datacontractserializer-element.md) necessario includere un elemento del comportamento > DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="fc285-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc285-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc285-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="fc285-132">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="fc285-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fc285-133">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="fc285-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fc285-134">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="fc285-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fc285-135">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="fc285-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fc285-136">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="fc285-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="fc285-137">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="fc285-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="fc285-138">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="fc285-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="fc285-139">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="fc285-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
