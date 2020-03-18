---
title: Debug delle impostazioni di configurazione della profilaturaDebugging profiling config settings
description: Informazioni sulle impostazioni di runtime che configurano il debug e la profilatura per le app .NET Core.Learn about run-time settings that configure debugging and profiling for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74802799"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="a8054-103">Opzioni di configurazione in fase di esecuzione per il debug e la profilatura</span><span class="sxs-lookup"><span data-stu-id="a8054-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="a8054-104">Abilitare la diagnostica</span><span class="sxs-lookup"><span data-stu-id="a8054-104">Enable diagnostics</span></span>

- <span data-ttu-id="a8054-105">Configura se il debugger, il profiler e la diagnostica EventPipe sono abilitati o disabilitati.</span><span class="sxs-lookup"><span data-stu-id="a8054-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="a8054-106">Impostazione predefinita: Abilitato (`1`).</span><span class="sxs-lookup"><span data-stu-id="a8054-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="a8054-107">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a8054-107">Setting name</span></span> | <span data-ttu-id="a8054-108">Valori</span><span class="sxs-lookup"><span data-stu-id="a8054-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a8054-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a8054-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="a8054-110">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-110">N/A</span></span> | <span data-ttu-id="a8054-111">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-111">N/A</span></span> |
| <span data-ttu-id="a8054-112">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="a8054-113">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-113">`1` - enabled</span></span><br/><span data-ttu-id="a8054-114">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="a8054-115">Abilita profilatura</span><span class="sxs-lookup"><span data-stu-id="a8054-115">Enable profiling</span></span>

- <span data-ttu-id="a8054-116">Configura se la profilatura è abilitata per il processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a8054-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="a8054-117">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="a8054-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="a8054-118">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a8054-118">Setting name</span></span> | <span data-ttu-id="a8054-119">Valori</span><span class="sxs-lookup"><span data-stu-id="a8054-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a8054-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a8054-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="a8054-121">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-121">N/A</span></span> | <span data-ttu-id="a8054-122">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-122">N/A</span></span> |
| <span data-ttu-id="a8054-123">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="a8054-124">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-124">`0` - disabled</span></span><br/><span data-ttu-id="a8054-125">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="a8054-126">Profiler GUID</span><span class="sxs-lookup"><span data-stu-id="a8054-126">Profiler GUID</span></span>

- <span data-ttu-id="a8054-127">Specifica il GUID del profiler da caricare nel processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a8054-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="a8054-128">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a8054-128">Setting name</span></span> | <span data-ttu-id="a8054-129">Valori</span><span class="sxs-lookup"><span data-stu-id="a8054-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a8054-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a8054-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="a8054-131">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-131">N/A</span></span> | <span data-ttu-id="a8054-132">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-132">N/A</span></span> |
| <span data-ttu-id="a8054-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="a8054-134">*guid di stringa*</span><span class="sxs-lookup"><span data-stu-id="a8054-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="a8054-135">Posizione del profiler</span><span class="sxs-lookup"><span data-stu-id="a8054-135">Profiler location</span></span>

- <span data-ttu-id="a8054-136">Specifica il percorso della DLL del profiler da caricare nel processo attualmente in esecuzione (o processo a 32 bit o a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="a8054-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="a8054-137">Se è impostata più di una variabile, le variabili specifiche di bit hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="a8054-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="a8054-138">Specificano il numero di bit del profiler da caricare.</span><span class="sxs-lookup"><span data-stu-id="a8054-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="a8054-139">Per ulteriori informazioni, vedere [Ricerca della libreria del profiler](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="a8054-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="a8054-140">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a8054-140">Setting name</span></span> | <span data-ttu-id="a8054-141">Valori</span><span class="sxs-lookup"><span data-stu-id="a8054-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a8054-142">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="a8054-143">*percorso-stringa*</span><span class="sxs-lookup"><span data-stu-id="a8054-143">*string-path*</span></span> |
| <span data-ttu-id="a8054-144">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="a8054-145">*percorso-stringa*</span><span class="sxs-lookup"><span data-stu-id="a8054-145">*string-path*</span></span> |
| <span data-ttu-id="a8054-146">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="a8054-147">*percorso-stringa*</span><span class="sxs-lookup"><span data-stu-id="a8054-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="a8054-148">Scrivi mappa perf</span><span class="sxs-lookup"><span data-stu-id="a8054-148">Write perf map</span></span>

- <span data-ttu-id="a8054-149">Abilita o disabilita la scrittura */tmp/perf-$pid.map* nei sistemi Linux.</span><span class="sxs-lookup"><span data-stu-id="a8054-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="a8054-150">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="a8054-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="a8054-151">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a8054-151">Setting name</span></span> | <span data-ttu-id="a8054-152">Valori</span><span class="sxs-lookup"><span data-stu-id="a8054-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a8054-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a8054-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="a8054-154">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-154">N/A</span></span> | <span data-ttu-id="a8054-155">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-155">N/A</span></span> |
| <span data-ttu-id="a8054-156">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="a8054-157">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-157">`0` - disabled</span></span><br/><span data-ttu-id="a8054-158">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="a8054-159">Marcatori di log perf</span><span class="sxs-lookup"><span data-stu-id="a8054-159">Perf log markers</span></span>

- <span data-ttu-id="a8054-160">Quando `COMPlus_PerfMapEnabled` è `1`impostato su , abilita o disabilita l'accettato e l'ignorato del segnale specificato come marcatore nei registri perf.</span><span class="sxs-lookup"><span data-stu-id="a8054-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="a8054-161">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="a8054-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="a8054-162">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="a8054-162">Setting name</span></span> | <span data-ttu-id="a8054-163">Valori</span><span class="sxs-lookup"><span data-stu-id="a8054-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a8054-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a8054-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="a8054-165">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-165">N/A</span></span> | <span data-ttu-id="a8054-166">N/D</span><span class="sxs-lookup"><span data-stu-id="a8054-166">N/A</span></span> |
| <span data-ttu-id="a8054-167">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="a8054-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="a8054-168">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-168">`0` - disabled</span></span><br/><span data-ttu-id="a8054-169">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="a8054-169">`1` - enabled</span></span> |
