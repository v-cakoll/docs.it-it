---
title: Elemento gcServer
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968940"
---
# <a name="gcserver-element"></a><span data-ttu-id="fcdb5-102">\<elemento > gcServer</span><span class="sxs-lookup"><span data-stu-id="fcdb5-102">\<gcServer> element</span></span>

<span data-ttu-id="fcdb5-103">Specifica se Common Language Runtime esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

<span data-ttu-id="fcdb5-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fcdb5-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="fcdb5-105">&nbsp;&nbsp;[\<runtime >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="fcdb5-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="fcdb5-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer ></span><span class="sxs-lookup"><span data-stu-id="fcdb5-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer></span></span>

## <a name="syntax"></a><span data-ttu-id="fcdb5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcdb5-107">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fcdb5-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fcdb5-108">Attributes and elements</span></span>

<span data-ttu-id="fcdb5-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fcdb5-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fcdb5-110">Attributes</span></span>

|<span data-ttu-id="fcdb5-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="fcdb5-111">Attribute</span></span>|<span data-ttu-id="fcdb5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcdb5-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="fcdb5-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-113">Required attribute.</span></span><br /><br /><span data-ttu-id="fcdb5-114">Specifica se il runtime esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-114">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="fcdb5-115">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="fcdb5-115">enabled attribute</span></span>

|<span data-ttu-id="fcdb5-116">Value</span><span class="sxs-lookup"><span data-stu-id="fcdb5-116">Value</span></span>|<span data-ttu-id="fcdb5-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcdb5-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="fcdb5-118">Non esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-118">Does not run server garbage collection.</span></span> <span data-ttu-id="fcdb5-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="fcdb5-120">Esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-120">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fcdb5-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fcdb5-121">Child elements</span></span>

<span data-ttu-id="fcdb5-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fcdb5-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fcdb5-123">Parent elements</span></span>

|<span data-ttu-id="fcdb5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fcdb5-124">Element</span></span>|<span data-ttu-id="fcdb5-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcdb5-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="fcdb5-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="fcdb5-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fcdb5-128">Note</span><span class="sxs-lookup"><span data-stu-id="fcdb5-128">Remarks</span></span>

<span data-ttu-id="fcdb5-129">Common Language Runtime (CLR) supporta due tipi di Garbage Collection: Garbage Collection per workstation, disponibile in tutti i sistemi, e Garbage Collection per server, disponibile nei sistemi con più processori.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="fcdb5-130">Utilizzare l'elemento **gcserver** per controllare il tipo di Garbage Collection eseguita da CLR.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-130">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="fcdb5-131">Usare la proprietà <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> per determinare se l'operazione Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="fcdb5-132">Per i computer con un solo processore, l'operazione di Garbage Collection per workstation predefinita dovrebbe essere l'opzione più rapida.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="fcdb5-133">Per i computer con due processori, si può usare quella per workstation o quella per server.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="fcdb5-134">L'operazione di Garbage Collection per server dovrebbe essere l'opzione più rapida per più di due processori.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-134">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="fcdb5-135">In genere, i sistemi server multiprocessore disabilitano GC server e utilizzano GC workstation quando molte istanze di un'app Server vengono eseguite nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-135">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="fcdb5-136">Questo elemento può essere usato solo nel file di configurazione dell'applicazione. Se è nel file di configurazione del computer, viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-136">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="fcdb5-137">In .NET Framework 4 e versioni precedenti, la modalità di Garbage Collection simultanea non è disponibile quando l'operazione di Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-137">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="fcdb5-138">A partire da .NET Framework 4.5, l'operazione di Garbage Collection per server è simultanea.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-138">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="fcdb5-139">Per utilizzare il Garbage Collection server non simultaneo, impostare l'elemento **gcserver** su `true` e l' [elemento gcConcurrent](gcconcurrent-element.md) su `false`.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-139">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="fcdb5-140">A partire da .NET Framework 4.6.2, è anche possibile usare gli elementi seguenti per configurare GC del server:</span><span class="sxs-lookup"><span data-stu-id="fcdb5-140">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="fcdb5-141">[GCNoAffinitize](gcnoaffinitize-element.md), che specifica se esiste un'affinità tra gli heap GC del server e i processori.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-141">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="fcdb5-142">Per impostazione predefinita, esiste un heap GC server per ogni processore.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-142">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="fcdb5-143">[GCHeapCount](gcheapcount-element.md), che limita il numero di heap utilizzati da un processo.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-143">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="fcdb5-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), che definisce l'affinità tra gli heap GC del server disponibili e i singoli processori.</span><span class="sxs-lookup"><span data-stu-id="fcdb5-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="fcdb5-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcdb5-145">Example</span></span>

<span data-ttu-id="fcdb5-146">Nell'esempio seguente viene abilitata l'Garbage Collection server:</span><span class="sxs-lookup"><span data-stu-id="fcdb5-146">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fcdb5-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcdb5-147">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fcdb5-148">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="fcdb5-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fcdb5-149">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="fcdb5-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fcdb5-150">Per disabilitare Garbage Collection simultanee</span><span class="sxs-lookup"><span data-stu-id="fcdb5-150">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
