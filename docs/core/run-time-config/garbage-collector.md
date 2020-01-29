---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di run-time per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733527"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="55eb4-103">Opzioni di configurazione in fase di esecuzione per Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="55eb4-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="55eb4-104">Questa pagina contiene informazioni sulle impostazioni di Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="55eb4-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="55eb4-105">Se si sta tentando di ottenere prestazioni ottimali di un'app in esecuzione, è consigliabile usare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="55eb4-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="55eb4-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="55eb4-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="55eb4-107">Le impostazioni sono disposte in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="55eb4-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="55eb4-108">Le impostazioni all'interno di ogni gruppo vengono comunemente usate insieme tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="55eb4-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="55eb4-109">Queste impostazioni possono essere modificate anche in modo dinamico dall'app mentre è in esecuzione, quindi è possibile eseguire l'override di tutte le impostazioni di runtime impostate.</span><span class="sxs-lookup"><span data-stu-id="55eb4-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="55eb4-110">Alcune impostazioni, ad esempio il [livello di latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="55eb4-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="55eb4-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="55eb4-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="55eb4-112">Per i valori numerici, usare la notazione decimale per le impostazioni nel file *runtimeconfig. JSON* e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="55eb4-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="55eb4-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="55eb4-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="55eb4-114">Tipi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="55eb4-114">Flavors of garbage collection</span></span>

