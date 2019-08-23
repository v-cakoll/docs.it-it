---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: e3a9ee00aab6ab48a1ba891565b63824e62b20fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934221"
---
# <a name="resolver"></a><span data-ttu-id="8c14e-101">\<> resolver</span><span class="sxs-lookup"><span data-stu-id="8c14e-101">\<resolver></span></span>
<span data-ttu-id="8c14e-102">Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.</span><span class="sxs-lookup"><span data-stu-id="8c14e-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="8c14e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c14e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c14e-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="8c14e-104">\<bindings></span></span>  
<span data-ttu-id="8c14e-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="8c14e-105">\<netPeerBinding></span></span>  
<span data-ttu-id="8c14e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c14e-106">\<binding></span></span>  
<span data-ttu-id="8c14e-107">\<> resolver</span><span class="sxs-lookup"><span data-stu-id="8c14e-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c14e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c14e-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c14e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c14e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8c14e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c14e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c14e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c14e-111">Attributes</span></span>  
  
|<span data-ttu-id="8c14e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="8c14e-112">Attribute</span></span>|<span data-ttu-id="8c14e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c14e-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="8c14e-114">Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8c14e-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="8c14e-115">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="8c14e-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="8c14e-116">Una stringa che specifica la modalità di condivisione dei riferimenti fra peer.</span><span class="sxs-lookup"><span data-stu-id="8c14e-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="8c14e-117">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="8c14e-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c14e-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c14e-118">Child Elements</span></span>  
  
|<span data-ttu-id="8c14e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c14e-119">Element</span></span>|<span data-ttu-id="8c14e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c14e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c14e-121">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="8c14e-121">\<headers></span></span>](headers.md)|<span data-ttu-id="8c14e-122">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8c14e-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c14e-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c14e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8c14e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c14e-124">Element</span></span>|<span data-ttu-id="8c14e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c14e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c14e-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c14e-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="8c14e-127">Definisce tutte le funzionalità di associazione del [ \<> NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8c14e-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c14e-128">Note</span><span class="sxs-lookup"><span data-stu-id="8c14e-128">Remarks</span></span>  
 <span data-ttu-id="8c14e-129">Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer.</span><span class="sxs-lookup"><span data-stu-id="8c14e-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="8c14e-130">Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="8c14e-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="8c14e-131">Per ulteriori informazioni sui resolver del peer, vedere [resolver](../../../wcf/feature-details/peer-resolvers.md)del peer.</span><span class="sxs-lookup"><span data-stu-id="8c14e-131">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c14e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c14e-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="8c14e-133">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="8c14e-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="8c14e-134">[Aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8c14e-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
