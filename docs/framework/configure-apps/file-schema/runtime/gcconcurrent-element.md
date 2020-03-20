---
title: Elemento gcConcurrent
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400043"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="9b58a-102">\<elemento> gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9b58a-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="9b58a-103">Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="9b58a-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="9b58a-104">[\<>di configurazione](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b58a-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="9b58a-105">&nbsp;&nbsp;[\<>di runtime](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b58a-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="9b58a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<> di gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="9b58a-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="9b58a-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b58a-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9b58a-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9b58a-108">Attributes and elements</span></span>

<span data-ttu-id="9b58a-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9b58a-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9b58a-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="9b58a-110">Attributes</span></span>

|<span data-ttu-id="9b58a-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="9b58a-111">Attribute</span></span>|<span data-ttu-id="9b58a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b58a-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="9b58a-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9b58a-113">Required attribute.</span></span><br /><br /><span data-ttu-id="9b58a-114">Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="9b58a-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="9b58a-115">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="9b58a-115">enabled attribute</span></span>

|<span data-ttu-id="9b58a-116">valore</span><span class="sxs-lookup"><span data-stu-id="9b58a-116">Value</span></span>|<span data-ttu-id="9b58a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b58a-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="9b58a-118">Non esegue la procedura di Garbage Collection contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9b58a-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="9b58a-119">Viene eseguita la procedura di Garbage Collection in modo concorrente.</span><span class="sxs-lookup"><span data-stu-id="9b58a-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="9b58a-120">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="9b58a-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9b58a-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9b58a-121">Child elements</span></span>

<span data-ttu-id="9b58a-122">No.</span><span class="sxs-lookup"><span data-stu-id="9b58a-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9b58a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9b58a-123">Parent elements</span></span>

|<span data-ttu-id="9b58a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b58a-124">Element</span></span>|<span data-ttu-id="9b58a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b58a-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="9b58a-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b58a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="9b58a-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9b58a-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9b58a-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9b58a-128">Remarks</span></span>

<span data-ttu-id="9b58a-129">Prima di .NET Framework 4, l'operazione di Garbage Collection per workstation supportava l'operazione di Garbage Collection simultanea, che eseguiva operazioni di Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="9b58a-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="9b58a-130">In .NET Framework 4.NET Framework 4, la Garbage Collection simultanea è stata sostituita da GC in background, che esegue anche la garbage collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="9b58a-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="9b58a-131">A partire da .NET Framework 4.5.NET Framework 4.5,NET Framework 4.5, la raccolta in background è diventata disponibile nell'operazione di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="9b58a-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="9b58a-132">L'elemento **gcConcurrent** controlla se il runtime esegue un'operazione di Garbage Collection simultanea o in background, se disponibile o se esegue operazioni di Garbage Collection in primo piano.</span><span class="sxs-lookup"><span data-stu-id="9b58a-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="9b58a-133">Per disabilitare l'operazione di Garbage Collection in background</span><span class="sxs-lookup"><span data-stu-id="9b58a-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="9b58a-134">A partire da .NET Framework 4.NET Framework 4, l'operazione di Garbage Collection simultanea viene sostituita da Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="9b58a-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="9b58a-135">I termini *simultanei* e *in background* vengono utilizzati in modo intercambiabile nella documentazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b58a-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="9b58a-136">Per disabilitare l'operazione di Garbage Collection in background, usare l'elemento **gcConcurrent,** come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="9b58a-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="9b58a-137">Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza.</span><span class="sxs-lookup"><span data-stu-id="9b58a-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="9b58a-138">Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="9b58a-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="9b58a-139">Se si `enabled` imposta l'attributo dell'elemento **gcConcurrent** su `false`, il runtime utilizza un'operazione di Garbage Collection non simultanea, ottimizzata per la velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="9b58a-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="9b58a-140">Il file di configurazione seguente disabilita l'operazione di Garbage Collection in background:The following configuration file disables background garbage collection:</span><span class="sxs-lookup"><span data-stu-id="9b58a-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="9b58a-141">Se è presente **un'impostazione gcConcurrentSetting** nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b58a-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="9b58a-142">Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b58a-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="9b58a-143">Per ulteriori informazioni sull'operazione di Garbage Collection simultanea e in background, vedere le [sezioni](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) Operazioni di Garbage Collection [simultanee](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection)e in background, vedere le sezioni Operazioni di Garbage [Collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)simultanee e in background nell'articolo [Nozioni fondamentali sulla Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) .</span><span class="sxs-lookup"><span data-stu-id="9b58a-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="9b58a-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b58a-144">Example</span></span>

<span data-ttu-id="9b58a-145">L'esempio seguente abilita l'operazione di Garbage Collection in background:The following example enables background garbage collection:</span><span class="sxs-lookup"><span data-stu-id="9b58a-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="9b58a-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b58a-146">See also</span></span>

- [<span data-ttu-id="9b58a-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="9b58a-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9b58a-148">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="9b58a-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9b58a-149">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9b58a-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
