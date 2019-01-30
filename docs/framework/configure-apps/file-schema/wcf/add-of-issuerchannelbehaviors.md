---
title: <add> di <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 65c76cba696ae388d6184eaaa70a1f2f5a301e1c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271794"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="f1d11-102">\<aggiungere > di \<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f1d11-102">\<add> of \<issuerChannelBehaviors></span></span>
<span data-ttu-id="f1d11-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="f1d11-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1d11-104">Se qualsiasi comportamento dell'endpoint contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f1d11-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="f1d11-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f1d11-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f1d11-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f1d11-106">\<behaviors></span></span>  
<span data-ttu-id="f1d11-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="f1d11-107">endpointBehaviors section</span></span>  
<span data-ttu-id="f1d11-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f1d11-108">\<behavior></span></span>  
<span data-ttu-id="f1d11-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f1d11-109">\<clientCredentials></span></span>  
<span data-ttu-id="f1d11-110">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="f1d11-110">\<issuedToken></span></span>  
<span data-ttu-id="f1d11-111">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="f1d11-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="f1d11-112">\<add></span><span class="sxs-lookup"><span data-stu-id="f1d11-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d11-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1d11-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"
     behaviorConfiguraton="string" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1d11-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1d11-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f1d11-115">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1d11-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1d11-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1d11-116">Attributes</span></span>  
  
|<span data-ttu-id="f1d11-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="f1d11-117">Attribute</span></span>|<span data-ttu-id="f1d11-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1d11-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1d11-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="f1d11-119">issuerAddress</span></span>|<span data-ttu-id="f1d11-120">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="f1d11-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="f1d11-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1d11-121">behaviorConfiguration</span></span>|<span data-ttu-id="f1d11-122">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1d11-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1d11-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1d11-123">Child Elements</span></span>  
 <span data-ttu-id="f1d11-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f1d11-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1d11-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1d11-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f1d11-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1d11-126">Element</span></span>|<span data-ttu-id="f1d11-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1d11-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1d11-128">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="f1d11-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="f1d11-129">Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="f1d11-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1d11-130">Note</span><span class="sxs-lookup"><span data-stu-id="f1d11-130">Remarks</span></span>  
 <span data-ttu-id="f1d11-131">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="f1d11-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="f1d11-132">`behaviorConfiguration` punta a un comportamento dell'endpoint utilizzati dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token rilasciati dal servizio Token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f1d11-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d11-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1d11-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="f1d11-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="f1d11-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f1d11-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1d11-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f1d11-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="f1d11-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f1d11-137">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f1d11-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f1d11-138">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="f1d11-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="f1d11-139">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="f1d11-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f1d11-140">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="f1d11-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="f1d11-141">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="f1d11-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f1d11-142">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="f1d11-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
