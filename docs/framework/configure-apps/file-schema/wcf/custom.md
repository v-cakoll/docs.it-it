---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 2b268d9d040bbeed2b3563783226f7ca8c18e3b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254288"
---
# <a name="custom"></a><span data-ttu-id="33b49-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="33b49-101">\<custom></span></span>
<span data-ttu-id="33b49-102">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33b49-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="33b49-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="33b49-103">\<system.serviceModel></span></span>  
<span data-ttu-id="33b49-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="33b49-104">\<bindings></span></span>  
<span data-ttu-id="33b49-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="33b49-105">\<netPeerBinding></span></span>  
<span data-ttu-id="33b49-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="33b49-106">\<binding></span></span>  
<span data-ttu-id="33b49-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="33b49-107">\<resolver></span></span>  
<span data-ttu-id="33b49-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="33b49-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b49-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33b49-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33b49-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33b49-110">Attributes and Elements</span></span>  
 <span data-ttu-id="33b49-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33b49-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33b49-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="33b49-112">Attributes</span></span>  
  
|<span data-ttu-id="33b49-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="33b49-113">Attribute</span></span>|<span data-ttu-id="33b49-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b49-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="33b49-115">URI che specifica l'indirizzo dell'endpoint del nodo peer che ospita il servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33b49-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="33b49-116">Stringa che specifica il tipo del servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33b49-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33b49-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33b49-117">Child Elements</span></span>  
  
|<span data-ttu-id="33b49-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b49-118">Element</span></span>|<span data-ttu-id="33b49-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b49-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33b49-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="33b49-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="33b49-121">Specifica l'identità dei resolver peer personalizzati configurati per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="33b49-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="33b49-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="33b49-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="33b49-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="33b49-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="33b49-124">Raccolta di intestazioni di indirizzo usate per i messaggi SOAP gestiti dal resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="33b49-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33b49-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33b49-125">Parent Elements</span></span>  
  
|<span data-ttu-id="33b49-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b49-126">Element</span></span>|<span data-ttu-id="33b49-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33b49-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33b49-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="33b49-128">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="33b49-129">Resolver peer usato per risolvere un ID della rete di peer in un set di indirizzi di nodo peer che rappresenta alcuni nodi appartenenti alla rete.</span><span class="sxs-lookup"><span data-stu-id="33b49-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33b49-130">Note</span><span class="sxs-lookup"><span data-stu-id="33b49-130">Remarks</span></span>  
 <span data-ttu-id="33b49-131">Questo elemento definisce le impostazioni di base per un servizio resolver peer personalizzato, inclusi l'indirizzo dell'endpoint del peer che ospita il servizio e le impostazioni dell'associazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="33b49-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="33b49-132">Per altre informazioni sulla creazione di un resolver personalizzato, vedere [aggiunta di un Resolver personalizzato a un'applicazione PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="33b49-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b49-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b49-133">See also</span></span>
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="33b49-134">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="33b49-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [<span data-ttu-id="33b49-135">Aggiunta di un Resolver personalizzato a un'applicazione PeerChannel</span><span class="sxs-lookup"><span data-stu-id="33b49-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
