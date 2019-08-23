---
title: <issuerChannelBehaviors> Elemento
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929934"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="39539-102">\<Elemento > issuerChannelBehaviors</span><span class="sxs-lookup"><span data-stu-id="39539-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="39539-103">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) (definiti nella configurazione) da utilizzare durante la comunicazione con i servizi del token del servizio specificati.</span><span class="sxs-lookup"><span data-stu-id="39539-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="39539-104">I comportamenti definiti non possono includere [ \<](clientcredentials.md) gli elementi ClientCredentials >.</span><span class="sxs-lookup"><span data-stu-id="39539-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="39539-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39539-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="39539-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="39539-106">Attributes and Elements</span></span>

<span data-ttu-id="39539-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="39539-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="39539-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="39539-108">Attributes</span></span>

<span data-ttu-id="39539-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="39539-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="39539-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="39539-110">Child Elements</span></span>

|<span data-ttu-id="39539-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="39539-111">Element</span></span>|<span data-ttu-id="39539-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="39539-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39539-113">\<add></span><span class="sxs-lookup"><span data-stu-id="39539-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="39539-114">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="39539-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="39539-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="39539-115">Parent Elements</span></span>

|<span data-ttu-id="39539-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="39539-116">Element</span></span>|<span data-ttu-id="39539-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39539-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39539-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="39539-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="39539-119">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="39539-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="39539-120">Note</span><span class="sxs-lookup"><span data-stu-id="39539-120">Remarks</span></span>

<span data-ttu-id="39539-121">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="39539-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="39539-122">Ad esempio, se è [ \<](datacontractserializer-element.md) necessario includere un elemento del comportamento > DataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="39539-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="39539-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39539-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="39539-124">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="39539-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="39539-125">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="39539-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="39539-126">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="39539-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="39539-127">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="39539-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="39539-128">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="39539-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="39539-129">Procedura: Creazione di un client federato</span><span class="sxs-lookup"><span data-stu-id="39539-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="39539-130">Procedura: Configurare un'autorità emittente locale</span><span class="sxs-lookup"><span data-stu-id="39539-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="39539-131">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="39539-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