<span data-ttu-id="55eb4-115">I due principali tipi di Garbage Collection sono GC della workstation e GC del server.</span><span class="sxs-lookup"><span data-stu-id="55eb4-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="55eb4-116">Per ulteriori informazioni sulle differenze tra le due, vedere [nozioni fondamentali di Garbage Collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="55eb4-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="55eb4-117">Le sottoversioni di Garbage Collection sono in background e non simultanee.</span><span class="sxs-lookup"><span data-stu-id="55eb4-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="55eb4-118">Usare le impostazioni seguenti per selezionare le versioni di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="55eb4-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="55eb4-119">System. GC. Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="55eb4-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="55eb4-120">Configura se l'applicazione utilizza la workstation Garbage Collection o Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="55eb4-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="55eb4-121">Impostazione predefinita: Garbage Collection workstation (`false`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="55eb4-122">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-122">Setting name</span></span> | <span data-ttu-id="55eb4-123">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-123">Values</span></span> | <span data-ttu-id="55eb4-124">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-125">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="55eb4-126">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="55eb4-126">`false` - workstation</span></span><br/><span data-ttu-id="55eb4-127">Server `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-127">`true` - server</span></span> | <span data-ttu-id="55eb4-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-129">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="55eb4-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="55eb4-130">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="55eb4-130">`false` - workstation</span></span><br/><span data-ttu-id="55eb4-131">Server `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-131">`true` - server</span></span> | <span data-ttu-id="55eb4-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="55eb4-134">workstation `0`</span><span class="sxs-lookup"><span data-stu-id="55eb4-134">`0` - workstation</span></span><br/><span data-ttu-id="55eb4-135">Server `1`</span><span class="sxs-lookup"><span data-stu-id="55eb4-135">`1` - server</span></span> | <span data-ttu-id="55eb4-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-137">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="55eb4-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="55eb4-139">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="55eb4-139">`false` - workstation</span></span><br/><span data-ttu-id="55eb4-140">Server `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="55eb4-141">Esempi</span><span class="sxs-lookup"><span data-stu-id="55eb4-141">Examples</span></span>

<span data-ttu-id="55eb4-142">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="55eb4-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="55eb4-143">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="55eb4-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="55eb4-144">System. GC. Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="55eb4-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="55eb4-145">Configura se la Garbage Collection di sfondo (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="55eb4-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="55eb4-146">Impostazione predefinita: abilitata (`true`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="55eb4-147">Per ulteriori informazioni, vedere [Garbage Collection in background](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) e [Garbage Collection server in background](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="55eb4-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="55eb4-148">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-148">Setting name</span></span> | <span data-ttu-id="55eb4-149">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-149">Values</span></span> | <span data-ttu-id="55eb4-150">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-151">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="55eb4-152">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-152">`true` - background GC</span></span><br/><span data-ttu-id="55eb4-153">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="55eb4-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="55eb4-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-155">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="55eb4-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="55eb4-156">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-156">`true` - background GC</span></span><br/><span data-ttu-id="55eb4-157">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="55eb4-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="55eb4-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="55eb4-160">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-160">`true` - background GC</span></span><br/><span data-ttu-id="55eb4-161">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="55eb4-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="55eb4-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-163">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="55eb4-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="55eb4-165">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-165">`true` - background GC</span></span><br/><span data-ttu-id="55eb4-166">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="55eb4-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="55eb4-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="55eb4-167">Examples</span></span>

<span data-ttu-id="55eb4-168">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="55eb4-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="55eb4-169">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="55eb4-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="55eb4-170">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="55eb4-170">Manage resource usage</span></span>

<span data-ttu-id="55eb4-171">Usare le impostazioni descritte in questa sezione per gestire l'utilizzo della memoria e del processore del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="55eb4-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="55eb4-172">Per altre informazioni su alcune di queste impostazioni, vedere la parte intermedia tra la voce del Blog di [GC workstation e server](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .</span><span class="sxs-lookup"><span data-stu-id="55eb4-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="55eb4-173">System. GC. HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="55eb4-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="55eb4-174">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="55eb4-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="55eb4-175">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="55eb4-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="55eb4-176">Se è abilitata l'affinità processori GC, ovvero l'impostazione predefinita, il numero di heap imposta cui `n` heap GC/thread per i primi processori `n`.</span><span class="sxs-lookup"><span data-stu-id="55eb4-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="55eb4-177">Usare le impostazioni creare affinità tra mask o creare affinità tra Ranges per specificare esattamente i processori da creare affinità tra.</span><span class="sxs-lookup"><span data-stu-id="55eb4-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="55eb4-178">Se l'affinità processori GC è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="55eb4-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="55eb4-179">Per ulteriori informazioni, vedere la [sezione Osservazioni GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="55eb4-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="55eb4-180">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-180">Setting name</span></span> | <span data-ttu-id="55eb4-181">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-181">Values</span></span> | <span data-ttu-id="55eb4-182">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-183">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="55eb4-184">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-184">*decimal value*</span></span> | <span data-ttu-id="55eb4-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-186">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="55eb4-187">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-187">*hexadecimal value*</span></span> | <span data-ttu-id="55eb4-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-189">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="55eb4-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="55eb4-191">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-191">*decimal value*</span></span> | <span data-ttu-id="55eb4-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="55eb4-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="55eb4-193">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-193">Example:</span></span>

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
> <span data-ttu-id="55eb4-194">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="55eb4-195">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="55eb4-196">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="55eb4-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="55eb4-197">System. GC. HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="55eb4-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="55eb4-198">Specifica i processori esatti che Garbage Collector thread devono usare.</span><span class="sxs-lookup"><span data-stu-id="55eb4-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="55eb4-199">Se l'affinità del processore è disabilitata impostando `System.GC.NoAffinitize` su `true`, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="55eb4-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="55eb4-200">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="55eb4-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="55eb4-201">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="55eb4-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="55eb4-202">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si usa la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="55eb4-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="55eb4-203">Specifica che devono essere usati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="55eb4-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="55eb4-204">Per specificare i 10 processori successivi, ovvero i processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), equivalente a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="55eb4-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="55eb4-205">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-205">Setting name</span></span> | <span data-ttu-id="55eb4-206">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-206">Values</span></span> | <span data-ttu-id="55eb4-207">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-208">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="55eb4-209">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-209">*decimal value*</span></span> | <span data-ttu-id="55eb4-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-211">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="55eb4-212">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-212">*hexadecimal value*</span></span> | <span data-ttu-id="55eb4-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-214">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="55eb4-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="55eb4-216">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-216">*decimal value*</span></span> | <span data-ttu-id="55eb4-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="55eb4-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="55eb4-218">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="55eb4-219">System. GC. GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="55eb4-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="55eb4-220">Specifica l'elenco di processori da usare per Garbage Collector thread.</span><span class="sxs-lookup"><span data-stu-id="55eb4-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="55eb4-221">Questa impostazione è simile a `System.GC.HeapAffinitizeMask`, ad eccezione del fatto che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="55eb4-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="55eb4-222">Per i sistemi operativi Windows, anteporre al [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente il numero o l'intervallo del processore, ad esempio "0:1-10, 0:12, 1:50-52, 1:70".</span><span class="sxs-lookup"><span data-stu-id="55eb4-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="55eb4-223">Se l'affinità del processore è disabilitata impostando `System.GC.NoAffinitize` su `true`, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="55eb4-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="55eb4-224">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="55eb4-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="55eb4-225">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="55eb4-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="55eb4-226">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-226">Setting name</span></span> | <span data-ttu-id="55eb4-227">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-227">Values</span></span> | <span data-ttu-id="55eb4-228">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-229">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="55eb4-230">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="55eb4-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="55eb4-231">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="55eb4-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="55eb4-232">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="55eb4-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="55eb4-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-234">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="55eb4-235">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="55eb4-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="55eb4-236">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="55eb4-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="55eb4-237">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="55eb4-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="55eb4-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-238">.NET Core 3.0</span></span> |

<span data-ttu-id="55eb4-239">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="55eb4-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="55eb4-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="55eb4-241">Configura se il Garbage Collector utilizza o meno [gruppi di CPU](/windows/win32/procthread/processor-groups) .</span><span class="sxs-lookup"><span data-stu-id="55eb4-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="55eb4-242">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="55eb4-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="55eb4-243">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="55eb4-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="55eb4-244">Si applica al server Garbage Collection solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="55eb4-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="55eb4-245">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="55eb4-246">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="55eb4-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="55eb4-247">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-247">Setting name</span></span> | <span data-ttu-id="55eb4-248">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-248">Values</span></span> | <span data-ttu-id="55eb4-249">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-250">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="55eb4-251">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-251">N/A</span></span> | <span data-ttu-id="55eb4-252">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-252">N/A</span></span> | <span data-ttu-id="55eb4-253">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-253">N/A</span></span> |
| <span data-ttu-id="55eb4-254">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="55eb4-255">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="55eb4-255">`0` - disabled</span></span><br/><span data-ttu-id="55eb4-256">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="55eb4-256">`1` - enabled</span></span> | <span data-ttu-id="55eb4-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-258">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="55eb4-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="55eb4-260">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="55eb4-260">`false` - disabled</span></span><br/><span data-ttu-id="55eb4-261">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="55eb4-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="55eb4-262">Per configurare il Common Language Runtime (CLR) in modo da distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="55eb4-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="55eb4-263">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della variabile di ambiente `COMPlus_Thread_UseAllCpuGroups` su `1`.</span><span class="sxs-lookup"><span data-stu-id="55eb4-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="55eb4-264">System. GC. NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="55eb4-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="55eb4-265">Specifica se *creare affinità tra* Garbage Collection thread con i processori.</span><span class="sxs-lookup"><span data-stu-id="55eb4-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="55eb4-266">Per creare affinità tra un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="55eb4-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="55eb4-267">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="55eb4-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="55eb4-268">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="55eb4-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="55eb4-269">Impostazione predefinita: creare affinità tra Garbage Collection thread con processori (`false`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="55eb4-270">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-270">Setting name</span></span> | <span data-ttu-id="55eb4-271">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-271">Values</span></span> | <span data-ttu-id="55eb4-272">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-273">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="55eb4-274">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="55eb4-274">`false` - affinitize</span></span><br/><span data-ttu-id="55eb4-275">`true` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="55eb4-275">`true` - don't affinitize</span></span> | <span data-ttu-id="55eb4-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-277">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="55eb4-278">`0`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="55eb4-278">`0` - affinitize</span></span><br/><span data-ttu-id="55eb4-279">`1` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="55eb4-279">`1` - don't affinitize</span></span> | <span data-ttu-id="55eb4-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-281">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="55eb4-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="55eb4-283">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="55eb4-283">`false` - affinitize</span></span><br/><span data-ttu-id="55eb4-284">`true` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="55eb4-284">`true` - don't affinitize</span></span> | <span data-ttu-id="55eb4-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="55eb4-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="55eb4-286">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="55eb4-287">System. GC. HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="55eb4-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="55eb4-288">Specifica la dimensione massima del commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="55eb4-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="55eb4-289">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-289">Setting name</span></span> | <span data-ttu-id="55eb4-290">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-290">Values</span></span> | <span data-ttu-id="55eb4-291">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-292">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="55eb4-293">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-293">*decimal value*</span></span> | <span data-ttu-id="55eb4-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-295">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="55eb4-296">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-296">*hexadecimal value*</span></span> | <span data-ttu-id="55eb4-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-297">.NET Core 3.0</span></span> |

<span data-ttu-id="55eb4-298">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-298">Example:</span></span>

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
> <span data-ttu-id="55eb4-299">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="55eb4-300">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="55eb4-301">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibytes (MiB), i valori sarebbero 209715200 per il file JSON e 0xC800000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="55eb4-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="55eb4-302">System. GC. HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="55eb4-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="55eb4-303">Specifica l'utilizzo dell'heap GC come percentuale della memoria totale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="55eb4-304">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-304">Setting name</span></span> | <span data-ttu-id="55eb4-305">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-305">Values</span></span> | <span data-ttu-id="55eb4-306">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-307">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="55eb4-308">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-308">*decimal value*</span></span> | <span data-ttu-id="55eb4-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="55eb4-310">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="55eb4-311">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-311">*hexadecimal value*</span></span> | <span data-ttu-id="55eb4-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-312">.NET Core 3.0</span></span> |

<span data-ttu-id="55eb4-313">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-313">Example:</span></span>

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
> <span data-ttu-id="55eb4-314">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="55eb4-315">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="55eb4-316">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="55eb4-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="55eb4-317">System. GC. RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="55eb4-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="55eb4-318">Configura se i segmenti da eliminare vengono inseriti in un elenco di standby per un uso futuro o vengono rilasciati al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="55eb4-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="55eb4-319">Impostazione predefinita: rilascia i segmenti al sistema operativo (`false`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="55eb4-320">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-320">Setting name</span></span> | <span data-ttu-id="55eb4-321">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-321">Values</span></span> | <span data-ttu-id="55eb4-322">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-323">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="55eb4-324">`false`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="55eb4-324">`false` - release to OS</span></span><br/><span data-ttu-id="55eb4-325">`true`-put in standby</span><span class="sxs-lookup"><span data-stu-id="55eb4-325">`true` - put on standby</span></span> | <span data-ttu-id="55eb4-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-327">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="55eb4-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="55eb4-328">`false`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="55eb4-328">`false` - release to OS</span></span><br/><span data-ttu-id="55eb4-329">`true`-put in standby</span><span class="sxs-lookup"><span data-stu-id="55eb4-329">`true` - put on standby</span></span> | <span data-ttu-id="55eb4-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-331">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="55eb4-332">`0`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="55eb4-332">`0` - release to OS</span></span><br/><span data-ttu-id="55eb4-333">`1`-put in standby</span><span class="sxs-lookup"><span data-stu-id="55eb4-333">`1` - put on standby</span></span> | <span data-ttu-id="55eb4-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="55eb4-335">Esempi</span><span class="sxs-lookup"><span data-stu-id="55eb4-335">Examples</span></span>

<span data-ttu-id="55eb4-336">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="55eb4-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="55eb4-337">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="55eb4-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="55eb4-338">Pagine di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="55eb4-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="55eb4-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="55eb4-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="55eb4-340">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="55eb4-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="55eb4-341">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="55eb4-342">Si tratta di un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="55eb4-343">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-343">Setting name</span></span> | <span data-ttu-id="55eb4-344">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-344">Values</span></span> | <span data-ttu-id="55eb4-345">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-346">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="55eb4-347">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-347">N/A</span></span> | <span data-ttu-id="55eb4-348">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-348">N/A</span></span> | <span data-ttu-id="55eb4-349">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-349">N/A</span></span> |
| <span data-ttu-id="55eb4-350">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="55eb4-351">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="55eb4-351">`0` - disabled</span></span><br/><span data-ttu-id="55eb4-352">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="55eb4-352">`1` - enabled</span></span> | <span data-ttu-id="55eb4-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="55eb4-354">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="55eb4-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="55eb4-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="55eb4-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="55eb4-356">Configura Garbage Collector il supporto per le piattaforme a 64 bit per le matrici con dimensione totale superiore a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="55eb4-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="55eb4-357">Impostazione predefinita: abilitata (`1`).</span><span class="sxs-lookup"><span data-stu-id="55eb4-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="55eb4-358">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="55eb4-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="55eb4-359">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-359">Setting name</span></span> | <span data-ttu-id="55eb4-360">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-360">Values</span></span> | <span data-ttu-id="55eb4-361">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-362">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="55eb4-363">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-363">N/A</span></span> | <span data-ttu-id="55eb4-364">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-364">N/A</span></span> | <span data-ttu-id="55eb4-365">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-365">N/A</span></span> |
| <span data-ttu-id="55eb4-366">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="55eb4-367">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="55eb4-367">`1` - enabled</span></span><br/> <span data-ttu-id="55eb4-368">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="55eb4-368">`0` - disabled</span></span> | <span data-ttu-id="55eb4-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-370">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="55eb4-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="55eb4-372">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="55eb4-372">`1` - enabled</span></span><br/> <span data-ttu-id="55eb4-373">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="55eb4-373">`0` - disabled</span></span> | <span data-ttu-id="55eb4-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="55eb4-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="55eb4-375">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="55eb4-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="55eb4-376">System. GC. LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="55eb4-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="55eb4-377">Specifica le dimensioni della soglia, in byte, che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="55eb4-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="55eb4-378">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="55eb4-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="55eb4-379">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="55eb4-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="55eb4-380">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-380">Setting name</span></span> | <span data-ttu-id="55eb4-381">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-381">Values</span></span> | <span data-ttu-id="55eb4-382">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-383">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="55eb4-384">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-384">*decimal value*</span></span> | <span data-ttu-id="55eb4-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-386">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="55eb4-387">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-387">*hexadecimal value*</span></span> | <span data-ttu-id="55eb4-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="55eb4-389">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="55eb4-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="55eb4-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="55eb4-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="55eb4-391">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="55eb4-391">*decimal value*</span></span> | <span data-ttu-id="55eb4-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="55eb4-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="55eb4-393">Esempio:</span><span class="sxs-lookup"><span data-stu-id="55eb4-393">Example:</span></span>

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
> <span data-ttu-id="55eb4-394">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="55eb4-395">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="55eb4-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="55eb4-396">Ad esempio, per impostare una dimensione della soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="55eb4-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="55eb4-397">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="55eb4-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="55eb4-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="55eb4-398">COMPlus_GCName</span></span>

- <span data-ttu-id="55eb4-399">Specifica un percorso della libreria che contiene il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="55eb4-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="55eb4-400">Per ulteriori informazioni, vedere la pagina relativa alla [progettazione del caricatore GC autonomo](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="55eb4-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="55eb4-401">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="55eb4-401">Setting name</span></span> | <span data-ttu-id="55eb4-402">Valori</span><span class="sxs-lookup"><span data-stu-id="55eb4-402">Values</span></span> | <span data-ttu-id="55eb4-403">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="55eb4-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="55eb4-404">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="55eb4-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="55eb4-405">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-405">N/A</span></span> | <span data-ttu-id="55eb4-406">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-406">N/A</span></span> | <span data-ttu-id="55eb4-407">N/D</span><span class="sxs-lookup"><span data-stu-id="55eb4-407">N/A</span></span> |
| <span data-ttu-id="55eb4-408">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="55eb4-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="55eb4-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="55eb4-409">*string_path*</span></span> | <span data-ttu-id="55eb4-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="55eb4-410">.NET Core 2.0</span></span> |
