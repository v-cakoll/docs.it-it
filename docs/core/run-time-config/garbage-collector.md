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
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="52488-103">Opzioni di configurazione in fase di esecuzione per Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="52488-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="52488-104">Questa pagina contiene informazioni sulle impostazioni di Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="52488-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="52488-105">Se si sta tentando di ottenere prestazioni ottimali di un'app in esecuzione, è consigliabile usare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="52488-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="52488-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="52488-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="52488-107">Le impostazioni sono disposte in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="52488-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="52488-108">Le impostazioni all'interno di ogni gruppo vengono comunemente usate insieme tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="52488-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="52488-109">Queste impostazioni possono essere modificate anche in modo dinamico dall'app mentre è in esecuzione, quindi è possibile eseguire l'override di tutte le impostazioni di runtime impostate.</span><span class="sxs-lookup"><span data-stu-id="52488-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="52488-110">Alcune impostazioni, ad esempio il [livello di latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="52488-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="52488-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="52488-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="52488-112">Per i valori numerici, usare la notazione decimale per le impostazioni nel file *runtimeconfig. JSON* e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="52488-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="52488-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="52488-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="52488-114">Tipi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="52488-114">Flavors of garbage collection</span></span>

<span data-ttu-id="52488-115">I due principali tipi di Garbage Collection sono GC della workstation e GC del server.</span><span class="sxs-lookup"><span data-stu-id="52488-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="52488-116">Per ulteriori informazioni sulle differenze tra le due, vedere [nozioni fondamentali di Garbage Collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="52488-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="52488-117">Le sottoversioni di Garbage Collection sono in background e non simultanee.</span><span class="sxs-lookup"><span data-stu-id="52488-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="52488-118">Usare le impostazioni seguenti per selezionare le versioni di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="52488-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="52488-119">System. GC. Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="52488-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="52488-120">Configura se l'applicazione utilizza la workstation Garbage Collection o Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="52488-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="52488-121">Impostazione predefinita: Garbage Collection workstation (`false`).</span><span class="sxs-lookup"><span data-stu-id="52488-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="52488-122">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-122">Setting name</span></span> | <span data-ttu-id="52488-123">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-123">Values</span></span> | <span data-ttu-id="52488-124">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-125">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="52488-126">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="52488-126">`false` - workstation</span></span><br/><span data-ttu-id="52488-127">Server `true`</span><span class="sxs-lookup"><span data-stu-id="52488-127">`true` - server</span></span> | <span data-ttu-id="52488-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-129">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="52488-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="52488-130">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="52488-130">`false` - workstation</span></span><br/><span data-ttu-id="52488-131">Server `true`</span><span class="sxs-lookup"><span data-stu-id="52488-131">`true` - server</span></span> | <span data-ttu-id="52488-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="52488-134">workstation `0`</span><span class="sxs-lookup"><span data-stu-id="52488-134">`0` - workstation</span></span><br/><span data-ttu-id="52488-135">Server `1`</span><span class="sxs-lookup"><span data-stu-id="52488-135">`1` - server</span></span> | <span data-ttu-id="52488-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-137">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="52488-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="52488-139">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="52488-139">`false` - workstation</span></span><br/><span data-ttu-id="52488-140">Server `true`</span><span class="sxs-lookup"><span data-stu-id="52488-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="52488-141">Esempi</span><span class="sxs-lookup"><span data-stu-id="52488-141">Examples</span></span>

<span data-ttu-id="52488-142">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="52488-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="52488-143">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="52488-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="52488-144">System. GC. Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="52488-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="52488-145">Configura se la Garbage Collection di sfondo (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="52488-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="52488-146">Impostazione predefinita: abilitata (`true`).</span><span class="sxs-lookup"><span data-stu-id="52488-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="52488-147">Per ulteriori informazioni, vedere [Garbage Collection in background](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) e [Garbage Collection server in background](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="52488-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="52488-148">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-148">Setting name</span></span> | <span data-ttu-id="52488-149">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-149">Values</span></span> | <span data-ttu-id="52488-150">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-151">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="52488-152">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="52488-152">`true` - background GC</span></span><br/><span data-ttu-id="52488-153">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="52488-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="52488-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-155">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="52488-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="52488-156">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="52488-156">`true` - background GC</span></span><br/><span data-ttu-id="52488-157">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="52488-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="52488-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="52488-160">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="52488-160">`true` - background GC</span></span><br/><span data-ttu-id="52488-161">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="52488-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="52488-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-163">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="52488-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="52488-165">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="52488-165">`true` - background GC</span></span><br/><span data-ttu-id="52488-166">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="52488-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="52488-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="52488-167">Examples</span></span>

<span data-ttu-id="52488-168">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="52488-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="52488-169">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="52488-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="52488-170">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="52488-170">Manage resource usage</span></span>

<span data-ttu-id="52488-171">Usare le impostazioni descritte in questa sezione per gestire l'utilizzo della memoria e del processore del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="52488-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="52488-172">Per altre informazioni su alcune di queste impostazioni, vedere la parte intermedia tra la voce del Blog di [GC workstation e server](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .</span><span class="sxs-lookup"><span data-stu-id="52488-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="52488-173">System. GC. HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="52488-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="52488-174">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="52488-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="52488-175">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="52488-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="52488-176">Se è abilitata l'affinità processori GC, ovvero l'impostazione predefinita, il numero di heap imposta cui `n` heap GC/thread per i primi processori `n`.</span><span class="sxs-lookup"><span data-stu-id="52488-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="52488-177">Usare le impostazioni creare affinità tra mask o creare affinità tra Ranges per specificare esattamente i processori da creare affinità tra.</span><span class="sxs-lookup"><span data-stu-id="52488-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="52488-178">Se l'affinità processori GC è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="52488-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="52488-179">Per ulteriori informazioni, vedere la [sezione Osservazioni GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="52488-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="52488-180">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-180">Setting name</span></span> | <span data-ttu-id="52488-181">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-181">Values</span></span> | <span data-ttu-id="52488-182">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-183">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="52488-184">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-184">*decimal value*</span></span> | <span data-ttu-id="52488-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-186">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="52488-187">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="52488-187">*hexadecimal value*</span></span> | <span data-ttu-id="52488-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-189">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="52488-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="52488-191">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-191">*decimal value*</span></span> | <span data-ttu-id="52488-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="52488-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="52488-193">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-193">Example:</span></span>

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
> <span data-ttu-id="52488-194">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="52488-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="52488-195">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="52488-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="52488-196">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="52488-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="52488-197">System. GC. HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="52488-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="52488-198">Specifica i processori esatti che Garbage Collector thread devono usare.</span><span class="sxs-lookup"><span data-stu-id="52488-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="52488-199">Se l'affinità del processore è disabilitata impostando `System.GC.NoAffinitize` su `true`, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="52488-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="52488-200">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="52488-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="52488-201">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="52488-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="52488-202">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si usa la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="52488-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="52488-203">Specifica che devono essere usati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="52488-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="52488-204">Per specificare i 10 processori successivi, ovvero i processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), equivalente a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="52488-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="52488-205">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-205">Setting name</span></span> | <span data-ttu-id="52488-206">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-206">Values</span></span> | <span data-ttu-id="52488-207">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-208">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="52488-209">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-209">*decimal value*</span></span> | <span data-ttu-id="52488-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-211">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="52488-212">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="52488-212">*hexadecimal value*</span></span> | <span data-ttu-id="52488-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-214">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="52488-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="52488-216">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-216">*decimal value*</span></span> | <span data-ttu-id="52488-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="52488-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="52488-218">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="52488-219">System. GC. GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="52488-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="52488-220">Specifica l'elenco di processori da usare per Garbage Collector thread.</span><span class="sxs-lookup"><span data-stu-id="52488-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="52488-221">Questa impostazione è simile a `System.GC.HeapAffinitizeMask`, ad eccezione del fatto che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="52488-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="52488-222">Per i sistemi operativi Windows, anteporre al [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente il numero o l'intervallo del processore, ad esempio "0:1-10, 0:12, 1:50-52, 1:70".</span><span class="sxs-lookup"><span data-stu-id="52488-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="52488-223">Se l'affinità del processore è disabilitata impostando `System.GC.NoAffinitize` su `true`, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="52488-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="52488-224">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="52488-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="52488-225">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="52488-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="52488-226">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-226">Setting name</span></span> | <span data-ttu-id="52488-227">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-227">Values</span></span> | <span data-ttu-id="52488-228">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-229">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="52488-230">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="52488-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="52488-231">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="52488-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="52488-232">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="52488-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="52488-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-234">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="52488-235">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="52488-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="52488-236">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="52488-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="52488-237">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="52488-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="52488-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-238">.NET Core 3.0</span></span> |

