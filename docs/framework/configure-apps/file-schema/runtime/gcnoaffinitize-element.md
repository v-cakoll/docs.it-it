---
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978375"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="4771f-102">\<elemento > GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="4771f-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="4771f-103">Specifica se creare affinità tra i thread GC del server con CPU.</span><span class="sxs-lookup"><span data-stu-id="4771f-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

<span data-ttu-id="4771f-104">> di configurazione di \<</span><span class="sxs-lookup"><span data-stu-id="4771f-104">\<configuration></span></span>\
<span data-ttu-id="4771f-105">&nbsp;&nbsp;\<Runtime > </span><span class="sxs-lookup"><span data-stu-id="4771f-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="4771f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize ></span><span class="sxs-lookup"><span data-stu-id="4771f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize></span></span>

## <a name="syntax"></a><span data-ttu-id="4771f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4771f-107">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4771f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4771f-108">Attributes and elements</span></span>

<span data-ttu-id="4771f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4771f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4771f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4771f-110">Attributes</span></span>

|<span data-ttu-id="4771f-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4771f-111">Attribute</span></span>|<span data-ttu-id="4771f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4771f-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="4771f-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4771f-113">Required attribute.</span></span><br /><br /><span data-ttu-id="4771f-114">Specifica se i thread o gli heap GC del server sono creata un'affinità con i processori disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="4771f-114">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="4771f-115">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="4771f-115">enabled attribute</span></span>

|<span data-ttu-id="4771f-116">Value</span><span class="sxs-lookup"><span data-stu-id="4771f-116">Value</span></span>|<span data-ttu-id="4771f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4771f-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="4771f-118">Thread GC del server cui con CPU.</span><span class="sxs-lookup"><span data-stu-id="4771f-118">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="4771f-119">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4771f-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="4771f-120">Non creare affinità tra i thread GC del server con CPU.</span><span class="sxs-lookup"><span data-stu-id="4771f-120">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4771f-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4771f-121">Child elements</span></span>

<span data-ttu-id="4771f-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="4771f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4771f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4771f-123">Parent elements</span></span>

|<span data-ttu-id="4771f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4771f-124">Element</span></span>|<span data-ttu-id="4771f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4771f-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="4771f-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4771f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="4771f-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4771f-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4771f-128">Note</span><span class="sxs-lookup"><span data-stu-id="4771f-128">Remarks</span></span>

<span data-ttu-id="4771f-129">Per impostazione predefinita, i thread GC del server sono creata un'affinità con le rispettive CPU.</span><span class="sxs-lookup"><span data-stu-id="4771f-129">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="4771f-130">Ogni processore disponibile del sistema dispone di un proprio heap GC e di un thread.</span><span class="sxs-lookup"><span data-stu-id="4771f-130">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="4771f-131">Si tratta in genere dell'impostazione preferita perché ottimizza l'utilizzo della cache.</span><span class="sxs-lookup"><span data-stu-id="4771f-131">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="4771f-132">A partire da .NET Framework 4.6.2, impostando l'attributo `enabled` dell'elemento **GCNoAffinitize** su `false`, è possibile specificare che le CPU e i thread GC del server non devono essere strettamente collegati.</span><span class="sxs-lookup"><span data-stu-id="4771f-132">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `false`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="4771f-133">È possibile specificare solo l'elemento di configurazione **GCNoAffinitize** per non creare affinità tra i thread GC del server con CPU.</span><span class="sxs-lookup"><span data-stu-id="4771f-133">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="4771f-134">È anche possibile usarlo insieme all'elemento [GCHeapCount](gcheapcount-element.md) per controllare il numero di heap e thread GC usati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4771f-134">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="4771f-135">Se l'attributo `enabled` dell'elemento **GCNoAffinitize** è `false` (valore predefinito), è anche possibile usare l'elemento [GCHeapCount](gcheapcount-element.md) per specificare il numero di thread e heap GC, insieme all'elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) per specificare i processori a cui sono creata un'affinità i thread GC e gli heap.</span><span class="sxs-lookup"><span data-stu-id="4771f-135">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="4771f-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="4771f-136">Example</span></span>

<span data-ttu-id="4771f-137">L'esempio seguente non creare affinità tra i thread GC del server:</span><span class="sxs-lookup"><span data-stu-id="4771f-137">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="4771f-138">L'esempio seguente non creare affinità tra i thread GC del server e limita il numero di heap GC/thread a 10:</span><span class="sxs-lookup"><span data-stu-id="4771f-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4771f-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4771f-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4771f-140">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="4771f-140">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="4771f-141">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="4771f-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="4771f-142">Principi fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="4771f-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="4771f-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="4771f-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4771f-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="4771f-144">Configuration File Schema</span></span>](../index.md)
