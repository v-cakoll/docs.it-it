---
title: Elemento <memoryCache> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 9ed3c290c3d4836eb783348b559cab46a38b2063
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592681"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="6684b-102">\<memoryCache > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="6684b-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="6684b-103">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="6684b-104">La classe <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> definisce un elemento [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) che è possibile usare per configurare la cache.</span><span class="sxs-lookup"><span data-stu-id="6684b-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="6684b-105">In una singola applicazione possono essere usate più istanze della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="6684b-106">Ogni elemento `memoryCache` nel file di configurazione può contenere le impostazioni per un'istanza denominata di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
 <span data-ttu-id="6684b-107">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6684b-107">\<configuration></span></span>  
<span data-ttu-id="6684b-108">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="6684b-108">\<system.runtime.caching></span></span>  
<span data-ttu-id="6684b-109">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="6684b-109">\<memoryCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6684b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6684b-110">Syntax</span></span>  
  
```xml  
<memoryCache>   
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>   
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="6684b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="6684b-111">Type</span></span>  
 <span data-ttu-id="6684b-112">Classe<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-112"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6684b-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6684b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6684b-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6684b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6684b-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="6684b-115">Attributes</span></span>  
  
|<span data-ttu-id="6684b-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="6684b-116">Attribute</span></span>|<span data-ttu-id="6684b-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6684b-117">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="6684b-118">La dimensione massima di memoria, in megabyte, che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="6684b-118">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="6684b-119">Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="6684b-120">Nome della configurazione della cache.</span><span class="sxs-lookup"><span data-stu-id="6684b-120">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="6684b-121">Percentuale di memoria fisica utilizzabile dalla cache.</span><span class="sxs-lookup"><span data-stu-id="6684b-121">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="6684b-122">Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-122">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="6684b-123">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="6684b-123">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="6684b-124">Il valore viene inserito nel formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="6684b-124">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6684b-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6684b-125">Child Elements</span></span>  
  
|<span data-ttu-id="6684b-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6684b-126">Element</span></span>|<span data-ttu-id="6684b-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6684b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6684b-128">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="6684b-128">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="6684b-129">Contiene una raccolta di impostazioni di configurazione per l'istanza `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="6684b-129">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6684b-130">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6684b-130">Parent Elements</span></span>  
  
|<span data-ttu-id="6684b-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="6684b-131">Element</span></span>|<span data-ttu-id="6684b-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6684b-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6684b-133">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="6684b-133">\<system.runtime.caching></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="6684b-134">Contiene tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni integrate in [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6684b-134">Contains types that let you implement output caching in applications that are built into the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6684b-135">Note</span><span class="sxs-lookup"><span data-stu-id="6684b-135">Remarks</span></span>  
 <span data-ttu-id="6684b-136">La classe <xref:System.Runtime.Caching.MemoryCache> è un'implementazione concreta della classe astratta <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-136">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="6684b-137">Alle istanze della classe <xref:System.Runtime.Caching.MemoryCache> possono essere fornite le informazioni di configurazione dei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6684b-137">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="6684b-138">La sezione [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) della configurazione contiene una raccolta di configurazioni `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="6684b-138">The [memoryCache](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="6684b-139">Quando viene inizializzato un oggetto cache basato sulla memoria, esso tenta innanzitutto di trovare una voce `namedCaches` che corrisponde al nome nel parametro che viene passato al costruttore della cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="6684b-139">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="6684b-140">Se viene trovata una voce `namedCaches` , le informazioni di polling e di gestione della memoria vengono recuperate dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6684b-140">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="6684b-141">Il processo di inizializzazione determina quindi se è stato eseguito l'override di qualche voce di configurazione usando la raccolta facoltativa di coppie nome-valore delle informazioni di configurazione nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="6684b-141">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="6684b-142">Se viene passato uno qualsiasi dei seguenti valori nella raccolta di coppie nome-valore, questi valori eseguono l'override delle informazioni ottenute dal file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="6684b-142">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="6684b-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="6684b-143">Example</span></span>  
 <span data-ttu-id="6684b-144">L'esempio seguente illustra come impostare il nome dell'oggetto <xref:System.Runtime.Caching.MemoryCache> sul nome dell'oggetto cache predefinito impostando l'attributo `name` "default".</span><span class="sxs-lookup"><span data-stu-id="6684b-144">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="6684b-145">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryLimitPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="6684b-145">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="6684b-146">Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6684b-146">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="6684b-147">L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.</span><span class="sxs-lookup"><span data-stu-id="6684b-147">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6684b-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6684b-148">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="6684b-149">\<Caching > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="6684b-149">\<system.runtime.caching> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="6684b-150">\<namedCaches > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="6684b-150">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
