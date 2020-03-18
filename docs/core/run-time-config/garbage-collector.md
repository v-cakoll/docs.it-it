---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di runtime per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.Learn about run-time settings for configuring how the garbage collector manages memory for .NET Core apps.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733527"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="188da-103">Opzioni di configurazione in fase di esecuzione per la procedura di Garbage CollectionRun-time configuration options for garbage collection</span><span class="sxs-lookup"><span data-stu-id="188da-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="188da-104">Questa pagina contiene informazioni sulle impostazioni del Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="188da-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="188da-105">Se stai cercando di ottenere prestazioni di picco di un'app in esecuzione, prendi in considerazione l'uso di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="188da-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="188da-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="188da-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="188da-107">Le impostazioni sono organizzate in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="188da-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="188da-108">Le impostazioni all'interno di ogni gruppo sono comunemente utilizzate in combinazione tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="188da-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="188da-109">Queste impostazioni possono anche essere modificate dinamicamente dall'app mentre è in esecuzione, pertanto qualsiasi impostazione di runtime impostata può essere sostituita.</span><span class="sxs-lookup"><span data-stu-id="188da-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="188da-110">Alcune impostazioni, ad esempio il livello di [latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="188da-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="188da-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="188da-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="188da-112">Per i valori numerici, utilizzare la notazione decimale per le impostazioni nel file *runtimeconfig.json* e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="188da-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="188da-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="188da-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="188da-114">Sapori di garbage collection</span><span class="sxs-lookup"><span data-stu-id="188da-114">Flavors of garbage collection</span></span>

<span data-ttu-id="188da-115">I due tipi principali di garbage collection sono workstation GC e server GC.</span><span class="sxs-lookup"><span data-stu-id="188da-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="188da-116">Per ulteriori informazioni sulle differenze tra i due, vedere [Nozioni fondamentali sulla procedura di Garbage Collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="188da-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="188da-117">I sottoprogusti della garbage collection sono di sfondo e non simultanei.</span><span class="sxs-lookup"><span data-stu-id="188da-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="188da-118">Utilizzare le impostazioni seguenti per selezionare le tà dei Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="188da-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="188da-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="188da-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="188da-120">Configura se l'applicazione utilizza l'operazione di Garbage Collection per workstation o la procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="188da-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="188da-121">Impostazione predefinita:`false`Operazione compensata workstation ( ).</span><span class="sxs-lookup"><span data-stu-id="188da-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="188da-122">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-122">Setting name</span></span> | <span data-ttu-id="188da-123">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-123">Values</span></span> | <span data-ttu-id="188da-124">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="188da-126">`false`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="188da-126">`false` - workstation</span></span><br/><span data-ttu-id="188da-127">`true`- server</span><span class="sxs-lookup"><span data-stu-id="188da-127">`true` - server</span></span> | <span data-ttu-id="188da-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-129">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="188da-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="188da-130">`false`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="188da-130">`false` - workstation</span></span><br/><span data-ttu-id="188da-131">`true`- server</span><span class="sxs-lookup"><span data-stu-id="188da-131">`true` - server</span></span> | <span data-ttu-id="188da-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="188da-134">`0`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="188da-134">`0` - workstation</span></span><br/><span data-ttu-id="188da-135">`1`- server</span><span class="sxs-lookup"><span data-stu-id="188da-135">`1` - server</span></span> | <span data-ttu-id="188da-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-137">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-138">Server globale</span><span class="sxs-lookup"><span data-stu-id="188da-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="188da-139">`false`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="188da-139">`false` - workstation</span></span><br/><span data-ttu-id="188da-140">`true`- server</span><span class="sxs-lookup"><span data-stu-id="188da-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="188da-141">Esempi</span><span class="sxs-lookup"><span data-stu-id="188da-141">Examples</span></span>

