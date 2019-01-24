---
title: Elemento &lt;issuerChannelBehaviors&gt;
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: b77d0ce79557dff4b5a243da4d24703ed45fde07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677108"
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="fac12-102">Elemento &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="fac12-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="fac12-103">Contiene una raccolta di comportamenti dell'endpoint client Windows Communication Foundation (WCF) (definita nella configurazione) da utilizzare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="fac12-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="fac12-104">I comportamenti definiti non possono includere [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="fac12-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="fac12-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fac12-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="fac12-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fac12-106">\<behaviors></span></span>  
<span data-ttu-id="fac12-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="fac12-107">endpointBehaviors section</span></span>  
<span data-ttu-id="fac12-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fac12-108">\<behavior></span></span>  
<span data-ttu-id="fac12-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="fac12-109">\<clientCredentials></span></span>  
<span data-ttu-id="fac12-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="fac12-110">\<issuedToken></span></span>  
<span data-ttu-id="fac12-111">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="fac12-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac12-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fac12-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>
  <add behaviorConfiguraton="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fac12-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fac12-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fac12-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fac12-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fac12-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="fac12-115">Attributes</span></span>  
 <span data-ttu-id="fac12-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fac12-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fac12-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fac12-117">Child Elements</span></span>  
  
|<span data-ttu-id="fac12-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fac12-118">Element</span></span>|<span data-ttu-id="fac12-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fac12-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fac12-120">\<add></span><span class="sxs-lookup"><span data-stu-id="fac12-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="fac12-121">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="fac12-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fac12-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fac12-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fac12-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="fac12-123">Element</span></span>|<span data-ttu-id="fac12-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fac12-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fac12-125">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="fac12-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="fac12-126">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="fac12-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fac12-127">Note</span><span class="sxs-lookup"><span data-stu-id="fac12-127">Remarks</span></span>  
 <span data-ttu-id="fac12-128">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="fac12-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="fac12-129">Ad esempio, se un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) elemento di comportamento deve essere incluso.</span><span class="sxs-lookup"><span data-stu-id="fac12-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac12-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac12-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="fac12-131">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="fac12-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fac12-132">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="fac12-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fac12-133">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="fac12-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fac12-134">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="fac12-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fac12-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="fac12-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="fac12-136">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="fac12-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="fac12-137">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="fac12-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="fac12-138">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="fac12-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
