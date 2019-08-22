---
title: Elemento <remove> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663480"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="aee70-102">\<Rimuovi elemento > per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="aee70-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="aee70-103">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="aee70-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="aee70-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="aee70-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="aee70-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="aee70-105">\<memoryCache></span></span>  
<span data-ttu-id="aee70-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="aee70-106">\<namedCaches></span></span>  
<span data-ttu-id="aee70-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="aee70-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee70-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aee70-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="aee70-109">Type</span><span class="sxs-lookup"><span data-stu-id="aee70-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aee70-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="aee70-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aee70-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="aee70-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aee70-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="aee70-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="aee70-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="aee70-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="aee70-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="aee70-114">Parent Elements</span></span>  
  
|<span data-ttu-id="aee70-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="aee70-115">Element</span></span>|<span data-ttu-id="aee70-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aee70-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aee70-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="aee70-117">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="aee70-118">Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="aee70-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aee70-119">Note</span><span class="sxs-lookup"><span data-stu-id="aee70-119">Remarks</span></span>  
 <span data-ttu-id="aee70-120">L' `remove` elemento rimuove una `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="aee70-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee70-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee70-121">See also</span></span>

- [<span data-ttu-id="aee70-122">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="aee70-122">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