<span data-ttu-id="52488-239">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="52488-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="52488-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="52488-241">Configura se il Garbage Collector utilizza o meno [gruppi di CPU](/windows/win32/procthread/processor-groups) .</span><span class="sxs-lookup"><span data-stu-id="52488-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="52488-242">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="52488-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="52488-243">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="52488-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="52488-244">Si applica al server Garbage Collection solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="52488-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="52488-245">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="52488-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="52488-246">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="52488-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="52488-247">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-247">Setting name</span></span> | <span data-ttu-id="52488-248">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-248">Values</span></span> | <span data-ttu-id="52488-249">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-250">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="52488-251">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-251">N/A</span></span> | <span data-ttu-id="52488-252">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-252">N/A</span></span> | <span data-ttu-id="52488-253">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-253">N/A</span></span> |
| <span data-ttu-id="52488-254">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="52488-255">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="52488-255">`0` - disabled</span></span><br/><span data-ttu-id="52488-256">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="52488-256">`1` - enabled</span></span> | <span data-ttu-id="52488-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-258">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="52488-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="52488-260">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="52488-260">`false` - disabled</span></span><br/><span data-ttu-id="52488-261">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="52488-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="52488-262">Per configurare il Common Language Runtime (CLR) in modo da distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="52488-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="52488-263">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della variabile di ambiente `COMPlus_Thread_UseAllCpuGroups` su `1`.</span><span class="sxs-lookup"><span data-stu-id="52488-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="52488-264">System. GC. NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="52488-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="52488-265">Specifica se *creare affinità tra* Garbage Collection thread con i processori.</span><span class="sxs-lookup"><span data-stu-id="52488-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="52488-266">Per creare affinità tra un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="52488-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="52488-267">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="52488-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="52488-268">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="52488-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="52488-269">Impostazione predefinita: creare affinità tra Garbage Collection thread con processori (`false`).</span><span class="sxs-lookup"><span data-stu-id="52488-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="52488-270">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-270">Setting name</span></span> | <span data-ttu-id="52488-271">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-271">Values</span></span> | <span data-ttu-id="52488-272">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-273">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="52488-274">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="52488-274">`false` - affinitize</span></span><br/><span data-ttu-id="52488-275">`true` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="52488-275">`true` - don't affinitize</span></span> | <span data-ttu-id="52488-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-277">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="52488-278">`0`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="52488-278">`0` - affinitize</span></span><br/><span data-ttu-id="52488-279">`1` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="52488-279">`1` - don't affinitize</span></span> | <span data-ttu-id="52488-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-281">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="52488-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="52488-283">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="52488-283">`false` - affinitize</span></span><br/><span data-ttu-id="52488-284">`true` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="52488-284">`true` - don't affinitize</span></span> | <span data-ttu-id="52488-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="52488-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="52488-286">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="52488-287">System. GC. HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="52488-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="52488-288">Specifica la dimensione massima del commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="52488-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="52488-289">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-289">Setting name</span></span> | <span data-ttu-id="52488-290">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-290">Values</span></span> | <span data-ttu-id="52488-291">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-292">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="52488-293">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-293">*decimal value*</span></span> | <span data-ttu-id="52488-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-295">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="52488-296">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="52488-296">*hexadecimal value*</span></span> | <span data-ttu-id="52488-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-297">.NET Core 3.0</span></span> |

