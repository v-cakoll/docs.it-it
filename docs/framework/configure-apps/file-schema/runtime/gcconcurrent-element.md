---
title: '&lt;gcConcurrent&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c7ab16546ae85d1161f9e1323d74f17253edb7e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="3a683-102">&lt;gcConcurrent&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="3a683-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="3a683-103">Specifica se in Common Language Runtime viene eseguita una procedura di Garbage Collection in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="3a683-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="3a683-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3a683-104">\<configuration></span></span>  
<span data-ttu-id="3a683-105">\<runtime ></span><span class="sxs-lookup"><span data-stu-id="3a683-105">\<runtime></span></span>  
<span data-ttu-id="3a683-106">\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="3a683-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a683-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a683-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a683-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a683-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3a683-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a683-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a683-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a683-110">Attributes</span></span>  
  
|<span data-ttu-id="3a683-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a683-111">Attribute</span></span>|<span data-ttu-id="3a683-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a683-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3a683-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3a683-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3a683-114">Specifica se il runtime esegue operazioni di Garbage Collection simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="3a683-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3a683-115">Attributo enabled</span><span class="sxs-lookup"><span data-stu-id="3a683-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3a683-116">Valore</span><span class="sxs-lookup"><span data-stu-id="3a683-116">Value</span></span>|<span data-ttu-id="3a683-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a683-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3a683-118">La procedura di Garbage Collection non viene eseguita in modo concorrente.</span><span class="sxs-lookup"><span data-stu-id="3a683-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="3a683-119">Viene eseguita la procedura di Garbage Collection in modo concorrente.</span><span class="sxs-lookup"><span data-stu-id="3a683-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="3a683-120">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3a683-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a683-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a683-121">Child Elements</span></span>  
 <span data-ttu-id="3a683-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3a683-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a683-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a683-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3a683-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a683-124">Element</span></span>|<span data-ttu-id="3a683-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a683-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3a683-126">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a683-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3a683-127">Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3a683-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a683-128">Note</span><span class="sxs-lookup"><span data-stu-id="3a683-128">Remarks</span></span>  
 <span data-ttu-id="3a683-129">Prima di .NET Framework 4, la Garbage Collection per workstation supportava la Garbage Collection in modalità simultanea, che eseguiva la Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="3a683-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="3a683-130">A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è stata sostituita dalla modalità in background, che esegue anch'essa la Garbage Collection in background in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="3a683-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="3a683-131">A partire da .NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile anche per server.</span><span class="sxs-lookup"><span data-stu-id="3a683-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="3a683-132">L'elemento `<gcConcurrent>` controlla se il runtime esegue la Garbage Collection simultanea o in background, se è disponibile o se esegue la Garbage Collection in primo piano.</span><span class="sxs-lookup"><span data-stu-id="3a683-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3a683-133">A partire da .NET Framework 4, la Garbage Collection in modalità simultanea è sostituita dalla Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="3a683-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="3a683-134">Le condizioni di *simultanee* e *background* vengono usati indifferentemente nella documentazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a683-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="3a683-135">Per disabilitare il Garbage Collection in background, usare l'elemento `<gcConcurrent>`, come illustrato in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3a683-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="3a683-136">Per impostazione predefinita, il runtime usa la Garbage Collection in modalità simultanea che è ottimizzata per la latenza.</span><span class="sxs-lookup"><span data-stu-id="3a683-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="3a683-137">Se si usa un'applicazione che prevede una notevole interazione da parte dell'utente, non disabilitare l'esecuzione simultanea di Garbage Collection in modo da ridurre il tempo di sospensione dell'applicazione durante l'esecuzione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3a683-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="3a683-138">Se si imposta l'attributo `enabled` dell'elemento `<gcConcurrent>` su `false`, da parte del runtime viene usata la Garbage Collection in modalità non simultanea, ottimizzata per la velocità effettiva.</span><span class="sxs-lookup"><span data-stu-id="3a683-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="3a683-139">Il file di configurazione seguente disabilita la Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="3a683-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="3a683-140">Se esiste un'impostazone `<gcConcurrentSetting>` nel file di configurazione del computer, definisce il valore predefinito per tutte le applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a683-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="3a683-141">Con l'impostazione del file di configurazione del computer viene eseguito l'override dell'impostazione del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3a683-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="3a683-142">Per ulteriori informazioni su simultanee e garbage collection in background, vedere la sezione "garbage collection contemporanea" nel [principi fondamentali di Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="3a683-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a683-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="3a683-143">Example</span></span>  
 <span data-ttu-id="3a683-144">L'esempio seguente abilita la Garbage Collection in modalità simultanea.</span><span class="sxs-lookup"><span data-stu-id="3a683-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a683-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a683-145">See Also</span></span>  
 [<span data-ttu-id="3a683-146">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="3a683-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="3a683-147">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="3a683-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="3a683-148">Principi fondamentali di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="3a683-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)
