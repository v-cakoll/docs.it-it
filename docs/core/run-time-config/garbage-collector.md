---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di run-time per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: d7e3d040cd634eeb020beff806c60f834cc02585
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761980"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="bacc0-103">Opzioni di configurazione in fase di esecuzione per Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="bacc0-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="bacc0-104">Questa pagina contiene informazioni sulle impostazioni di Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bacc0-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="bacc0-105">Se si sta tentando di ottenere prestazioni ottimali di un'app in esecuzione, è consigliabile usare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="bacc0-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="bacc0-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="bacc0-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="bacc0-107">Le impostazioni sono disposte in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="bacc0-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="bacc0-108">Le impostazioni all'interno di ogni gruppo vengono comunemente usate insieme tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="bacc0-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bacc0-109">Queste impostazioni possono essere modificate anche in modo dinamico dall'app mentre è in esecuzione, quindi è possibile eseguire l'override di tutte le impostazioni di runtime impostate.</span><span class="sxs-lookup"><span data-stu-id="bacc0-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="bacc0-110">Alcune impostazioni, ad esempio il [livello di latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="bacc0-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="bacc0-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="bacc0-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="bacc0-112">Per i valori numerici, usare la notazione decimale per le impostazioni nel file *runtimeconfig. JSON* e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="bacc0-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="bacc0-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="bacc0-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="bacc0-114">Tipi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="bacc0-114">Flavors of garbage collection</span></span>

<span data-ttu-id="bacc0-115">I due principali tipi di Garbage Collection sono GC della workstation e GC del server.</span><span class="sxs-lookup"><span data-stu-id="bacc0-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="bacc0-116">Per ulteriori informazioni sulle differenze tra le due, vedere [workstation e server Garbage Collection](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="bacc0-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="bacc0-117">Le sottoversioni di Garbage Collection sono in background e non simultanee.</span><span class="sxs-lookup"><span data-stu-id="bacc0-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="bacc0-118">Usare le impostazioni seguenti per selezionare le versioni di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="bacc0-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="bacc0-119">System. GC. Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="bacc0-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="bacc0-120">Configura se l'applicazione utilizza la workstation Garbage Collection o Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="bacc0-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="bacc0-121">Impostazione predefinita: Garbage Collection workstation.</span><span class="sxs-lookup"><span data-stu-id="bacc0-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="bacc0-122">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="bacc0-123">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-123">Setting name</span></span> | <span data-ttu-id="bacc0-124">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-124">Values</span></span> | <span data-ttu-id="bacc0-125">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-126">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="bacc0-127">`false`-workstation</span><span class="sxs-lookup"><span data-stu-id="bacc0-127">`false` - workstation</span></span><br/><span data-ttu-id="bacc0-128">`true`-Server</span><span class="sxs-lookup"><span data-stu-id="bacc0-128">`true` - server</span></span> | <span data-ttu-id="bacc0-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-130">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="bacc0-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="bacc0-131">`false`-workstation</span><span class="sxs-lookup"><span data-stu-id="bacc0-131">`false` - workstation</span></span><br/><span data-ttu-id="bacc0-132">`true`-Server</span><span class="sxs-lookup"><span data-stu-id="bacc0-132">`true` - server</span></span> | <span data-ttu-id="bacc0-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-134">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="bacc0-135">`0`-workstation</span><span class="sxs-lookup"><span data-stu-id="bacc0-135">`0` - workstation</span></span><br/><span data-ttu-id="bacc0-136">`1`-Server</span><span class="sxs-lookup"><span data-stu-id="bacc0-136">`1` - server</span></span> | <span data-ttu-id="bacc0-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-138">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="bacc0-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="bacc0-140">`false`-workstation</span><span class="sxs-lookup"><span data-stu-id="bacc0-140">`false` - workstation</span></span><br/><span data-ttu-id="bacc0-141">`true`-Server</span><span class="sxs-lookup"><span data-stu-id="bacc0-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="bacc0-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="bacc0-142">Examples</span></span>

