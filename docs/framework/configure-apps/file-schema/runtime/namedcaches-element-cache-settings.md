---
title: Elemento <namedCaches> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252455"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="b6368-102">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="b6368-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="b6368-103">Specifica una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="b6368-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="b6368-104">La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta di impostazioni di configurazione da uno `namedCaches` o più elementi del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b6368-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="b6368-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6368-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6368-106">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b6368-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="b6368-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> memoryCache**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="b6368-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="b6368-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> namedCaches**</span><span class="sxs-lookup"><span data-stu-id="b6368-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6368-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6368-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="b6368-110">Type</span><span class="sxs-lookup"><span data-stu-id="b6368-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6368-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6368-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b6368-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6368-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6368-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6368-113">Attributes</span></span>  
  
|<span data-ttu-id="b6368-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="b6368-114">Attribute</span></span>|<span data-ttu-id="b6368-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b6368-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="b6368-116">Valore intero che specifica le dimensioni massime consentite, in megabyte, che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> oggetto può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="b6368-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="b6368-117">Il valore predefinito è 0, che indica che per impostazione predefinita vengono usate le euristiche di dimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe.</span><span class="sxs-lookup"><span data-stu-id="b6368-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="b6368-118">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="b6368-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="b6368-119">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="b6368-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="b6368-120">Il valore predefinito è 0, che indica che per impostazione predefinita vengono usate le euristiche di dimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe.</span><span class="sxs-lookup"><span data-stu-id="b6368-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="b6368-121">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="b6368-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="b6368-122">Questo valore viene immesso nel formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="b6368-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6368-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6368-123">Child Elements</span></span>  
  
|<span data-ttu-id="b6368-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6368-124">Element</span></span>|<span data-ttu-id="b6368-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6368-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6368-126">\<add></span><span class="sxs-lookup"><span data-stu-id="b6368-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="b6368-127">Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="b6368-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="b6368-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="b6368-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="b6368-129">Cancella la raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="b6368-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="b6368-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="b6368-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="b6368-131">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="b6368-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6368-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6368-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b6368-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6368-133">Element</span></span>|<span data-ttu-id="b6368-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6368-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6368-135">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b6368-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="b6368-136">Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6368-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="b6368-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="b6368-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="b6368-138">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="b6368-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="b6368-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="b6368-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="b6368-140">Contiene i tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni integrate nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6368-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6368-141">Note</span><span class="sxs-lookup"><span data-stu-id="b6368-141">Remarks</span></span>  
 <span data-ttu-id="b6368-142">La sezione di configurazione della cache in memoria del file Web. config `add`può `remove`contenere gli `clear` attributi, e `namedCaches` per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="b6368-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="b6368-143">Ogni `namedCaches` voce viene identificata `name` in modo univoco dall'attributo.</span><span class="sxs-lookup"><span data-stu-id="b6368-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="b6368-144">È possibile recuperare le istanze delle voci della cache di memoria facendo riferimento alle informazioni nei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b6368-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="b6368-145">Per impostazione predefinita, solo l'istanza della cache predefinita include una voce nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b6368-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="b6368-146">L'istanza della cache predefinita è l'istanza restituita dalla <xref:System.Runtime.Caching.MemoryCache.Default%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="b6368-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="b6368-147">Se si imposta l'attributo Name su "default", l'elemento utilizza l'istanza della cache di memoria predefinita.</span><span class="sxs-lookup"><span data-stu-id="b6368-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6368-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6368-148">Example</span></span>  
 <span data-ttu-id="b6368-149">Nell'esempio seguente viene illustrato come impostare il nome della cache sul nome della voce della cache predefinita impostando l' `name` attributo su "default".</span><span class="sxs-lookup"><span data-stu-id="b6368-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="b6368-150">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="b6368-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="b6368-151">L'impostazione di questi attributi su zero indica che vengono utilizzate le euristiche <xref:System.Runtime.Caching.MemoryCache> di dimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="b6368-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="b6368-152">L'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria assoluti e in percentuale ogni due minuti.</span><span class="sxs-lookup"><span data-stu-id="b6368-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6368-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6368-153">See also</span></span>

- [<span data-ttu-id="b6368-154">\<Elemento > memoryCache (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="b6368-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