<span data-ttu-id="52488-298">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-298">Example:</span></span>

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
> <span data-ttu-id="52488-299">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="52488-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="52488-300">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="52488-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="52488-301">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibytes (MiB), i valori sarebbero 209715200 per il file JSON e 0xC800000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="52488-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="52488-302">System. GC. HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="52488-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="52488-303">Specifica l'utilizzo dell'heap GC come percentuale della memoria totale.</span><span class="sxs-lookup"><span data-stu-id="52488-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="52488-304">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-304">Setting name</span></span> | <span data-ttu-id="52488-305">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-305">Values</span></span> | <span data-ttu-id="52488-306">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-307">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="52488-308">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-308">*decimal value*</span></span> | <span data-ttu-id="52488-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="52488-310">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="52488-311">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="52488-311">*hexadecimal value*</span></span> | <span data-ttu-id="52488-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-312">.NET Core 3.0</span></span> |

<span data-ttu-id="52488-313">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-313">Example:</span></span>

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
> <span data-ttu-id="52488-314">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="52488-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="52488-315">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="52488-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="52488-316">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="52488-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="52488-317">System. GC. RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="52488-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="52488-318">Configura se i segmenti da eliminare vengono inseriti in un elenco di standby per un uso futuro o vengono rilasciati al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="52488-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="52488-319">Impostazione predefinita: rilascia i segmenti al sistema operativo (`false`).</span><span class="sxs-lookup"><span data-stu-id="52488-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="52488-320">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-320">Setting name</span></span> | <span data-ttu-id="52488-321">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-321">Values</span></span> | <span data-ttu-id="52488-322">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-323">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="52488-324">`false`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="52488-324">`false` - release to OS</span></span><br/><span data-ttu-id="52488-325">`true`-put in standby</span><span class="sxs-lookup"><span data-stu-id="52488-325">`true` - put on standby</span></span> | <span data-ttu-id="52488-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-327">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="52488-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="52488-328">`false`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="52488-328">`false` - release to OS</span></span><br/><span data-ttu-id="52488-329">`true`-put in standby</span><span class="sxs-lookup"><span data-stu-id="52488-329">`true` - put on standby</span></span> | <span data-ttu-id="52488-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-331">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="52488-332">`0`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="52488-332">`0` - release to OS</span></span><br/><span data-ttu-id="52488-333">`1`-put in standby</span><span class="sxs-lookup"><span data-stu-id="52488-333">`1` - put on standby</span></span> | <span data-ttu-id="52488-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="52488-335">Esempi</span><span class="sxs-lookup"><span data-stu-id="52488-335">Examples</span></span>

