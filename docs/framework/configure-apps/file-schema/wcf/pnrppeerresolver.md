---
title: '&lt;pnrpPeerResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0152dfaa498b84b6e8cfa277abe858cc24ad34cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="12409-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="12409-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="12409-103">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="12409-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="12409-104">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="12409-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="12409-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="12409-105">\<system.serviceModel></span></span>  
<span data-ttu-id="12409-106">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="12409-106">\<bindings></span></span>  
<span data-ttu-id="12409-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="12409-107">\<customBinding></span></span>  
<span data-ttu-id="12409-108">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="12409-108">\<binding></span></span>  
<span data-ttu-id="12409-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="12409-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12409-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12409-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12409-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="12409-111">Attributes and Elements</span></span>  
 <span data-ttu-id="12409-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="12409-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12409-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="12409-113">Attributes</span></span>  
  
|<span data-ttu-id="12409-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="12409-114">Attribute</span></span>|<span data-ttu-id="12409-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12409-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12409-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="12409-116">resolverType</span></span>|<span data-ttu-id="12409-117">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="12409-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="12409-118">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="12409-118">This attribute is optional.</span></span> <span data-ttu-id="12409-119">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="12409-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12409-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="12409-120">Child Elements</span></span>  
 <span data-ttu-id="12409-121">None</span><span class="sxs-lookup"><span data-stu-id="12409-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12409-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="12409-122">Parent Elements</span></span>  
  
|<span data-ttu-id="12409-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="12409-123">Element</span></span>|<span data-ttu-id="12409-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12409-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12409-125">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="12409-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="12409-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="12409-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="12409-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="12409-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="12409-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12409-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="12409-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="12409-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="12409-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="12409-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="12409-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="12409-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="12409-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="12409-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="12409-133">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="12409-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
