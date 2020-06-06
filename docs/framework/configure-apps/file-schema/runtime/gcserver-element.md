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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968940"
---
# <a name="gcserver-element"></a><span data-ttu-id="1ea96-102">Elemento \<gcServer></span><span class="sxs-lookup"><span data-stu-id="1ea96-102">\<gcServer> element</span></span>

<span data-ttu-id="1ea96-103">Specifica se Common Language Runtime esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="1ea96-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a><span data-ttu-id="1ea96-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ea96-104">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ea96-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1ea96-105">Attributes and elements</span></span>

<span data-ttu-id="1ea96-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1ea96-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ea96-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ea96-107">Attributes</span></span>

|<span data-ttu-id="1ea96-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="1ea96-108">Attribute</span></span>|<span data-ttu-id="1ea96-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ea96-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="1ea96-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1ea96-110">Required attribute.</span></span><br /><br /><span data-ttu-id="1ea96-111">Specifica se il runtime esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="1ea96-111">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="1ea96-112">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="1ea96-112">enabled attribute</span></span>

|<span data-ttu-id="1ea96-113">Valore</span><span class="sxs-lookup"><span data-stu-id="1ea96-113">Value</span></span>|<span data-ttu-id="1ea96-114">Description</span><span class="sxs-lookup"><span data-stu-id="1ea96-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="1ea96-115">Non esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="1ea96-115">Does not run server garbage collection.</span></span> <span data-ttu-id="1ea96-116">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="1ea96-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="1ea96-117">Esegue Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="1ea96-117">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1ea96-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ea96-118">Child elements</span></span>

<span data-ttu-id="1ea96-119">No.</span><span class="sxs-lookup"><span data-stu-id="1ea96-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1ea96-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1ea96-120">Parent elements</span></span>

|<span data-ttu-id="1ea96-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ea96-121">Element</span></span>|<span data-ttu-id="1ea96-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ea96-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="1ea96-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ea96-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="1ea96-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1ea96-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ea96-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="1ea96-125">Remarks</span></span>

<span data-ttu-id="1ea96-126">Common Language Runtime (CLR) supporta due tipi di Garbage Collection: Garbage Collection per workstation, disponibile in tutti i sistemi, e Garbage Collection per server, disponibile nei sistemi con più processori.</span><span class="sxs-lookup"><span data-stu-id="1ea96-126">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="1ea96-127">Utilizzare l'elemento **gcserver** per controllare il tipo di Garbage Collection eseguita da CLR.</span><span class="sxs-lookup"><span data-stu-id="1ea96-127">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="1ea96-128">Usare la proprietà <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> per determinare se l'operazione Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1ea96-128">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="1ea96-129">Per i computer con un solo processore, l'operazione di Garbage Collection per workstation predefinita dovrebbe essere l'opzione più rapida.</span><span class="sxs-lookup"><span data-stu-id="1ea96-129">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="1ea96-130">Per i computer con due processori, si può usare quella per workstation o quella per server.</span><span class="sxs-lookup"><span data-stu-id="1ea96-130">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="1ea96-131">L'operazione di Garbage Collection per server dovrebbe essere l'opzione più rapida per più di due processori.</span><span class="sxs-lookup"><span data-stu-id="1ea96-131">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="1ea96-132">In genere, i sistemi server multiprocessore disabilitano GC server e utilizzano GC workstation quando molte istanze di un'app Server vengono eseguite nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="1ea96-132">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="1ea96-133">Questo elemento può essere usato solo nel file di configurazione dell'applicazione. Se è nel file di configurazione del computer, viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="1ea96-133">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="1ea96-134">In .NET Framework 4 e versioni precedenti, la modalità di Garbage Collection simultanea non è disponibile quando l'operazione di Garbage Collection per server è abilitata.</span><span class="sxs-lookup"><span data-stu-id="1ea96-134">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="1ea96-135">A partire da .NET Framework 4.5, l'operazione di Garbage Collection per server è simultanea.</span><span class="sxs-lookup"><span data-stu-id="1ea96-135">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="1ea96-136">Per utilizzare il Garbage Collection server non simultaneo, impostare l'elemento **gcserver** su `true` e l' [elemento gcConcurrent](gcconcurrent-element.md) su `false` .</span><span class="sxs-lookup"><span data-stu-id="1ea96-136">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="1ea96-137">A partire da .NET Framework 4.6.2, è anche possibile usare gli elementi seguenti per configurare GC del server:</span><span class="sxs-lookup"><span data-stu-id="1ea96-137">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="1ea96-138">[GCNoAffinitize](gcnoaffinitize-element.md), che specifica se esiste un'affinità tra gli heap GC del server e i processori.</span><span class="sxs-lookup"><span data-stu-id="1ea96-138">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="1ea96-139">Per impostazione predefinita, esiste un heap GC server per ogni processore.</span><span class="sxs-lookup"><span data-stu-id="1ea96-139">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="1ea96-140">[GCHeapCount](gcheapcount-element.md), che limita il numero di heap utilizzati da un processo.</span><span class="sxs-lookup"><span data-stu-id="1ea96-140">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="1ea96-141">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), che definisce l'affinità tra gli heap GC del server disponibili e i singoli processori.</span><span class="sxs-lookup"><span data-stu-id="1ea96-141">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="1ea96-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ea96-142">Example</span></span>

<span data-ttu-id="1ea96-143">Nell'esempio seguente viene abilitata l'Garbage Collection server:</span><span class="sxs-lookup"><span data-stu-id="1ea96-143">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="1ea96-144">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1ea96-144">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1ea96-145">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1ea96-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1ea96-146">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1ea96-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1ea96-147">Per disabilitare Garbage Collection simultanee</span><span class="sxs-lookup"><span data-stu-id="1ea96-147">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
