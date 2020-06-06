---
title: Elemento <clear> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252751"
---
# <a name="clear-element-for-namedcaches"></a><span data-ttu-id="d7587-102">Elemento \<clear> per \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="d7587-102">\<clear> Element for \<namedCaches></span></span>
<span data-ttu-id="d7587-103">Cancella tutte le `namedCache` voci della `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="d7587-103">Clears all `namedCache` entries in the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**  
  
## <a name="syntax"></a><span data-ttu-id="d7587-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7587-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="d7587-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="d7587-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7587-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d7587-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d7587-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d7587-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7587-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="d7587-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="d7587-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d7587-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="d7587-110">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d7587-110">Parent Elements</span></span>  
  
|<span data-ttu-id="d7587-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7587-111">Element</span></span>|<span data-ttu-id="d7587-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7587-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="d7587-113">Contiene una raccolta di impostazioni di configurazione per le istanze denominate <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="d7587-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7587-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="d7587-114">Remarks</span></span>  
 <span data-ttu-id="d7587-115">L' `clear` elemento Cancella tutte le `namedCache` voci della raccolta cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="d7587-115">The `clear` element clears all `namedCache` entries in the named cache collection for a memory cache.</span></span> <span data-ttu-id="d7587-116">È possibile utilizzare l' `clear` elemento prima di utilizzare l' `add` elemento per aggiungere una nuova voce della cache denominata per assicurarsi che non vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="d7587-116">You can use the `clear` element before you use the `add` element to add a new named cache entry in order to be certain there are no other named caches in the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7587-117">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d7587-117">See also</span></span>

- [<span data-ttu-id="d7587-118">\<namedCaches>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="d7587-118">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
