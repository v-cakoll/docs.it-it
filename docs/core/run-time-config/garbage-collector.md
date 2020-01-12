---
title: Impostazioni di configurazione del Garbage Collector
description: Informazioni sulle impostazioni di run-time per la configurazione del modo in cui il Garbage Collector gestisce la memoria per le app .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900104"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="49498-103">Opzioni di configurazione in fase di esecuzione per Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="49498-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="49498-104">Questa pagina contiene informazioni sulle impostazioni di Garbage Collector (GC) che possono essere modificate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="49498-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="49498-105">Se si sta tentando di ottenere prestazioni ottimali di un'app in esecuzione, è consigliabile usare queste impostazioni.</span><span class="sxs-lookup"><span data-stu-id="49498-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="49498-106">Tuttavia, le impostazioni predefinite forniscono prestazioni ottimali per la maggior parte delle applicazioni in situazioni tipiche.</span><span class="sxs-lookup"><span data-stu-id="49498-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="49498-107">Le impostazioni sono disposte in gruppi in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="49498-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="49498-108">Le impostazioni all'interno di ogni gruppo vengono comunemente usate insieme tra loro per ottenere un risultato specifico.</span><span class="sxs-lookup"><span data-stu-id="49498-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="49498-109">Queste impostazioni possono essere modificate anche in modo dinamico dall'app mentre è in esecuzione, quindi è possibile eseguire l'override di tutte le impostazioni di runtime impostate.</span><span class="sxs-lookup"><span data-stu-id="49498-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="49498-110">Alcune impostazioni, ad esempio il [livello di latenza](../../standard/garbage-collection/latency.md), vengono in genere impostate solo tramite l'API in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="49498-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="49498-111">Tali impostazioni vengono omesse da questa pagina.</span><span class="sxs-lookup"><span data-stu-id="49498-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="49498-112">Per i valori numerici, usare la notazione decimale per le impostazioni nel file *runtimeconfig. JSON* e la notazione esadecimale per le impostazioni delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="49498-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="49498-113">Per i valori esadecimali, è possibile specificarli con o senza il prefisso "0x".</span><span class="sxs-lookup"><span data-stu-id="49498-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="49498-114">Tipi di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="49498-114">Flavors of garbage collection</span></span>

<span data-ttu-id="49498-115">I due principali tipi di Garbage Collection sono GC della workstation e GC del server.</span><span class="sxs-lookup"><span data-stu-id="49498-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="49498-116">Per ulteriori informazioni sulle differenze tra le due, vedere [nozioni fondamentali di Garbage Collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="49498-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="49498-117">Le sottoversioni di Garbage Collection sono in background e non simultanee.</span><span class="sxs-lookup"><span data-stu-id="49498-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="49498-118">Usare le impostazioni seguenti per selezionare le versioni di Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="49498-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="49498-119">System. GC. Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="49498-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="49498-120">Configura se l'applicazione utilizza la workstation Garbage Collection o Garbage Collection server.</span><span class="sxs-lookup"><span data-stu-id="49498-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="49498-121">Impostazione predefinita: Garbage Collection workstation (`false`).</span><span class="sxs-lookup"><span data-stu-id="49498-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="49498-122">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-122">Setting name</span></span> | <span data-ttu-id="49498-123">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-123">Values</span></span> | <span data-ttu-id="49498-124">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-125">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="49498-126">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="49498-126">`false` - workstation</span></span><br/><span data-ttu-id="49498-127">Server `true`</span><span class="sxs-lookup"><span data-stu-id="49498-127">`true` - server</span></span> | <span data-ttu-id="49498-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-129">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="49498-130">workstation `0`</span><span class="sxs-lookup"><span data-stu-id="49498-130">`0` - workstation</span></span><br/><span data-ttu-id="49498-131">Server `1`</span><span class="sxs-lookup"><span data-stu-id="49498-131">`1` - server</span></span> | <span data-ttu-id="49498-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-133">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="49498-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="49498-135">workstation `false`</span><span class="sxs-lookup"><span data-stu-id="49498-135">`false` - workstation</span></span><br/><span data-ttu-id="49498-136">Server `true`</span><span class="sxs-lookup"><span data-stu-id="49498-136">`true` - server</span></span> |  |