<span data-ttu-id="188da-142">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="188da-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="188da-143">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="188da-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="188da-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="188da-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="188da-145">Configura se l'operazione di Garbage Collection in background (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="188da-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="188da-146">Impostazione predefinita: Abilitato (`true`).</span><span class="sxs-lookup"><span data-stu-id="188da-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="188da-147">Per ulteriori informazioni, consultate [Garbage Collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) in background e Garbage Collection del server in [background.](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)</span><span class="sxs-lookup"><span data-stu-id="188da-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="188da-148">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-148">Setting name</span></span> | <span data-ttu-id="188da-149">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-149">Values</span></span> | <span data-ttu-id="188da-150">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="188da-152">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="188da-152">`true` - background GC</span></span><br/><span data-ttu-id="188da-153">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="188da-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="188da-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-155">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="188da-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="188da-156">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="188da-156">`true` - background GC</span></span><br/><span data-ttu-id="188da-157">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="188da-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="188da-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="188da-160">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="188da-160">`true` - background GC</span></span><br/><span data-ttu-id="188da-161">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="188da-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="188da-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-163">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-164">gcConcurrent (corrente)</span><span class="sxs-lookup"><span data-stu-id="188da-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="188da-165">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="188da-165">`true` - background GC</span></span><br/><span data-ttu-id="188da-166">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="188da-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="188da-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="188da-167">Examples</span></span>

<span data-ttu-id="188da-168">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="188da-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="188da-169">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="188da-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="188da-170">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="188da-170">Manage resource usage</span></span>

