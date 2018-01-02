---
title: '&lt;add&gt; di &lt;issuerChannelBehaviors&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf66b3d3b531ae41329aade6a416c330957d83c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="81c17-102">&lt;add&gt; di &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="81c17-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="81c17-103">Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.</span><span class="sxs-lookup"><span data-stu-id="81c17-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81c17-104">Se qualsiasi comportamento dell'endpoint contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="81c17-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="81c17-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="81c17-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="81c17-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="81c17-106">\<behaviors></span></span>  
<span data-ttu-id="81c17-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="81c17-107">endpointBehaviors section</span></span>  
<span data-ttu-id="81c17-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="81c17-108">\<behavior></span></span>  
<span data-ttu-id="81c17-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="81c17-109">\<clientCredentials></span></span>  
<span data-ttu-id="81c17-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="81c17-110">\<issuedToken></span></span>  
<span data-ttu-id="81c17-111">\<issuerChannelBehaviors > elemento</span><span class="sxs-lookup"><span data-stu-id="81c17-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="81c17-112">\<add></span><span class="sxs-lookup"><span data-stu-id="81c17-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c17-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81c17-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81c17-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="81c17-114">Attributes and Elements</span></span>  
 <span data-ttu-id="81c17-115">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="81c17-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81c17-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="81c17-116">Attributes</span></span>  
  
|<span data-ttu-id="81c17-117">Attributo</span><span class="sxs-lookup"><span data-stu-id="81c17-117">Attribute</span></span>|<span data-ttu-id="81c17-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81c17-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81c17-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="81c17-119">issuerAddress</span></span>|<span data-ttu-id="81c17-120">URI dell'emittente del token di sicurezza con cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="81c17-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="81c17-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="81c17-121">behaviorConfiguration</span></span>|<span data-ttu-id="81c17-122">Nome di un comportamento di endpoint definito nello stesso file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="81c17-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81c17-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="81c17-123">Child Elements</span></span>  
 <span data-ttu-id="81c17-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="81c17-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81c17-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="81c17-125">Parent Elements</span></span>  
  
|<span data-ttu-id="81c17-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="81c17-126">Element</span></span>|<span data-ttu-id="81c17-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81c17-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81c17-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="81c17-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="81c17-129">Contiene una raccolta di comportamenti di endpoint di client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] da usare durante le comunicazioni con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="81c17-129">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81c17-130">Note</span><span class="sxs-lookup"><span data-stu-id="81c17-130">Remarks</span></span>  
 <span data-ttu-id="81c17-131">`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare.</span><span class="sxs-lookup"><span data-stu-id="81c17-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="81c17-132">`behaviorConfiguration` punta al comportamento di un endpoint usato dall'applicazione nei canali creati da [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] per ottenere i token pubblicati dai servizi token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="81c17-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c17-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c17-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="81c17-134">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="81c17-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="81c17-135">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="81c17-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="81c17-136">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="81c17-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="81c17-137">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="81c17-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="81c17-138">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="81c17-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="81c17-139">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="81c17-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="81c17-140">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="81c17-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="81c17-141">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="81c17-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="81c17-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="81c17-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
