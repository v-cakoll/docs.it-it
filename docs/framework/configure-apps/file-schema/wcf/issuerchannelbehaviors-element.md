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
ms.workload: dotnet
ms.openlocfilehash: bb90b318f99816a3886056394559fdc80fa986ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="3474d-102">Elemento &lt;issuerChannelBehaviors&gt;</span><span class="sxs-lookup"><span data-stu-id="3474d-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="3474d-103">Contiene una raccolta di comportamenti di endpoint del client [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] (definiti nella configurazione) da usare durante la comunicazione con i servizi STS specificati.</span><span class="sxs-lookup"><span data-stu-id="3474d-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="3474d-104">Non possono contenere i comportamenti definiti [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elementi.</span><span class="sxs-lookup"><span data-stu-id="3474d-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="3474d-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3474d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3474d-106">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="3474d-106">\<behaviors></span></span>  
<span data-ttu-id="3474d-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="3474d-107">endpointBehaviors section</span></span>  
<span data-ttu-id="3474d-108">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="3474d-108">\<behavior></span></span>  
<span data-ttu-id="3474d-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="3474d-109">\<clientCredentials></span></span>  
<span data-ttu-id="3474d-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="3474d-110">\<issuedToken></span></span>  
<span data-ttu-id="3474d-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3474d-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3474d-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3474d-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3474d-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3474d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3474d-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3474d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3474d-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="3474d-115">Attributes</span></span>  
 <span data-ttu-id="3474d-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3474d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3474d-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3474d-117">Child Elements</span></span>  
  
|<span data-ttu-id="3474d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="3474d-118">Element</span></span>|<span data-ttu-id="3474d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3474d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3474d-120">\<add></span><span class="sxs-lookup"><span data-stu-id="3474d-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="3474d-121">Aggiunge un comportamento alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="3474d-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3474d-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3474d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3474d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3474d-123">Element</span></span>|<span data-ttu-id="3474d-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3474d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3474d-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="3474d-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="3474d-126">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="3474d-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3474d-127">Note</span><span class="sxs-lookup"><span data-stu-id="3474d-127">Remarks</span></span>  
 <span data-ttu-id="3474d-128">Usare questo elemento quando per comunicare con un servizio è necessario usare comportamenti diversi da quelli includono elementi `<clientCredentials>`,</span><span class="sxs-lookup"><span data-stu-id="3474d-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="3474d-129">Ad esempio, se un [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) elemento di comportamento deve essere incluso.</span><span class="sxs-lookup"><span data-stu-id="3474d-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3474d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3474d-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="3474d-131">Identità del servizio e autenticazione</span><span class="sxs-lookup"><span data-stu-id="3474d-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="3474d-132">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="3474d-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="3474d-133">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="3474d-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="3474d-134">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="3474d-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3474d-135">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="3474d-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="3474d-136">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="3474d-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="3474d-137">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="3474d-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="3474d-138">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="3474d-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
