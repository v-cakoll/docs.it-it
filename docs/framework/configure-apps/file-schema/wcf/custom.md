---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: b5cc522604fa7aca8ca6eae787520265b36fef6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925947"
---
# <a name="custom"></a><span data-ttu-id="499dc-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="499dc-101">\<custom></span></span>
<span data-ttu-id="499dc-102">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="499dc-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="499dc-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="499dc-103">\<system.serviceModel></span></span>  
<span data-ttu-id="499dc-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="499dc-104">\<bindings></span></span>  
<span data-ttu-id="499dc-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="499dc-105">\<netPeerBinding></span></span>  
<span data-ttu-id="499dc-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="499dc-106">\<binding></span></span>  
<span data-ttu-id="499dc-107">\<> resolver</span><span class="sxs-lookup"><span data-stu-id="499dc-107">\<resolver></span></span>  
<span data-ttu-id="499dc-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="499dc-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499dc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="499dc-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="499dc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="499dc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="499dc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="499dc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="499dc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="499dc-112">Attributes</span></span>  
  
|<span data-ttu-id="499dc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="499dc-113">Attribute</span></span>|<span data-ttu-id="499dc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="499dc-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="499dc-115">URI che specifica l'indirizzo dell'endpoint del nodo peer che ospita il servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="499dc-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="499dc-116">Stringa che specifica il tipo del servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="499dc-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="499dc-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="499dc-117">Child Elements</span></span>  
  
|<span data-ttu-id="499dc-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="499dc-118">Element</span></span>|<span data-ttu-id="499dc-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="499dc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="499dc-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="499dc-120">\<identity></span></span>](identity.md)|<span data-ttu-id="499dc-121">Specifica l'identità dei resolver peer personalizzati configurati per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="499dc-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="499dc-122">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="499dc-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="499dc-123">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="499dc-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="499dc-124">Raccolta di intestazioni di indirizzo usate per i messaggi SOAP gestiti dal resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="499dc-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="499dc-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="499dc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="499dc-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="499dc-126">Element</span></span>|<span data-ttu-id="499dc-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="499dc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="499dc-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="499dc-128">\<resolver></span></span>](resolver.md)|<span data-ttu-id="499dc-129">Resolver peer usato per risolvere un ID della rete di peer in un set di indirizzi di nodo peer che rappresenta alcuni nodi appartenenti alla rete.</span><span class="sxs-lookup"><span data-stu-id="499dc-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="499dc-130">Note</span><span class="sxs-lookup"><span data-stu-id="499dc-130">Remarks</span></span>  
 <span data-ttu-id="499dc-131">Questo elemento definisce le impostazioni di base per un servizio resolver peer personalizzato, inclusi l'indirizzo dell'endpoint del peer che ospita il servizio e le impostazioni dell'associazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="499dc-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="499dc-132">Per ulteriori informazioni sulla creazione di un sistema di risoluzione personalizzato, vedere [aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="499dc-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499dc-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="499dc-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="499dc-134">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="499dc-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="499dc-135">[Aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="499dc-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