<span data-ttu-id="bacc0-143">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="bacc0-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="bacc0-144">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="bacc0-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="bacc0-145">System. GC. Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="bacc0-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="bacc0-146">Configura se la Garbage Collection di sfondo (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="bacc0-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="bacc0-147">Impostazione predefinita: USA GC in background.</span><span class="sxs-lookup"><span data-stu-id="bacc0-147">Default: Use background GC.</span></span> <span data-ttu-id="bacc0-148">Equivale a impostare il valore su `true` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="bacc0-149">Per ulteriori informazioni, vedere [Background Garbage Collection](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="bacc0-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="bacc0-150">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-150">Setting name</span></span> | <span data-ttu-id="bacc0-151">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-151">Values</span></span> | <span data-ttu-id="bacc0-152">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-153">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="bacc0-154">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="bacc0-154">`true` - background GC</span></span><br/><span data-ttu-id="bacc0-155">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="bacc0-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bacc0-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-157">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="bacc0-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="bacc0-158">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="bacc0-158">`true` - background GC</span></span><br/><span data-ttu-id="bacc0-159">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="bacc0-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bacc0-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-161">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="bacc0-162">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="bacc0-162">`true` - background GC</span></span><br/><span data-ttu-id="bacc0-163">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="bacc0-163">`false` - non-concurrent GC</span></span> | <span data-ttu-id="bacc0-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-165">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="bacc0-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="bacc0-167">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="bacc0-167">`true` - background GC</span></span><br/><span data-ttu-id="bacc0-168">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="bacc0-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="bacc0-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="bacc0-169">Examples</span></span>

<span data-ttu-id="bacc0-170">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="bacc0-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="bacc0-171">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="bacc0-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="bacc0-172">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="bacc0-172">Manage resource usage</span></span>

<span data-ttu-id="bacc0-173">Usare le impostazioni descritte in questa sezione per gestire l'utilizzo della memoria e del processore del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="bacc0-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="bacc0-174">Per altre informazioni su alcune di queste impostazioni, vedere la parte intermedia tra la voce del Blog di [GC workstation e server](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .</span><span class="sxs-lookup"><span data-stu-id="bacc0-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="bacc0-175">System. GC. HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="bacc0-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="bacc0-176">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="bacc0-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="bacc0-177">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bacc0-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bacc0-178">Se è abilitata l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) , che è l'impostazione predefinita, il numero di heap imposta cui `n` GC Heaps/Threads sui primi `n` processori.</span><span class="sxs-lookup"><span data-stu-id="bacc0-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="bacc0-179">Usare le impostazioni [creare affinità tra mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [creare affinità tra Ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) per specificare esattamente i processori da creare affinità tra.</span><span class="sxs-lookup"><span data-stu-id="bacc0-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="bacc0-180">Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="bacc0-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="bacc0-181">Per ulteriori informazioni, vedere la [sezione Osservazioni GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="bacc0-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="bacc0-182">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-182">Setting name</span></span> | <span data-ttu-id="bacc0-183">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-183">Values</span></span> | <span data-ttu-id="bacc0-184">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-185">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="bacc0-186">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-186">*decimal value*</span></span> | <span data-ttu-id="bacc0-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-188">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="bacc0-189">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-189">*hexadecimal value*</span></span> | <span data-ttu-id="bacc0-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-191">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="bacc0-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="bacc0-193">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-193">*decimal value*</span></span> | <span data-ttu-id="bacc0-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bacc0-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bacc0-195">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-195">Example:</span></span>

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
> <span data-ttu-id="bacc0-196">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bacc0-197">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bacc0-198">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="bacc0-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="bacc0-199">System. GC. HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="bacc0-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="bacc0-200">Specifica i processori esatti che Garbage Collector thread devono usare.</span><span class="sxs-lookup"><span data-stu-id="bacc0-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="bacc0-201">Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="bacc0-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="bacc0-202">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bacc0-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bacc0-203">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="bacc0-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="bacc0-204">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si usa la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="bacc0-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="bacc0-205">Specifica che devono essere usati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="bacc0-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="bacc0-206">Per specificare i 10 processori successivi, ovvero i processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), equivalente a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="bacc0-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="bacc0-207">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-207">Setting name</span></span> | <span data-ttu-id="bacc0-208">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-208">Values</span></span> | <span data-ttu-id="bacc0-209">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-210">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="bacc0-211">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-211">*decimal value*</span></span> | <span data-ttu-id="bacc0-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-213">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="bacc0-214">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-214">*hexadecimal value*</span></span> | <span data-ttu-id="bacc0-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-216">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="bacc0-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="bacc0-218">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-218">*decimal value*</span></span> | <span data-ttu-id="bacc0-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bacc0-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bacc0-220">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="bacc0-221">System. GC. GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="bacc0-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="bacc0-222">Specifica l'elenco di processori da usare per Garbage Collector thread.</span><span class="sxs-lookup"><span data-stu-id="bacc0-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="bacc0-223">Questa impostazione è simile a [System. GC. HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), con la differenza che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="bacc0-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="bacc0-224">Per i sistemi operativi Windows, anteporre al [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente il numero o l'intervallo del processore, ad esempio "0:1-10, 0:12, 1:50-52, 1:70".</span><span class="sxs-lookup"><span data-stu-id="bacc0-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="bacc0-225">Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="bacc0-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="bacc0-226">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bacc0-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bacc0-227">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="bacc0-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="bacc0-228">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-228">Setting name</span></span> | <span data-ttu-id="bacc0-229">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-229">Values</span></span> | <span data-ttu-id="bacc0-230">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-231">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="bacc0-232">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="bacc0-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="bacc0-233">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="bacc0-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="bacc0-234">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="bacc0-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="bacc0-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-236">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="bacc0-237">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="bacc0-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="bacc0-238">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="bacc0-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="bacc0-239">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="bacc0-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="bacc0-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-240">.NET Core 3.0</span></span> |

