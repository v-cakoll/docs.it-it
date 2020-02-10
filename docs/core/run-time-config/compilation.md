---
title: Impostazioni di configurazione della compilazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il funzionamento del compilatore JIT per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: adf1f01dba7387b89ee56784e33653d6a132c0e3
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092889"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="e206a-103">Opzioni di configurazione della fase di esecuzione per la compilazione</span><span class="sxs-lookup"><span data-stu-id="e206a-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="e206a-104">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="e206a-104">Tiered compilation</span></span>

- <span data-ttu-id="e206a-105">Configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="e206a-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="e206a-106">Metodi di transizione di compilazione a più livelli tramite due livelli:</span><span class="sxs-lookup"><span data-stu-id="e206a-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="e206a-107">Il primo livello genera il codice più rapidamente ([Quick JIT](#quick-jit)) o carica il codice precompilato ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="e206a-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="e206a-108">Il secondo livello genera il codice ottimizzato in background ("Optimizing JIT").</span><span class="sxs-lookup"><span data-stu-id="e206a-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="e206a-109">In .NET Core 3,0 e versioni successive la compilazione a più livelli è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e206a-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="e206a-110">In .NET Core 2,1 e 2,2 la compilazione a più livelli è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e206a-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="e206a-111">Per ulteriori informazioni, vedere la [Guida alla compilazione](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md)a più livelli.</span><span class="sxs-lookup"><span data-stu-id="e206a-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md).</span></span>

| | <span data-ttu-id="e206a-112">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e206a-112">Setting name</span></span> | <span data-ttu-id="e206a-113">Valori</span><span class="sxs-lookup"><span data-stu-id="e206a-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e206a-114">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e206a-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="e206a-115">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="e206a-115">`true` - enabled</span></span><br/><span data-ttu-id="e206a-116">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-116">`false` - disabled</span></span> |
| <span data-ttu-id="e206a-117">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="e206a-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="e206a-118">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="e206a-118">`true` - enabled</span></span><br/><span data-ttu-id="e206a-119">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-119">`false` - disabled</span></span> |
| <span data-ttu-id="e206a-120">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e206a-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="e206a-121">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="e206a-121">`1` - enabled</span></span><br/><span data-ttu-id="e206a-122">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="e206a-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="e206a-123">Examples</span></span>

<span data-ttu-id="e206a-124">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="e206a-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="e206a-125">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="e206a-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="e206a-126">JIT rapido</span><span class="sxs-lookup"><span data-stu-id="e206a-126">Quick JIT</span></span>

- <span data-ttu-id="e206a-127">Configura se il compilatore JIT utilizza *JIT rapido*.</span><span class="sxs-lookup"><span data-stu-id="e206a-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="e206a-128">Per i metodi che non contengono cicli e per cui il codice precompilato non è disponibile, Quick JIT li compila più rapidamente ma senza ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e206a-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="e206a-129">L'abilitazione di JIT rapido riduce il tempo di avvio ma può produrre codice con caratteristiche di prestazioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="e206a-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="e206a-130">Ad esempio, il codice può usare più spazio dello stack, allocare più memoria ed eseguire più lentamente.</span><span class="sxs-lookup"><span data-stu-id="e206a-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="e206a-131">Se JIT è disabilitato ma la compilazione a più [livelli](#tiered-compilation) è abilitata, solo il codice precompilato partecipa alla compilazione a più livelli.</span><span class="sxs-lookup"><span data-stu-id="e206a-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="e206a-132">Se un metodo non è precompilato con [ReadyToRun](#readytorun), il comportamento JIT è identico a quello in cui la [compilazione a livelli](#tiered-compilation) è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e206a-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="e206a-133">In .NET Core 3,0 e versioni successive, Quick JIT è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e206a-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="e206a-134">In .NET Core 2,1 e 2,2, Quick JIT è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e206a-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="e206a-135">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e206a-135">Setting name</span></span> | <span data-ttu-id="e206a-136">Valori</span><span class="sxs-lookup"><span data-stu-id="e206a-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e206a-137">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e206a-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="e206a-138">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="e206a-138">`true` - enabled</span></span><br/><span data-ttu-id="e206a-139">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-139">`false` - disabled</span></span> |
| <span data-ttu-id="e206a-140">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="e206a-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="e206a-141">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="e206a-141">`true` - enabled</span></span><br/><span data-ttu-id="e206a-142">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-142">`false` - disabled</span></span> |
| <span data-ttu-id="e206a-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e206a-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="e206a-144">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="e206a-144">`1` - enabled</span></span><br/><span data-ttu-id="e206a-145">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="e206a-146">Esempi</span><span class="sxs-lookup"><span data-stu-id="e206a-146">Examples</span></span>

<span data-ttu-id="e206a-147">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="e206a-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="e206a-148">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="e206a-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="e206a-149">JIT rapido per i cicli</span><span class="sxs-lookup"><span data-stu-id="e206a-149">Quick JIT for loops</span></span>

- <span data-ttu-id="e206a-150">Configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="e206a-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="e206a-151">L'abilitazione di Quick JIT for loops può migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="e206a-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="e206a-152">Tuttavia, i cicli con esecuzione prolungata possono rimanere bloccati nel codice meno ottimizzato per lunghi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="e206a-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="e206a-153">Se [JIT rapido](#quick-jit) è disabilitato, questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="e206a-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="e206a-154">Impostazione predefinita: disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="e206a-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="e206a-155">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e206a-155">Setting name</span></span> | <span data-ttu-id="e206a-156">Valori</span><span class="sxs-lookup"><span data-stu-id="e206a-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e206a-157">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e206a-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="e206a-158">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-158">`false` - disabled</span></span><br/><span data-ttu-id="e206a-159">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="e206a-159">`true` - enabled</span></span> |
| <span data-ttu-id="e206a-160">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="e206a-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="e206a-161">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-161">`false` - disabled</span></span><br/><span data-ttu-id="e206a-162">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="e206a-162">`true` - enabled</span></span> |
| <span data-ttu-id="e206a-163">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e206a-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="e206a-164">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-164">`0` - disabled</span></span><br/><span data-ttu-id="e206a-165">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="e206a-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="e206a-166">Esempi</span><span class="sxs-lookup"><span data-stu-id="e206a-166">Examples</span></span>

<span data-ttu-id="e206a-167">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="e206a-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="e206a-168">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="e206a-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="e206a-169">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="e206a-169">ReadyToRun</span></span>

- <span data-ttu-id="e206a-170">Configura se il runtime di .NET Core usa codice precompilato per le immagini con i dati ReadyToRun disponibili.</span><span class="sxs-lookup"><span data-stu-id="e206a-170">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="e206a-171">La disabilitazione di questa opzione impone al runtime il codice del Framework per la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="e206a-171">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="e206a-172">Per ulteriori informazioni, vedere [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="e206a-172">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="e206a-173">Impostazione predefinita: abilitata (`1`).</span><span class="sxs-lookup"><span data-stu-id="e206a-173">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="e206a-174">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e206a-174">Setting name</span></span> | <span data-ttu-id="e206a-175">Valori</span><span class="sxs-lookup"><span data-stu-id="e206a-175">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e206a-176">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e206a-176">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="e206a-177">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="e206a-177">`1` - enabled</span></span><br/><span data-ttu-id="e206a-178">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="e206a-178">`0` - disabled</span></span> |
