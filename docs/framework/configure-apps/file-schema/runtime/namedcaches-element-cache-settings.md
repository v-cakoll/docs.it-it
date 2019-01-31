---
title: Elemento <namedCaches> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 1dedd3ca192b5fb0ee561ce138f0948c52581f89
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287482"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="72a12-102">\<namedCaches > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="72a12-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="72a12-103">Specifica una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="72a12-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="72a12-104">Il <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta di impostazioni di configurazione da uno o più `namedCaches` gli elementi del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="72a12-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="72a12-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="72a12-105">\<configuration></span></span>  
<span data-ttu-id="72a12-106">\< system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="72a12-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="72a12-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="72a12-107">\<memoryCache></span></span>  
<span data-ttu-id="72a12-108">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="72a12-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72a12-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72a12-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="72a12-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="72a12-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72a12-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="72a12-111">Attributes and Elements</span></span>  
 <span data-ttu-id="72a12-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="72a12-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72a12-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="72a12-113">Attributes</span></span>  
  
|<span data-ttu-id="72a12-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="72a12-114">Attribute</span></span>|<span data-ttu-id="72a12-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72a12-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="72a12-116">Valore intero che specifica la dimensione massima consentita, in megabyte, che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="72a12-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="72a12-117">Il valore predefinito è 0, che significa che le euristiche di ridimensionamento automatico del <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="72a12-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="72a12-118">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="72a12-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="72a12-119">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer fisicamente installati che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="72a12-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="72a12-120">Il valore predefinito è 0, che significa che le euristiche di ridimensionamento automatico del <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="72a12-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="72a12-121">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="72a12-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="72a12-122">Questo valore viene immesso nel formato "Hh".</span><span class="sxs-lookup"><span data-stu-id="72a12-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72a12-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="72a12-123">Child Elements</span></span>  
  
|<span data-ttu-id="72a12-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="72a12-124">Element</span></span>|<span data-ttu-id="72a12-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72a12-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72a12-126">\<add></span><span class="sxs-lookup"><span data-stu-id="72a12-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="72a12-127">Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="72a12-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="72a12-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="72a12-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="72a12-129">Cancella la raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="72a12-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="72a12-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="72a12-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="72a12-131">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="72a12-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72a12-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="72a12-132">Parent Elements</span></span>  
  
|<span data-ttu-id="72a12-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="72a12-133">Element</span></span>|<span data-ttu-id="72a12-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72a12-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72a12-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="72a12-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="72a12-136">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="72a12-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72a12-137">Note</span><span class="sxs-lookup"><span data-stu-id="72a12-137">Remarks</span></span>  
 <span data-ttu-id="72a12-138">La sezione di configurazione della memoria cache del file Web. config deve contenere `add`, `remove`, e `clear` gli attributi per il `namedCaches` raccolta.</span><span class="sxs-lookup"><span data-stu-id="72a12-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="72a12-139">Ciascuna `namedCaches` voce è identificata dal `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="72a12-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="72a12-140">È possibile recuperare le istanze di voci della cache di memoria facendo le informazioni nei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72a12-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="72a12-141">Per impostazione predefinita, solo l'istanza di cache predefinita include una voce nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="72a12-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="72a12-142">L'istanza di cache predefinita è l'istanza che viene restituito dal <xref:System.Runtime.Caching.MemoryCache.Default%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="72a12-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="72a12-143">Se si imposta l'attributo name su "default", l'elemento Usa l'istanza di cache di memoria predefinita.</span><span class="sxs-lookup"><span data-stu-id="72a12-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72a12-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="72a12-144">Example</span></span>  
 <span data-ttu-id="72a12-145">Nell'esempio seguente viene illustrato come impostare il nome della cache per il nome della voce della cache predefinita impostando la `name` attributo "default".</span><span class="sxs-lookup"><span data-stu-id="72a12-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="72a12-146">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="72a12-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="72a12-147">L'impostazione di questi attributi a zero indica che le euristiche di ridimensionamento automatico del <xref:System.Runtime.Caching.MemoryCache> classe vengono utilizzate.</span><span class="sxs-lookup"><span data-stu-id="72a12-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="72a12-148">L'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria in percentuale e assoluti ogni due minuti.</span><span class="sxs-lookup"><span data-stu-id="72a12-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72a12-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72a12-149">See also</span></span>
- [<span data-ttu-id="72a12-150">\<memoryCache > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="72a12-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