<span data-ttu-id="49498-137">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="49498-138">System. GC. Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="49498-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="49498-139">Configura se la Garbage Collection di sfondo (simultanea) è abilitata.</span><span class="sxs-lookup"><span data-stu-id="49498-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="49498-140">Impostazione predefinita: abilitata (`true`).</span><span class="sxs-lookup"><span data-stu-id="49498-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="49498-141">Per ulteriori informazioni, vedere [Garbage Collection in background](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) e [Garbage Collection server in background](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span><span class="sxs-lookup"><span data-stu-id="49498-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="49498-142">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-142">Setting name</span></span> | <span data-ttu-id="49498-143">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-143">Values</span></span> | <span data-ttu-id="49498-144">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-145">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="49498-146">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="49498-146">`true` - background GC</span></span><br/><span data-ttu-id="49498-147">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="49498-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="49498-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-149">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="49498-150">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="49498-150">`true` - background GC</span></span><br/><span data-ttu-id="49498-151">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="49498-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="49498-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-153">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="49498-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="49498-155">GC in background `true`</span><span class="sxs-lookup"><span data-stu-id="49498-155">`true` - background GC</span></span><br/><span data-ttu-id="49498-156">GC `false` non simultaneo</span><span class="sxs-lookup"><span data-stu-id="49498-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="49498-157">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="49498-158">Gestire l'utilizzo delle risorse</span><span class="sxs-lookup"><span data-stu-id="49498-158">Manage resource usage</span></span>

