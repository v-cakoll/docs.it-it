---
title: Impostazioni di configurazione della compilazione
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il funzionamento del compilatore JIT per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: cfcf9b5fc8d11a4ae35ab9b152f32133cd6930bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762006"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="448ee-103">Opzioni di configurazione della fase di esecuzione per la compilazione</span><span class="sxs-lookup"><span data-stu-id="448ee-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="448ee-104">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="448ee-104">Tiered compilation</span></span>

- <span data-ttu-id="448ee-105">Configura se il compilatore just-in-time (JIT) utilizza la [compilazione a livelli](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="448ee-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="448ee-106">Metodi di transizione di compilazione a più livelli tramite due livelli:</span><span class="sxs-lookup"><span data-stu-id="448ee-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="448ee-107">Il primo livello genera il codice più rapidamente ([Quick JIT](#quick-jit)) o carica il codice precompilato ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="448ee-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="448ee-108">Il secondo livello genera il codice ottimizzato in background ("Optimizing JIT").</span><span class="sxs-lookup"><span data-stu-id="448ee-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="448ee-109">In .NET Core 3,0 e versioni successive la compilazione a più livelli è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="448ee-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="448ee-110">In .NET Core 2,1 e 2,2 la compilazione a più livelli è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="448ee-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="448ee-111">Per ulteriori informazioni, vedere la [Guida alla compilazione](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)a più livelli.</span><span class="sxs-lookup"><span data-stu-id="448ee-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="448ee-112">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="448ee-112">Setting name</span></span> | <span data-ttu-id="448ee-113">Valori</span><span class="sxs-lookup"><span data-stu-id="448ee-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="448ee-114">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="448ee-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="448ee-115">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-115">`true` - enabled</span></span><br/><span data-ttu-id="448ee-116">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-116">`false` - disabled</span></span> |
| <span data-ttu-id="448ee-117">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="448ee-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="448ee-118">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-118">`true` - enabled</span></span><br/><span data-ttu-id="448ee-119">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-119">`false` - disabled</span></span> |
| <span data-ttu-id="448ee-120">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="448ee-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="448ee-121">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-121">`1` - enabled</span></span><br/><span data-ttu-id="448ee-122">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="448ee-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="448ee-123">Examples</span></span>

<span data-ttu-id="448ee-124">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="448ee-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="448ee-125">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="448ee-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="448ee-126">JIT rapido</span><span class="sxs-lookup"><span data-stu-id="448ee-126">Quick JIT</span></span>

- <span data-ttu-id="448ee-127">Configura se il compilatore JIT utilizza *JIT rapido*.</span><span class="sxs-lookup"><span data-stu-id="448ee-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="448ee-128">Per i metodi che non contengono cicli e per cui il codice precompilato non è disponibile, Quick JIT li compila più rapidamente ma senza ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="448ee-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="448ee-129">L'abilitazione di JIT rapido riduce il tempo di avvio ma può produrre codice con caratteristiche di prestazioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="448ee-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="448ee-130">Ad esempio, il codice può usare più spazio dello stack, allocare più memoria ed eseguire più lentamente.</span><span class="sxs-lookup"><span data-stu-id="448ee-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="448ee-131">Se JIT è disabilitato ma la compilazione a più [livelli](#tiered-compilation) è abilitata, solo il codice precompilato partecipa alla compilazione a più livelli.</span><span class="sxs-lookup"><span data-stu-id="448ee-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="448ee-132">Se un metodo non è precompilato con [ReadyToRun](#readytorun), il comportamento JIT è identico a quello in cui la [compilazione a livelli](#tiered-compilation) è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="448ee-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="448ee-133">In .NET Core 3,0 e versioni successive, Quick JIT è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="448ee-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="448ee-134">In .NET Core 2,1 e 2,2, Quick JIT è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="448ee-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="448ee-135">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="448ee-135">Setting name</span></span> | <span data-ttu-id="448ee-136">Valori</span><span class="sxs-lookup"><span data-stu-id="448ee-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="448ee-137">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="448ee-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="448ee-138">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-138">`true` - enabled</span></span><br/><span data-ttu-id="448ee-139">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-139">`false` - disabled</span></span> |
| <span data-ttu-id="448ee-140">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="448ee-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="448ee-141">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-141">`true` - enabled</span></span><br/><span data-ttu-id="448ee-142">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-142">`false` - disabled</span></span> |
| <span data-ttu-id="448ee-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="448ee-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="448ee-144">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-144">`1` - enabled</span></span><br/><span data-ttu-id="448ee-145">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="448ee-146">Esempi</span><span class="sxs-lookup"><span data-stu-id="448ee-146">Examples</span></span>

<span data-ttu-id="448ee-147">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="448ee-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="448ee-148">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="448ee-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="448ee-149">JIT rapido per i cicli</span><span class="sxs-lookup"><span data-stu-id="448ee-149">Quick JIT for loops</span></span>

- <span data-ttu-id="448ee-150">Configura se il compilatore JIT USA Quick JIT sui metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="448ee-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="448ee-151">L'abilitazione di Quick JIT for loops può migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="448ee-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="448ee-152">Tuttavia, i cicli con esecuzione prolungata possono rimanere bloccati nel codice meno ottimizzato per lunghi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="448ee-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="448ee-153">Se [JIT rapido](#quick-jit) è disabilitato, questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="448ee-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="448ee-154">Se si omette questa impostazione, Quick JIT non viene usato per i metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="448ee-154">If you omit this setting, quick JIT is not used for methods that contain loops.</span></span> <span data-ttu-id="448ee-155">Equivale a impostare il valore su `false` .</span><span class="sxs-lookup"><span data-stu-id="448ee-155">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="448ee-156">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="448ee-156">Setting name</span></span> | <span data-ttu-id="448ee-157">Valori</span><span class="sxs-lookup"><span data-stu-id="448ee-157">Values</span></span> |
| - | - | - |
| <span data-ttu-id="448ee-158">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="448ee-158">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="448ee-159">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-159">`false` - disabled</span></span><br/><span data-ttu-id="448ee-160">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-160">`true` - enabled</span></span> |
| <span data-ttu-id="448ee-161">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="448ee-161">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="448ee-162">`false`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-162">`false` - disabled</span></span><br/><span data-ttu-id="448ee-163">`true`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-163">`true` - enabled</span></span> |
| <span data-ttu-id="448ee-164">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="448ee-164">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="448ee-165">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-165">`0` - disabled</span></span><br/><span data-ttu-id="448ee-166">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-166">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="448ee-167">Esempi</span><span class="sxs-lookup"><span data-stu-id="448ee-167">Examples</span></span>

<span data-ttu-id="448ee-168">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="448ee-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="448ee-169">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="448ee-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="448ee-170">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="448ee-170">ReadyToRun</span></span>

- <span data-ttu-id="448ee-171">Configura se il runtime di .NET Core usa codice precompilato per le immagini con i dati ReadyToRun disponibili.</span><span class="sxs-lookup"><span data-stu-id="448ee-171">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="448ee-172">La disabilitazione di questa opzione impone al runtime il codice del Framework per la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="448ee-172">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="448ee-173">Per ulteriori informazioni, vedere [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="448ee-173">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="448ee-174">Se si omette questa impostazione, .NET utilizzerà i dati ReadyToRun quando sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="448ee-174">If you omit this setting, .NET uses ReadyToRun data when it's available.</span></span> <span data-ttu-id="448ee-175">Equivale a impostare il valore su `1` .</span><span class="sxs-lookup"><span data-stu-id="448ee-175">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="448ee-176">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="448ee-176">Setting name</span></span> | <span data-ttu-id="448ee-177">Valori</span><span class="sxs-lookup"><span data-stu-id="448ee-177">Values</span></span> |
| - | - | - |
| <span data-ttu-id="448ee-178">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="448ee-178">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="448ee-179">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-179">`1` - enabled</span></span><br/><span data-ttu-id="448ee-180">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="448ee-180">`0` - disabled</span></span> |
