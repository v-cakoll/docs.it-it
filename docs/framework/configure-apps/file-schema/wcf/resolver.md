---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 39dcb868bd3ff25451509616e1dac7d41f94cfa1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075879"
---
# <a name="resolver"></a><span data-ttu-id="70121-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="70121-101">\<resolver></span></span>
<span data-ttu-id="70121-102">Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.</span><span class="sxs-lookup"><span data-stu-id="70121-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="70121-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="70121-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="70121-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="70121-104">\<bindings></span></span>  
<span data-ttu-id="70121-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="70121-105">\<netPeerBinding></span></span>  
<span data-ttu-id="70121-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="70121-106">\<binding></span></span>  
<span data-ttu-id="70121-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="70121-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70121-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70121-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70121-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="70121-109">Attributes and Elements</span></span>  
 <span data-ttu-id="70121-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="70121-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70121-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="70121-111">Attributes</span></span>  
  
|<span data-ttu-id="70121-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="70121-112">Attribute</span></span>|<span data-ttu-id="70121-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70121-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="70121-114">Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="70121-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="70121-115">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="70121-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="70121-116">Una stringa che specifica la modalità di condivisione dei riferimenti fra peer.</span><span class="sxs-lookup"><span data-stu-id="70121-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="70121-117">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="70121-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70121-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="70121-118">Child Elements</span></span>  
  
|<span data-ttu-id="70121-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="70121-119">Element</span></span>|<span data-ttu-id="70121-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70121-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70121-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="70121-121">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="70121-122">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="70121-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70121-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="70121-123">Parent Elements</span></span>  
  
|<span data-ttu-id="70121-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="70121-124">Element</span></span>|<span data-ttu-id="70121-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70121-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70121-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="70121-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="70121-127">Definisce tutte le funzionalità di associazione del [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="70121-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70121-128">Note</span><span class="sxs-lookup"><span data-stu-id="70121-128">Remarks</span></span>  
 <span data-ttu-id="70121-129">Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer.</span><span class="sxs-lookup"><span data-stu-id="70121-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="70121-130">Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="70121-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="70121-131">Per altre informazioni sui resolver del peer, vedere [i resolver del Peer](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="70121-131">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70121-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70121-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="70121-133">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="70121-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="70121-134">[Aggiunta di un Resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="70121-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