<span data-ttu-id="49498-159">Usare le impostazioni descritte in questa sezione per gestire l'utilizzo della memoria e del processore del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="49498-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="49498-160">Per altre informazioni su alcune di queste impostazioni, vedere la parte intermedia tra la voce del Blog di [GC workstation e server](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) .</span><span class="sxs-lookup"><span data-stu-id="49498-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="49498-161">System. GC. HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="49498-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="49498-162">Limita il numero di heap creati dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="49498-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="49498-163">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="49498-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49498-164">Se è abilitata l'affinità processori GC, ovvero l'impostazione predefinita, il numero di heap imposta cui `n` heap GC/thread per i primi processori `n`.</span><span class="sxs-lookup"><span data-stu-id="49498-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="49498-165">Usare le impostazioni creare affinità tra mask o creare affinità tra Ranges per specificare esattamente i processori da creare affinità tra.</span><span class="sxs-lookup"><span data-stu-id="49498-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="49498-166">Se l'affinità processori GC è disabilitata, questa impostazione limita il numero di heap GC.</span><span class="sxs-lookup"><span data-stu-id="49498-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="49498-167">Per ulteriori informazioni, vedere la [sezione Osservazioni GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span><span class="sxs-lookup"><span data-stu-id="49498-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="49498-168">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-168">Setting name</span></span> | <span data-ttu-id="49498-169">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-169">Values</span></span> | <span data-ttu-id="49498-170">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-171">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="49498-172">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-172">*decimal value*</span></span> | <span data-ttu-id="49498-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-174">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="49498-175">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="49498-175">*hexadecimal value*</span></span> | <span data-ttu-id="49498-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-177">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="49498-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="49498-179">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-179">*decimal value*</span></span> | <span data-ttu-id="49498-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="49498-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="49498-181">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-181">Example:</span></span>

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
> <span data-ttu-id="49498-182">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="49498-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49498-183">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="49498-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49498-184">Ad esempio, per limitare il numero di heap a 16, i valori sarebbero 16 per il file JSON e 0x10 o 10 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="49498-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="49498-185">System. GC. HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="49498-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="49498-186">Specifica i processori esatti che Garbage Collector thread devono usare.</span><span class="sxs-lookup"><span data-stu-id="49498-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="49498-187">Se l'affinità del processore è disabilitata impostando `System.GC.NoAffinitize` su `true`, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="49498-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="49498-188">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="49498-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49498-189">Il valore è una maschera di bit che definisce i processori disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="49498-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="49498-190">Ad esempio, un valore decimale di 1023 (o un valore esadecimale di 0x3FF o 3FF se si usa la variabile di ambiente) è 0011 1111 1111 in notazione binaria.</span><span class="sxs-lookup"><span data-stu-id="49498-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="49498-191">Specifica che devono essere usati i primi 10 processori.</span><span class="sxs-lookup"><span data-stu-id="49498-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="49498-192">Per specificare i 10 processori successivi, ovvero i processori 10-19, specificare un valore decimale di 1047552 (o un valore esadecimale di 0xFFC00 o FFC00), equivalente a un valore binario di 1111 1111 1100 0000 0000.</span><span class="sxs-lookup"><span data-stu-id="49498-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="49498-193">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-193">Setting name</span></span> | <span data-ttu-id="49498-194">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-194">Values</span></span> | <span data-ttu-id="49498-195">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-196">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="49498-197">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-197">*decimal value*</span></span> | <span data-ttu-id="49498-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-199">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="49498-200">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="49498-200">*hexadecimal value*</span></span> | <span data-ttu-id="49498-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-202">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="49498-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="49498-204">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-204">*decimal value*</span></span> | <span data-ttu-id="49498-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="49498-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="49498-206">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="49498-207">System. GC. GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="49498-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="49498-208">Specifica l'elenco di processori da usare per Garbage Collector thread.</span><span class="sxs-lookup"><span data-stu-id="49498-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="49498-209">Questa impostazione è simile a `System.GC.HeapAffinitizeMask`, ad eccezione del fatto che consente di specificare più di 64 processori.</span><span class="sxs-lookup"><span data-stu-id="49498-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="49498-210">Per i sistemi operativi Windows, anteporre al [gruppo di CPU](/windows/win32/procthread/processor-groups)corrispondente il numero o l'intervallo del processore, ad esempio "0:1-10, 0:12, 1:50-52, 1:70".</span><span class="sxs-lookup"><span data-stu-id="49498-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="49498-211">Se l'affinità del processore è disabilitata impostando `System.GC.NoAffinitize` su `true`, questa impostazione viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="49498-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="49498-212">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="49498-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49498-213">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="49498-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="49498-214">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-214">Setting name</span></span> | <span data-ttu-id="49498-215">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-215">Values</span></span> | <span data-ttu-id="49498-216">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-217">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="49498-218">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="49498-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="49498-219">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="49498-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="49498-220">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="49498-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="49498-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-222">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="49498-223">Elenco delimitato da virgole di numeri di processore o intervalli di numeri del processore.</span><span class="sxs-lookup"><span data-stu-id="49498-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="49498-224">Esempio di UNIX: "1-10, 12, 50-52, 70"</span><span class="sxs-lookup"><span data-stu-id="49498-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="49498-225">Esempio di Windows: "0:1-10, 0:12, 1:50-52, 1:70"</span><span class="sxs-lookup"><span data-stu-id="49498-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="49498-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-226">.NET Core 3.0</span></span> |

