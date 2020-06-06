---
title: Elemento <remove> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: 991ad0eb9c04c27ded4d566115107ac7b47a71e1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252344"
---
# <a name="remove-element-for-namedcaches"></a><span data-ttu-id="2393d-102">Elemento \<remove> per \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="2393d-102">\<remove> Element for \<namedCaches></span></span>
<span data-ttu-id="2393d-103">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="2393d-103">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**  
  
## <a name="syntax"></a><span data-ttu-id="2393d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2393d-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="2393d-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="2393d-105">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2393d-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2393d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2393d-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2393d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2393d-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="2393d-108">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="2393d-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2393d-109">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="2393d-110">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2393d-110">Parent Elements</span></span>  
  
|<span data-ttu-id="2393d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2393d-111">Element</span></span>|<span data-ttu-id="2393d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2393d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="2393d-113">Contiene una raccolta di impostazioni di configurazione per le istanze denominate <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="2393d-113">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2393d-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="2393d-114">Remarks</span></span>  
 <span data-ttu-id="2393d-115">L' `remove` elemento rimuove una `namedCache` voce dalla raccolta di cache denominata per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="2393d-115">The `remove` element removes a `namedCache` entry from the named cache collection for a memory cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2393d-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2393d-116">See also</span></span>

- [<span data-ttu-id="2393d-117">\<namedCaches>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="2393d-117">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