<span data-ttu-id="bacc0-241">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="bacc0-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bacc0-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="bacc0-243">Configura se il Garbage Collector utilizza o meno [gruppi di CPU](/windows/win32/procthread/processor-groups) .</span><span class="sxs-lookup"><span data-stu-id="bacc0-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="bacc0-244">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="bacc0-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="bacc0-245">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="bacc0-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="bacc0-246">Si applica al server Garbage Collection solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="bacc0-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="bacc0-247">Impostazione predefinita: GC non si estende tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="bacc0-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="bacc0-248">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="bacc0-249">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="bacc0-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="bacc0-250">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-250">Setting name</span></span> | <span data-ttu-id="bacc0-251">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-251">Values</span></span> | <span data-ttu-id="bacc0-252">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-253">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="bacc0-254">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-254">N/A</span></span> | <span data-ttu-id="bacc0-255">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-255">N/A</span></span> | <span data-ttu-id="bacc0-256">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-256">N/A</span></span> |
| <span data-ttu-id="bacc0-257">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="bacc0-258">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-258">`0` - disabled</span></span><br/><span data-ttu-id="bacc0-259">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-259">`1` - enabled</span></span> | <span data-ttu-id="bacc0-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-261">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="bacc0-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="bacc0-263">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-263">`false` - disabled</span></span><br/><span data-ttu-id="bacc0-264">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="bacc0-265">Per configurare il Common Language Runtime (CLR) in modo da distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="bacc0-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="bacc0-266">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della `COMPlus_Thread_UseAllCpuGroups` variabile di ambiente su `1` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="bacc0-267">System. GC. NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="bacc0-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="bacc0-268">Specifica se *creare affinità tra* Garbage Collection thread con i processori.</span><span class="sxs-lookup"><span data-stu-id="bacc0-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="bacc0-269">Per creare affinità tra un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="bacc0-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="bacc0-270">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="bacc0-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="bacc0-271">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bacc0-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="bacc0-272">Impostazione predefinita: creare affinità tra Garbage Collection thread con processori.</span><span class="sxs-lookup"><span data-stu-id="bacc0-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="bacc0-273">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="bacc0-274">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-274">Setting name</span></span> | <span data-ttu-id="bacc0-275">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-275">Values</span></span> | <span data-ttu-id="bacc0-276">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-277">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="bacc0-278">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="bacc0-278">`false` - affinitize</span></span><br/><span data-ttu-id="bacc0-279">`true`-non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="bacc0-279">`true` - don't affinitize</span></span> | <span data-ttu-id="bacc0-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-281">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="bacc0-282">`0`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="bacc0-282">`0` - affinitize</span></span><br/><span data-ttu-id="bacc0-283">`1`-non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="bacc0-283">`1` - don't affinitize</span></span> | <span data-ttu-id="bacc0-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-285">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="bacc0-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="bacc0-287">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="bacc0-287">`false` - affinitize</span></span><br/><span data-ttu-id="bacc0-288">`true`-non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="bacc0-288">`true` - don't affinitize</span></span> | <span data-ttu-id="bacc0-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="bacc0-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="bacc0-290">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="bacc0-291">System. GC. HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="bacc0-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="bacc0-292">Specifica la dimensione massima del commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="bacc0-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="bacc0-293">Questa impostazione si applica solo ai computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="bacc0-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="bacc0-294">Il valore predefinito, applicabile solo in alcuni casi, è maggiore di 20 MB o del 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="bacc0-294">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="bacc0-295">Il valore predefinito si applica se:</span><span class="sxs-lookup"><span data-stu-id="bacc0-295">The default value applies if:</span></span>

  - <span data-ttu-id="bacc0-296">Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="bacc0-296">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="bacc0-297">[System. GC. HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) non è impostato.</span><span class="sxs-lookup"><span data-stu-id="bacc0-297">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="bacc0-298">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-298">Setting name</span></span> | <span data-ttu-id="bacc0-299">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-299">Values</span></span> | <span data-ttu-id="bacc0-300">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-300">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-301">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-301">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="bacc0-302">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-302">*decimal value*</span></span> | <span data-ttu-id="bacc0-303">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-303">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-304">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-304">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="bacc0-305">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-305">*hexadecimal value*</span></span> | <span data-ttu-id="bacc0-306">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-306">.NET Core 3.0</span></span> |

