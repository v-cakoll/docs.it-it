---
title: Elemento <memoryCache> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 46f430f7cf112da40aa3b25bfb280c5014612eae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663615"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="9ffb0-102">\<Elemento > memoryCache (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="9ffb0-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="9ffb0-103">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="9ffb0-104">La classe <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> definisce un elemento [memoryCache](memorycache-element-cache-settings.md) che è possibile usare per configurare la cache.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="9ffb0-105">In una singola applicazione possono essere usate più istanze della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="9ffb0-106">Ogni elemento `memoryCache` nel file di configurazione può contenere le impostazioni per un'istanza denominata di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="9ffb0-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9ffb0-107">\<configuration></span></span>  
<span data-ttu-id="9ffb0-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="9ffb0-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="9ffb0-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="9ffb0-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ffb0-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ffb0-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="9ffb0-111">Type</span><span class="sxs-lookup"><span data-stu-id="9ffb0-111">Type</span></span>  
 <span data-ttu-id="9ffb0-112">Classe<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ffb0-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9ffb0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9ffb0-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ffb0-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="9ffb0-115">Attributes</span></span>  
  
|<span data-ttu-id="9ffb0-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="9ffb0-116">Attribute</span></span>|<span data-ttu-id="9ffb0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ffb0-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="9ffb0-118">La dimensione massima di memoria, in megabyte, che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="9ffb0-119">Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="9ffb0-120">Nome della configurazione della cache.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="9ffb0-121">Percentuale di memoria fisica utilizzabile dalla cache.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="9ffb0-122">Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="9ffb0-123">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="9ffb0-124">Il valore viene inserito nel formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="9ffb0-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ffb0-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9ffb0-125">Child Elements</span></span>  
  
|<span data-ttu-id="9ffb0-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ffb0-126">Element</span></span>|<span data-ttu-id="9ffb0-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ffb0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ffb0-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="9ffb0-128">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="9ffb0-129">Contiene una raccolta di impostazioni di configurazione per l'istanza `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ffb0-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9ffb0-130">Parent Elements</span></span>  
  
|<span data-ttu-id="9ffb0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ffb0-131">Element</span></span>|<span data-ttu-id="9ffb0-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ffb0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ffb0-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="9ffb0-133">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="9ffb0-134">Contiene i tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni integrate nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-134">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ffb0-135">Note</span><span class="sxs-lookup"><span data-stu-id="9ffb0-135">Remarks</span></span>  
 <span data-ttu-id="9ffb0-136">La classe <xref:System.Runtime.Caching.MemoryCache> è un'implementazione concreta della classe astratta <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="9ffb0-137">Alle istanze della classe <xref:System.Runtime.Caching.MemoryCache> possono essere fornite le informazioni di configurazione dei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="9ffb0-138">La sezione [memoryCache](memorycache-element-cache-settings.md) della configurazione contiene una raccolta di configurazioni `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-138">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="9ffb0-139">Quando viene inizializzato un oggetto cache basato sulla memoria, esso tenta innanzitutto di trovare una voce `namedCaches` che corrisponde al nome nel parametro che viene passato al costruttore della cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="9ffb0-140">Se viene trovata una voce `namedCaches` , le informazioni di polling e di gestione della memoria vengono recuperate dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="9ffb0-141">Il processo di inizializzazione determina quindi se è stato eseguito l'override di qualche voce di configurazione usando la raccolta facoltativa di coppie nome-valore delle informazioni di configurazione nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="9ffb0-142">Se viene passato uno qualsiasi dei seguenti valori nella raccolta di coppie nome-valore, questi valori eseguono l'override delle informazioni ottenute dal file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="9ffb0-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="9ffb0-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ffb0-143">Example</span></span>  
 <span data-ttu-id="9ffb0-144">Nell'esempio seguente viene illustrato come impostare il nome dell' <xref:System.Runtime.Caching.MemoryCache> oggetto sul nome dell'oggetto cache predefinito impostando l' `name` attributo su "default".</span><span class="sxs-lookup"><span data-stu-id="9ffb0-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="9ffb0-145">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryLimitPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="9ffb0-146">Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="9ffb0-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="9ffb0-147">L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.</span><span class="sxs-lookup"><span data-stu-id="9ffb0-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9ffb0-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ffb0-148">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="9ffb0-149">\<System. Runtime. Caching elemento > (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="9ffb0-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="9ffb0-150">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="9ffb0-150">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
