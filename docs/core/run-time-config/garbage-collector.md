---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di run-time per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441407"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="6895c-103">Opzioni di configurazione in fase di esecuzione per Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="6895c-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="6895c-104">Questa pagina contiene informazioni sulle impostazioni di Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6895c-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="6895c-105">Se si sta tentando di ottenere prestazioni ottimali di un'app in esecuzione, è consigliabile usare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6895c-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="6895c-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="6895c-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="6895c-107">Le impostazioni sono disposte in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="6895c-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="6895c-108">Le impostazioni all'interno di ogni gruppo vengono comunemente usate insieme tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="6895c-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6895c-109">Queste impostazioni possono essere modificate anche in modo dinamico dall'app mentre è in esecuzione, quindi è possibile eseguire l'override di tutte le impostazioni di runtime impostate.</span><span class="sxs-lookup"><span data-stu-id="6895c-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="6895c-110">Alcune impostazioni, ad esempio il [livello di latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6895c-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="6895c-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="6895c-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="6895c-112">Per i valori numerici, usare la notazione decimale per le impostazioni nel *runtimeconfig.jssu* file e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="6895c-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="6895c-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="6895c-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="6895c-114">Tipi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="6895c-114">Flavors of garbage collection</span></span>

<span data-ttu-id="6895c-115">I due principali tipi di Garbage Collection sono GC della workstation e GC del server.</span><span class="sxs-lookup"><span data-stu-id="6895c-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="6895c-116">Per ulteriori informazioni sulle differenze tra le due, vedere [workstation e server Garbage Collection](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="6895c-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="6895c-117">Le sottoversioni di Garbage Collection sono in background e non simultanee.</span><span class="sxs-lookup"><span data-stu-id="6895c-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="6895c-118">Usare le impostazioni seguenti per selezionare le versioni di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="6895c-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="6895c-119">System. GC. Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="6895c-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="6895c-120">Configura se l'applicazione utilizza la workstation Garbage Collection o Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="6895c-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="6895c-121">Impostazione predefinita: Garbage Collection workstation.</span><span class="sxs-lookup"><span data-stu-id="6895c-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="6895c-122">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="6895c-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="6895c-123">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-123">Setting name</span></span> | <span data-ttu-id="6895c-124">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-124">Values</span></span> | <span data-ttu-id="6895c-125">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-126">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="6895c-127">`false`-workstation</span><span class="sxs-lookup"><span data-stu-id="6895c-127">`false` - workstation</span></span><br/><span data-ttu-id="6895c-128">`true`-Server</span><span class="sxs-lookup"><span data-stu-id="6895c-128">`true` - server</span></span> | <span data-ttu-id="6895c-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-130">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="6895c-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="6895c-131">`false`-workstation</span><span class="sxs-lookup"><span data-stu-id="6895c-131">`false` - workstation</span></span><br/><span data-ttu-id="6895c-132">`true`-Server</span><span class="sxs-lookup"><span data-stu-id="6895c-132">`true` - server</span></span> | <span data-ttu-id="6895c-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-134">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="6895c-135">`0`-workstation</span><span class="sxs-lookup"><span data-stu-id="6895c-135">`0` - workstation</span></span><br/><span data-ttu-id="6895c-136">`1`-Server</span><span class="sxs-lookup"><span data-stu-id="6895c-136">`1` - server</span></span> | <span data-ttu-id="6895c-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-138">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="6895c-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="6895c-140">`false`-workstation</span><span class="sxs-lookup"><span data-stu-id="6895c-140">`false` - workstation</span></span><br/><span data-ttu-id="6895c-141">`true`-Server</span><span class="sxs-lookup"><span data-stu-id="6895c-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="6895c-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="6895c-142">Examples</span></span>

