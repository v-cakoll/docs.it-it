---
title: Elemento <add> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 9a7e370f9cce0e9ddf6dbe49984b7597e041eb84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674324"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="59618-102">\<aggiungere > (elemento) per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="59618-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="59618-103">Aggiunge un `namedCache` voce il `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="59618-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="59618-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="59618-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="59618-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="59618-105">\<memoryCache></span></span>  
<span data-ttu-id="59618-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="59618-106">\<namedCaches></span></span>  
<span data-ttu-id="59618-107">\<add></span><span class="sxs-lookup"><span data-stu-id="59618-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59618-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59618-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="59618-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="59618-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59618-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="59618-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59618-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="59618-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59618-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="59618-112">Attributes</span></span>  
  
|<span data-ttu-id="59618-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="59618-113">Attribute</span></span>|<span data-ttu-id="59618-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59618-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="59618-115">Valore intero che specifica la dimensione massima consentita (in megabyte) che un'istanza di un <xref:System.Runtime.Caching.MemoryCache> può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="59618-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="59618-116">Il valore predefinito è 0, a indicare che il <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="59618-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="59618-117">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="59618-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="59618-118">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer fisicamente installati che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="59618-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="59618-119">Il valore predefinito è 0, a indicare che il <xref:System.Runtime.Caching.MemoryCache> per impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="59618-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="59618-120">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="59618-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="59618-121">Questo valore viene immesso nel formato "Hh".</span><span class="sxs-lookup"><span data-stu-id="59618-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59618-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="59618-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="59618-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="59618-123">Parent Elements</span></span>  
  
|<span data-ttu-id="59618-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="59618-124">Element</span></span>|<span data-ttu-id="59618-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59618-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59618-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="59618-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="59618-127">Contiene una raccolta di impostazioni di configurazione per l'oggetto denominato <xref:System.Runtime.Caching.MemoryCache> istanze.</span><span class="sxs-lookup"><span data-stu-id="59618-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59618-128">Note</span><span class="sxs-lookup"><span data-stu-id="59618-128">Remarks</span></span>  
 <span data-ttu-id="59618-129">Il `add` elemento aggiunge una voce per il `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="59618-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="59618-130">È possibile usare la [cancellare](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) elemento prima di usare il `add` elemento per essere certi che non esistono nessun altro denominato le cache nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="59618-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="59618-131">Questo elemento può essere usato nel file Machine. config e nel file Web. config.</span><span class="sxs-lookup"><span data-stu-id="59618-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59618-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="59618-132">Example</span></span>  
 <span data-ttu-id="59618-133">Nell'esempio seguente viene illustrato come definire le impostazioni per il valore predefinito `namedCache` voce il `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="59618-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59618-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59618-134">See also</span></span>

- [<span data-ttu-id="59618-135">\<namedCaches > (impostazioni Cache)</span><span class="sxs-lookup"><span data-stu-id="59618-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
