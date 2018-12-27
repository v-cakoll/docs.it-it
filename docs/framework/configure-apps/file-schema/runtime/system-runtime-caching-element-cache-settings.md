---
title: '&lt;Caching&gt; (impostazioni Cache)'
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: daa08bb8a92a13941093a77f580318558dc14e9c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610372"
---
# <a name="ltsystemruntimecachinggt-element-cache-settings"></a><span data-ttu-id="f1576-102">&lt;Caching&gt; (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="f1576-102">&lt;system.runtime.caching&gt; Element (Cache Settings)</span></span>
<span data-ttu-id="f1576-103">Fornisce la configurazione per l'implementazione predefinita in memoria <xref:System.Runtime.Caching.ObjectCache> tramite la voce `memoryCache` nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1576-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
 <span data-ttu-id="f1576-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1576-104">\<configuration></span></span>  
<span data-ttu-id="f1576-105">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="f1576-105">\<system.runtime.caching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1576-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1576-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1576-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1576-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f1576-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f1576-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1576-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1576-109">Attributes</span></span>  
 `None`  
  
### <a name="child-elements"></a><span data-ttu-id="f1576-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1576-110">Child Elements</span></span>  
  
|<span data-ttu-id="f1576-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1576-111">Element</span></span>|<span data-ttu-id="f1576-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1576-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1576-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="f1576-113">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="f1576-114">Definisce un elemento che viene usato per configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="f1576-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1576-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1576-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f1576-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1576-116">Element</span></span>|<span data-ttu-id="f1576-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1576-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1576-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1576-118">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="f1576-119">Specifica l'elemento radice in ogni file di configurazione usato dal Common Language Runtime e dalle applicazioni [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1576-119">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1576-120">Note</span><span class="sxs-lookup"><span data-stu-id="f1576-120">Remarks</span></span>  
 <span data-ttu-id="f1576-121">Le classi in questo spazio dei nomi consentono di usare le funzionalità di memorizzazione nella cache come quelle in ASP.NET, ma senza una dipendenza sull'assembly `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="f1576-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="f1576-122">Per altre informazioni, vedere [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f1576-122">For more information, see [Caching in .NET Framework Applications](../../../../../docs/framework/performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1576-123">Le funzionalità di memorizzazione nella cache di output e i tipi nello spazio dei nomi <xref:System.Runtime.Caching> sono nuovi in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1576-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1576-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1576-124">Example</span></span>  
 <span data-ttu-id="f1576-125">L'esempio seguente illustra come configurare una cache basata sulla classe <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="f1576-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="f1576-126">L'esempio mostra come configurare un'istanza della voce `namedCaches` per la cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="f1576-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="f1576-127">Per la voce della cache è impostato il nome predefinito, come indicato dal valore "default" dell'attributo `name` .</span><span class="sxs-lookup"><span data-stu-id="f1576-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="f1576-128">Gli attributi `cacheMemoryLimitMegabytes` e `physicalMemoryPercentage` sono impostati su zero.</span><span class="sxs-lookup"><span data-stu-id="f1576-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="f1576-129">Il valore zero di questi attributi indica che per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico di <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="f1576-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="f1576-130">L'implementazione della cache deve confrontare ogni due minuti il carico di memoria corrente con i limiti di memoria assoluti e in percentuale.</span><span class="sxs-lookup"><span data-stu-id="f1576-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1576-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1576-131">See Also</span></span>  
- [<span data-ttu-id="f1576-132">\<memoryCache > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="f1576-132">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
