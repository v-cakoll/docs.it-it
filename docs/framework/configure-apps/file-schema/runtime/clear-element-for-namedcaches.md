---
title: Elemento <clear> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658857"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="325af-102">\<Cancella > elemento per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="325af-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="325af-103">Cancella tutte `namedCache` le voci della `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="325af-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="325af-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="325af-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="325af-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="325af-105">\<memoryCache></span></span>  
<span data-ttu-id="325af-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="325af-106">\<namedCaches></span></span>  
<span data-ttu-id="325af-107">\<add></span><span class="sxs-lookup"><span data-stu-id="325af-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325af-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="325af-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="325af-109">Type</span><span class="sxs-lookup"><span data-stu-id="325af-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="325af-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="325af-110">Attributes and Elements</span></span>  
 <span data-ttu-id="325af-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="325af-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="325af-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="325af-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="325af-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="325af-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="325af-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="325af-114">Parent Elements</span></span>  
  
|<span data-ttu-id="325af-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="325af-115">Element</span></span>|<span data-ttu-id="325af-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="325af-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="325af-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="325af-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="325af-118">Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="325af-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="325af-119">Note</span><span class="sxs-lookup"><span data-stu-id="325af-119">Remarks</span></span>  
 <span data-ttu-id="325af-120">L' `clear` elemento Cancella tutte le `namedCache` voci della raccolta cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="325af-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="325af-121">È possibile utilizzare l' `clear` elemento prima di utilizzare l' `add` elemento per aggiungere una nuova voce della cache denominata per assicurarsi che non vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="325af-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325af-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="325af-122">See also</span></span>

- [<span data-ttu-id="325af-123">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="325af-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
