---
title: '&lt;sistema di risoluzione&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a9b63848590fba6e07a4a32d8ffd70c277448adf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="ltresolvergt"></a><span data-ttu-id="bca66-102">&lt;sistema di risoluzione&gt;</span><span class="sxs-lookup"><span data-stu-id="bca66-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="bca66-103">Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.</span><span class="sxs-lookup"><span data-stu-id="bca66-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="bca66-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bca66-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bca66-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="bca66-105">\<bindings></span></span>  
<span data-ttu-id="bca66-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="bca66-106">\<netPeerBinding></span></span>  
<span data-ttu-id="bca66-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="bca66-107">\<binding></span></span>  
<span data-ttu-id="bca66-108">\<resolver ></span><span class="sxs-lookup"><span data-stu-id="bca66-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bca66-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bca66-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bca66-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="bca66-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bca66-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="bca66-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bca66-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="bca66-112">Attributes</span></span>  
  
|<span data-ttu-id="bca66-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="bca66-113">Attribute</span></span>|<span data-ttu-id="bca66-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bca66-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="bca66-115">Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bca66-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="bca66-116">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="bca66-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="bca66-117">Una stringa che specifica la modalità di condivisione dei riferimenti fra peer.</span><span class="sxs-lookup"><span data-stu-id="bca66-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="bca66-118">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="bca66-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bca66-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="bca66-119">Child Elements</span></span>  
  
|<span data-ttu-id="bca66-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="bca66-120">Element</span></span>|<span data-ttu-id="bca66-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bca66-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bca66-122">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="bca66-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="bca66-123">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bca66-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bca66-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="bca66-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bca66-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bca66-125">Element</span></span>|<span data-ttu-id="bca66-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bca66-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bca66-127">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="bca66-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="bca66-128">Definisce tutte le funzionalità di associazione di [ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bca66-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bca66-129">Note</span><span class="sxs-lookup"><span data-stu-id="bca66-129">Remarks</span></span>  
 <span data-ttu-id="bca66-130">Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer.</span><span class="sxs-lookup"><span data-stu-id="bca66-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="bca66-131">Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="bca66-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="bca66-132">Per ulteriori informazioni sul resolver peer, vedere [i resolver del Peer](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span><span class="sxs-lookup"><span data-stu-id="bca66-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca66-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bca66-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="bca66-134">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="bca66-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="bca66-135">Aggiunta di un Resolver personalizzato a un'applicazione il canale peer</span><span class="sxs-lookup"><span data-stu-id="bca66-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
