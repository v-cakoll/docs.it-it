---
title: Elemento <memoryCache> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 94c21e0408b7616bf0c8a24267b72bfa7cc3aaa0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153984"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="c4b6f-102">Elemento \<memoryCache> (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="c4b6f-102">\<memoryCache> Element (Cache Settings)</span></span>
<span data-ttu-id="c4b6f-103">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-103">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="c4b6f-104">La classe <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> definisce un elemento [memoryCache](memorycache-element-cache-settings.md) che è possibile usare per configurare la cache.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="c4b6f-105">In una singola applicazione possono essere usate più istanze della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-105">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="c4b6f-106">Ogni elemento `memoryCache` nel file di configurazione può contenere le impostazioni per un'istanza denominata di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-106">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a><span data-ttu-id="c4b6f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4b6f-107">Syntax</span></span>  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="c4b6f-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="c4b6f-108">Type</span></span>  
 <span data-ttu-id="c4b6f-109">Classe<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-109"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4b6f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c4b6f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c4b6f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4b6f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c4b6f-112">Attributes</span></span>  
  
|<span data-ttu-id="c4b6f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c4b6f-113">Attribute</span></span>|<span data-ttu-id="c4b6f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4b6f-114">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="c4b6f-115">La dimensione massima di memoria, in megabyte, che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-115">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="c4b6f-116">Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="c4b6f-117">Nome della configurazione della cache.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-117">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="c4b6f-118">Percentuale di memoria fisica utilizzabile dalla cache.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-118">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="c4b6f-119">Il valore predefinito è 0 e significa che vengono usate per impostazione predefinita le euristiche di dimensionamento automatico della classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="c4b6f-120">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="c4b6f-121">Il valore viene inserito nel formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="c4b6f-121">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4b6f-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c4b6f-122">Child Elements</span></span>  
  
|<span data-ttu-id="c4b6f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4b6f-123">Element</span></span>|<span data-ttu-id="c4b6f-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4b6f-124">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="c4b6f-125">Contiene una raccolta di impostazioni di configurazione per l'istanza `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-125">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4b6f-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c4b6f-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c4b6f-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4b6f-127">Element</span></span>|<span data-ttu-id="c4b6f-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4b6f-128">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="c4b6f-129">Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-129">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="c4b6f-130">Contiene i tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni integrate nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4b6f-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="c4b6f-131">Remarks</span></span>  
 <span data-ttu-id="c4b6f-132">La classe <xref:System.Runtime.Caching.MemoryCache> è un'implementazione concreta della classe astratta <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-132">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="c4b6f-133">Alle istanze della classe <xref:System.Runtime.Caching.MemoryCache> possono essere fornite le informazioni di configurazione dei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-133">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="c4b6f-134">La sezione [memoryCache](memorycache-element-cache-settings.md) della configurazione contiene una raccolta di configurazioni `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-134">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="c4b6f-135">Quando viene inizializzato un oggetto cache basato sulla memoria, esso tenta innanzitutto di trovare una voce `namedCaches` che corrisponde al nome nel parametro che viene passato al costruttore della cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-135">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="c4b6f-136">Se viene trovata una voce `namedCaches` , le informazioni di polling e di gestione della memoria vengono recuperate dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-136">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="c4b6f-137">Il processo di inizializzazione determina quindi se è stato eseguito l'override di qualche voce di configurazione usando la raccolta facoltativa di coppie nome-valore delle informazioni di configurazione nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-137">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="c4b6f-138">Se viene passato uno qualsiasi dei seguenti valori nella raccolta di coppie nome-valore, questi valori eseguono l'override delle informazioni ottenute dal file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="c4b6f-138">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="c4b6f-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4b6f-139">Example</span></span>  
 <span data-ttu-id="c4b6f-140">Nell'esempio seguente viene illustrato come impostare il nome dell' <xref:System.Runtime.Caching.MemoryCache> oggetto sul nome dell'oggetto cache predefinito impostando l' `name` attributo su "default".</span><span class="sxs-lookup"><span data-stu-id="c4b6f-140">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="c4b6f-141">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryLimitPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-141">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="c4b6f-142">Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="c4b6f-142">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="c4b6f-143">L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-143">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c4b6f-144">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c4b6f-144">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="c4b6f-145">\<system.runtime.caching>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="c4b6f-145">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="c4b6f-146">\<namedCaches>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="c4b6f-146">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
