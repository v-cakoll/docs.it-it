---
title: Elemento <add> per <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659023"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="46b5f-102">\<aggiungere > elemento per \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="46b5f-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="46b5f-103">Aggiunge una `namedCache` voce `namedCaches` alla raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="46b5f-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="46b5f-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="46b5f-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="46b5f-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="46b5f-105">\<memoryCache></span></span>  
<span data-ttu-id="46b5f-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="46b5f-106">\<namedCaches></span></span>  
<span data-ttu-id="46b5f-107">\<add></span><span class="sxs-lookup"><span data-stu-id="46b5f-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b5f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46b5f-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="46b5f-109">Type</span><span class="sxs-lookup"><span data-stu-id="46b5f-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46b5f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="46b5f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46b5f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="46b5f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46b5f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="46b5f-112">Attributes</span></span>  
  
|<span data-ttu-id="46b5f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="46b5f-113">Attribute</span></span>|<span data-ttu-id="46b5f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46b5f-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="46b5f-115">Valore intero che specifica le dimensioni massime consentite (in megabyte) che un'istanza di <xref:System.Runtime.Caching.MemoryCache> un oggetto può raggiungere.</span><span class="sxs-lookup"><span data-stu-id="46b5f-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="46b5f-116">Il valore predefinito è 0, che indica che per <xref:System.Runtime.Caching.MemoryCache> impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="46b5f-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="46b5f-117">Nome della cache.</span><span class="sxs-lookup"><span data-stu-id="46b5f-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="46b5f-118">Valore intero compreso tra 0 e 100 che specifica la percentuale massima di memoria del computer installata fisicamente che può essere utilizzata dalla cache.</span><span class="sxs-lookup"><span data-stu-id="46b5f-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="46b5f-119">Il valore predefinito è 0, che indica che per <xref:System.Runtime.Caching.MemoryCache> impostazione predefinita vengono usate le euristiche di ridimensionamento automatico della classe.</span><span class="sxs-lookup"><span data-stu-id="46b5f-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="46b5f-120">Un valore che indica l'intervallo di tempo dopo il quale l'implementazione della cache confronta il carico di memoria corrente con i limiti di memoria percentuali e assoluti impostati per l'istanza della cache.</span><span class="sxs-lookup"><span data-stu-id="46b5f-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="46b5f-121">Questo valore viene immesso nel formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="46b5f-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46b5f-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="46b5f-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="46b5f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="46b5f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="46b5f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="46b5f-124">Element</span></span>|<span data-ttu-id="46b5f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46b5f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46b5f-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="46b5f-126">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="46b5f-127">Contiene una raccolta di impostazioni di configurazione per le <xref:System.Runtime.Caching.MemoryCache> istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="46b5f-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46b5f-128">Note</span><span class="sxs-lookup"><span data-stu-id="46b5f-128">Remarks</span></span>  
 <span data-ttu-id="46b5f-129">L' `add` elemento aggiunge una voce `namedCaches` alla raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="46b5f-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="46b5f-130">È possibile utilizzare l'elemento [Clear](clear-element-for-namedcaches.md) prima di utilizzare l' `add` elemento per verificare che non siano presenti altre cache denominate nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="46b5f-130">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="46b5f-131">Questo elemento può essere utilizzato nel file Machine. config e nel file Web. config.</span><span class="sxs-lookup"><span data-stu-id="46b5f-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46b5f-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="46b5f-132">Example</span></span>  
 <span data-ttu-id="46b5f-133">Nell'esempio seguente viene illustrato come definire le impostazioni per la `namedCache` voce predefinita della `namedCaches` raccolta per una cache in memoria.</span><span class="sxs-lookup"><span data-stu-id="46b5f-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46b5f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46b5f-134">See also</span></span>

- [<span data-ttu-id="46b5f-135">\<Elemento > namedCaches (impostazioni cache)</span><span class="sxs-lookup"><span data-stu-id="46b5f-135">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
