---
title: Elemento <system.runtime.caching> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: 70573f92f1799a54116bc91f7a39d157a7ae5b36
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115510"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="e6c00-102">Elemento \<System. Runtime. Caching > (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="e6c00-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="e6c00-103">Fornisce la configurazione per l'implementazione predefinita in memoria <xref:System.Runtime.Caching.ObjectCache> tramite la voce `memoryCache` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e6c00-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
<span data-ttu-id="e6c00-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e6c00-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e6c00-105">&nbsp;&nbsp; **\<System. Runtime. caching >**</span><span class="sxs-lookup"><span data-stu-id="e6c00-105">&nbsp;&nbsp;**\<system.runtime.caching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6c00-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6c00-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6c00-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e6c00-107">Attributes and Elements</span></span>

<span data-ttu-id="e6c00-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e6c00-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6c00-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="e6c00-109">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="e6c00-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e6c00-110">Child Elements</span></span>

|<span data-ttu-id="e6c00-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6c00-111">Element</span></span>|<span data-ttu-id="e6c00-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6c00-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6c00-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="e6c00-113">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="e6c00-114">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e6c00-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6c00-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e6c00-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e6c00-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6c00-116">Element</span></span>|<span data-ttu-id="e6c00-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6c00-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6c00-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e6c00-118">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="e6c00-119">Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e6c00-119">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6c00-120">Note</span><span class="sxs-lookup"><span data-stu-id="e6c00-120">Remarks</span></span>

<span data-ttu-id="e6c00-121">Le classi in questo spazio dei nomi consentono di usare le funzionalità di memorizzazione nella cache come quelle in ASP.NET, ma senza una dipendenza sull'assembly `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="e6c00-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="e6c00-122">Per altre informazioni, vedere [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e6c00-122">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6c00-123">La funzionalità di memorizzazione nella cache di output e i tipi nello spazio dei nomi <xref:System.Runtime.Caching> sono una novità di .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e6c00-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6c00-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6c00-124">Example</span></span>

<span data-ttu-id="e6c00-125">L'esempio seguente illustra come configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e6c00-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="e6c00-126">L'esempio mostra come configurare un'istanza della voce `namedCaches` per la cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="e6c00-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="e6c00-127">Il nome della cache è impostato sul nome predefinito della voce della cache impostando l'attributo `name` su "default".</span><span class="sxs-lookup"><span data-stu-id="e6c00-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="e6c00-128">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="e6c00-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="e6c00-129">Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e6c00-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="e6c00-130">L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.</span><span class="sxs-lookup"><span data-stu-id="e6c00-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6c00-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6c00-131">See also</span></span>

- [<span data-ttu-id="e6c00-132">\<elemento > memoryCache (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="e6c00-132">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
