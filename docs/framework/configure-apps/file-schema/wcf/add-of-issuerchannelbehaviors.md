---
title: '&lt;add&gt; di &lt;issuerChannelBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: e0f49f71a3f9649492b3ad7ccf263114957ee4e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729931"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="700f4-102">&lt;add&gt; di &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="700f4-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="700f4-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="700f4-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="700f4-104">Se qualsiasi comportamento dell'endpoint contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="700f4-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="700f4-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="700f4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="700f4-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="700f4-106">\<behaviors></span></span>  
<span data-ttu-id="700f4-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="700f4-107">endpointBehaviors section</span></span>  
<span data-ttu-id="700f4-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="700f4-108">\<behavior></span></span>  
<span data-ttu-id="700f4-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="700f4-109">\<clientCredentials></span></span>  
<span data-ttu-id="700f4-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="700f4-110">\<issuedToken></span></span>  
<span data-ttu-id="700f4-111">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="700f4-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="700f4-112">\<add></span><span class="sxs-lookup"><span data-stu-id="700f4-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="700f4-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="700f4-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="700f4-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="700f4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="700f4-115">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="700f4-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="700f4-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="700f4-116">Attributes</span></span>  
  
|<span data-ttu-id="700f4-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="700f4-117">Attribute</span></span>|<span data-ttu-id="700f4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="700f4-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="700f4-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="700f4-119">issuerAddress</span></span>|<span data-ttu-id="700f4-120">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="700f4-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="700f4-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="700f4-121">behaviorConfiguration</span></span>|<span data-ttu-id="700f4-122">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="700f4-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="700f4-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="700f4-123">Child Elements</span></span>  
 <span data-ttu-id="700f4-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="700f4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="700f4-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="700f4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="700f4-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="700f4-126">Element</span></span>|<span data-ttu-id="700f4-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="700f4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="700f4-128">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="700f4-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="700f4-129">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="700f4-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="700f4-130">Note</span><span class="sxs-lookup"><span data-stu-id="700f4-130">Remarks</span></span>  
 <span data-ttu-id="700f4-131">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="700f4-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="700f4-132">`behaviorConfiguration` punta a un comportamento dell'endpoint utilizzati dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token rilasciati dal servizio Token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="700f4-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700f4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="700f4-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="700f4-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="700f4-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="700f4-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="700f4-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="700f4-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="700f4-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="700f4-137">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="700f4-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="700f4-138">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="700f4-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="700f4-139">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="700f4-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="700f4-140">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="700f4-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="700f4-141">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="700f4-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="700f4-142">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="700f4-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
