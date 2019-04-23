---
title: Elemento <remove> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 053e2776153489dfdd61547fdc039980646ae697
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229771"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="e79ee-102">\<rimuovere > (elemento) per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="e79ee-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="e79ee-103">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="e79ee-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="e79ee-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="e79ee-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="e79ee-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="e79ee-105">\<memoryCache></span></span>  
<span data-ttu-id="e79ee-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e79ee-106">\<namedCaches></span></span>  
<span data-ttu-id="e79ee-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="e79ee-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79ee-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e79ee-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e79ee-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="e79ee-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e79ee-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e79ee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e79ee-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e79ee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e79ee-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e79ee-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="e79ee-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e79ee-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="e79ee-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e79ee-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e79ee-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e79ee-115">Element</span></span>|<span data-ttu-id="e79ee-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e79ee-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e79ee-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e79ee-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="e79ee-118">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="e79ee-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e79ee-119">Note</span><span class="sxs-lookup"><span data-stu-id="e79ee-119">Remarks</span></span>  
 <span data-ttu-id="e79ee-120">Il `remove` elemento consente di rimuovere un `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="e79ee-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79ee-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e79ee-121">See also</span></span>

- [<span data-ttu-id="e79ee-122">\<namedCaches > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="e79ee-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