<span data-ttu-id="49498-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="49498-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="49498-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="49498-229">Configura se il Garbage Collector utilizza o meno [gruppi di CPU](/windows/win32/procthread/processor-groups) .</span><span class="sxs-lookup"><span data-stu-id="49498-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="49498-230">Quando un computer Windows a 64 bit dispone di più gruppi di CPU, ovvero sono presenti più di 64 processori, l'abilitazione di questo elemento estende Garbage Collection in tutti i gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="49498-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="49498-231">Il Garbage Collector utilizza tutti i core per creare e bilanciare gli heap.</span><span class="sxs-lookup"><span data-stu-id="49498-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="49498-232">Si applica al server Garbage Collection solo nei sistemi operativi Windows a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="49498-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="49498-233">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="49498-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="49498-234">Per altre informazioni, vedere [migliorare la configurazione della CPU per GC nei computer con > cpu 64](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) nel Blog di Maoni Stephens.</span><span class="sxs-lookup"><span data-stu-id="49498-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="49498-235">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-235">Setting name</span></span> | <span data-ttu-id="49498-236">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-236">Values</span></span> | <span data-ttu-id="49498-237">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-238">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="49498-239">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-239">N/A</span></span> | <span data-ttu-id="49498-240">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-240">N/A</span></span> | <span data-ttu-id="49498-241">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-241">N/A</span></span> |
| <span data-ttu-id="49498-242">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="49498-243">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="49498-243">`0` - disabled</span></span><br/><span data-ttu-id="49498-244">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="49498-244">`1` - enabled</span></span> | <span data-ttu-id="49498-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-246">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="49498-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="49498-248">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="49498-248">`false` - disabled</span></span><br/><span data-ttu-id="49498-249">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="49498-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="49498-250">Per configurare il Common Language Runtime (CLR) in modo da distribuire anche i thread dal pool di thread in tutti i gruppi di CPU, abilitare l'opzione [elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="49498-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="49498-251">Per le app .NET Core, è possibile abilitare questa opzione impostando il valore della variabile di ambiente `COMPlus_Thread_UseAllCpuGroups` su `1`.</span><span class="sxs-lookup"><span data-stu-id="49498-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="49498-252">System. GC. NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="49498-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="49498-253">Specifica se *creare affinità tra* Garbage Collection thread con i processori.</span><span class="sxs-lookup"><span data-stu-id="49498-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="49498-254">Per creare affinità tra un thread GC significa che può essere eseguito solo sulla CPU specifica.</span><span class="sxs-lookup"><span data-stu-id="49498-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="49498-255">Viene creato un heap per ogni thread GC.</span><span class="sxs-lookup"><span data-stu-id="49498-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="49498-256">Si applica solo al server Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="49498-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="49498-257">Impostazione predefinita: creare affinità tra Garbage Collection thread con processori (`false`).</span><span class="sxs-lookup"><span data-stu-id="49498-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="49498-258">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-258">Setting name</span></span> | <span data-ttu-id="49498-259">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-259">Values</span></span> | <span data-ttu-id="49498-260">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-261">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="49498-262">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="49498-262">`false` - affinitize</span></span><br/><span data-ttu-id="49498-263">`true` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="49498-263">`true` - don't affinitize</span></span> | <span data-ttu-id="49498-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-265">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="49498-266">`0`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="49498-266">`0` - affinitize</span></span><br/><span data-ttu-id="49498-267">`1` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="49498-267">`1` - don't affinitize</span></span> | <span data-ttu-id="49498-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-269">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="49498-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="49498-271">`false`-creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="49498-271">`false` - affinitize</span></span><br/><span data-ttu-id="49498-272">`true` non creare affinità tra</span><span class="sxs-lookup"><span data-stu-id="49498-272">`true` - don't affinitize</span></span> | <span data-ttu-id="49498-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="49498-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="49498-274">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="49498-275">System. GC. HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="49498-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="49498-276">Specifica la dimensione massima del commit, in byte, per l'heap GC e la contabilità GC.</span><span class="sxs-lookup"><span data-stu-id="49498-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="49498-277">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-277">Setting name</span></span> | <span data-ttu-id="49498-278">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-278">Values</span></span> | <span data-ttu-id="49498-279">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-280">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="49498-281">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-281">*decimal value*</span></span> | <span data-ttu-id="49498-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-283">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="49498-284">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="49498-284">*hexadecimal value*</span></span> | <span data-ttu-id="49498-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-285">.NET Core 3.0</span></span> |

