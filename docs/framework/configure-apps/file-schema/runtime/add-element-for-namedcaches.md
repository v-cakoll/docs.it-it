---
title: '&lt;aggiungere&gt; elemento per &lt;namedCaches&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0baafcb53bf79a25618dad56c2dcf1412e48624b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="3cc31-102">&lt;aggiungere&gt; elemento per &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="3cc31-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="3cc31-103">Aggiunge un `namedCache` voce per il `namedCaches` insieme per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="3cc31-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="3cc31-104">\<Caching ></span><span class="sxs-lookup"><span data-stu-id="3cc31-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="3cc31-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="3cc31-105">\<memoryCache></span></span>  
<span data-ttu-id="3cc31-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="3cc31-106">\<namedCaches></span></span>  
<span data-ttu-id="3cc31-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3cc31-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc31-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cc31-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="3cc31-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="3cc31-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cc31-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3cc31-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3cc31-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3cc31-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cc31-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3cc31-112">Attributes</span></span>  
  
|<span data-ttu-id="3cc31-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3cc31-113">Attribute</span></span>|<span data-ttu-id="3cc31-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cc31-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="3cc31-115">Valore intero che specifica la dimensione massima consentita (in megabyte) che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="3cc31-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="3cc31-116">Il valore predefinito è 0, il che significa che il <xref:System.Runtime.Caching.MemoryCache> euristiche di dimensionamento automatico della classe vengono utilizzate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cc31-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="3cc31-117">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="3cc31-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="3cc31-118">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria installata fisicamente i computer che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="3cc31-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="3cc31-119">Il valore predefinito è 0, il che significa che il <xref:System.Runtime.Caching.MemoryCache> euristiche di dimensionamento automatico della classe vengono utilizzate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3cc31-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="3cc31-120">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="3cc31-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="3cc31-121">Questo valore viene immesso nel formato "Hh".</span><span class="sxs-lookup"><span data-stu-id="3cc31-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cc31-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3cc31-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="3cc31-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3cc31-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3cc31-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cc31-124">Element</span></span>|<span data-ttu-id="3cc31-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cc31-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cc31-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="3cc31-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="3cc31-127">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="3cc31-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cc31-128">Note</span><span class="sxs-lookup"><span data-stu-id="3cc31-128">Remarks</span></span>  
 <span data-ttu-id="3cc31-129">Il `add` elemento aggiunge una voce per il `namedCaches` insieme per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="3cc31-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="3cc31-130">È possibile utilizzare il [deselezionare](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) elemento prima di utilizzare il `add` elemento per essere certi che vi siano altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="3cc31-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="3cc31-131">Questo elemento può essere usato nel file Machine. config e nel file Web. config.</span><span class="sxs-lookup"><span data-stu-id="3cc31-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cc31-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="3cc31-132">Example</span></span>  
 <span data-ttu-id="3cc31-133">Nell'esempio seguente viene illustrato come definire le impostazioni per il valore predefinito `namedCache` voce per il `namedCaches` insieme per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="3cc31-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cc31-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cc31-134">See Also</span></span>  
 [<span data-ttu-id="3cc31-135">\<namedCaches > Element (Cache Settings)</span><span class="sxs-lookup"><span data-stu-id="3cc31-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
