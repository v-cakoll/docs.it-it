---
title: Elemento <namedCaches> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153958"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="fd0f2-102">Elemento \<namedCaches> (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="fd0f2-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="fd0f2-103">Specifica una raccolta di impostazioni di configurazione per le istanze denominate <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="fd0f2-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="fd0f2-104">La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> proprietà fa riferimento alla raccolta di impostazioni di configurazione da uno o più `namedCaches` elementi del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a><span data-ttu-id="fd0f2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd0f2-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="fd0f2-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="fd0f2-106">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd0f2-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fd0f2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fd0f2-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd0f2-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="fd0f2-109">Attributes</span></span>  
  
|<span data-ttu-id="fd0f2-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="fd0f2-110">Attribute</span></span>|<span data-ttu-id="fd0f2-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f2-111">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="fd0f2-112">Valore intero che specifica le dimensioni massime consentite, in megabyte, che un'istanza di un oggetto <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-112">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="fd0f2-113">Il valore predefinito è 0, che indica che <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di dimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-113">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="fd0f2-114">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-114">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="fd0f2-115">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-115">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="fd0f2-116">Il valore predefinito è 0, che indica che <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di dimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-116">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="fd0f2-117">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-117">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="fd0f2-118">Questo valore viene immesso nel formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="fd0f2-118">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd0f2-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fd0f2-119">Child Elements</span></span>  
  
|<span data-ttu-id="fd0f2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd0f2-120">Element</span></span>|<span data-ttu-id="fd0f2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f2-121">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|<span data-ttu-id="fd0f2-122">Aggiunge una cache denominata alla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-122">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[\<clear>](clear-element-for-namedcaches.md)|<span data-ttu-id="fd0f2-123">Cancella la raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-123">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[\<remove>](remove-element-for-namedcaches.md)|<span data-ttu-id="fd0f2-124">Rimuove una cache denominata dalla raccolta `namedCaches` per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-124">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd0f2-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fd0f2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fd0f2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="fd0f2-126">Element</span></span>|<span data-ttu-id="fd0f2-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd0f2-127">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="fd0f2-128">Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-128">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="fd0f2-129">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="fd0f2-129">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="fd0f2-130">Contiene i tipi che consentono di implementare la memorizzazione nella cache di output nelle applicazioni integrate nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0f2-131">Commenti</span><span class="sxs-lookup"><span data-stu-id="fd0f2-131">Remarks</span></span>  
 <span data-ttu-id="fd0f2-132">La sezione di configurazione della cache in memoria del file Web. config può contenere `add` `remove` `clear` gli attributi, e per la `namedCaches` raccolta.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-132">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="fd0f2-133">Ogni `namedCaches` voce viene identificata in modo univoco dall' `name` attributo.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-133">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="fd0f2-134">È possibile recuperare le istanze delle voci della cache di memoria facendo riferimento alle informazioni nei file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-134">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="fd0f2-135">Per impostazione predefinita, solo l'istanza della cache predefinita include una voce nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-135">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="fd0f2-136">L'istanza della cache predefinita è l'istanza restituita dalla <xref:System.Runtime.Caching.MemoryCache.Default%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-136">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="fd0f2-137">Se si imposta l'attributo Name su "default", l'elemento utilizza l'istanza della cache di memoria predefinita.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-137">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd0f2-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd0f2-138">Example</span></span>  
 <span data-ttu-id="fd0f2-139">Nell'esempio seguente viene illustrato come impostare il nome della cache sul nome della voce della cache predefinita impostando l' `name` attributo su "default".</span><span class="sxs-lookup"><span data-stu-id="fd0f2-139">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="fd0f2-140">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-140">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="fd0f2-141">L'impostazione di questi attributi su zero indica che vengono utilizzate le euristiche di dimensionamento automatico della <xref:System.Runtime.Caching.MemoryCache> classe.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-141">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="fd0f2-142">L'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria assoluti e in percentuale ogni due minuti.</span><span class="sxs-lookup"><span data-stu-id="fd0f2-142">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd0f2-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fd0f2-143">See also</span></span>

- [<span data-ttu-id="fd0f2-144">\<memoryCache>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="fd0f2-144">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
