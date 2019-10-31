---
title: <gcConcurrent> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 4897462e20b193496c44d26923d0d0e2a13f7dd6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116806"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="72ff6-102">\<elemento > gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="72ff6-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="72ff6-103">Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="72ff6-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="72ff6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="72ff6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="72ff6-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="72ff6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="72ff6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcConcurrent >**</span><span class="sxs-lookup"><span data-stu-id="72ff6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcConcurrent>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="72ff6-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72ff6-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72ff6-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="72ff6-108">Attributes and elements</span></span>

<span data-ttu-id="72ff6-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="72ff6-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="72ff6-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="72ff6-110">Attributes</span></span>

|<span data-ttu-id="72ff6-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="72ff6-111">Attribute</span></span>|<span data-ttu-id="72ff6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72ff6-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="72ff6-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="72ff6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="72ff6-114">Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="72ff6-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="72ff6-115">attributo enabled</span><span class="sxs-lookup"><span data-stu-id="72ff6-115">enabled attribute</span></span>

|<span data-ttu-id="72ff6-116">Value</span><span class="sxs-lookup"><span data-stu-id="72ff6-116">Value</span></span>|<span data-ttu-id="72ff6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72ff6-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="72ff6-118">Non viene eseguito Garbage Collection simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="72ff6-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="72ff6-119">Viene eseguita la procedura di Garbage Collection in modo concorrente.</span><span class="sxs-lookup"><span data-stu-id="72ff6-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="72ff6-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="72ff6-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="72ff6-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="72ff6-121">Child elements</span></span>

<span data-ttu-id="72ff6-122">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="72ff6-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="72ff6-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="72ff6-123">Parent elements</span></span>

|<span data-ttu-id="72ff6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="72ff6-124">Element</span></span>|<span data-ttu-id="72ff6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72ff6-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="72ff6-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72ff6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="72ff6-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="72ff6-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72ff6-128">Note</span><span class="sxs-lookup"><span data-stu-id="72ff6-128">Remarks</span></span>

<span data-ttu-id="72ff6-129">Prima di .NET Framework 4, la Garbage Collection per workstation supportava la Garbage Collection in modalità simultanea, che eseguiva la Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="72ff6-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="72ff6-130">A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è stata sostituita dalla modalità in background, che esegue anch'essa la Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="72ff6-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="72ff6-131">A partire da .NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile anche per server.</span><span class="sxs-lookup"><span data-stu-id="72ff6-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="72ff6-132">L'elemento `<gcConcurrent>` controlla se il runtime esegue Garbage Collection simultanee o in background, se disponibile, o se esegue Garbage Collection in primo piano.</span><span class="sxs-lookup"><span data-stu-id="72ff6-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="72ff6-133">Per disabilitare lo sfondo Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="72ff6-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="72ff6-134">A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è sostituita dalla Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="72ff6-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="72ff6-135">I termini *simultanei* e in *background* vengono usati in modo interscambiabile nella documentazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72ff6-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="72ff6-136">Per disabilitare il Garbage Collection in background, usare l'elemento `<gcConcurrent>`, come illustrato in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="72ff6-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="72ff6-137">Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza.</span><span class="sxs-lookup"><span data-stu-id="72ff6-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="72ff6-138">Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="72ff6-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="72ff6-139">Se si imposta l'attributo `enabled` dell'elemento `<gcConcurrent>` su `false`, da parte del runtime viene usata la Garbage Collection in modalità non simultanea, ottimizzata per la velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="72ff6-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="72ff6-140">Il file di configurazione seguente disabilita la Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="72ff6-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="72ff6-141">Se è presente un'impostazione di `<gcConcurrentSetting>` nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72ff6-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="72ff6-142">Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72ff6-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="72ff6-143">Per altre informazioni sulle Garbage Collection simultanee e in background, vedere la sezione [Garbage Collection simultanea](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) nell'articolo [nozioni fondamentali di Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) .</span><span class="sxs-lookup"><span data-stu-id="72ff6-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="72ff6-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="72ff6-144">Example</span></span>

<span data-ttu-id="72ff6-145">Nell'esempio seguente viene abilitata la Garbage Collection simultanea:</span><span class="sxs-lookup"><span data-stu-id="72ff6-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="72ff6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72ff6-146">See also</span></span>

- [<span data-ttu-id="72ff6-147">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="72ff6-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="72ff6-148">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="72ff6-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="72ff6-149">Principi fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="72ff6-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