<span data-ttu-id="52488-336">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="52488-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="52488-337">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="52488-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="52488-338">Pagine di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="52488-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="52488-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="52488-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="52488-340">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="52488-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="52488-341">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="52488-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="52488-342">Si tratta di un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="52488-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="52488-343">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-343">Setting name</span></span> | <span data-ttu-id="52488-344">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-344">Values</span></span> | <span data-ttu-id="52488-345">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-346">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="52488-347">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-347">N/A</span></span> | <span data-ttu-id="52488-348">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-348">N/A</span></span> | <span data-ttu-id="52488-349">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-349">N/A</span></span> |
| <span data-ttu-id="52488-350">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="52488-351">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="52488-351">`0` - disabled</span></span><br/><span data-ttu-id="52488-352">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="52488-352">`1` - enabled</span></span> | <span data-ttu-id="52488-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="52488-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="52488-354">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="52488-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="52488-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="52488-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="52488-356">Configura Garbage Collector il supporto per le piattaforme a 64 bit per le matrici con dimensione totale superiore a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="52488-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="52488-357">Impostazione predefinita: abilitata (`1`).</span><span class="sxs-lookup"><span data-stu-id="52488-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="52488-358">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="52488-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="52488-359">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-359">Setting name</span></span> | <span data-ttu-id="52488-360">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-360">Values</span></span> | <span data-ttu-id="52488-361">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-362">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="52488-363">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-363">N/A</span></span> | <span data-ttu-id="52488-364">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-364">N/A</span></span> | <span data-ttu-id="52488-365">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-365">N/A</span></span> |
| <span data-ttu-id="52488-366">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="52488-367">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="52488-367">`1` - enabled</span></span><br/> <span data-ttu-id="52488-368">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="52488-368">`0` - disabled</span></span> | <span data-ttu-id="52488-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-370">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="52488-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="52488-372">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="52488-372">`1` - enabled</span></span><br/> <span data-ttu-id="52488-373">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="52488-373">`0` - disabled</span></span> | <span data-ttu-id="52488-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="52488-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="52488-375">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="52488-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="52488-376">System. GC. LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="52488-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="52488-377">Specifica le dimensioni della soglia, in byte, che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="52488-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="52488-378">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="52488-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="52488-379">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="52488-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="52488-380">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-380">Setting name</span></span> | <span data-ttu-id="52488-381">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-381">Values</span></span> | <span data-ttu-id="52488-382">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-383">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="52488-384">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-384">*decimal value*</span></span> | <span data-ttu-id="52488-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-386">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="52488-387">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="52488-387">*hexadecimal value*</span></span> | <span data-ttu-id="52488-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="52488-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="52488-389">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="52488-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="52488-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="52488-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="52488-391">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="52488-391">*decimal value*</span></span> | <span data-ttu-id="52488-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="52488-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="52488-393">Esempio:</span><span class="sxs-lookup"><span data-stu-id="52488-393">Example:</span></span>

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
> <span data-ttu-id="52488-394">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="52488-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="52488-395">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="52488-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="52488-396">Ad esempio, per impostare una dimensione della soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="52488-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="52488-397">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="52488-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="52488-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="52488-398">COMPlus_GCName</span></span>

- <span data-ttu-id="52488-399">Specifica un percorso della libreria che contiene il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="52488-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="52488-400">Per ulteriori informazioni, vedere la pagina relativa alla [progettazione del caricatore GC autonomo](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="52488-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="52488-401">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="52488-401">Setting name</span></span> | <span data-ttu-id="52488-402">Valori</span><span class="sxs-lookup"><span data-stu-id="52488-402">Values</span></span> | <span data-ttu-id="52488-403">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="52488-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="52488-404">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="52488-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="52488-405">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-405">N/A</span></span> | <span data-ttu-id="52488-406">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-406">N/A</span></span> | <span data-ttu-id="52488-407">N/D</span><span class="sxs-lookup"><span data-stu-id="52488-407">N/A</span></span> |
| <span data-ttu-id="52488-408">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="52488-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="52488-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="52488-409">*string_path*</span></span> | <span data-ttu-id="52488-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="52488-410">.NET Core 2.0</span></span> |
