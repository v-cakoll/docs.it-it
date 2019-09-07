---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d7c6c8efa971fb60f0257cc1c74ceda72e31cb84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400041"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="ce083-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="ce083-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="ce083-102">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="ce083-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="ce083-103">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="ce083-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="ce083-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce083-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce083-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ce083-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ce083-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ce083-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ce083-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="ce083-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="ce083-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="ce083-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ce083-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> pnrpResolver**</span><span class="sxs-lookup"><span data-stu-id="ce083-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce083-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce083-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce083-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ce083-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce083-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ce083-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce083-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="ce083-113">Attributes</span></span>  
  
|<span data-ttu-id="ce083-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="ce083-114">Attribute</span></span>|<span data-ttu-id="ce083-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce083-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce083-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="ce083-116">resolverType</span></span>|<span data-ttu-id="ce083-117">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="ce083-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="ce083-118">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ce083-118">This attribute is optional.</span></span> <span data-ttu-id="ce083-119">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="ce083-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce083-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ce083-120">Child Elements</span></span>  
 <span data-ttu-id="ce083-121">Nessuna</span><span class="sxs-lookup"><span data-stu-id="ce083-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce083-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ce083-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ce083-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce083-123">Element</span></span>|<span data-ttu-id="ce083-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce083-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce083-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="ce083-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ce083-126">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ce083-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ce083-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce083-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="ce083-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce083-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ce083-129">Associazioni</span><span class="sxs-lookup"><span data-stu-id="ce083-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ce083-130">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="ce083-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ce083-131">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="ce083-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ce083-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ce083-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="ce083-133">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="ce083-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
