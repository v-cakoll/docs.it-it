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
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102918"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="a240a-102">Elemento \<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="a240a-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="a240a-103">Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="a240a-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a><span data-ttu-id="a240a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a240a-104">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a240a-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a240a-105">Attributes and elements</span></span>

<span data-ttu-id="a240a-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a240a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a240a-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a240a-107">Attributes</span></span>

|<span data-ttu-id="a240a-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="a240a-108">Attribute</span></span>|<span data-ttu-id="a240a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a240a-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a240a-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a240a-110">Required attribute.</span></span><br /><br /><span data-ttu-id="a240a-111">Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="a240a-111">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="a240a-112">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="a240a-112">enabled attribute</span></span>

|<span data-ttu-id="a240a-113">Valore</span><span class="sxs-lookup"><span data-stu-id="a240a-113">Value</span></span>|<span data-ttu-id="a240a-114">Description</span><span class="sxs-lookup"><span data-stu-id="a240a-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a240a-115">Non viene eseguito Garbage Collection simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="a240a-115">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="a240a-116">Viene eseguita la procedura di Garbage Collection in modo concorrente.</span><span class="sxs-lookup"><span data-stu-id="a240a-116">Runs garbage collection concurrently.</span></span> <span data-ttu-id="a240a-117">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a240a-117">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a240a-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a240a-118">Child elements</span></span>

<span data-ttu-id="a240a-119">No.</span><span class="sxs-lookup"><span data-stu-id="a240a-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a240a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a240a-120">Parent elements</span></span>

|<span data-ttu-id="a240a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a240a-121">Element</span></span>|<span data-ttu-id="a240a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a240a-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a240a-123">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a240a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a240a-124">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a240a-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a240a-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="a240a-125">Remarks</span></span>

<span data-ttu-id="a240a-126">Prima di .NET Framework 4, la workstation Garbage Collection supportava Garbage Collection simultanee, che eseguivano Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="a240a-126">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a240a-127">In .NET Framework 4, il Garbage Collection simultaneo è stato sostituito da GC in background, che esegue anche Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="a240a-127">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a240a-128">A partire da .NET Framework 4,5, la raccolta in background è diventata disponibile nell'Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="a240a-128">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="a240a-129">L'elemento **gcConcurrent** controlla se il runtime esegue le Garbage Collection simultanee o in background, se disponibile, o se esegue Garbage Collection in primo piano.</span><span class="sxs-lookup"><span data-stu-id="a240a-129">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="a240a-130">Per disabilitare lo sfondo Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a240a-130">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="a240a-131">A partire da .NET Framework 4, il Garbage Collection simultaneo viene sostituito da Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="a240a-131">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="a240a-132">I termini *simultanei* e in *background* vengono usati in modo interscambiabile nella documentazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a240a-132">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="a240a-133">Per disabilitare Garbage Collection in background, usare l'elemento **gcConcurrent** , come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a240a-133">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="a240a-134">Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza.</span><span class="sxs-lookup"><span data-stu-id="a240a-134">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="a240a-135">Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a240a-135">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="a240a-136">Se si imposta l' `enabled` attributo dell'elemento **gcConcurrent** su `false` , il runtime USA Garbage Collection non simultanee, ottimizzate per la velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="a240a-136">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="a240a-137">Il file di configurazione seguente Disabilita Garbage Collection di sfondo:</span><span class="sxs-lookup"><span data-stu-id="a240a-137">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="a240a-138">Se è presente un'impostazione **gcConcurrentSetting** nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a240a-138">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="a240a-139">Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a240a-139">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="a240a-140">Per ulteriori informazioni sulle Garbage Collection simultanee e in background, vedere [Garbage Collection di sfondo](../../../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="a240a-140">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="a240a-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="a240a-141">Example</span></span>

<span data-ttu-id="a240a-142">Nell'esempio seguente viene abilitata la Garbage Collection in background:</span><span class="sxs-lookup"><span data-stu-id="a240a-142">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a240a-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a240a-143">See also</span></span>

- [<span data-ttu-id="a240a-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="a240a-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a240a-145">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a240a-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a240a-146">Nozioni fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a240a-146">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
