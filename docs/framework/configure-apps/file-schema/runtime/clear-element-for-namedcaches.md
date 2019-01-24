---
title: '&lt;deselezionare&gt; (elemento) per &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ea860c185d68a24c31ec24de4a087b9b98fe791f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727807"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="204bd-102">&lt;deselezionare&gt; (elemento) per &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="204bd-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="204bd-103">Cancella tutto `namedCache` voci il `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="204bd-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="204bd-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="204bd-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="204bd-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="204bd-105">\<memoryCache></span></span>  
<span data-ttu-id="204bd-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="204bd-106">\<namedCaches></span></span>  
<span data-ttu-id="204bd-107">\<add></span><span class="sxs-lookup"><span data-stu-id="204bd-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="204bd-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="204bd-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="204bd-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="204bd-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="204bd-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="204bd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="204bd-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="204bd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="204bd-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="204bd-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="204bd-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="204bd-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="204bd-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="204bd-114">Parent Elements</span></span>  
  
|<span data-ttu-id="204bd-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="204bd-115">Element</span></span>|<span data-ttu-id="204bd-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="204bd-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="204bd-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="204bd-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="204bd-118">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="204bd-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="204bd-119">Note</span><span class="sxs-lookup"><span data-stu-id="204bd-119">Remarks</span></span>  
 <span data-ttu-id="204bd-120">Il `clear` elemento cancellato tutto `namedCache` voci della raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="204bd-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="204bd-121">È possibile usare la `clear` elemento prima di usare il `add` elemento a cui aggiungere una nuova voce di cache denominata per essere certi che vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="204bd-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="204bd-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="204bd-122">See also</span></span>
- [<span data-ttu-id="204bd-123">\<namedCaches > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="204bd-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
