---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738734"
---
# <a name="resolver"></a><span data-ttu-id="44c5e-101">\<resolver ></span><span class="sxs-lookup"><span data-stu-id="44c5e-101">\<resolver></span></span>
<span data-ttu-id="44c5e-102">Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.</span><span class="sxs-lookup"><span data-stu-id="44c5e-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="44c5e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44c5e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44c5e-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44c5e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44c5e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="44c5e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="44c5e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetPeerTcpBinding**](netpeertcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="44c5e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="44c5e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="44c5e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="44c5e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**resolver**\<</span><span class="sxs-lookup"><span data-stu-id="44c5e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c5e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44c5e-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44c5e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44c5e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="44c5e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44c5e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44c5e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="44c5e-112">Attributes</span></span>  
  
|<span data-ttu-id="44c5e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="44c5e-113">Attribute</span></span>|<span data-ttu-id="44c5e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44c5e-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="44c5e-115">Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="44c5e-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="44c5e-116">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="44c5e-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="44c5e-117">Una stringa che specifica la modalità di condivisione dei riferimenti fra peer.</span><span class="sxs-lookup"><span data-stu-id="44c5e-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="44c5e-118">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="44c5e-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44c5e-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44c5e-119">Child Elements</span></span>  
  
|<span data-ttu-id="44c5e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="44c5e-120">Element</span></span>|<span data-ttu-id="44c5e-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44c5e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44c5e-122">intestazioni \<</span><span class="sxs-lookup"><span data-stu-id="44c5e-122">\<headers></span></span>](headers.md)|<span data-ttu-id="44c5e-123">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="44c5e-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44c5e-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44c5e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="44c5e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="44c5e-125">Element</span></span>|<span data-ttu-id="44c5e-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44c5e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44c5e-127">\<binding ></span><span class="sxs-lookup"><span data-stu-id="44c5e-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="44c5e-128">Definisce tutte le funzionalità di associazione della [\<> NetPeerTcpBinding](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="44c5e-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44c5e-129">Note</span><span class="sxs-lookup"><span data-stu-id="44c5e-129">Remarks</span></span>  
 <span data-ttu-id="44c5e-130">Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer.</span><span class="sxs-lookup"><span data-stu-id="44c5e-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="44c5e-131">Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="44c5e-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="44c5e-132">Per ulteriori informazioni sui resolver del peer, vedere [resolver](../../../wcf/feature-details/peer-resolvers.md)del peer.</span><span class="sxs-lookup"><span data-stu-id="44c5e-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c5e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44c5e-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="44c5e-134">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="44c5e-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="44c5e-135">[Aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="44c5e-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
