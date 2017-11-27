---
title: '&lt;deselezionare&gt; elemento per &lt;namedCaches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0819141b2135a2de99a2801a1888f7b0e1cd19fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcleargt-element-for-ltnamedcachesgt"></a><span data-ttu-id="52d55-102">&lt;deselezionare&gt; elemento per &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="52d55-102">&lt;clear&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="52d55-103">Cancella tutti `namedCache` voci di `namedCaches` insieme per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="52d55-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="52d55-104">\<Caching ></span><span class="sxs-lookup"><span data-stu-id="52d55-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="52d55-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="52d55-105">\<memoryCache></span></span>  
<span data-ttu-id="52d55-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="52d55-106">\<namedCaches></span></span>  
<span data-ttu-id="52d55-107">\<add></span><span class="sxs-lookup"><span data-stu-id="52d55-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d55-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52d55-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="52d55-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="52d55-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52d55-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="52d55-110">Attributes and Elements</span></span>  
 <span data-ttu-id="52d55-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="52d55-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52d55-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="52d55-112">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="52d55-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="52d55-113">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="52d55-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="52d55-114">Parent Elements</span></span>  
  
|<span data-ttu-id="52d55-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="52d55-115">Element</span></span>|<span data-ttu-id="52d55-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52d55-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52d55-117">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="52d55-117">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="52d55-118">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="52d55-118">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52d55-119">Note</span><span class="sxs-lookup"><span data-stu-id="52d55-119">Remarks</span></span>  
 <span data-ttu-id="52d55-120">Il `clear` elemento cancella tutti `namedCache` voci nella raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="52d55-120">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="52d55-121">È possibile utilizzare il `clear` elemento prima di utilizzare il `add` elemento per aggiungere una nuova voce di cache denominata per essere certi che vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="52d55-121">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d55-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52d55-122">See Also</span></span>  
 [<span data-ttu-id="52d55-123">\<namedCaches > Element (Cache Settings)</span><span class="sxs-lookup"><span data-stu-id="52d55-123">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
