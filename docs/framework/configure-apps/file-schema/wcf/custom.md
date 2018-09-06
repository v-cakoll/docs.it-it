---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 7d558be66b8a1e46d9743c5f8bf0bb9a8b4c349e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43776223"
---
# <a name="ltcustomgt"></a><span data-ttu-id="ce11a-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="ce11a-102">&lt;custom&gt;</span></span>
<span data-ttu-id="ce11a-103">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ce11a-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="ce11a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce11a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ce11a-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="ce11a-105">\<bindings></span></span>  
<span data-ttu-id="ce11a-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="ce11a-106">\<netPeerBinding></span></span>  
<span data-ttu-id="ce11a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ce11a-107">\<binding></span></span>  
<span data-ttu-id="ce11a-108">\<resolver ></span><span class="sxs-lookup"><span data-stu-id="ce11a-108">\<resolver></span></span>  
<span data-ttu-id="ce11a-109">\<custom></span><span class="sxs-lookup"><span data-stu-id="ce11a-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce11a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce11a-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce11a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce11a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce11a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce11a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce11a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce11a-113">Attributes</span></span>  
  
|<span data-ttu-id="ce11a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ce11a-114">Attribute</span></span>|<span data-ttu-id="ce11a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce11a-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="ce11a-116">URI che specifica l'indirizzo dell'endpoint del nodo peer che ospita il servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ce11a-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="ce11a-117">Stringa che specifica il tipo del servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ce11a-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce11a-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce11a-118">Child Elements</span></span>  
  
|<span data-ttu-id="ce11a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce11a-119">Element</span></span>|<span data-ttu-id="ce11a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce11a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce11a-121">\<identità ></span><span class="sxs-lookup"><span data-stu-id="ce11a-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ce11a-122">Specifica l'identità dei resolver peer personalizzati configurati per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="ce11a-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="ce11a-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="ce11a-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="ce11a-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="ce11a-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="ce11a-125">Raccolta di intestazioni di indirizzo usate per i messaggi SOAP gestiti dal resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ce11a-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce11a-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce11a-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ce11a-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce11a-127">Element</span></span>|<span data-ttu-id="ce11a-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce11a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce11a-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="ce11a-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="ce11a-130">Resolver peer usato per risolvere un ID della rete di peer in un set di indirizzi di nodo peer che rappresenta alcuni nodi appartenenti alla rete.</span><span class="sxs-lookup"><span data-stu-id="ce11a-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce11a-131">Note</span><span class="sxs-lookup"><span data-stu-id="ce11a-131">Remarks</span></span>  
 <span data-ttu-id="ce11a-132">Questo elemento definisce le impostazioni di base per un servizio resolver peer personalizzato, inclusi l'indirizzo dell'endpoint del peer che ospita il servizio e le impostazioni dell'associazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="ce11a-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="ce11a-133">Per altre informazioni sulla creazione di un resolver personalizzato, vedere [aggiunta di un Resolver personalizzato a un'applicazione PeerChannel](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="ce11a-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce11a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce11a-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="ce11a-135">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="ce11a-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="ce11a-136">Aggiunta di un Resolver personalizzato a un'applicazione PeerChannel</span><span class="sxs-lookup"><span data-stu-id="ce11a-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