<span data-ttu-id="6895c-143">*runtimeconfig.jsnel* file:</span><span class="sxs-lookup"><span data-stu-id="6895c-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="6895c-144">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="6895c-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="6895c-145">System. GC. Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="6895c-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="6895c-146">Configura se la Garbage Collection di sfondo (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="6895c-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="6895c-147">Impostazione predefinita: USA GC in background.</span><span class="sxs-lookup"><span data-stu-id="6895c-147">Default: Use background GC.</span></span> <span data-ttu-id="6895c-148">Equivale a impostare il valore su `true` .</span><span class="sxs-lookup"><span data-stu-id="6895c-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="6895c-149">Per ulteriori informazioni, vedere [Background Garbage Collection](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="6895c-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="6895c-150">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-150">Setting name</span></span> | <span data-ttu-id="6895c-151">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-151">Values</span></span> | <span data-ttu-id="6895c-152">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-153">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="6895c-154">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="6895c-154">`true` - background GC</span></span><br/><span data-ttu-id="6895c-155">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="6895c-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="6895c-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-157">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="6895c-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="6895c-158">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="6895c-158">`true` - background GC</span></span><br/><span data-ttu-id="6895c-159">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="6895c-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="6895c-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-161">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="6895c-162">`1`-GC in background</span><span class="sxs-lookup"><span data-stu-id="6895c-162">`1` - background GC</span></span><br/><span data-ttu-id="6895c-163">`0`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="6895c-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="6895c-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-165">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="6895c-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="6895c-167">`true`-GC in background</span><span class="sxs-lookup"><span data-stu-id="6895c-167">`true` - background GC</span></span><br/><span data-ttu-id="6895c-168">`false`-GC non simultanei</span><span class="sxs-lookup"><span data-stu-id="6895c-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="6895c-169">Esempio</span><span class="sxs-lookup"><span data-stu-id="6895c-169">Examples</span></span>

<span data-ttu-id="6895c-170">*runtimeconfig.jsnel* file:</span><span class="sxs-lookup"><span data-stu-id="6895c-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="6895c-171">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="6895c-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="6895c-172">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="6895c-172">Manage resource usage</span></span>

<span data-ttu-id="6895c-173">Usare le impostazioni descritte in questa sezione per gestire l'utilizzo della memoria e del processore del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="6895c-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="6895c-174">Per altre informazioni su alcune di queste impostazioni, vedere la parte intermedia tra la voce del Blog di [GC workstation e server](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .</span><span class="sxs-lookup"><span data-stu-id="6895c-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="6895c-175">System. GC. HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="6895c-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="6895c-176">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="6895c-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="6895c-177">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6895c-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6895c-178">Se è abilitata l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) , che è l'impostazione predefinita, il numero di heap imposta cui `n` GC Heaps/Threads sui primi `n` processori.</span><span class="sxs-lookup"><span data-stu-id="6895c-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="6895c-179">Usare le impostazioni [creare affinità tra mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [creare affinità tra Ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) per specificare esattamente i processori da creare affinità tra.</span><span class="sxs-lookup"><span data-stu-id="6895c-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="6895c-180">Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="6895c-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="6895c-181">Per ulteriori informazioni, vedere la [sezione Osservazioni GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="6895c-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="6895c-182">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-182">Setting name</span></span> | <span data-ttu-id="6895c-183">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-183">Values</span></span> | <span data-ttu-id="6895c-184">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-185">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="6895c-186">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-186">*decimal value*</span></span> | <span data-ttu-id="6895c-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-188">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="6895c-189">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-189">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-191">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="6895c-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="6895c-193">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-193">*decimal value*</span></span> | <span data-ttu-id="6895c-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="6895c-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="6895c-195">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-195">Example:</span></span>

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
> <span data-ttu-id="6895c-196">Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6895c-197">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6895c-198">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="6895c-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="6895c-199">System. GC. HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="6895c-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="6895c-200">Specifica i processori esatti che Garbage Collector thread devono usare.</span><span class="sxs-lookup"><span data-stu-id="6895c-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="6895c-201">Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="6895c-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="6895c-202">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6895c-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6895c-203">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="6895c-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="6895c-204">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si usa la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="6895c-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="6895c-205">Specifica che devono essere usati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="6895c-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="6895c-206">Per specificare i 10 processori successivi, ovvero i processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), equivalente a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="6895c-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="6895c-207">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-207">Setting name</span></span> | <span data-ttu-id="6895c-208">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-208">Values</span></span> | <span data-ttu-id="6895c-209">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-210">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="6895c-211">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-211">*decimal value*</span></span> | <span data-ttu-id="6895c-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-213">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="6895c-214">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-214">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-216">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="6895c-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="6895c-218">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-218">*decimal value*</span></span> | <span data-ttu-id="6895c-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="6895c-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="6895c-220">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="6895c-221">System. GC. GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="6895c-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="6895c-222">Specifica l'elenco di processori da usare per Garbage Collector thread.</span><span class="sxs-lookup"><span data-stu-id="6895c-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="6895c-223">Questa impostazione è simile a [System. GC. HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), con la differenza che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="6895c-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="6895c-224">Per i sistemi operativi Windows, anteporre al [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente il numero o l'intervallo del processore, ad esempio "0:1-10, 0:12, 1:50-52, 1:70".</span><span class="sxs-lookup"><span data-stu-id="6895c-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="6895c-225">Se l' [affinità processori GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) è disabilitata, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="6895c-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="6895c-226">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6895c-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6895c-227">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="6895c-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="6895c-228">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-228">Setting name</span></span> | <span data-ttu-id="6895c-229">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-229">Values</span></span> | <span data-ttu-id="6895c-230">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-231">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="6895c-232">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="6895c-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="6895c-233">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="6895c-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="6895c-234">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="6895c-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="6895c-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-236">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="6895c-237">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="6895c-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="6895c-238">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="6895c-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="6895c-239">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="6895c-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="6895c-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-240">.NET Core 3.0</span></span> |

