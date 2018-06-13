---
title: '&lt;deselezionare&gt; elemento per &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cdd6e4a4849a031dc6bcad909509498406fcb129
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745513"
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="b657c-102">&lt;deselezionare&gt; elemento per &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="b657c-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="b657c-103">Cancella tutti `namedCache` voci di `namedCaches` insieme per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="b657c-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="b657c-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="b657c-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="b657c-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="b657c-105">\<memoryCache></span></span>  
<span data-ttu-id="b657c-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="b657c-106">\<namedCaches></span></span>  
<span data-ttu-id="b657c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b657c-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b657c-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b657c-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="b657c-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b657c-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b657c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b657c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b657c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b657c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b657c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b657c-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="b657c-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b657c-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="b657c-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b657c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b657c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b657c-115">Element</span></span>|<span data-ttu-id="b657c-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b657c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b657c-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="b657c-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="b657c-118">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="b657c-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b657c-119">Note</span><span class="sxs-lookup"><span data-stu-id="b657c-119">Remarks</span></span>  
 <span data-ttu-id="b657c-120">Il `clear` elemento cancella tutti `namedCache` voci nella raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="b657c-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="b657c-121">È possibile utilizzare il `clear` elemento prima di utilizzare il `add` elemento per aggiungere una nuova voce di cache denominata per essere certi che vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="b657c-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b657c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b657c-122">See Also</span></span>  
 [<span data-ttu-id="b657c-123">\<namedCaches > Element (Cache Settings)</span><span class="sxs-lookup"><span data-stu-id="b657c-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
