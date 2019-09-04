---
title: Elemento <remove> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252344"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="19c21-102">\<Rimuovi elemento > per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="19c21-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="19c21-103">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="19c21-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="19c21-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19c21-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19c21-105">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="19c21-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="19c21-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> memoryCache**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="19c21-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="19c21-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> namedCaches**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="19c21-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="19c21-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Rimuovi >**</span><span class="sxs-lookup"><span data-stu-id="19c21-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c21-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19c21-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="19c21-110">Type</span><span class="sxs-lookup"><span data-stu-id="19c21-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19c21-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="19c21-111">Attributes and Elements</span></span>  
 <span data-ttu-id="19c21-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="19c21-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19c21-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="19c21-113">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="19c21-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="19c21-114">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="19c21-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="19c21-115">Parent Elements</span></span>  
  
|<span data-ttu-id="19c21-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="19c21-116">Element</span></span>|<span data-ttu-id="19c21-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19c21-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19c21-118">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="19c21-118">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="19c21-119">Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="19c21-119">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19c21-120">Note</span><span class="sxs-lookup"><span data-stu-id="19c21-120">Remarks</span></span>  
 <span data-ttu-id="19c21-121">L' `remove` elemento rimuove una `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="19c21-121">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c21-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19c21-122">See also</span></span>

- [<span data-ttu-id="19c21-123">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="19c21-123">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