<span data-ttu-id="bacc0-307">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-307">Example:</span></span>

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
> <span data-ttu-id="bacc0-308">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-308">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bacc0-309">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-309">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bacc0-310">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibytes (MiB), i valori sarebbero 209715200 per il file JSON e 0xC800000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="bacc0-310">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="bacc0-311">System. GC. HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="bacc0-311">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="bacc0-312">Specifica l'utilizzo dell'heap GC consentito come percentuale della memoria fisica totale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-312">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="bacc0-313">Se viene impostato anche [System. GC. HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) , questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="bacc0-313">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="bacc0-314">Questa impostazione si applica solo ai computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="bacc0-314">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="bacc0-315">Se il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato, la percentuale viene calcolata come percentuale del limite di memoria.</span><span class="sxs-lookup"><span data-stu-id="bacc0-315">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="bacc0-316">Il valore predefinito, applicabile solo in alcuni casi, è minore di 20 MB o del 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="bacc0-316">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="bacc0-317">Il valore predefinito si applica se:</span><span class="sxs-lookup"><span data-stu-id="bacc0-317">The default value applies if:</span></span>

  - <span data-ttu-id="bacc0-318">Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="bacc0-318">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="bacc0-319">[System. GC. HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) non è impostato.</span><span class="sxs-lookup"><span data-stu-id="bacc0-319">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="bacc0-320">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-320">Setting name</span></span> | <span data-ttu-id="bacc0-321">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-321">Values</span></span> | <span data-ttu-id="bacc0-322">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-323">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-323">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="bacc0-324">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-324">*decimal value*</span></span> | <span data-ttu-id="bacc0-325">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-325">.NET Core 3.0</span></span> |
