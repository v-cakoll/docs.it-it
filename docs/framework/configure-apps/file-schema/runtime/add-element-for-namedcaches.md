---
title: Elemento <add> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154505"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="4c089-102">Elemento \<add> per \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="4c089-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="4c089-103">Aggiunge una `namedCache` voce alla `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="4c089-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="4c089-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c089-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="4c089-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="4c089-105">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c089-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4c089-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4c089-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4c089-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c089-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="4c089-108">Attributes</span></span>  
  
|<span data-ttu-id="4c089-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="4c089-109">Attribute</span></span>|<span data-ttu-id="4c089-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c089-110">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="4c089-111">Valore intero che specifica le dimensioni massime consentite (in megabyte) che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="4c089-111">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="4c089-112">Il valore predefinito è 0, che indica che <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="4c089-112">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="4c089-113">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="4c089-113">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="4c089-114">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="4c089-114">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="4c089-115">Il valore predefinito è 0, che indica che <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="4c089-115">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="4c089-116">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="4c089-116">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="4c089-117">Questo valore viene immesso nel formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="4c089-117">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c089-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4c089-118">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="4c089-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4c089-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4c089-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c089-120">Element</span></span>|<span data-ttu-id="4c089-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c089-121">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="4c089-122">Contiene una raccolta di impostazioni di configurazione per le istanze denominate <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="4c089-122">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c089-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="4c089-123">Remarks</span></span>  
 <span data-ttu-id="4c089-124">L' `add` elemento aggiunge una voce alla `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="4c089-124">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="4c089-125">È possibile utilizzare l'elemento [Clear](clear-element-for-namedcaches.md) prima di utilizzare l' `add` elemento per verificare che non siano presenti altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="4c089-125">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="4c089-126">Questo elemento può essere utilizzato nel file Machine. config e nel file Web. config.</span><span class="sxs-lookup"><span data-stu-id="4c089-126">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c089-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c089-127">Example</span></span>  
 <span data-ttu-id="4c089-128">Nell'esempio seguente viene illustrato come definire le impostazioni per la `namedCache` voce predefinita della `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="4c089-128">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c089-129">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="4c089-129">See also</span></span>

- [<span data-ttu-id="4c089-130">\<namedCaches>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="4c089-130">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
