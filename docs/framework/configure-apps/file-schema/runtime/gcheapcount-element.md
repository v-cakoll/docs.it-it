---
title: Elemento GCHeapCount
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74283078"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="189b2-102">Elemento \<GCHeapCount></span><span class="sxs-lookup"><span data-stu-id="189b2-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="189b2-103">Specifica il numero di heap/thread da usare per il Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="189b2-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a><span data-ttu-id="189b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="189b2-104">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="189b2-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="189b2-105">Attributes and elements</span></span>

<span data-ttu-id="189b2-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="189b2-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="189b2-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="189b2-107">Attributes</span></span>

|<span data-ttu-id="189b2-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="189b2-108">Attribute</span></span>|<span data-ttu-id="189b2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="189b2-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="189b2-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="189b2-110">Required attribute.</span></span><br /><br /><span data-ttu-id="189b2-111">Specifica il numero di heap da usare per il Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="189b2-111">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="189b2-112">Il numero effettivo di heap è il numero minimo di heap specificato e il numero di processori che il processo è autorizzato a utilizzare.</span><span class="sxs-lookup"><span data-stu-id="189b2-112">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="189b2-113">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="189b2-113">enabled attribute</span></span>

|<span data-ttu-id="189b2-114">Valore</span><span class="sxs-lookup"><span data-stu-id="189b2-114">Value</span></span>|<span data-ttu-id="189b2-115">Description</span><span class="sxs-lookup"><span data-stu-id="189b2-115">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="189b2-116">Numero di heap da utilizzare per GC del server.</span><span class="sxs-lookup"><span data-stu-id="189b2-116">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="189b2-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="189b2-117">Child elements</span></span>

<span data-ttu-id="189b2-118">No.</span><span class="sxs-lookup"><span data-stu-id="189b2-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="189b2-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="189b2-119">Parent elements</span></span>

|<span data-ttu-id="189b2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="189b2-120">Element</span></span>|<span data-ttu-id="189b2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="189b2-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="189b2-122">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="189b2-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="189b2-123">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="189b2-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="189b2-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="189b2-124">Remarks</span></span>

<span data-ttu-id="189b2-125">Per impostazione predefinita, i thread GC del server sono creata un'affinità con la rispettiva CPU, in modo da avere un heap GC, un thread GC server e un thread GC del server in background per ogni processore.</span><span class="sxs-lookup"><span data-stu-id="189b2-125">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="189b2-126">A partire da .NET Framework 4.6.2, è possibile usare l'elemento **GCHeapCount** per limitare il numero di heap usati dall'applicazione per il Garbage Collector del server.</span><span class="sxs-lookup"><span data-stu-id="189b2-126">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="189b2-127">La limitazione del numero di heap utilizzati per il Garbage Collector del server è particolarmente utile per i sistemi che eseguono più istanze di un'applicazione server.</span><span class="sxs-lookup"><span data-stu-id="189b2-127">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="189b2-128">**GCHeapCount** viene in genere usato insieme ad altri due flag:</span><span class="sxs-lookup"><span data-stu-id="189b2-128">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="189b2-129">[GCNoAffinitize](gcnoaffinitize-element.md), che controlla se i thread o gli heap GC del server sono creata un'affinità con CPU.</span><span class="sxs-lookup"><span data-stu-id="189b2-129">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="189b2-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), che controlla l'affinità dei thread GC/heap con le CPU.</span><span class="sxs-lookup"><span data-stu-id="189b2-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="189b2-131">Se **GCHeapCount** è impostato e **GCNoAffinitize** è disabilitato (impostazione predefinita), esiste un'affinità tra i thread GC/heap *nn* e i primi processori *nn* .</span><span class="sxs-lookup"><span data-stu-id="189b2-131">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="189b2-132">È possibile utilizzare l'elemento **GCHeapAffinitizeMask** per specificare quali processori vengono utilizzati dagli heap GC del server del processo.</span><span class="sxs-lookup"><span data-stu-id="189b2-132">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="189b2-133">In caso contrario, se più processi server sono in esecuzione in un sistema, l'utilizzo del processore si sovrappone.</span><span class="sxs-lookup"><span data-stu-id="189b2-133">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="189b2-134">Se **GCHeapCount** è impostato e **GCNoAffinitize** è abilitato, il Garbage Collector limita il numero di processori utilizzati per il catalogo globale del server, ma non creare affinità tra gli heap GC e i processori.</span><span class="sxs-lookup"><span data-stu-id="189b2-134">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="189b2-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="189b2-135">Example</span></span>

<span data-ttu-id="189b2-136">Nell'esempio seguente viene indicato che un'applicazione utilizza GC server con 10 heap/thread.</span><span class="sxs-lookup"><span data-stu-id="189b2-136">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="189b2-137">Poiché non si vuole che tali heap si sovrappongano con gli heap di altre applicazioni in esecuzione nel sistema, usare **GCHeapAffinitizeMask** per specificare che il processo deve usare le CPU da 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="189b2-137">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="189b2-138">L'esempio seguente non creare affinità tra i thread GC del server e limita il numero di heap GC/thread a 10.</span><span class="sxs-lookup"><span data-stu-id="189b2-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="189b2-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="189b2-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="189b2-140">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="189b2-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="189b2-141">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="189b2-141">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="189b2-142">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="189b2-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="189b2-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="189b2-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="189b2-144">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="189b2-144">Configuration File Schema</span></span>](../index.md)
