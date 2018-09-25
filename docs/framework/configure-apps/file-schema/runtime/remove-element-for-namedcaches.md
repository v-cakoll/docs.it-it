---
title: '&lt;rimuovere&gt; (elemento) per &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f885416629ae58949cc688f4e6fbd41e77e872aa
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47071727"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a><span data-ttu-id="4771c-102">&lt;rimuovere&gt; (elemento) per &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="4771c-102">&lt;remove&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="4771c-103">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="4771c-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="4771c-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="4771c-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="4771c-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="4771c-105">\<memoryCache></span></span>  
<span data-ttu-id="4771c-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="4771c-106">\<namedCaches></span></span>  
<span data-ttu-id="4771c-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="4771c-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4771c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4771c-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="4771c-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="4771c-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4771c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4771c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4771c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4771c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4771c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4771c-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="4771c-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4771c-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="4771c-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4771c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4771c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4771c-115">Element</span></span>|<span data-ttu-id="4771c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4771c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4771c-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="4771c-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="4771c-118">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="4771c-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4771c-119">Note</span><span class="sxs-lookup"><span data-stu-id="4771c-119">Remarks</span></span>  
 <span data-ttu-id="4771c-120">Il `remove` elemento consente di rimuovere un `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="4771c-120">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4771c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4771c-121">See Also</span></span>  
 [<span data-ttu-id="4771c-122">\<namedCaches > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="4771c-122">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
