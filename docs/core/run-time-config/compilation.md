---
title: Impostazioni di configurazione compilazione
description: Informazioni sulle impostazioni di runtime che configurano il funzionamento del compilatore JIT per le app .NET Core.Learn about run-time settings that configure how the JIT compiler works for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ac51aa13254b2f2b1fdd8d1dd9c52559831a1659
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989116"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="0bd2a-103">Opzioni di configurazione in fase di esecuzione per la compilazioneRun-time configuration options for compilation</span><span class="sxs-lookup"><span data-stu-id="0bd2a-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="0bd2a-104">Compilazione a livelli</span><span class="sxs-lookup"><span data-stu-id="0bd2a-104">Tiered compilation</span></span>

- <span data-ttu-id="0bd2a-105">Configura se il compilatore JIT (Just-In-Time) utilizza la [compilazione a livelli.](../whats-new/dotnet-core-3-0.md#tiered-compilation)</span><span class="sxs-lookup"><span data-stu-id="0bd2a-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="0bd2a-106">Metodi di transizione di compilazione a livelli tramite due livelli:Tiered compilation transitions methods through two tiers:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="0bd2a-107">Il primo livello genera codice più rapidamente ([JIT rapido](#quick-jit)) o carica codice precompilato ([ReadyToRun](#readytorun)).</span><span class="sxs-lookup"><span data-stu-id="0bd2a-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="0bd2a-108">Il secondo livello genera codice ottimizzato in background ("ottimizzazione di JIT").</span><span class="sxs-lookup"><span data-stu-id="0bd2a-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="0bd2a-109">In .NET Core 3.0 e versioni successive, la compilazione a livelli è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="0bd2a-110">In .NET Core 2.1 e 2.2 la compilazione a livelli è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="0bd2a-111">Per ulteriori informazioni, vedere la guida alla [compilazione a livelli](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="0bd2a-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="0bd2a-112">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="0bd2a-112">Setting name</span></span> | <span data-ttu-id="0bd2a-113">Valori</span><span class="sxs-lookup"><span data-stu-id="0bd2a-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0bd2a-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="0bd2a-115">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-115">`true` - enabled</span></span><br/><span data-ttu-id="0bd2a-116">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-116">`false` - disabled</span></span> |
| <span data-ttu-id="0bd2a-117">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="0bd2a-118">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-118">`true` - enabled</span></span><br/><span data-ttu-id="0bd2a-119">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-119">`false` - disabled</span></span> |
| <span data-ttu-id="0bd2a-120">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="0bd2a-121">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-121">`1` - enabled</span></span><br/><span data-ttu-id="0bd2a-122">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="0bd2a-123">Esempi</span><span class="sxs-lookup"><span data-stu-id="0bd2a-123">Examples</span></span>

<span data-ttu-id="0bd2a-124">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="0bd2a-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="0bd2a-125">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="0bd2a-126">JIT veloce</span><span class="sxs-lookup"><span data-stu-id="0bd2a-126">Quick JIT</span></span>

- <span data-ttu-id="0bd2a-127">Configura se il compilatore JIT utilizza *JIT rapido*.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="0bd2a-128">Per i metodi che non contengono cicli e per i quali il codice precompilato non è disponibile, JIT rapido li compila più rapidamente ma senza ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="0bd2a-129">L'abilitazione rapida di JIT riduce il tempo di avvio ma può produrre codice con caratteristiche di prestazioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="0bd2a-130">Ad esempio, il codice può utilizzare più spazio dello stack, allocare più memoria ed eseguire più lentamente.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="0bd2a-131">Se JIT rapido è disabilitato ma [la compilazione a più livelli](#tiered-compilation) è abilitata, solo il codice precompilato partecipa alla compilazione a livelli.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="0bd2a-132">Se un metodo non è precompilato con [ReadyToRun](#readytorun), il comportamento JIT è lo stesso di se la compilazione a più livelli fosse [disabilitata.](#tiered-compilation)</span><span class="sxs-lookup"><span data-stu-id="0bd2a-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="0bd2a-133">In .NET Core 3.0 e versioni successive, JIT rapido è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="0bd2a-134">In .NET Core 2.1 e 2.2, JIT rapido è disabilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="0bd2a-135">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="0bd2a-135">Setting name</span></span> | <span data-ttu-id="0bd2a-136">Valori</span><span class="sxs-lookup"><span data-stu-id="0bd2a-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0bd2a-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="0bd2a-138">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-138">`true` - enabled</span></span><br/><span data-ttu-id="0bd2a-139">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-139">`false` - disabled</span></span> |
| <span data-ttu-id="0bd2a-140">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="0bd2a-141">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-141">`true` - enabled</span></span><br/><span data-ttu-id="0bd2a-142">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-142">`false` - disabled</span></span> |
| <span data-ttu-id="0bd2a-143">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="0bd2a-144">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-144">`1` - enabled</span></span><br/><span data-ttu-id="0bd2a-145">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="0bd2a-146">Esempi</span><span class="sxs-lookup"><span data-stu-id="0bd2a-146">Examples</span></span>

<span data-ttu-id="0bd2a-147">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="0bd2a-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="0bd2a-148">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="0bd2a-149">JIT rapido per i loop</span><span class="sxs-lookup"><span data-stu-id="0bd2a-149">Quick JIT for loops</span></span>

- <span data-ttu-id="0bd2a-150">Configura se il compilatore JIT utilizza JIT rapido su metodi che contengono cicli.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="0bd2a-151">L'abilitazione rapida di JIT per i cicli può migliorare le prestazioni di avvio.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="0bd2a-152">Tuttavia, i cicli a esecuzione prolungata possono rimanere bloccati nel codice meno ottimizzato per lunghi periodi.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="0bd2a-153">Se [Quick JIT](#quick-jit) è disabilitato, questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="0bd2a-154">Impostazione predefinita: Disabilitato (`false`).</span><span class="sxs-lookup"><span data-stu-id="0bd2a-154">Default: Disabled (`false`).</span></span>

| | <span data-ttu-id="0bd2a-155">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="0bd2a-155">Setting name</span></span> | <span data-ttu-id="0bd2a-156">Valori</span><span class="sxs-lookup"><span data-stu-id="0bd2a-156">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0bd2a-157">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-157">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="0bd2a-158">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-158">`false` - disabled</span></span><br/><span data-ttu-id="0bd2a-159">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-159">`true` - enabled</span></span> |
| <span data-ttu-id="0bd2a-160">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-160">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="0bd2a-161">`false`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-161">`false` - disabled</span></span><br/><span data-ttu-id="0bd2a-162">`true`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-162">`true` - enabled</span></span> |
| <span data-ttu-id="0bd2a-163">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-163">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="0bd2a-164">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-164">`0` - disabled</span></span><br/><span data-ttu-id="0bd2a-165">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-165">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="0bd2a-166">Esempi</span><span class="sxs-lookup"><span data-stu-id="0bd2a-166">Examples</span></span>

<span data-ttu-id="0bd2a-167">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="0bd2a-167">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="0bd2a-168">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="0bd2a-168">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>false</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="0bd2a-169">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="0bd2a-169">ReadyToRun</span></span>

- <span data-ttu-id="0bd2a-170">Configura se il runtime di .NET Core utilizza codice precompilato per le immagini con i dati ReadyToRun disponibili.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-170">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="0bd2a-171">La disabilitazione di questa opzione forza il runtime a compilare il codice del framework JIT.</span><span class="sxs-lookup"><span data-stu-id="0bd2a-171">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="0bd2a-172">Per ulteriori informazioni, vedere [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span><span class="sxs-lookup"><span data-stu-id="0bd2a-172">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="0bd2a-173">Impostazione predefinita: Abilitato (`1`).</span><span class="sxs-lookup"><span data-stu-id="0bd2a-173">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="0bd2a-174">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="0bd2a-174">Setting name</span></span> | <span data-ttu-id="0bd2a-175">Valori</span><span class="sxs-lookup"><span data-stu-id="0bd2a-175">Values</span></span> |
| - | - | - |
| <span data-ttu-id="0bd2a-176">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="0bd2a-176">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="0bd2a-177">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-177">`1` - enabled</span></span><br/><span data-ttu-id="0bd2a-178">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="0bd2a-178">`0` - disabled</span></span> |