<span data-ttu-id="6895c-241">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="6895c-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="6895c-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="6895c-243">Configura se il Garbage Collector utilizza o meno [gruppi di CPU](/windows/win32/procthread/processor-groups) .</span><span class="sxs-lookup"><span data-stu-id="6895c-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="6895c-244">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="6895c-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="6895c-245">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="6895c-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="6895c-246">Si applica al server Garbage Collection solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6895c-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="6895c-247">Impostazione predefinita: GC non si estende tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="6895c-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="6895c-248">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="6895c-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="6895c-249">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="6895c-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="6895c-250">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-250">Setting name</span></span> | <span data-ttu-id="6895c-251">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-251">Values</span></span> | <span data-ttu-id="6895c-252">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-253">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="6895c-254">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-254">N/A</span></span> | <span data-ttu-id="6895c-255">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-255">N/A</span></span> | <span data-ttu-id="6895c-256">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-256">N/A</span></span> |
| <span data-ttu-id="6895c-257">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="6895c-258">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-258">`0` - disabled</span></span><br/><span data-ttu-id="6895c-259">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-259">`1` - enabled</span></span> | <span data-ttu-id="6895c-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-261">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="6895c-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="6895c-263">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-263">`false` - disabled</span></span><br/><span data-ttu-id="6895c-264">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="6895c-265">Per configurare il Common Language Runtime (CLR) in modo da distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="6895c-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="6895c-266">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della `COMPlus_Thread_UseAllCpuGroups` variabile di ambiente su `1` .</span><span class="sxs-lookup"><span data-stu-id="6895c-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="6895c-267">System. GC. NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="6895c-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="6895c-268">Specifica se *creare affinità tra* Garbage Collection thread con i processori.</span><span class="sxs-lookup"><span data-stu-id="6895c-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="6895c-269">Per creare affinità tra un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="6895c-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="6895c-270">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="6895c-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="6895c-271">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="6895c-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="6895c-272">Impostazione predefinita: creare affinità tra Garbage Collection thread con processori.</span><span class="sxs-lookup"><span data-stu-id="6895c-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="6895c-273">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="6895c-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="6895c-274">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-274">Setting name</span></span> | <span data-ttu-id="6895c-275">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-275">Values</span></span> | <span data-ttu-id="6895c-276">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-277">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="6895c-278">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="6895c-278">`false` - affinitize</span></span><br/><span data-ttu-id="6895c-279">`true`-non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="6895c-279">`true` - don't affinitize</span></span> | <span data-ttu-id="6895c-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-281">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="6895c-282">`0`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="6895c-282">`0` - affinitize</span></span><br/><span data-ttu-id="6895c-283">`1`-non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="6895c-283">`1` - don't affinitize</span></span> | <span data-ttu-id="6895c-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-285">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="6895c-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="6895c-287">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="6895c-287">`false` - affinitize</span></span><br/><span data-ttu-id="6895c-288">`true`-non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="6895c-288">`true` - don't affinitize</span></span> | <span data-ttu-id="6895c-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="6895c-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="6895c-290">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="6895c-291">System. GC. HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="6895c-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="6895c-292">Specifica la dimensione massima del commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="6895c-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="6895c-293">Questa impostazione si applica solo ai computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6895c-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="6895c-294">Questa impostazione viene ignorata se sono configurati i [limiti dell'heap per oggetto](#per-object-heap-limits) .</span><span class="sxs-lookup"><span data-stu-id="6895c-294">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="6895c-295">Il valore predefinito, applicabile solo in alcuni casi, è maggiore di 20 MB o del 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="6895c-295">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="6895c-296">Il valore predefinito si applica se:</span><span class="sxs-lookup"><span data-stu-id="6895c-296">The default value applies if:</span></span>

  - <span data-ttu-id="6895c-297">Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="6895c-297">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="6895c-298">[System. GC. HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) non è impostato.</span><span class="sxs-lookup"><span data-stu-id="6895c-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="6895c-299">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-299">Setting name</span></span> | <span data-ttu-id="6895c-300">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-300">Values</span></span> | <span data-ttu-id="6895c-301">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-301">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-302">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-302">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="6895c-303">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-303">*decimal value*</span></span> | <span data-ttu-id="6895c-304">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-304">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-305">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-305">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="6895c-306">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-306">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-307">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-307">.NET Core 3.0</span></span> |

