---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738774"
---
# \<pnrpPeerResolver>
<span data-ttu-id="54dfa-101">Specifica l'uso di PNRP (Peer Name Resolution Protocol) come resolver.</span><span class="sxs-lookup"><span data-stu-id="54dfa-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="54dfa-102">Questo elemento è facoltativo perché PNRP è il resolver predefinito.</span><span class="sxs-lookup"><span data-stu-id="54dfa-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="54dfa-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54dfa-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54dfa-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="54dfa-104">Attributes and Elements</span></span>  
 <span data-ttu-id="54dfa-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="54dfa-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54dfa-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="54dfa-106">Attributes</span></span>  
  
|<span data-ttu-id="54dfa-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="54dfa-107">Attribute</span></span>|<span data-ttu-id="54dfa-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54dfa-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54dfa-109">resolverType</span><span class="sxs-lookup"><span data-stu-id="54dfa-109">resolverType</span></span>|<span data-ttu-id="54dfa-110">Stringa che specifica il resolver da usare.</span><span class="sxs-lookup"><span data-stu-id="54dfa-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="54dfa-111">L'attributo è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="54dfa-111">This attribute is optional.</span></span> <span data-ttu-id="54dfa-112">Se non è impostato o se è impostato su una stringa vuota, viene usato PNRP.</span><span class="sxs-lookup"><span data-stu-id="54dfa-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54dfa-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="54dfa-113">Child Elements</span></span>  
 <span data-ttu-id="54dfa-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="54dfa-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54dfa-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="54dfa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="54dfa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="54dfa-116">Element</span></span>|<span data-ttu-id="54dfa-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54dfa-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="54dfa-118">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="54dfa-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="54dfa-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="54dfa-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="54dfa-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54dfa-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="54dfa-121">Binding</span><span class="sxs-lookup"><span data-stu-id="54dfa-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="54dfa-122">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="54dfa-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="54dfa-123">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="54dfa-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="54dfa-124">Resolver del peer</span><span class="sxs-lookup"><span data-stu-id="54dfa-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
