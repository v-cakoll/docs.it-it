---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: e7e82117304ac133e5e84c0fc36b987560bcef96
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933804"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="5feed-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="5feed-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="5feed-102">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="5feed-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="5feed-103">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="5feed-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="5feed-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5feed-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5feed-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="5feed-105">\<bindings></span></span>  
<span data-ttu-id="5feed-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5feed-106">\<customBinding></span></span>  
<span data-ttu-id="5feed-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5feed-107">\<binding></span></span>  
<span data-ttu-id="5feed-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="5feed-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5feed-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5feed-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5feed-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5feed-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5feed-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5feed-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5feed-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5feed-112">Attributes</span></span>  
  
|<span data-ttu-id="5feed-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="5feed-113">Attribute</span></span>|<span data-ttu-id="5feed-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5feed-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5feed-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="5feed-115">resolverType</span></span>|<span data-ttu-id="5feed-116">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="5feed-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="5feed-117">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5feed-117">This attribute is optional.</span></span> <span data-ttu-id="5feed-118">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="5feed-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5feed-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5feed-119">Child Elements</span></span>  
 <span data-ttu-id="5feed-120">Nessuna</span><span class="sxs-lookup"><span data-stu-id="5feed-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5feed-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5feed-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5feed-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5feed-122">Element</span></span>|<span data-ttu-id="5feed-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5feed-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5feed-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="5feed-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="5feed-125">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5feed-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5feed-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="5feed-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5feed-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5feed-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5feed-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5feed-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5feed-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="5feed-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5feed-130">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5feed-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5feed-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5feed-131">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="5feed-132">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="5feed-132">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
