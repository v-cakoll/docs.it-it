---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di runtime per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.Learn about run-time settings for configuring how the garbage collector manages memory for .NET Core apps.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: ec575bdd17c8a7c290673b7085074bbba94cedef
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102866"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="4b201-103">Opzioni di configurazione in fase di esecuzione per la procedura di Garbage CollectionRun-time configuration options for garbage collection</span><span class="sxs-lookup"><span data-stu-id="4b201-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="4b201-104">Questa pagina contiene informazioni sulle impostazioni del Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4b201-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="4b201-105">Se stai cercando di ottenere prestazioni di picco di un'app in esecuzione, prendi in considerazione l'uso di queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="4b201-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="4b201-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="4b201-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="4b201-107">Le impostazioni sono organizzate in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="4b201-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="4b201-108">Le impostazioni all'interno di ogni gruppo sono comunemente utilizzate in combinazione tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="4b201-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="4b201-109">Queste impostazioni possono anche essere modificate dinamicamente dall'app mentre è in esecuzione, pertanto qualsiasi impostazione di runtime impostata può essere sostituita.</span><span class="sxs-lookup"><span data-stu-id="4b201-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="4b201-110">Alcune impostazioni, ad esempio il livello di [latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4b201-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="4b201-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="4b201-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="4b201-112">Per i valori numerici, utilizzare la notazione decimale per le impostazioni nel file *runtimeconfig.json* e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b201-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="4b201-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="4b201-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="4b201-114">Sapori di garbage collection</span><span class="sxs-lookup"><span data-stu-id="4b201-114">Flavors of garbage collection</span></span>

<span data-ttu-id="4b201-115">I due tipi principali di garbage collection sono workstation GC e server GC.</span><span class="sxs-lookup"><span data-stu-id="4b201-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="4b201-116">Per ulteriori informazioni sulle differenze tra i due, vedere [Garbage Collection per workstation e server.](../../standard/garbage-collection/workstation-server-gc.md)</span><span class="sxs-lookup"><span data-stu-id="4b201-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="4b201-117">I sottoprogusti della garbage collection sono di sfondo e non simultanei.</span><span class="sxs-lookup"><span data-stu-id="4b201-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="4b201-118">Utilizzare le impostazioni seguenti per selezionare le tà dei Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="4b201-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="4b201-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="4b201-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="4b201-120">Configura se l'applicazione utilizza l'operazione di Garbage Collection per workstation o la procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4b201-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="4b201-121">Impostazione predefinita:`false`Operazione compensata workstation ( ).</span><span class="sxs-lookup"><span data-stu-id="4b201-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="4b201-122">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-122">Setting name</span></span> | <span data-ttu-id="4b201-123">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-123">Values</span></span> | <span data-ttu-id="4b201-124">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="4b201-126">`false`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="4b201-126">`false` - workstation</span></span><br/><span data-ttu-id="4b201-127">`true`- server</span><span class="sxs-lookup"><span data-stu-id="4b201-127">`true` - server</span></span> | <span data-ttu-id="4b201-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-129">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="4b201-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="4b201-130">`false`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="4b201-130">`false` - workstation</span></span><br/><span data-ttu-id="4b201-131">`true`- server</span><span class="sxs-lookup"><span data-stu-id="4b201-131">`true` - server</span></span> | <span data-ttu-id="4b201-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="4b201-134">`0`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="4b201-134">`0` - workstation</span></span><br/><span data-ttu-id="4b201-135">`1`- server</span><span class="sxs-lookup"><span data-stu-id="4b201-135">`1` - server</span></span> | <span data-ttu-id="4b201-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-137">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-138">Server globale</span><span class="sxs-lookup"><span data-stu-id="4b201-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="4b201-139">`false`- stazione di lavoro</span><span class="sxs-lookup"><span data-stu-id="4b201-139">`false` - workstation</span></span><br/><span data-ttu-id="4b201-140">`true`- server</span><span class="sxs-lookup"><span data-stu-id="4b201-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="4b201-141">Esempi</span><span class="sxs-lookup"><span data-stu-id="4b201-141">Examples</span></span>