<span data-ttu-id="6895c-308">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-308">Example:</span></span>

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
> <span data-ttu-id="6895c-309">Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-309">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6895c-310">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-310">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6895c-311">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibytes (MiB), i valori sarebbero 209715200 per il file JSON e 0xC800000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="6895c-311">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="6895c-312">System. GC. HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="6895c-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="6895c-313">Specifica l'utilizzo dell'heap GC consentito come percentuale della memoria fisica totale.</span><span class="sxs-lookup"><span data-stu-id="6895c-313">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="6895c-314">Se viene impostato anche [System. GC. HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) , questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="6895c-314">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="6895c-315">Questa impostazione si applica solo ai computer a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="6895c-315">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="6895c-316">Se il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato, la percentuale viene calcolata come percentuale del limite di memoria.</span><span class="sxs-lookup"><span data-stu-id="6895c-316">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="6895c-317">Questa impostazione viene ignorata se sono configurati i [limiti dell'heap per oggetto](#per-object-heap-limits) .</span><span class="sxs-lookup"><span data-stu-id="6895c-317">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="6895c-318">Il valore predefinito, applicabile solo in alcuni casi, è minore di 20 MB o del 75% del limite di memoria nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="6895c-318">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="6895c-319">Il valore predefinito si applica se:</span><span class="sxs-lookup"><span data-stu-id="6895c-319">The default value applies if:</span></span>

  - <span data-ttu-id="6895c-320">Il processo è in esecuzione all'interno di un contenitore con un limite di memoria specificato.</span><span class="sxs-lookup"><span data-stu-id="6895c-320">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="6895c-321">[System. GC. HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) non è impostato.</span><span class="sxs-lookup"><span data-stu-id="6895c-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="6895c-322">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-322">Setting name</span></span> | <span data-ttu-id="6895c-323">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-323">Values</span></span> | <span data-ttu-id="6895c-324">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-324">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-325">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-325">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="6895c-326">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-326">*decimal value*</span></span> | <span data-ttu-id="6895c-327">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-327">.NET Core 3.0</span></span> |
| <span data-ttu-id="6895c-328">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-328">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="6895c-329">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-329">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-330">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-330">.NET Core 3.0</span></span> |

<span data-ttu-id="6895c-331">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-331">Example:</span></span>

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
> <span data-ttu-id="6895c-332">Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-332">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6895c-333">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-333">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6895c-334">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="6895c-334">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="6895c-335">Limiti per oggetto-heap</span><span class="sxs-lookup"><span data-stu-id="6895c-335">Per-object-heap limits</span></span>

