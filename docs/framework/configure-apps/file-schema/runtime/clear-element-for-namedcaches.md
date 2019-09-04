---
title: Elemento <clear> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252751"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="73f61-102">\<Cancella > elemento per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="73f61-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="73f61-103">Cancella tutte `namedCache` le voci della `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="73f61-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="73f61-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73f61-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73f61-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73f61-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="73f61-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> memoryCache**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73f61-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="73f61-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> namedCaches**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73f61-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="73f61-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Cancella >**</span><span class="sxs-lookup"><span data-stu-id="73f61-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f61-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73f61-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="73f61-110">Type</span><span class="sxs-lookup"><span data-stu-id="73f61-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73f61-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="73f61-111">Attributes and Elements</span></span>  
 <span data-ttu-id="73f61-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="73f61-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73f61-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="73f61-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="73f61-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="73f61-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="73f61-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="73f61-115">Parent Elements</span></span>  
  
|<span data-ttu-id="73f61-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="73f61-116">Element</span></span>|<span data-ttu-id="73f61-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="73f61-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73f61-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="73f61-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="73f61-119">Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="73f61-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73f61-120">Note</span><span class="sxs-lookup"><span data-stu-id="73f61-120">Remarks</span></span>  
 <span data-ttu-id="73f61-121">L' `clear` elemento Cancella tutte le `namedCache` voci della raccolta cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="73f61-121">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="73f61-122">È possibile utilizzare l' `clear` elemento prima di utilizzare l' `add` elemento per aggiungere una nuova voce della cache denominata per assicurarsi che non vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="73f61-122">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f61-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73f61-123">See also</span></span>

- [<span data-ttu-id="73f61-124">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="73f61-124">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
