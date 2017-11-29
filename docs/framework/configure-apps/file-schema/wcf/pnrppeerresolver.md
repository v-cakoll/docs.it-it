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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd93bdadec120050813fcc1097d3041d6be94f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="77e03-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="77e03-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="77e03-103">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="77e03-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="77e03-104">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="77e03-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="77e03-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="77e03-105">\<system.serviceModel></span></span>  
<span data-ttu-id="77e03-106">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="77e03-106">\<bindings></span></span>  
<span data-ttu-id="77e03-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="77e03-107">\<customBinding></span></span>  
<span data-ttu-id="77e03-108">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="77e03-108">\<binding></span></span>  
<span data-ttu-id="77e03-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="77e03-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e03-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77e03-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77e03-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="77e03-111">Attributes and Elements</span></span>  
 <span data-ttu-id="77e03-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="77e03-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77e03-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="77e03-113">Attributes</span></span>  
  
|<span data-ttu-id="77e03-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="77e03-114">Attribute</span></span>|<span data-ttu-id="77e03-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77e03-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77e03-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="77e03-116">resolverType</span></span>|<span data-ttu-id="77e03-117">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="77e03-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="77e03-118">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="77e03-118">This attribute is optional.</span></span> <span data-ttu-id="77e03-119">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="77e03-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77e03-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="77e03-120">Child Elements</span></span>  
 <span data-ttu-id="77e03-121">None</span><span class="sxs-lookup"><span data-stu-id="77e03-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77e03-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="77e03-122">Parent Elements</span></span>  
  
|<span data-ttu-id="77e03-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="77e03-123">Element</span></span>|<span data-ttu-id="77e03-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77e03-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77e03-125">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="77e03-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="77e03-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="77e03-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="77e03-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="77e03-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="77e03-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77e03-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="77e03-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="77e03-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="77e03-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="77e03-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="77e03-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="77e03-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="77e03-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="77e03-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="77e03-133">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="77e03-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