<span data-ttu-id="188da-171">Utilizzare le impostazioni descritte in questa sezione per gestire la memoria del Garbage Collector e l'utilizzo del processore.</span><span class="sxs-lookup"><span data-stu-id="188da-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="188da-172">Per ulteriori informazioni su alcune di queste impostazioni, vedere il punto [di mezzo tra workstation e server GC(](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) server).</span><span class="sxs-lookup"><span data-stu-id="188da-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="188da-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="188da-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="188da-174">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="188da-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="188da-175">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="188da-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="188da-176">Se l'affinità del processore GC è abilitata, che `n` è l'impostazione predefinita, l'impostazione del numero di heap affina gli heap/thread GC ai primi `n` processori.</span><span class="sxs-lookup"><span data-stu-id="188da-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="188da-177">Utilizzare le impostazioni affinitize mask o affinitize ranges per specificare esattamente i processori di cui eseguire l'affinità.</span><span class="sxs-lookup"><span data-stu-id="188da-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="188da-178">Se l'affinità del processore GC è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="188da-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="188da-179">Per ulteriori informazioni, vedere le [osservazioni di GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="188da-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="188da-180">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-180">Setting name</span></span> | <span data-ttu-id="188da-181">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-181">Values</span></span> | <span data-ttu-id="188da-182">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="188da-184">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-184">*decimal value*</span></span> | <span data-ttu-id="188da-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-186">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="188da-187">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="188da-187">*hexadecimal value*</span></span> | <span data-ttu-id="188da-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-189">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-190">Metodo GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="188da-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="188da-191">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-191">*decimal value*</span></span> | <span data-ttu-id="188da-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="188da-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="188da-193">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-193">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="188da-194">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="188da-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="188da-195">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="188da-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="188da-196">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="188da-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="188da-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="188da-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="188da-198">Specifica i processori esatti che i thread del Garbage Collector devono utilizzare.</span><span class="sxs-lookup"><span data-stu-id="188da-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="188da-199">Se l'affinità del `System.GC.NoAffinitize` `true`processore è disabilitata impostando su , questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="188da-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="188da-200">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="188da-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="188da-201">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="188da-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="188da-202">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si utilizza la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="188da-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="188da-203">Specifica che devono essere utilizzati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="188da-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="188da-204">Per specificare i successivi 10 processori, ovvero processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), che equivale a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="188da-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="188da-205">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-205">Setting name</span></span> | <span data-ttu-id="188da-206">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-206">Values</span></span> | <span data-ttu-id="188da-207">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="188da-209">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-209">*decimal value*</span></span> | <span data-ttu-id="188da-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-211">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="188da-212">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="188da-212">*hexadecimal value*</span></span> | <span data-ttu-id="188da-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-214">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-215">MASCHERAPer tuttaMaschera</span><span class="sxs-lookup"><span data-stu-id="188da-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="188da-216">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-216">*decimal value*</span></span> | <span data-ttu-id="188da-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="188da-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="188da-218">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="188da-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="188da-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="188da-220">Specifica l'elenco dei processori da utilizzare per i thread del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="188da-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="188da-221">Questa impostazione `System.GC.HeapAffinitizeMask`è simile a , ad eccezione del fatto che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="188da-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="188da-222">Per i sistemi operativi Windows, anteporre al numero o all'intervallo del processore il [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente, ad esempio "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="188da-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="188da-223">Se l'affinità del `System.GC.NoAffinitize` `true`processore è disabilitata impostando su , questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="188da-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="188da-224">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="188da-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="188da-225">Per ulteriori informazioni, consulta [Migliorare la configurazione della CPU per GC sulle macchine con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="188da-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="188da-226">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-226">Setting name</span></span> | <span data-ttu-id="188da-227">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-227">Values</span></span> | <span data-ttu-id="188da-228">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="188da-230">Elenco delimitato da virgole di numeri di processore o intervalli di numeri di processore.</span><span class="sxs-lookup"><span data-stu-id="188da-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="188da-231">Esempio Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="188da-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="188da-232">Esempio di Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="188da-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="188da-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-234">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="188da-235">Elenco delimitato da virgole di numeri di processore o intervalli di numeri di processore.</span><span class="sxs-lookup"><span data-stu-id="188da-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="188da-236">Esempio Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="188da-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="188da-237">Esempio di Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="188da-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="188da-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-238">.NET Core 3.0</span></span> |

<span data-ttu-id="188da-239">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="188da-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="188da-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="188da-241">Configura se il Garbage Collector utilizza o meno [i gruppi della CPU.](/windows/win32/procthread/processor-groups)</span><span class="sxs-lookup"><span data-stu-id="188da-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="188da-242">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende la procedura di Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="188da-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="188da-243">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="188da-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="188da-244">Si applica alla procedura di Garbage Collection per server solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="188da-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="188da-245">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="188da-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="188da-246">Per ulteriori informazioni, consulta [Migliorare la configurazione della CPU per GC sulle macchine con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="188da-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="188da-247">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-247">Setting name</span></span> | <span data-ttu-id="188da-248">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-248">Values</span></span> | <span data-ttu-id="188da-249">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="188da-251">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-251">N/A</span></span> | <span data-ttu-id="188da-252">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-252">N/A</span></span> | <span data-ttu-id="188da-253">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-253">N/A</span></span> |
| <span data-ttu-id="188da-254">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="188da-255">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="188da-255">`0` - disabled</span></span><br/><span data-ttu-id="188da-256">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="188da-256">`1` - enabled</span></span> | <span data-ttu-id="188da-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-258">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-259">Gruppo GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="188da-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="188da-260">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="188da-260">`false` - disabled</span></span><br/><span data-ttu-id="188da-261">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="188da-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="188da-262">Per configurare Common Language Runtime (CLR) per distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [Thread_UseAllCpuGroups elemento.](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)</span><span class="sxs-lookup"><span data-stu-id="188da-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="188da-263">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della variabile di `COMPlus_Thread_UseAllCpuGroups` ambiente su `1`.</span><span class="sxs-lookup"><span data-stu-id="188da-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="188da-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="188da-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="188da-265">Specifica se *eseguire l'affinità* di thread di Garbage Collection con i processori.</span><span class="sxs-lookup"><span data-stu-id="188da-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="188da-266">Per affinizzare un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="188da-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="188da-267">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="188da-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="188da-268">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="188da-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="188da-269">Impostazione predefinita: affinizzare i thread`false`di Garbage Collection con processori ( ).</span><span class="sxs-lookup"><span data-stu-id="188da-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="188da-270">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-270">Setting name</span></span> | <span data-ttu-id="188da-271">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-271">Values</span></span> | <span data-ttu-id="188da-272">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="188da-274">`false`- affinizzare</span><span class="sxs-lookup"><span data-stu-id="188da-274">`false` - affinitize</span></span><br/><span data-ttu-id="188da-275">`true`- non affinizzare</span><span class="sxs-lookup"><span data-stu-id="188da-275">`true` - don't affinitize</span></span> | <span data-ttu-id="188da-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-277">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="188da-278">`0`- affinizzare</span><span class="sxs-lookup"><span data-stu-id="188da-278">`0` - affinitize</span></span><br/><span data-ttu-id="188da-279">`1`- non affinizzare</span><span class="sxs-lookup"><span data-stu-id="188da-279">`1` - don't affinitize</span></span> | <span data-ttu-id="188da-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-281">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="188da-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="188da-283">`false`- affinizzare</span><span class="sxs-lookup"><span data-stu-id="188da-283">`false` - affinitize</span></span><br/><span data-ttu-id="188da-284">`true`- non affinizzare</span><span class="sxs-lookup"><span data-stu-id="188da-284">`true` - don't affinitize</span></span> | <span data-ttu-id="188da-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="188da-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="188da-286">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="188da-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="188da-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="188da-288">Specifica la dimensione massima di commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="188da-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="188da-289">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-289">Setting name</span></span> | <span data-ttu-id="188da-290">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-290">Values</span></span> | <span data-ttu-id="188da-291">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="188da-293">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-293">*decimal value*</span></span> | <span data-ttu-id="188da-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-295">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="188da-296">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="188da-296">*hexadecimal value*</span></span> | <span data-ttu-id="188da-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-297">.NET Core 3.0</span></span> |

<span data-ttu-id="188da-298">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-298">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="188da-299">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="188da-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="188da-300">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="188da-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="188da-301">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibyte (MiB), i valori sarebbero 209715200 per il file JSON e 0xC8000000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="188da-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="188da-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="188da-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="188da-303">Specifica l'utilizzo dell'heap GC come percentuale della memoria totale.</span><span class="sxs-lookup"><span data-stu-id="188da-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="188da-304">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-304">Setting name</span></span> | <span data-ttu-id="188da-305">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-305">Values</span></span> | <span data-ttu-id="188da-306">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="188da-308">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-308">*decimal value*</span></span> | <span data-ttu-id="188da-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="188da-310">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="188da-311">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="188da-311">*hexadecimal value*</span></span> | <span data-ttu-id="188da-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-312">.NET Core 3.0</span></span> |

<span data-ttu-id="188da-313">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-313">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="188da-314">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="188da-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="188da-315">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="188da-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="188da-316">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="188da-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="188da-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="188da-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="188da-318">Configura se i segmenti che devono essere eliminati vengono inseriti in un elenco di standby per un utilizzo futuro o vengono rilasciati nuovamente al sistema operativo (OS).</span><span class="sxs-lookup"><span data-stu-id="188da-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="188da-319">Impostazione predefinita: rilasciare i segmenti`false`al sistema operativo ( ).</span><span class="sxs-lookup"><span data-stu-id="188da-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="188da-320">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-320">Setting name</span></span> | <span data-ttu-id="188da-321">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-321">Values</span></span> | <span data-ttu-id="188da-322">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="188da-324">`false`- rilascio al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="188da-324">`false` - release to OS</span></span><br/><span data-ttu-id="188da-325">`true`- messo in standby</span><span class="sxs-lookup"><span data-stu-id="188da-325">`true` - put on standby</span></span> | <span data-ttu-id="188da-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-327">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="188da-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="188da-328">`false`- rilascio al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="188da-328">`false` - release to OS</span></span><br/><span data-ttu-id="188da-329">`true`- messo in standby</span><span class="sxs-lookup"><span data-stu-id="188da-329">`true` - put on standby</span></span> | <span data-ttu-id="188da-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-331">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="188da-332">`0`- rilascio al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="188da-332">`0` - release to OS</span></span><br/><span data-ttu-id="188da-333">`1`- messo in standby</span><span class="sxs-lookup"><span data-stu-id="188da-333">`1` - put on standby</span></span> | <span data-ttu-id="188da-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="188da-335">Esempi</span><span class="sxs-lookup"><span data-stu-id="188da-335">Examples</span></span>

<span data-ttu-id="188da-336">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="188da-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="188da-337">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="188da-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="188da-338">Pagine grandi</span><span class="sxs-lookup"><span data-stu-id="188da-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="188da-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="188da-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="188da-340">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="188da-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="188da-341">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="188da-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="188da-342">Questa è un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="188da-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="188da-343">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-343">Setting name</span></span> | <span data-ttu-id="188da-344">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-344">Values</span></span> | <span data-ttu-id="188da-345">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="188da-347">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-347">N/A</span></span> | <span data-ttu-id="188da-348">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-348">N/A</span></span> | <span data-ttu-id="188da-349">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-349">N/A</span></span> |
| <span data-ttu-id="188da-350">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="188da-351">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="188da-351">`0` - disabled</span></span><br/><span data-ttu-id="188da-352">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="188da-352">`1` - enabled</span></span> | <span data-ttu-id="188da-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="188da-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="188da-354">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="188da-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="188da-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="188da-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="188da-356">Configura il supporto del Garbage Collector su piattaforme a 64 bit per array di dimensioni superiori a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="188da-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="188da-357">Impostazione predefinita: Abilitato (`1`).</span><span class="sxs-lookup"><span data-stu-id="188da-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="188da-358">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="188da-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="188da-359">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-359">Setting name</span></span> | <span data-ttu-id="188da-360">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-360">Values</span></span> | <span data-ttu-id="188da-361">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="188da-363">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-363">N/A</span></span> | <span data-ttu-id="188da-364">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-364">N/A</span></span> | <span data-ttu-id="188da-365">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-365">N/A</span></span> |
| <span data-ttu-id="188da-366">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="188da-367">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="188da-367">`1` - enabled</span></span><br/> <span data-ttu-id="188da-368">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="188da-368">`0` - disabled</span></span> | <span data-ttu-id="188da-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-370">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="188da-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="188da-372">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="188da-372">`1` - enabled</span></span><br/> <span data-ttu-id="188da-373">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="188da-373">`0` - disabled</span></span> | <span data-ttu-id="188da-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="188da-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="188da-375">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="188da-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="188da-376">System.GC.LOHSoglia/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="188da-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="188da-377">Specifica la dimensione della soglia, in byte, che determina l'attivazione dell'heap oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="188da-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="188da-378">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="188da-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="188da-379">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="188da-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="188da-380">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-380">Setting name</span></span> | <span data-ttu-id="188da-381">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-381">Values</span></span> | <span data-ttu-id="188da-382">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="188da-384">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-384">*decimal value*</span></span> | <span data-ttu-id="188da-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-386">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="188da-387">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="188da-387">*hexadecimal value*</span></span> | <span data-ttu-id="188da-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="188da-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="188da-389">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="188da-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="188da-390">Soglia GCLOH</span><span class="sxs-lookup"><span data-stu-id="188da-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="188da-391">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="188da-391">*decimal value*</span></span> | <span data-ttu-id="188da-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="188da-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="188da-393">Esempio:</span><span class="sxs-lookup"><span data-stu-id="188da-393">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="188da-394">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="188da-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="188da-395">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="188da-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="188da-396">Ad esempio, per impostare una dimensione di soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="188da-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="188da-397">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="188da-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="188da-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="188da-398">COMPlus_GCName</span></span>

- <span data-ttu-id="188da-399">Specifica un percorso alla libreria contenente il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="188da-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="188da-400">Per ulteriori informazioni, consultate [Progettazione di caricatori GC autonomi.](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)</span><span class="sxs-lookup"><span data-stu-id="188da-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="188da-401">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="188da-401">Setting name</span></span> | <span data-ttu-id="188da-402">Valori</span><span class="sxs-lookup"><span data-stu-id="188da-402">Values</span></span> | <span data-ttu-id="188da-403">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="188da-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="188da-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="188da-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="188da-405">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-405">N/A</span></span> | <span data-ttu-id="188da-406">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-406">N/A</span></span> | <span data-ttu-id="188da-407">N/D</span><span class="sxs-lookup"><span data-stu-id="188da-407">N/A</span></span> |
| <span data-ttu-id="188da-408">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="188da-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="188da-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="188da-409">*string_path*</span></span> | <span data-ttu-id="188da-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="188da-410">.NET Core 2.0</span></span> |
