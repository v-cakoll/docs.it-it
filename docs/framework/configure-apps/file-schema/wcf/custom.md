---
title: '&lt;custom&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ba9c8f6fa5bf574bdcaa9cb46b6c666e7117a9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ltcustomgt"></a><span data-ttu-id="0e922-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="0e922-102">&lt;custom&gt;</span></span>
<span data-ttu-id="0e922-103">Specifica le impostazioni di un servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0e922-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="0e922-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0e922-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0e922-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0e922-105">\<bindings></span></span>  
<span data-ttu-id="0e922-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="0e922-106">\<netPeerBinding></span></span>  
<span data-ttu-id="0e922-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0e922-107">\<binding></span></span>  
<span data-ttu-id="0e922-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="0e922-108">\<resolver></span></span>  
<span data-ttu-id="0e922-109">\<custom></span><span class="sxs-lookup"><span data-stu-id="0e922-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e922-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e922-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e922-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0e922-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0e922-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0e922-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e922-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0e922-113">Attributes</span></span>  
  
|<span data-ttu-id="0e922-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="0e922-114">Attribute</span></span>|<span data-ttu-id="0e922-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e922-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="0e922-116">URI che specifica l'indirizzo dell'endpoint del nodo peer che ospita il servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0e922-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="0e922-117">Stringa che specifica il tipo del servizio resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0e922-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e922-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0e922-118">Child Elements</span></span>  
  
|<span data-ttu-id="0e922-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e922-119">Element</span></span>|<span data-ttu-id="0e922-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e922-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e922-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="0e922-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0e922-122">Specifica l'identità dei resolver peer personalizzati configurati per questo elemento.</span><span class="sxs-lookup"><span data-stu-id="0e922-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="0e922-123">L'elemento è di tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="0e922-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="0e922-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="0e922-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="0e922-125">Raccolta di intestazioni di indirizzo usate per i messaggi SOAP gestiti dal resolver peer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0e922-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e922-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0e922-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0e922-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e922-127">Element</span></span>|<span data-ttu-id="0e922-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e922-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e922-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="0e922-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="0e922-130">Resolver peer usato per risolvere un ID della rete di peer in un set di indirizzi di nodo peer che rappresenta alcuni nodi appartenenti alla rete.</span><span class="sxs-lookup"><span data-stu-id="0e922-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e922-131">Note</span><span class="sxs-lookup"><span data-stu-id="0e922-131">Remarks</span></span>  
 <span data-ttu-id="0e922-132">Questo elemento definisce le impostazioni di base per un servizio resolver peer personalizzato, inclusi l'indirizzo dell'endpoint del peer che ospita il servizio e le impostazioni dell'associazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="0e922-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="0e922-133">Per ulteriori informazioni sulla creazione di un sistema di risoluzione personalizzato, vedere [aggiunta di un Resolver personalizzato a un'applicazione di PeerChannel](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="0e922-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e922-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e922-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="0e922-135">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="0e922-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="0e922-136">Aggiunta di un Resolver personalizzato a un'applicazione il canale peer</span><span class="sxs-lookup"><span data-stu-id="0e922-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
