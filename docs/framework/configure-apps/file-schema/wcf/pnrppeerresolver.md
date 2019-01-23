---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: cefd46d7810149264f9c431a212da0f3f51f8186
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577646"
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="40e2f-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="40e2f-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="40e2f-103">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="40e2f-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="40e2f-104">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="40e2f-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="40e2f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="40e2f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="40e2f-106">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="40e2f-106">\<bindings></span></span>  
<span data-ttu-id="40e2f-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="40e2f-107">\<customBinding></span></span>  
<span data-ttu-id="40e2f-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="40e2f-108">\<binding></span></span>  
<span data-ttu-id="40e2f-109">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="40e2f-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e2f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40e2f-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40e2f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="40e2f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="40e2f-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="40e2f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40e2f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="40e2f-113">Attributes</span></span>  
  
|<span data-ttu-id="40e2f-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="40e2f-114">Attribute</span></span>|<span data-ttu-id="40e2f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40e2f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40e2f-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="40e2f-116">resolverType</span></span>|<span data-ttu-id="40e2f-117">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="40e2f-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="40e2f-118">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="40e2f-118">This attribute is optional.</span></span> <span data-ttu-id="40e2f-119">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="40e2f-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40e2f-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="40e2f-120">Child Elements</span></span>  
 <span data-ttu-id="40e2f-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="40e2f-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40e2f-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="40e2f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="40e2f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="40e2f-123">Element</span></span>|<span data-ttu-id="40e2f-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40e2f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40e2f-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="40e2f-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="40e2f-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="40e2f-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="40e2f-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="40e2f-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="40e2f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40e2f-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="40e2f-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="40e2f-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="40e2f-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="40e2f-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="40e2f-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="40e2f-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="40e2f-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="40e2f-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="40e2f-133">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="40e2f-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
