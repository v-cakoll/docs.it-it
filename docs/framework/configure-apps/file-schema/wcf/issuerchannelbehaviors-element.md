---
title: Elemento &lt;issuerChannelBehaviors&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b73d090aa47e18792d313b3d086e7a667e74bb08
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="501b3-102">Elemento &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="501b3-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="501b3-103">Contiene una raccolta di comportamenti di endpoint del client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (definiti nella configurazione) da usare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="501b3-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="501b3-104">Non possono contenere i comportamenti definiti [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="501b3-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="501b3-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="501b3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="501b3-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="501b3-106">\<behaviors></span></span>  
<span data-ttu-id="501b3-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="501b3-107">endpointBehaviors section</span></span>  
<span data-ttu-id="501b3-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="501b3-108">\<behavior></span></span>  
<span data-ttu-id="501b3-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="501b3-109">\<clientCredentials></span></span>  
<span data-ttu-id="501b3-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="501b3-110">\<issuedToken></span></span>  
<span data-ttu-id="501b3-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="501b3-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="501b3-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="501b3-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="501b3-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="501b3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="501b3-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="501b3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="501b3-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="501b3-115">Attributes</span></span>  
 <span data-ttu-id="501b3-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="501b3-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="501b3-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="501b3-117">Child Elements</span></span>  
  
|<span data-ttu-id="501b3-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="501b3-118">Element</span></span>|<span data-ttu-id="501b3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="501b3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="501b3-120">\<add></span><span class="sxs-lookup"><span data-stu-id="501b3-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="501b3-121">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="501b3-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="501b3-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="501b3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="501b3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="501b3-123">Element</span></span>|<span data-ttu-id="501b3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="501b3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="501b3-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="501b3-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="501b3-126">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="501b3-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="501b3-127">Note</span><span class="sxs-lookup"><span data-stu-id="501b3-127">Remarks</span></span>  
 <span data-ttu-id="501b3-128">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="501b3-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="501b3-129">Ad esempio, se un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) elemento di comportamento deve essere incluso.</span><span class="sxs-lookup"><span data-stu-id="501b3-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501b3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="501b3-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="501b3-131">L'autenticazione e identità del servizio</span><span class="sxs-lookup"><span data-stu-id="501b3-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="501b3-132">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="501b3-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="501b3-133">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="501b3-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="501b3-134">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="501b3-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="501b3-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="501b3-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="501b3-136">Procedura: creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="501b3-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="501b3-137">Procedura: configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="501b3-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="501b3-138">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="501b3-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
