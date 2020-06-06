---
title: Elemento <system.runtime.caching> (impostazioni cache)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: df4887c8801dcf8af06b3826673a03cbc7dbc9b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153854"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="cd31d-102">Elemento \<system.runtime.caching> (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="cd31d-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="cd31d-103">Fornisce la configurazione per l'implementazione predefinita in memoria <xref:System.Runtime.Caching.ObjectCache> tramite la voce `memoryCache` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="cd31d-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.caching>**  
  
## <a name="syntax"></a><span data-ttu-id="cd31d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd31d-104">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd31d-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cd31d-105">Attributes and Elements</span></span>

<span data-ttu-id="cd31d-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cd31d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd31d-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="cd31d-107">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="cd31d-108">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cd31d-108">Child Elements</span></span>

|<span data-ttu-id="cd31d-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd31d-109">Element</span></span>|<span data-ttu-id="cd31d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd31d-110">Description</span></span>|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="cd31d-111">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cd31d-111">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd31d-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cd31d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="cd31d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd31d-113">Element</span></span>|<span data-ttu-id="cd31d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd31d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="cd31d-115">Specifica l'elemento radice in ogni file di configurazione usato dalle applicazioni Common Language Runtime e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd31d-115">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd31d-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="cd31d-116">Remarks</span></span>

<span data-ttu-id="cd31d-117">Le classi in questo spazio dei nomi consentono di usare le funzionalità di memorizzazione nella cache come quelle in ASP.NET, ma senza una dipendenza sull'assembly `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="cd31d-117">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="cd31d-118">Per altre informazioni, vedere [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="cd31d-118">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd31d-119">La funzionalità di memorizzazione nella cache di output e i tipi nello <xref:System.Runtime.Caching> spazio dei nomi sono nuovi in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cd31d-119">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd31d-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd31d-120">Example</span></span>

<span data-ttu-id="cd31d-121">L'esempio seguente illustra come configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cd31d-121">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="cd31d-122">L'esempio mostra come configurare un'istanza della voce `namedCaches` per la cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="cd31d-122">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="cd31d-123">Il nome della cache è impostato sul nome predefinito della voce della cache impostando l' `name` attributo su "default".</span><span class="sxs-lookup"><span data-stu-id="cd31d-123">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="cd31d-124">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="cd31d-124">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="cd31d-125">Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="cd31d-125">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="cd31d-126">L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.</span><span class="sxs-lookup"><span data-stu-id="cd31d-126">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd31d-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="cd31d-127">See also</span></span>

- [<span data-ttu-id="cd31d-128">\<memoryCache>Elemento (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="cd31d-128">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