<span data-ttu-id="49498-286">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-286">Example:</span></span>

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
> <span data-ttu-id="49498-287">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="49498-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49498-288">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="49498-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49498-289">Ad esempio, per specificare un limite rigido dell'heap di 200 mebibytes (MiB), i valori sarebbero 209715200 per il file JSON e 0xC800000 o C800000 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="49498-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="49498-290">System. GC. HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="49498-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="49498-291">Specifica l'utilizzo dell'heap GC come percentuale della memoria totale.</span><span class="sxs-lookup"><span data-stu-id="49498-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="49498-292">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-292">Setting name</span></span> | <span data-ttu-id="49498-293">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-293">Values</span></span> | <span data-ttu-id="49498-294">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-295">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="49498-296">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-296">*decimal value*</span></span> | <span data-ttu-id="49498-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="49498-298">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="49498-299">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="49498-299">*hexadecimal value*</span></span> | <span data-ttu-id="49498-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-300">.NET Core 3.0</span></span> |

<span data-ttu-id="49498-301">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-301">Example:</span></span>

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
> <span data-ttu-id="49498-302">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="49498-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49498-303">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="49498-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49498-304">Ad esempio, per limitare l'utilizzo dell'heap al 30%, i valori sarebbero 30 per il file JSON e 0x1E o 1E per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="49498-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="49498-305">System. GC. RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="49498-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="49498-306">Configura se i segmenti da eliminare vengono inseriti in un elenco di standby per un uso futuro o vengono rilasciati al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="49498-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="49498-307">Impostazione predefinita: rilascia i segmenti al sistema operativo (`false`).</span><span class="sxs-lookup"><span data-stu-id="49498-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="49498-308">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-308">Setting name</span></span> | <span data-ttu-id="49498-309">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-309">Values</span></span> | <span data-ttu-id="49498-310">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-311">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="49498-312">`false`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="49498-312">`false` - release to OS</span></span><br/><span data-ttu-id="49498-313">`true`-put in standby</span><span class="sxs-lookup"><span data-stu-id="49498-313">`true` - put on standby</span></span>| <span data-ttu-id="49498-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-315">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="49498-316">`0`-rilascia al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="49498-316">`0` - release to OS</span></span><br/><span data-ttu-id="49498-317">`1`-put in standby</span><span class="sxs-lookup"><span data-stu-id="49498-317">`1` - put on standby</span></span> | <span data-ttu-id="49498-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-318">.NET Core 1.0</span></span> |

