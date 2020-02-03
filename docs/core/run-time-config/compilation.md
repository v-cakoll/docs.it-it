---
title: Impostazioni di configurazione della compilazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il funzionamento del compilatore JIT per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 0dab3b7b7726a232cf293e338308cf898b370759
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733532"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="872dd-103">Opzioni di configurazione della fase di esecuzione per la compilazione</span><span class="sxs-lookup"><span data-stu-id="872dd-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="872dd-104">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="872dd-104">Tiered compilation</span></span>

- <span data-ttu-id="872dd-105">Configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="872dd-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="872dd-106">Metodi di transizione di compilazione a più livelli tramite due livelli:</span><span class="sxs-lookup"><span data-stu-id="872dd-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="872dd-107">Il primo livello genera il codice più rapidamente ([Quick JIT](#quick-jit)) o carica il codice precompilato ([ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images)).</span><span class="sxs-lookup"><span data-stu-id="872dd-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images)).</span></span>
  - <span data-ttu-id="872dd-108">Il secondo livello genera il codice ottimizzato in background ("Optimizing JIT").</span><span class="sxs-lookup"><span data-stu-id="872dd-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="872dd-109">In .NET Core 3,0 e versioni successive la compilazione a più livelli è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="872dd-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="872dd-110">In .NET Core 2,1 e 2,2 la compilazione a più livelli è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="872dd-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="872dd-111">Per ulteriori informazioni, vedere la [Guida alla compilazione](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md)a più livelli.</span><span class="sxs-lookup"><span data-stu-id="872dd-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md).</span></span>

| | <span data-ttu-id="872dd-112">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="872dd-112">Setting name</span></span> | <span data-ttu-id="872dd-113">Valori</span><span class="sxs-lookup"><span data-stu-id="872dd-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="872dd-114">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="872dd-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="872dd-115">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="872dd-115">`true` - enabled</span></span><br/><span data-ttu-id="872dd-116">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-116">`false` - disabled</span></span> |
| <span data-ttu-id="872dd-117">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="872dd-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="872dd-118">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="872dd-118">`true` - enabled</span></span><br/><span data-ttu-id="872dd-119">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-119">`false` - disabled</span></span> |
| <span data-ttu-id="872dd-120">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="872dd-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="872dd-121">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="872dd-121">`1` - enabled</span></span><br/><span data-ttu-id="872dd-122">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="872dd-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="872dd-123">Examples</span></span>

<span data-ttu-id="872dd-124">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="872dd-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="872dd-125">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="872dd-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="872dd-126">JIT rapido</span><span class="sxs-lookup"><span data-stu-id="872dd-126">Quick JIT</span></span>

- <span data-ttu-id="872dd-127">Configura se il compilatore JIT utilizza *JIT rapido*.</span><span class="sxs-lookup"><span data-stu-id="872dd-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="872dd-128">Per i metodi che non contengono cicli e per cui il codice precompilato non è disponibile, Quick JIT li compila più rapidamente ma senza ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="872dd-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="872dd-129">L'abilitazione di JIT rapido riduce il tempo di avvio ma può produrre codice con caratteristiche di prestazioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="872dd-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="872dd-130">Ad esempio, il codice può usare più spazio dello stack, allocare più memoria ed eseguire più lentamente.</span><span class="sxs-lookup"><span data-stu-id="872dd-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="872dd-131">Se JIT è disabilitato ma la compilazione a più [livelli](#tiered-compilation) è abilitata, solo il codice precompilato partecipa alla compilazione a più livelli.</span><span class="sxs-lookup"><span data-stu-id="872dd-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="872dd-132">Se un metodo non è precompilato con [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images), il comportamento JIT è identico a quello in cui la [compilazione a livelli](#tiered-compilation) è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="872dd-132">If a method is not pre-compiled with [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="872dd-133">In .NET Core 3,0 e versioni successive, Quick JIT è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="872dd-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="872dd-134">In .NET Core 2,1 e 2,2, Quick JIT è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="872dd-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="872dd-135">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="872dd-135">Setting name</span></span> | <span data-ttu-id="872dd-136">Valori</span><span class="sxs-lookup"><span data-stu-id="872dd-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="872dd-137">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="872dd-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="872dd-138">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="872dd-138">`true` - enabled</span></span><br/><span data-ttu-id="872dd-139">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-139">`false` - disabled</span></span> |
| <span data-ttu-id="872dd-140">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="872dd-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="872dd-141">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="872dd-141">`true` - enabled</span></span><br/><span data-ttu-id="872dd-142">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-142">`false` - disabled</span></span> |
| <span data-ttu-id="872dd-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="872dd-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="872dd-144">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="872dd-144">`1` - enabled</span></span><br/><span data-ttu-id="872dd-145">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="872dd-146">Esempi</span><span class="sxs-lookup"><span data-stu-id="872dd-146">Examples</span></span>

<span data-ttu-id="872dd-147">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="872dd-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="872dd-148">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="872dd-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="872dd-149">JIT rapido per i cicli</span><span class="sxs-lookup"><span data-stu-id="872dd-149">Quick JIT for loops</span></span>

- <span data-ttu-id="872dd-150">Configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="872dd-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="872dd-151">L'abilitazione di Quick JIT for loops può migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="872dd-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="872dd-152">Tuttavia, i cicli con esecuzione prolungata possono rimanere bloccati nel codice meno ottimizzato per lunghi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="872dd-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="872dd-153">Se [JIT rapido](#quick-jit) è disabilitato, questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="872dd-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="872dd-154">Impostazione predefinita: disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="872dd-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="872dd-155">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="872dd-155">Setting name</span></span> | <span data-ttu-id="872dd-156">Valori</span><span class="sxs-lookup"><span data-stu-id="872dd-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="872dd-157">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="872dd-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="872dd-158">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-158">`false` - disabled</span></span><br/><span data-ttu-id="872dd-159">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="872dd-159">`true` - enabled</span></span> |
| <span data-ttu-id="872dd-160">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="872dd-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="872dd-161">`false` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-161">`false` - disabled</span></span><br/><span data-ttu-id="872dd-162">Abilitazione di `true`</span><span class="sxs-lookup"><span data-stu-id="872dd-162">`true` - enabled</span></span> |
| <span data-ttu-id="872dd-163">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="872dd-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="872dd-164">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="872dd-164">`0` - disabled</span></span><br/><span data-ttu-id="872dd-165">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="872dd-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="872dd-166">Esempi</span><span class="sxs-lookup"><span data-stu-id="872dd-166">Examples</span></span>

<span data-ttu-id="872dd-167">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="872dd-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="872dd-168">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="872dd-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```
