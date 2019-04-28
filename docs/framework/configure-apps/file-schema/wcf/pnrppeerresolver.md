---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 2404f00b2a3ba03e89c1e21fb25e13cabb8feed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783279"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="58831-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="58831-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="58831-102">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="58831-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="58831-103">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="58831-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="58831-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="58831-104">\<system.serviceModel></span></span>  
<span data-ttu-id="58831-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="58831-105">\<bindings></span></span>  
<span data-ttu-id="58831-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="58831-106">\<customBinding></span></span>  
<span data-ttu-id="58831-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="58831-107">\<binding></span></span>  
<span data-ttu-id="58831-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="58831-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58831-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58831-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58831-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58831-110">Attributes and Elements</span></span>  
 <span data-ttu-id="58831-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58831-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58831-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="58831-112">Attributes</span></span>  
  
|<span data-ttu-id="58831-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="58831-113">Attribute</span></span>|<span data-ttu-id="58831-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58831-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58831-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="58831-115">resolverType</span></span>|<span data-ttu-id="58831-116">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="58831-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="58831-117">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="58831-117">This attribute is optional.</span></span> <span data-ttu-id="58831-118">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="58831-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58831-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58831-119">Child Elements</span></span>  
 <span data-ttu-id="58831-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="58831-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58831-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58831-121">Parent Elements</span></span>  
  
|<span data-ttu-id="58831-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="58831-122">Element</span></span>|<span data-ttu-id="58831-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58831-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58831-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="58831-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="58831-125">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="58831-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="58831-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="58831-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="58831-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58831-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="58831-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="58831-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="58831-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="58831-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="58831-130">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="58831-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="58831-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="58831-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="58831-132">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="58831-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