<span data-ttu-id="6895c-336">È possibile specificare l'utilizzo dell'heap consentito del GC in base all'heap degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6895c-336">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="6895c-337">Gli heap diversi sono l'heap degli oggetti grandi (LOH), l'heap degli oggetti piccoli (SOH) e l'heap degli oggetti bloccati.</span><span class="sxs-lookup"><span data-stu-id="6895c-337">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a><span data-ttu-id="6895c-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span><span class="sxs-lookup"><span data-stu-id="6895c-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span></span>

- <span data-ttu-id="6895c-339">Se si specifica un valore per le `COMPLUS_GCHeapHardLimitSOH` `COMPLUS_GCHeapHardLimitLOH` Impostazioni, o `COMPLUS_GCHeapHardLimitPOH` , è necessario specificare anche un valore per `COMPLUS_GCHeapHardLimitSOH` e `COMPLUS_GCHeapHardLimitLOH` .</span><span class="sxs-lookup"><span data-stu-id="6895c-339">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="6895c-340">In caso contrario, il runtime non verrà inizializzato.</span><span class="sxs-lookup"><span data-stu-id="6895c-340">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="6895c-341">Il valore predefinito per `COMPLUS_GCHeapHardLimitPOH` è 0.</span><span class="sxs-lookup"><span data-stu-id="6895c-341">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="6895c-342">`COMPLUS_GCHeapHardLimitSOH`e `COMPLUS_GCHeapHardLimitLOH` non hanno valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6895c-342">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="6895c-343">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-343">Setting name</span></span> | <span data-ttu-id="6895c-344">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-344">Values</span></span> | <span data-ttu-id="6895c-345">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-346">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-346">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="6895c-347">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-347">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-348">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6895c-348">.NET 5.0</span></span> |
| <span data-ttu-id="6895c-349">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-349">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="6895c-350">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-350">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-351">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6895c-351">.NET 5.0</span></span> |
| <span data-ttu-id="6895c-352">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-352">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="6895c-353">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-353">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-354">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6895c-354">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="6895c-355">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-355">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6895c-356">Per specificare, ad esempio, un limite rigido dell'heap di 200 mebibytes (MiB), il valore sarà 0xC800000 o C800000.</span><span class="sxs-lookup"><span data-stu-id="6895c-356">For example, to specify a heap hard limit of 200 mebibytes (MiB), the value would be 0xC800000 or C800000.</span></span>

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a><span data-ttu-id="6895c-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span><span class="sxs-lookup"><span data-stu-id="6895c-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span></span>

