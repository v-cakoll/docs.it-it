---
title: Elemento GCHeapAffinitizeMask
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978382"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="fb61f-102">\<elemento > GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="fb61f-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="fb61f-103">Definisce l'affinità tra heap GC e singoli processori.</span><span class="sxs-lookup"><span data-stu-id="fb61f-103">Defines the affinity between GC heaps and individual processors.</span></span>

<span data-ttu-id="fb61f-104">> di configurazione di \<</span><span class="sxs-lookup"><span data-stu-id="fb61f-104">\<configuration></span></span>\
<span data-ttu-id="fb61f-105">&nbsp;&nbsp;\<Runtime > </span><span class="sxs-lookup"><span data-stu-id="fb61f-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="fb61f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask ></span><span class="sxs-lookup"><span data-stu-id="fb61f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask></span></span>

## <a name="syntax"></a><span data-ttu-id="fb61f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fb61f-107">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fb61f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fb61f-108">Attributes and elements</span></span>

<span data-ttu-id="fb61f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fb61f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fb61f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fb61f-110">Attributes</span></span>

|<span data-ttu-id="fb61f-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="fb61f-111">Attribute</span></span>|<span data-ttu-id="fb61f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb61f-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="fb61f-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fb61f-113">Required attribute.</span></span><br /><br /><span data-ttu-id="fb61f-114">Specifica l'affinità tra heap GC e singoli processori.</span><span class="sxs-lookup"><span data-stu-id="fb61f-114">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="fb61f-115">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="fb61f-115">enabled attribute</span></span>

|<span data-ttu-id="fb61f-116">Value</span><span class="sxs-lookup"><span data-stu-id="fb61f-116">Value</span></span>|<span data-ttu-id="fb61f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb61f-117">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="fb61f-118">Valore decimale che costituisce una maschera di maschera che definisce l'affinità tra heap GC del server e singoli processori.</span><span class="sxs-lookup"><span data-stu-id="fb61f-118">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="fb61f-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fb61f-119">Child elements</span></span>

<span data-ttu-id="fb61f-120">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="fb61f-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fb61f-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fb61f-121">Parent elements</span></span>

|<span data-ttu-id="fb61f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb61f-122">Element</span></span>|<span data-ttu-id="fb61f-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb61f-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="fb61f-124">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fb61f-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="fb61f-125">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="fb61f-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fb61f-126">Note</span><span class="sxs-lookup"><span data-stu-id="fb61f-126">Remarks</span></span>

<span data-ttu-id="fb61f-127">Per impostazione predefinita, i thread GC del server sono creata un'affinità con la rispettiva CPU, in modo da avere un heap GC, un thread GC server e un thread GC del server in background per ogni processore.</span><span class="sxs-lookup"><span data-stu-id="fb61f-127">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="fb61f-128">A partire da .NET Framework 4.6.2, è possibile usare l'elemento **GCHeapAffinitizeMask** per controllare l'affinità tra gli heap e i processori GC del server quando il numero di heap è limitato dall'elemento **GCHeapCount** .</span><span class="sxs-lookup"><span data-stu-id="fb61f-128">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="fb61f-129">**GCHeapAffinitizeMask** viene in genere usato insieme ad altri due flag:</span><span class="sxs-lookup"><span data-stu-id="fb61f-129">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="fb61f-130">[GCNoAffinitize](gcnoaffinitize-element.md), che controlla se i thread o gli heap GC del server sono creata un'affinità con CPU.</span><span class="sxs-lookup"><span data-stu-id="fb61f-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="fb61f-131">L'attributo `enabled` dell'elemento [GCNoAffinitize](gcnoaffinitize-element.md) deve essere `false` (valore predefinito) per l'impostazione **GCHeapAffinitizeMask** da usare.</span><span class="sxs-lookup"><span data-stu-id="fb61f-131">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="fb61f-132">[GCHeapCount](gcheapcount-element.md), che limita il numero di heap utilizzati dal processo per il Garbage Collector del server.</span><span class="sxs-lookup"><span data-stu-id="fb61f-132">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="fb61f-133">Per impostazione predefinita, è presente un heap per ogni processore.</span><span class="sxs-lookup"><span data-stu-id="fb61f-133">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="fb61f-134">**nnnn** è una maschera di bit espressa come valore decimale.</span><span class="sxs-lookup"><span data-stu-id="fb61f-134">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="fb61f-135">Il bit 0 del byte 0 rappresenta il processore 0, il bit 1 di byte 0 rappresenta il processore 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="fb61f-135">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="fb61f-136">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fb61f-136">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="fb61f-137">Il valore 1023 è 0x3FF o 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="fb61f-137">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="fb61f-138">Il processo utilizza 10 processori, dal processore 0 al processore 9.</span><span class="sxs-lookup"><span data-stu-id="fb61f-138">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="fb61f-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb61f-139">Example</span></span>

<span data-ttu-id="fb61f-140">Nell'esempio seguente viene indicato che un'applicazione utilizza GC server con 10 heap/thread.</span><span class="sxs-lookup"><span data-stu-id="fb61f-140">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="fb61f-141">Poiché non si vuole che tali heap si sovrappongano con gli heap di altre applicazioni in esecuzione nel sistema, usare **GCHeapAffinitizeMask** per specificare che il processo deve usare le CPU da 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="fb61f-141">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="fb61f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb61f-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fb61f-143">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="fb61f-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="fb61f-144">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="fb61f-144">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="fb61f-145">Principi fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="fb61f-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="fb61f-146">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="fb61f-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fb61f-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="fb61f-147">Configuration File Schema</span></span>](../index.md)
