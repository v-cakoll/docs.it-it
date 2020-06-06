---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738734"
---
# \<resolver>
<span data-ttu-id="01519-101">Specifica un resolver peer usato per risolvere un ID della rete di peer in un insieme di indirizzi di nodo peer che rappresenta alcuni nodi che partecipano nella rete.</span><span class="sxs-lookup"><span data-stu-id="01519-101">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a><span data-ttu-id="01519-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01519-102">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01519-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01519-103">Attributes and Elements</span></span>  
 <span data-ttu-id="01519-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01519-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01519-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="01519-105">Attributes</span></span>  
  
|<span data-ttu-id="01519-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="01519-106">Attribute</span></span>|<span data-ttu-id="01519-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01519-107">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="01519-108">Stringa che specifica se l'istanza del resolver peer associata a questo servizio è specifica di PNRP, un resolver personalizzato o viene determinata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="01519-108">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="01519-109">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span><span class="sxs-lookup"><span data-stu-id="01519-109">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="01519-110">Una stringa che specifica la modalità di condivisione dei riferimenti fra peer.</span><span class="sxs-lookup"><span data-stu-id="01519-110">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="01519-111">L'attributo è di tipo <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span><span class="sxs-lookup"><span data-stu-id="01519-111">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01519-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01519-112">Child Elements</span></span>  
  
|<span data-ttu-id="01519-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="01519-113">Element</span></span>|<span data-ttu-id="01519-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01519-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="01519-115">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="01519-115">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01519-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01519-116">Parent Elements</span></span>  
  
|<span data-ttu-id="01519-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="01519-117">Element</span></span>|<span data-ttu-id="01519-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01519-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="01519-119">Definisce tutte le funzionalità di associazione di [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="01519-119">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01519-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="01519-120">Remarks</span></span>  
 <span data-ttu-id="01519-121">Un resolver di nomi peer è un servizio di individuazione usato dai canali peer per trovare i nodi che partecipano a una rete peer.</span><span class="sxs-lookup"><span data-stu-id="01519-121">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="01519-122">Un resolver di nomi peer consente inoltre di "registrare" un nodo in una rete di peer, ovvero di renderlo individuabile e disponibile all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="01519-122">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="01519-123">Per ulteriori informazioni sui resolver del peer, vedere [resolver](../../../wcf/feature-details/peer-resolvers.md)del peer.</span><span class="sxs-lookup"><span data-stu-id="01519-123">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01519-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="01519-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="01519-125">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="01519-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="01519-126">[Aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="01519-126">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