- <span data-ttu-id="6895c-358">Se si specifica un valore per le `COMPLUS_GCHeapHardLimitSOHPercent` `COMPLUS_GCHeapHardLimitLOHPercent` Impostazioni, o `COMPLUS_GCHeapHardLimitPOHPercent` , è necessario specificare anche un valore per `COMPLUS_GCHeapHardLimitSOHPercent` e `COMPLUS_GCHeapHardLimitLOHPercent` .</span><span class="sxs-lookup"><span data-stu-id="6895c-358">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="6895c-359">In caso contrario, il runtime non verrà inizializzato.</span><span class="sxs-lookup"><span data-stu-id="6895c-359">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="6895c-360">Queste impostazioni vengono ignorate `COMPLUS_GCHeapHardLimitSOH` se `COMPLUS_GCHeapHardLimitLOH` `COMPLUS_GCHeapHardLimitPOH` vengono specificati, e.</span><span class="sxs-lookup"><span data-stu-id="6895c-360">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="6895c-361">Il valore 1 indica che GC utilizza l'1% della memoria fisica totale per l'heap degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="6895c-361">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="6895c-362">Ogni valore deve essere maggiore di zero e minore di 100.</span><span class="sxs-lookup"><span data-stu-id="6895c-362">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="6895c-363">Inoltre, la somma dei tre valori di percentuale deve essere minore di 100.</span><span class="sxs-lookup"><span data-stu-id="6895c-363">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="6895c-364">In caso contrario, il runtime non verrà inizializzato.</span><span class="sxs-lookup"><span data-stu-id="6895c-364">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="6895c-365">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-365">Setting name</span></span> | <span data-ttu-id="6895c-366">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-366">Values</span></span> | <span data-ttu-id="6895c-367">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-367">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-368">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-368">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="6895c-369">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-369">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-370">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6895c-370">.NET 5.0</span></span> |
| <span data-ttu-id="6895c-371">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-371">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="6895c-372">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-372">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-373">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6895c-373">.NET 5.0</span></span> |
| <span data-ttu-id="6895c-374">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-374">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="6895c-375">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-375">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-376">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="6895c-376">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="6895c-377">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6895c-378">Ad esempio, per limitare l'utilizzo dell'heap al 30%, il valore sarà 0x1E o 1E.</span><span class="sxs-lookup"><span data-stu-id="6895c-378">For example, to limit the heap usage to 30%, the value would be 0x1E or 1E.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="6895c-379">System. GC. RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="6895c-379">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="6895c-380">Configura se i segmenti da eliminare vengono inseriti in un elenco di standby per un uso futuro o vengono rilasciati al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6895c-380">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="6895c-381">Impostazione predefinita: rilascia i segmenti al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6895c-381">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="6895c-382">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="6895c-382">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="6895c-383">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-383">Setting name</span></span> | <span data-ttu-id="6895c-384">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-384">Values</span></span> | <span data-ttu-id="6895c-385">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-386">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-386">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="6895c-387">`false`-versione a sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6895c-387">`false` - release to OS</span></span><br/><span data-ttu-id="6895c-388">`true`-messa in standby</span><span class="sxs-lookup"><span data-stu-id="6895c-388">`true` - put on standby</span></span> | <span data-ttu-id="6895c-389">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-389">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-390">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="6895c-390">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="6895c-391">`false`-versione a sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6895c-391">`false` - release to OS</span></span><br/><span data-ttu-id="6895c-392">`true`-messa in standby</span><span class="sxs-lookup"><span data-stu-id="6895c-392">`true` - put on standby</span></span> | <span data-ttu-id="6895c-393">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-393">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-394">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-394">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="6895c-395">`0`-versione a sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6895c-395">`0` - release to OS</span></span><br/><span data-ttu-id="6895c-396">`1`-messa in standby</span><span class="sxs-lookup"><span data-stu-id="6895c-396">`1` - put on standby</span></span> | <span data-ttu-id="6895c-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-397">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="6895c-398">Esempio</span><span class="sxs-lookup"><span data-stu-id="6895c-398">Examples</span></span>

<span data-ttu-id="6895c-399">*runtimeconfig.jsnel* file:</span><span class="sxs-lookup"><span data-stu-id="6895c-399">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="6895c-400">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="6895c-400">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="6895c-401">Pagine di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="6895c-401">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="6895c-402">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="6895c-402">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="6895c-403">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="6895c-403">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="6895c-404">Impostazione predefinita: non utilizzare pagine di grandi dimensioni quando è impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="6895c-404">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="6895c-405">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="6895c-405">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="6895c-406">Si tratta di un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="6895c-406">This is an experimental setting.</span></span>