<span data-ttu-id="4b201-142">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="4b201-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="4b201-143">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="4b201-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="4b201-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="4b201-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="4b201-145">Configura se l'operazione di Garbage Collection in background (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4b201-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="4b201-146">Impostazione predefinita: Abilitato (`true`).</span><span class="sxs-lookup"><span data-stu-id="4b201-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="4b201-147">Per ulteriori informazioni, consultate [Garbage Collection](../../standard/garbage-collection/background-gc.md)in background .</span><span class="sxs-lookup"><span data-stu-id="4b201-147">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="4b201-148">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-148">Setting name</span></span> | <span data-ttu-id="4b201-149">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-149">Values</span></span> | <span data-ttu-id="4b201-150">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="4b201-152">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="4b201-152">`true` - background GC</span></span><br/><span data-ttu-id="4b201-153">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="4b201-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="4b201-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-155">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="4b201-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="4b201-156">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="4b201-156">`true` - background GC</span></span><br/><span data-ttu-id="4b201-157">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="4b201-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="4b201-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="4b201-160">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="4b201-160">`true` - background GC</span></span><br/><span data-ttu-id="4b201-161">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="4b201-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="4b201-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-163">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-164">gcConcurrent (corrente)</span><span class="sxs-lookup"><span data-stu-id="4b201-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="4b201-165">`true`- sfondo GC</span><span class="sxs-lookup"><span data-stu-id="4b201-165">`true` - background GC</span></span><br/><span data-ttu-id="4b201-166">`false`- GC non simultaneo</span><span class="sxs-lookup"><span data-stu-id="4b201-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="4b201-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="4b201-167">Examples</span></span>

<span data-ttu-id="4b201-168">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="4b201-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="4b201-169">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="4b201-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="4b201-170">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="4b201-170">Manage resource usage</span></span>