<span data-ttu-id="49498-319">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="49498-320">Pagine di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="49498-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="49498-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="49498-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="49498-322">Specifica se le pagine di grandi dimensioni devono essere utilizzate quando viene impostato un limite rigido dell'heap.</span><span class="sxs-lookup"><span data-stu-id="49498-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="49498-323">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="49498-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="49498-324">Si tratta di un'impostazione sperimentale.</span><span class="sxs-lookup"><span data-stu-id="49498-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="49498-325">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-325">Setting name</span></span> | <span data-ttu-id="49498-326">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-326">Values</span></span> | <span data-ttu-id="49498-327">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-328">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="49498-329">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-329">N/A</span></span> | <span data-ttu-id="49498-330">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-330">N/A</span></span> | <span data-ttu-id="49498-331">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-331">N/A</span></span> |
| <span data-ttu-id="49498-332">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="49498-333">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="49498-333">`0` - disabled</span></span><br/><span data-ttu-id="49498-334">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="49498-334">`1` - enabled</span></span> | <span data-ttu-id="49498-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="49498-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="49498-336">Oggetti di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="49498-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="49498-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="49498-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="49498-338">Configura Garbage Collector il supporto per le piattaforme a 64 bit per le matrici con dimensione totale superiore a 2 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="49498-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="49498-339">Impostazione predefinita: abilitata (`1`).</span><span class="sxs-lookup"><span data-stu-id="49498-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="49498-340">Questa opzione potrebbe diventare obsoleta in una versione futura di .NET.</span><span class="sxs-lookup"><span data-stu-id="49498-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="49498-341">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-341">Setting name</span></span> | <span data-ttu-id="49498-342">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-342">Values</span></span> | <span data-ttu-id="49498-343">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-344">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="49498-345">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-345">N/A</span></span> | <span data-ttu-id="49498-346">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-346">N/A</span></span> | <span data-ttu-id="49498-347">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-347">N/A</span></span> |
| <span data-ttu-id="49498-348">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="49498-349">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="49498-349">`1` - enabled</span></span><br/> <span data-ttu-id="49498-350">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="49498-350">`0` - disabled</span></span> | <span data-ttu-id="49498-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-352">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="49498-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="49498-354">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="49498-354">`1` - enabled</span></span><br/> <span data-ttu-id="49498-355">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="49498-355">`0` - disabled</span></span> | <span data-ttu-id="49498-356">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="49498-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="49498-357">Soglia heap oggetti grandi</span><span class="sxs-lookup"><span data-stu-id="49498-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="49498-358">System. GC. LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="49498-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="49498-359">Specifica le dimensioni della soglia, in byte, che determinano l'uso degli oggetti nell'heap degli oggetti grandi (LOH).</span><span class="sxs-lookup"><span data-stu-id="49498-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="49498-360">La soglia predefinita è 85.000 byte.</span><span class="sxs-lookup"><span data-stu-id="49498-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="49498-361">Il valore specificato deve essere maggiore della soglia predefinita.</span><span class="sxs-lookup"><span data-stu-id="49498-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="49498-362">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-362">Setting name</span></span> | <span data-ttu-id="49498-363">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-363">Values</span></span> | <span data-ttu-id="49498-364">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-365">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="49498-366">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-366">*decimal value*</span></span> | <span data-ttu-id="49498-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-368">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="49498-369">*valore esadecimale*</span><span class="sxs-lookup"><span data-stu-id="49498-369">*hexadecimal value*</span></span> | <span data-ttu-id="49498-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="49498-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="49498-371">**app. config per .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="49498-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="49498-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="49498-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="49498-373">*valore decimale*</span><span class="sxs-lookup"><span data-stu-id="49498-373">*decimal value*</span></span> | <span data-ttu-id="49498-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="49498-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="49498-375">Esempio:</span><span class="sxs-lookup"><span data-stu-id="49498-375">Example:</span></span>

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
> <span data-ttu-id="49498-376">Se si sta impostando l'opzione in *runtimeconfig. JSON*, specificare un valore decimale.</span><span class="sxs-lookup"><span data-stu-id="49498-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="49498-377">Se si imposta l'opzione come variabile di ambiente, specificare un valore esadecimale.</span><span class="sxs-lookup"><span data-stu-id="49498-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="49498-378">Ad esempio, per impostare una dimensione della soglia di 120.000 byte, i valori sarebbero 120000 per il file JSON e 0x1D4C0 o 1D4C0 per la variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="49498-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="49498-379">GC autonomo</span><span class="sxs-lookup"><span data-stu-id="49498-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="49498-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="49498-380">COMPlus_GCName</span></span>

- <span data-ttu-id="49498-381">Specifica un percorso della libreria che contiene il Garbage Collector che il runtime intende caricare.</span><span class="sxs-lookup"><span data-stu-id="49498-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="49498-382">Per ulteriori informazioni, vedere la pagina relativa alla [progettazione del caricatore GC autonomo](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span><span class="sxs-lookup"><span data-stu-id="49498-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="49498-383">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="49498-383">Setting name</span></span> | <span data-ttu-id="49498-384">Valori</span><span class="sxs-lookup"><span data-stu-id="49498-384">Values</span></span> | <span data-ttu-id="49498-385">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="49498-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="49498-386">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="49498-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="49498-387">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-387">N/A</span></span> | <span data-ttu-id="49498-388">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-388">N/A</span></span> | <span data-ttu-id="49498-389">N/D</span><span class="sxs-lookup"><span data-stu-id="49498-389">N/A</span></span> |
| <span data-ttu-id="49498-390">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="49498-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="49498-391">*string_path*</span><span class="sxs-lookup"><span data-stu-id="49498-391">*string_path*</span></span> | <span data-ttu-id="49498-392">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="49498-392">.NET Core 2.0</span></span> |