| | <span data-ttu-id="6895c-407">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-407">Setting name</span></span> | <span data-ttu-id="6895c-408">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-408">Values</span></span> | <span data-ttu-id="6895c-409">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-409">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-410">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-410">**runtimeconfig.json**</span></span> | <span data-ttu-id="6895c-411">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-411">N/A</span></span> | <span data-ttu-id="6895c-412">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-412">N/A</span></span> | <span data-ttu-id="6895c-413">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-413">N/A</span></span> |
| <span data-ttu-id="6895c-414">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-414">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="6895c-415">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-415">`0` - disabled</span></span><br/><span data-ttu-id="6895c-416">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-416">`1` - enabled</span></span> | <span data-ttu-id="6895c-417">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6895c-417">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="6895c-418">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="6895c-418">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="6895c-419">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="6895c-419">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="6895c-420">Configura Garbage Collector il supporto per le piattaforme a 64 bit per le matrici con dimensione totale superiore a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="6895c-420">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="6895c-421">Impostazione predefinita: GC supporta matrici di dimensioni maggiori di 2 GB.</span><span class="sxs-lookup"><span data-stu-id="6895c-421">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="6895c-422">Equivale a impostare il valore su `1` .</span><span class="sxs-lookup"><span data-stu-id="6895c-422">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="6895c-423">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="6895c-423">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="6895c-424">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-424">Setting name</span></span> | <span data-ttu-id="6895c-425">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-425">Values</span></span> | <span data-ttu-id="6895c-426">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-426">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-427">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-427">**runtimeconfig.json**</span></span> | <span data-ttu-id="6895c-428">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-428">N/A</span></span> | <span data-ttu-id="6895c-429">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-429">N/A</span></span> | <span data-ttu-id="6895c-430">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-430">N/A</span></span> |
| <span data-ttu-id="6895c-431">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-431">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="6895c-432">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-432">`1` - enabled</span></span><br/> <span data-ttu-id="6895c-433">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-433">`0` - disabled</span></span> | <span data-ttu-id="6895c-434">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-434">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-435">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-435">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-436">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="6895c-436">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="6895c-437">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-437">`1` - enabled</span></span><br/> <span data-ttu-id="6895c-438">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="6895c-438">`0` - disabled</span></span> | <span data-ttu-id="6895c-439">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="6895c-439">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="6895c-440">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="6895c-440">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="6895c-441">System. GC. LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="6895c-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="6895c-442">Specifica le dimensioni della soglia, in byte, che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="6895c-442">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="6895c-443">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="6895c-443">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="6895c-444">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="6895c-444">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="6895c-445">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-445">Setting name</span></span> | <span data-ttu-id="6895c-446">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-446">Values</span></span> | <span data-ttu-id="6895c-447">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-447">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-448">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-448">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="6895c-449">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-449">*decimal value*</span></span> | <span data-ttu-id="6895c-450">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-450">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-451">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-451">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="6895c-452">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-452">*hexadecimal value*</span></span> | <span data-ttu-id="6895c-453">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="6895c-453">.NET Core 1.0</span></span> |
| <span data-ttu-id="6895c-454">**app.config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="6895c-454">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="6895c-455">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="6895c-455">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="6895c-456">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="6895c-456">*decimal value*</span></span> | <span data-ttu-id="6895c-457">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="6895c-457">.NET Framework 4.8</span></span> |

<span data-ttu-id="6895c-458">Esempio:</span><span class="sxs-lookup"><span data-stu-id="6895c-458">Example:</span></span>

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
> <span data-ttu-id="6895c-459">Se si sta impostando l'opzione in *runtimeconfig.json*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-459">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="6895c-460">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="6895c-460">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="6895c-461">Ad esempio, per impostare una dimensione della soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="6895c-461">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="6895c-462">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="6895c-462">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="6895c-463">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="6895c-463">COMPlus_GCName</span></span>

- <span data-ttu-id="6895c-464">Specifica un percorso della libreria che contiene il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="6895c-464">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="6895c-465">Per ulteriori informazioni, vedere la pagina relativa alla [progettazione del caricatore GC autonomo](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="6895c-465">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="6895c-466">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="6895c-466">Setting name</span></span> | <span data-ttu-id="6895c-467">Valori</span><span class="sxs-lookup"><span data-stu-id="6895c-467">Values</span></span> | <span data-ttu-id="6895c-468">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6895c-468">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="6895c-469">**runtimeconfig.js**</span><span class="sxs-lookup"><span data-stu-id="6895c-469">**runtimeconfig.json**</span></span> | <span data-ttu-id="6895c-470">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-470">N/A</span></span> | <span data-ttu-id="6895c-471">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-471">N/A</span></span> | <span data-ttu-id="6895c-472">N/D</span><span class="sxs-lookup"><span data-stu-id="6895c-472">N/A</span></span> |
| <span data-ttu-id="6895c-473">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="6895c-473">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="6895c-474">*string_path*</span><span class="sxs-lookup"><span data-stu-id="6895c-474">*string_path*</span></span> | <span data-ttu-id="6895c-475">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6895c-475">.NET Core 2.0</span></span> |