<span data-ttu-id="4b201-171">Utilizzare le impostazioni descritte in questa sezione per gestire la memoria del Garbage Collector e l'utilizzo del processore.</span><span class="sxs-lookup"><span data-stu-id="4b201-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="4b201-172">Per ulteriori informazioni su alcune di queste impostazioni, vedere il punto [di mezzo tra workstation e server GC(](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) server).</span><span class="sxs-lookup"><span data-stu-id="4b201-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="4b201-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="4b201-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="4b201-174">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="4b201-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="4b201-175">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4b201-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="4b201-176">Se l'affinità [del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è abilitata, che `n` è l'impostazione predefinita, l'impostazione del numero di heap affina gli heap/thread GC ai primi `n` processori.</span><span class="sxs-lookup"><span data-stu-id="4b201-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="4b201-177">Utilizzare le impostazioni [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) per specificare esattamente i processori di cui eseguire l'affinità.</span><span class="sxs-lookup"><span data-stu-id="4b201-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="4b201-178">Se [l'affinità del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="4b201-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="4b201-179">Per ulteriori informazioni, vedere le [osservazioni di GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="4b201-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="4b201-180">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-180">Setting name</span></span> | <span data-ttu-id="4b201-181">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-181">Values</span></span> | <span data-ttu-id="4b201-182">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="4b201-184">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-184">*decimal value*</span></span> | <span data-ttu-id="4b201-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-186">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="4b201-187">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-187">*hexadecimal value*</span></span> | <span data-ttu-id="4b201-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-189">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-190">Metodo GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="4b201-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="4b201-191">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-191">*decimal value*</span></span> | <span data-ttu-id="4b201-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="4b201-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="4b201-193">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-193">Example:</span></span>

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
> <span data-ttu-id="4b201-194">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="4b201-195">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="4b201-196">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b201-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="4b201-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="4b201-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="4b201-198">Specifica i processori esatti che i thread del Garbage Collector devono utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4b201-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="4b201-199">Se [l'affinità del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="4b201-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="4b201-200">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4b201-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="4b201-201">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="4b201-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="4b201-202">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si utilizza la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="4b201-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="4b201-203">Specifica che devono essere utilizzati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="4b201-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="4b201-204">Per specificare i successivi 10 processori, ovvero processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), che equivale a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="4b201-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="4b201-205">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-205">Setting name</span></span> | <span data-ttu-id="4b201-206">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-206">Values</span></span> | <span data-ttu-id="4b201-207">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="4b201-209">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-209">*decimal value*</span></span> | <span data-ttu-id="4b201-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-211">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="4b201-212">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-212">*hexadecimal value*</span></span> | <span data-ttu-id="4b201-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-214">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-215">MASCHERAPer tuttaMaschera</span><span class="sxs-lookup"><span data-stu-id="4b201-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="4b201-216">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-216">*decimal value*</span></span> | <span data-ttu-id="4b201-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="4b201-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="4b201-218">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="4b201-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="4b201-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="4b201-220">Specifica l'elenco dei processori da utilizzare per i thread del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="4b201-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="4b201-221">Questa impostazione è simile a [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), ad eccezione del fatto che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="4b201-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="4b201-222">Per i sistemi operativi Windows, anteporre al numero o all'intervallo del processore il [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente, ad esempio "0:1-10,0:12,1:50-52,1:70".</span><span class="sxs-lookup"><span data-stu-id="4b201-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="4b201-223">Se [l'affinità del processore GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="4b201-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="4b201-224">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4b201-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="4b201-225">Per ulteriori informazioni, consulta [Migliorare la configurazione della CPU per GC sulle macchine con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="4b201-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="4b201-226">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-226">Setting name</span></span> | <span data-ttu-id="4b201-227">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-227">Values</span></span> | <span data-ttu-id="4b201-228">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="4b201-230">Elenco delimitato da virgole di numeri di processore o intervalli di numeri di processore.</span><span class="sxs-lookup"><span data-stu-id="4b201-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="4b201-231">Esempio Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="4b201-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="4b201-232">Esempio di Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="4b201-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="4b201-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-234">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="4b201-235">Elenco delimitato da virgole di numeri di processore o intervalli di numeri di processore.</span><span class="sxs-lookup"><span data-stu-id="4b201-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="4b201-236">Esempio Unix: "1-10,12,50-52,70"</span><span class="sxs-lookup"><span data-stu-id="4b201-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="4b201-237">Esempio di Windows: "0:1-10,0:12,1:50-52,1:70"</span><span class="sxs-lookup"><span data-stu-id="4b201-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="4b201-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-238">.NET Core 3.0</span></span> |

<span data-ttu-id="4b201-239">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="4b201-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="4b201-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="4b201-241">Configura se il Garbage Collector utilizza o meno [i gruppi della CPU.](/windows/win32/procthread/processor-groups)</span><span class="sxs-lookup"><span data-stu-id="4b201-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="4b201-242">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende la procedura di Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="4b201-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="4b201-243">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="4b201-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="4b201-244">Si applica alla procedura di Garbage Collection per server solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="4b201-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="4b201-245">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="4b201-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="4b201-246">Per ulteriori informazioni, consulta [Migliorare la configurazione della CPU per GC sulle macchine con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="4b201-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="4b201-247">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-247">Setting name</span></span> | <span data-ttu-id="4b201-248">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-248">Values</span></span> | <span data-ttu-id="4b201-249">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="4b201-251">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-251">N/A</span></span> | <span data-ttu-id="4b201-252">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-252">N/A</span></span> | <span data-ttu-id="4b201-253">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-253">N/A</span></span> |
| <span data-ttu-id="4b201-254">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="4b201-255">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-255">`0` - disabled</span></span><br/><span data-ttu-id="4b201-256">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-256">`1` - enabled</span></span> | <span data-ttu-id="4b201-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-258">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-259">Gruppo GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="4b201-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="4b201-260">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-260">`false` - disabled</span></span><br/><span data-ttu-id="4b201-261">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="4b201-262">Per configurare Common Language Runtime (CLR) per distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [Thread_UseAllCpuGroups elemento.](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)</span><span class="sxs-lookup"><span data-stu-id="4b201-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="4b201-263">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della variabile di `COMPlus_Thread_UseAllCpuGroups` ambiente su `1`.</span><span class="sxs-lookup"><span data-stu-id="4b201-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="4b201-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="4b201-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="4b201-265">Specifica se *eseguire l'affinità* di thread di Garbage Collection con i processori.</span><span class="sxs-lookup"><span data-stu-id="4b201-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="4b201-266">Per affinizzare un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="4b201-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="4b201-267">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="4b201-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="4b201-268">Si applica solo alla procedura di Garbage Collection per server.</span><span class="sxs-lookup"><span data-stu-id="4b201-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="4b201-269">Impostazione predefinita: affinizzare i thread`false`di Garbage Collection con processori ( ).</span><span class="sxs-lookup"><span data-stu-id="4b201-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="4b201-270">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-270">Setting name</span></span> | <span data-ttu-id="4b201-271">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-271">Values</span></span> | <span data-ttu-id="4b201-272">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="4b201-274">`false`- affinizzare</span><span class="sxs-lookup"><span data-stu-id="4b201-274">`false` - affinitize</span></span><br/><span data-ttu-id="4b201-275">`true`- non affinizzare</span><span class="sxs-lookup"><span data-stu-id="4b201-275">`true` - don't affinitize</span></span> | <span data-ttu-id="4b201-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-277">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="4b201-278">`0`- affinizzare</span><span class="sxs-lookup"><span data-stu-id="4b201-278">`0` - affinitize</span></span><br/><span data-ttu-id="4b201-279">`1`- non affinizzare</span><span class="sxs-lookup"><span data-stu-id="4b201-279">`1` - don't affinitize</span></span> | <span data-ttu-id="4b201-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-281">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="4b201-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="4b201-283">`false`- affinizzare</span><span class="sxs-lookup"><span data-stu-id="4b201-283">`false` - affinitize</span></span><br/><span data-ttu-id="4b201-284">`true`- non affinizzare</span><span class="sxs-lookup"><span data-stu-id="4b201-284">`true` - don't affinitize</span></span> | <span data-ttu-id="4b201-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="4b201-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="4b201-286">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="4b201-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="4b201-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="4b201-288">Specifica la dimensione massima di commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="4b201-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="4b201-289">Questa impostazione si applica solo ai computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="4b201-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="4b201-290">Il valore predefinito, che si applica solo in alcuni casi, è il maggiore di 20 MB o il 75% del limite di memoria sul contenitore.</span><span class="sxs-lookup"><span data-stu-id="4b201-290">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="4b201-291">Il valore predefinito viene applicato se:</span><span class="sxs-lookup"><span data-stu-id="4b201-291">The default value applies if:</span></span>

  - <span data-ttu-id="4b201-292">Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="4b201-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="4b201-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) non impostato.</span><span class="sxs-lookup"><span data-stu-id="4b201-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="4b201-294">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-294">Setting name</span></span> | <span data-ttu-id="4b201-295">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-295">Values</span></span> | <span data-ttu-id="4b201-296">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="4b201-298">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-298">*decimal value*</span></span> | <span data-ttu-id="4b201-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-300">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="4b201-301">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-301">*hexadecimal value*</span></span> | <span data-ttu-id="4b201-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-302">.NET Core 3.0</span></span> |

<span data-ttu-id="4b201-303">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-303">Example:</span></span>

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
> <span data-ttu-id="4b201-304">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="4b201-305">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="4b201-306">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibyte (MiB), i valori sarebbero 209715200 per il file JSON e 0xC8000000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b201-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="4b201-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="4b201-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="4b201-308">Specifica l'utilizzo consentito dell'heap GC come percentuale della memoria fisica totale.</span><span class="sxs-lookup"><span data-stu-id="4b201-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="4b201-309">Se è impostato anche [System.GC.HeapHardLimit,](#systemgcheaphardlimitcomplus_gcheaphardlimit) questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="4b201-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="4b201-310">Questa impostazione si applica solo ai computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="4b201-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="4b201-311">Se il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato, la percentuale viene calcolata come percentuale di tale limite di memoria.</span><span class="sxs-lookup"><span data-stu-id="4b201-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="4b201-312">Il valore predefinito, che si applica solo in alcuni casi, è il minore di 20 MB o il 75% del limite di memoria sul contenitore.</span><span class="sxs-lookup"><span data-stu-id="4b201-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="4b201-313">Il valore predefinito viene applicato se:</span><span class="sxs-lookup"><span data-stu-id="4b201-313">The default value applies if:</span></span>

  - <span data-ttu-id="4b201-314">Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="4b201-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="4b201-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) non impostato.</span><span class="sxs-lookup"><span data-stu-id="4b201-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="4b201-316">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-316">Setting name</span></span> | <span data-ttu-id="4b201-317">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-317">Values</span></span> | <span data-ttu-id="4b201-318">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="4b201-320">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-320">*decimal value*</span></span> | <span data-ttu-id="4b201-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="4b201-322">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="4b201-323">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-323">*hexadecimal value*</span></span> | <span data-ttu-id="4b201-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-324">.NET Core 3.0</span></span> |

<span data-ttu-id="4b201-325">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-325">Example:</span></span>

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
> <span data-ttu-id="4b201-326">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="4b201-327">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="4b201-328">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b201-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="4b201-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="4b201-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="4b201-330">Configura se i segmenti che devono essere eliminati vengono inseriti in un elenco di standby per un utilizzo futuro o vengono rilasciati nuovamente al sistema operativo (OS).</span><span class="sxs-lookup"><span data-stu-id="4b201-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="4b201-331">Impostazione predefinita: rilasciare i segmenti`false`al sistema operativo ( ).</span><span class="sxs-lookup"><span data-stu-id="4b201-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="4b201-332">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-332">Setting name</span></span> | <span data-ttu-id="4b201-333">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-333">Values</span></span> | <span data-ttu-id="4b201-334">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="4b201-336">`false`- rilascio al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4b201-336">`false` - release to OS</span></span><br/><span data-ttu-id="4b201-337">`true`- messo in standby</span><span class="sxs-lookup"><span data-stu-id="4b201-337">`true` - put on standby</span></span> | <span data-ttu-id="4b201-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-339">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="4b201-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="4b201-340">`false`- rilascio al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4b201-340">`false` - release to OS</span></span><br/><span data-ttu-id="4b201-341">`true`- messo in standby</span><span class="sxs-lookup"><span data-stu-id="4b201-341">`true` - put on standby</span></span> | <span data-ttu-id="4b201-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-343">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="4b201-344">`0`- rilascio al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="4b201-344">`0` - release to OS</span></span><br/><span data-ttu-id="4b201-345">`1`- messo in standby</span><span class="sxs-lookup"><span data-stu-id="4b201-345">`1` - put on standby</span></span> | <span data-ttu-id="4b201-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="4b201-347">Esempi</span><span class="sxs-lookup"><span data-stu-id="4b201-347">Examples</span></span>

<span data-ttu-id="4b201-348">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="4b201-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="4b201-349">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="4b201-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="4b201-350">Pagine grandi</span><span class="sxs-lookup"><span data-stu-id="4b201-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="4b201-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="4b201-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="4b201-352">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="4b201-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="4b201-353">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="4b201-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="4b201-354">Questa è un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="4b201-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="4b201-355">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-355">Setting name</span></span> | <span data-ttu-id="4b201-356">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-356">Values</span></span> | <span data-ttu-id="4b201-357">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="4b201-359">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-359">N/A</span></span> | <span data-ttu-id="4b201-360">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-360">N/A</span></span> | <span data-ttu-id="4b201-361">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-361">N/A</span></span> |
| <span data-ttu-id="4b201-362">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="4b201-363">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-363">`0` - disabled</span></span><br/><span data-ttu-id="4b201-364">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-364">`1` - enabled</span></span> | <span data-ttu-id="4b201-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4b201-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="4b201-366">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="4b201-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="4b201-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="4b201-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="4b201-368">Configura il supporto del Garbage Collector su piattaforme a 64 bit per array di dimensioni superiori a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="4b201-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="4b201-369">Impostazione predefinita: Abilitato (`1`).</span><span class="sxs-lookup"><span data-stu-id="4b201-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="4b201-370">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="4b201-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="4b201-371">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-371">Setting name</span></span> | <span data-ttu-id="4b201-372">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-372">Values</span></span> | <span data-ttu-id="4b201-373">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="4b201-375">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-375">N/A</span></span> | <span data-ttu-id="4b201-376">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-376">N/A</span></span> | <span data-ttu-id="4b201-377">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-377">N/A</span></span> |
| <span data-ttu-id="4b201-378">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="4b201-379">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-379">`1` - enabled</span></span><br/> <span data-ttu-id="4b201-380">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-380">`0` - disabled</span></span> | <span data-ttu-id="4b201-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-382">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="4b201-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="4b201-384">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-384">`1` - enabled</span></span><br/> <span data-ttu-id="4b201-385">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="4b201-385">`0` - disabled</span></span> | <span data-ttu-id="4b201-386">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="4b201-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="4b201-387">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="4b201-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="4b201-388">System.GC.LOHSoglia/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="4b201-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="4b201-389">Specifica la dimensione della soglia, in byte, che determina l'attivazione dell'heap oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="4b201-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="4b201-390">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="4b201-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="4b201-391">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="4b201-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="4b201-392">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-392">Setting name</span></span> | <span data-ttu-id="4b201-393">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-393">Values</span></span> | <span data-ttu-id="4b201-394">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="4b201-396">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-396">*decimal value*</span></span> | <span data-ttu-id="4b201-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-398">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="4b201-399">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-399">*hexadecimal value*</span></span> | <span data-ttu-id="4b201-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="4b201-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="4b201-401">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="4b201-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="4b201-402">Soglia GCLOH</span><span class="sxs-lookup"><span data-stu-id="4b201-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="4b201-403">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="4b201-403">*decimal value*</span></span> | <span data-ttu-id="4b201-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="4b201-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="4b201-405">Esempio:</span><span class="sxs-lookup"><span data-stu-id="4b201-405">Example:</span></span>

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
> <span data-ttu-id="4b201-406">Se si imposta l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="4b201-407">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="4b201-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="4b201-408">Ad esempio, per impostare una dimensione di soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b201-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="4b201-409">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="4b201-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="4b201-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="4b201-410">COMPlus_GCName</span></span>

- <span data-ttu-id="4b201-411">Specifica un percorso alla libreria contenente il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="4b201-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="4b201-412">Per ulteriori informazioni, consultate [Progettazione di caricatori GC autonomi.](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)</span><span class="sxs-lookup"><span data-stu-id="4b201-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="4b201-413">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="4b201-413">Setting name</span></span> | <span data-ttu-id="4b201-414">Valori</span><span class="sxs-lookup"><span data-stu-id="4b201-414">Values</span></span> | <span data-ttu-id="4b201-415">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="4b201-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="4b201-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4b201-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="4b201-417">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-417">N/A</span></span> | <span data-ttu-id="4b201-418">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-418">N/A</span></span> | <span data-ttu-id="4b201-419">N/D</span><span class="sxs-lookup"><span data-stu-id="4b201-419">N/A</span></span> |
| <span data-ttu-id="4b201-420">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="4b201-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="4b201-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="4b201-421">*string_path*</span></span> | <span data-ttu-id="4b201-422">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4b201-422">.NET Core 2.0</span></span> |