| <span data-ttu-id="bacc0-326">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-326">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="bacc0-327">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-327">*hexadecimal value*</span></span> | <span data-ttu-id="bacc0-328">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-328">.NET Core 3.0</span></span> |

<span data-ttu-id="bacc0-329">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-329">Example:</span></span>

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
> <span data-ttu-id="bacc0-330">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-330">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bacc0-331">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-331">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bacc0-332">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="bacc0-332">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="bacc0-333">System. GC. RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="bacc0-333">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="bacc0-334">Configura se i segmenti da eliminare vengono inseriti in un elenco di standby per un uso futuro o vengono rilasciati al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bacc0-334">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="bacc0-335">Impostazione predefinita: rilascia i segmenti al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bacc0-335">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="bacc0-336">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-336">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="bacc0-337">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-337">Setting name</span></span> | <span data-ttu-id="bacc0-338">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-338">Values</span></span> | <span data-ttu-id="bacc0-339">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-339">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-340">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-340">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="bacc0-341">`false`-versione a sistema operativo</span><span class="sxs-lookup"><span data-stu-id="bacc0-341">`false` - release to OS</span></span><br/><span data-ttu-id="bacc0-342">`true`-messa in standby</span><span class="sxs-lookup"><span data-stu-id="bacc0-342">`true` - put on standby</span></span> | <span data-ttu-id="bacc0-343">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-343">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-344">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="bacc0-344">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="bacc0-345">`false`-versione a sistema operativo</span><span class="sxs-lookup"><span data-stu-id="bacc0-345">`false` - release to OS</span></span><br/><span data-ttu-id="bacc0-346">`true`-messa in standby</span><span class="sxs-lookup"><span data-stu-id="bacc0-346">`true` - put on standby</span></span> | <span data-ttu-id="bacc0-347">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-347">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-348">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-348">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="bacc0-349">`0`-versione a sistema operativo</span><span class="sxs-lookup"><span data-stu-id="bacc0-349">`0` - release to OS</span></span><br/><span data-ttu-id="bacc0-350">`1`-messa in standby</span><span class="sxs-lookup"><span data-stu-id="bacc0-350">`1` - put on standby</span></span> | <span data-ttu-id="bacc0-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-351">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="bacc0-352">Esempi</span><span class="sxs-lookup"><span data-stu-id="bacc0-352">Examples</span></span>

<span data-ttu-id="bacc0-353">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="bacc0-353">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="bacc0-354">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="bacc0-354">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="bacc0-355">Pagine di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="bacc0-355">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="bacc0-356">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="bacc0-356">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="bacc0-357">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="bacc0-357">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="bacc0-358">Impostazione predefinita: non utilizzare pagine di grandi dimensioni quando è impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="bacc0-358">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="bacc0-359">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-359">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="bacc0-360">Si tratta di un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-360">This is an experimental setting.</span></span>

