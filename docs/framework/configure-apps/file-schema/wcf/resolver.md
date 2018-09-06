---
title: '&lt;resolver&gt;'
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 48b6b6ca315f7ab63a8f7a64b97167fa04fe1e4e
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43804094"
---
# <a name="ltresolvergt"></a><span data-ttu-id="750c4-102">&lt;resolver&gt;</span><span class="sxs-lookup"><span data-stu-id="750c4-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="750c4-103">Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.</span><span class="sxs-lookup"><span data-stu-id="750c4-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="750c4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="750c4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="750c4-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="750c4-105">\<bindings></span></span>  
<span data-ttu-id="750c4-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="750c4-106">\<netPeerBinding></span></span>  
<span data-ttu-id="750c4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="750c4-107">\<binding></span></span>  
<span data-ttu-id="750c4-108">\<resolver ></span><span class="sxs-lookup"><span data-stu-id="750c4-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="750c4-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="750c4-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="750c4-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="750c4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="750c4-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="750c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="750c4-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="750c4-112">Attributes</span></span>  
  
|<span data-ttu-id="750c4-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="750c4-113">Attribute</span></span>|<span data-ttu-id="750c4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="750c4-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="750c4-115">Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="750c4-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="750c4-116">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="750c4-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="750c4-117">Una stringa che specifica la modalità di condivisione dei riferimenti fra peer.</span><span class="sxs-lookup"><span data-stu-id="750c4-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="750c4-118">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="750c4-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="750c4-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="750c4-119">Child Elements</span></span>  
  
|<span data-ttu-id="750c4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="750c4-120">Element</span></span>|<span data-ttu-id="750c4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="750c4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="750c4-122">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="750c4-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="750c4-123">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="750c4-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="750c4-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="750c4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="750c4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="750c4-125">Element</span></span>|<span data-ttu-id="750c4-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="750c4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="750c4-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="750c4-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="750c4-128">Definisce tutte le funzionalità di associazione del [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="750c4-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="750c4-129">Note</span><span class="sxs-lookup"><span data-stu-id="750c4-129">Remarks</span></span>  
 <span data-ttu-id="750c4-130">Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer.</span><span class="sxs-lookup"><span data-stu-id="750c4-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="750c4-131">Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="750c4-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="750c4-132">Per altre informazioni sui resolver del peer, vedere [i resolver del Peer](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="750c4-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750c4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="750c4-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="750c4-134">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="750c4-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="750c4-135">Aggiunta di un Resolver personalizzato a un'applicazione PeerChannel</span><span class="sxs-lookup"><span data-stu-id="750c4-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
