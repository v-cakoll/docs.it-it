---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400458"
---
# <a name="custom"></a><span data-ttu-id="2f8cc-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="2f8cc-101">\<custom></span></span>
<span data-ttu-id="2f8cc-102">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="2f8cc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f8cc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f8cc-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2f8cc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2f8cc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2f8cc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2f8cc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netPeerTcpBinding**](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2f8cc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="2f8cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="2f8cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2f8cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> resolver**](resolver.md)</span><span class="sxs-lookup"><span data-stu-id="2f8cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)</span></span>\
<span data-ttu-id="2f8cc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> personalizzati**</span><span class="sxs-lookup"><span data-stu-id="2f8cc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f8cc-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f8cc-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f8cc-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f8cc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2f8cc-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f8cc-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f8cc-113">Attributes</span></span>  
  
|<span data-ttu-id="2f8cc-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="2f8cc-114">Attribute</span></span>|<span data-ttu-id="2f8cc-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2f8cc-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="2f8cc-116">URI che specifica l'indirizzo dell'endpoint del nodo peer che ospita il servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="2f8cc-117">Stringa che specifica il tipo del servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f8cc-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f8cc-118">Child Elements</span></span>  
  
|<span data-ttu-id="2f8cc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f8cc-119">Element</span></span>|<span data-ttu-id="2f8cc-120">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2f8cc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f8cc-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="2f8cc-121">\<identity></span></span>](identity.md)|<span data-ttu-id="2f8cc-122">Specifica l'identità dei resolver peer personalizzati configurati per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="2f8cc-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="2f8cc-124">\<intestazioni ></span><span class="sxs-lookup"><span data-stu-id="2f8cc-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="2f8cc-125">Raccolta di intestazioni di indirizzo usate per i messaggi SOAP gestiti dal resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f8cc-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f8cc-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2f8cc-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f8cc-127">Element</span></span>|<span data-ttu-id="2f8cc-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f8cc-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f8cc-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="2f8cc-129">\<resolver></span></span>](resolver.md)|<span data-ttu-id="2f8cc-130">Resolver peer usato per risolvere un ID della rete di peer in un set di indirizzi di nodo peer che rappresenta alcuni nodi appartenenti alla rete.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f8cc-131">Note</span><span class="sxs-lookup"><span data-stu-id="2f8cc-131">Remarks</span></span>  
 <span data-ttu-id="2f8cc-132">Questo elemento definisce le impostazioni di base per un servizio resolver peer personalizzato, inclusi l'indirizzo dell'endpoint del peer che ospita il servizio e le impostazioni dell'associazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="2f8cc-133">Per ulteriori informazioni sulla creazione di un sistema di risoluzione personalizzato, vedere [aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2f8cc-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8cc-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f8cc-134">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="2f8cc-135">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="2f8cc-135">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="2f8cc-136">[Aggiunta di un resolver personalizzato a un'applicazione PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2f8cc-136">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