| | <span data-ttu-id="bacc0-361">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-361">Setting name</span></span> | <span data-ttu-id="bacc0-362">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-362">Values</span></span> | <span data-ttu-id="bacc0-363">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-363">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-364">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-364">**runtimeconfig.json**</span></span> | <span data-ttu-id="bacc0-365">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-365">N/A</span></span> | <span data-ttu-id="bacc0-366">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-366">N/A</span></span> | <span data-ttu-id="bacc0-367">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-367">N/A</span></span> |
| <span data-ttu-id="bacc0-368">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-368">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="bacc0-369">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-369">`0` - disabled</span></span><br/><span data-ttu-id="bacc0-370">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-370">`1` - enabled</span></span> | <span data-ttu-id="bacc0-371">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-371">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="bacc0-372">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="bacc0-372">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="bacc0-373">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="bacc0-373">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="bacc0-374">Configura Garbage Collector il supporto per le piattaforme a 64 bit per le matrici con dimensione totale superiore a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="bacc0-374">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="bacc0-375">Impostazione predefinita: GC supporta matrici di dimensioni maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="bacc0-375">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="bacc0-376">Equivale a impostare il valore su `1` .</span><span class="sxs-lookup"><span data-stu-id="bacc0-376">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="bacc0-377">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="bacc0-377">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="bacc0-378">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-378">Setting name</span></span> | <span data-ttu-id="bacc0-379">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-379">Values</span></span> | <span data-ttu-id="bacc0-380">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-380">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-381">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-381">**runtimeconfig.json**</span></span> | <span data-ttu-id="bacc0-382">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-382">N/A</span></span> | <span data-ttu-id="bacc0-383">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-383">N/A</span></span> | <span data-ttu-id="bacc0-384">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-384">N/A</span></span> |
| <span data-ttu-id="bacc0-385">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-385">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="bacc0-386">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-386">`1` - enabled</span></span><br/> <span data-ttu-id="bacc0-387">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-387">`0` - disabled</span></span> | <span data-ttu-id="bacc0-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-389">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-390">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="bacc0-390">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="bacc0-391">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-391">`1` - enabled</span></span><br/> <span data-ttu-id="bacc0-392">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="bacc0-392">`0` - disabled</span></span> | <span data-ttu-id="bacc0-393">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="bacc0-393">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="bacc0-394">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="bacc0-394">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="bacc0-395">System. GC. LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="bacc0-395">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="bacc0-396">Specifica le dimensioni della soglia, in byte, che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="bacc0-396">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="bacc0-397">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="bacc0-397">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="bacc0-398">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="bacc0-398">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="bacc0-399">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-399">Setting name</span></span> | <span data-ttu-id="bacc0-400">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-400">Values</span></span> | <span data-ttu-id="bacc0-401">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-401">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-402">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-402">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="bacc0-403">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-403">*decimal value*</span></span> | <span data-ttu-id="bacc0-404">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-404">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-405">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-405">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="bacc0-406">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-406">*hexadecimal value*</span></span> | <span data-ttu-id="bacc0-407">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-407">.NET Core 1.0</span></span> |
| <span data-ttu-id="bacc0-408">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="bacc0-408">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="bacc0-409">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="bacc0-409">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="bacc0-410">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="bacc0-410">*decimal value*</span></span> | <span data-ttu-id="bacc0-411">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="bacc0-411">.NET Framework 4.8</span></span> |

<span data-ttu-id="bacc0-412">Esempio:</span><span class="sxs-lookup"><span data-stu-id="bacc0-412">Example:</span></span>

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
> <span data-ttu-id="bacc0-413">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-413">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="bacc0-414">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="bacc0-414">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="bacc0-415">Ad esempio, per impostare una dimensione della soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="bacc0-415">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="bacc0-416">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="bacc0-416">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="bacc0-417">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="bacc0-417">COMPlus_GCName</span></span>

- <span data-ttu-id="bacc0-418">Specifica un percorso della libreria che contiene il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="bacc0-418">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="bacc0-419">Per ulteriori informazioni, vedere la pagina relativa alla [progettazione del caricatore GC autonomo](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="bacc0-419">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="bacc0-420">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="bacc0-420">Setting name</span></span> | <span data-ttu-id="bacc0-421">Valori</span><span class="sxs-lookup"><span data-stu-id="bacc0-421">Values</span></span> | <span data-ttu-id="bacc0-422">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="bacc0-422">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="bacc0-423">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="bacc0-423">**runtimeconfig.json**</span></span> | <span data-ttu-id="bacc0-424">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-424">N/A</span></span> | <span data-ttu-id="bacc0-425">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-425">N/A</span></span> | <span data-ttu-id="bacc0-426">N/D</span><span class="sxs-lookup"><span data-stu-id="bacc0-426">N/A</span></span> |
| <span data-ttu-id="bacc0-427">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="bacc0-427">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="bacc0-428">*string_path*</span><span class="sxs-lookup"><span data-stu-id="bacc0-428">*string_path*</span></span> | <span data-ttu-id="bacc0-429">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="bacc0-429">.NET Core 2.0</span></span> |
