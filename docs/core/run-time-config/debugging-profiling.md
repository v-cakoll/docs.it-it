---
title: Debug delle impostazioni di configurazione della profilatura
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il debug e la profilatura per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802799"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="68d08-103">Opzioni di configurazione in fase di esecuzione per il debug e la profilatura</span><span class="sxs-lookup"><span data-stu-id="68d08-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="68d08-104">Abilitare la diagnostica</span><span class="sxs-lookup"><span data-stu-id="68d08-104">Enable diagnostics</span></span>

- <span data-ttu-id="68d08-105">Configura se il debugger, il profiler e la diagnostica EventPipe sono abilitati o disabilitati.</span><span class="sxs-lookup"><span data-stu-id="68d08-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="68d08-106">Impostazione predefinita: abilitata (`1`).</span><span class="sxs-lookup"><span data-stu-id="68d08-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="68d08-107">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="68d08-107">Setting name</span></span> | <span data-ttu-id="68d08-108">Valori</span><span class="sxs-lookup"><span data-stu-id="68d08-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="68d08-109">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="68d08-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="68d08-110">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-110">N/A</span></span> | <span data-ttu-id="68d08-111">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-111">N/A</span></span> |
| <span data-ttu-id="68d08-112">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="68d08-113">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="68d08-113">`1` - enabled</span></span><br/><span data-ttu-id="68d08-114">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="68d08-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="68d08-115">Abilita profilatura</span><span class="sxs-lookup"><span data-stu-id="68d08-115">Enable profiling</span></span>

- <span data-ttu-id="68d08-116">Configura se la profilatura è abilitata per il processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68d08-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="68d08-117">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="68d08-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="68d08-118">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="68d08-118">Setting name</span></span> | <span data-ttu-id="68d08-119">Valori</span><span class="sxs-lookup"><span data-stu-id="68d08-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="68d08-120">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="68d08-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="68d08-121">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-121">N/A</span></span> | <span data-ttu-id="68d08-122">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-122">N/A</span></span> |
| <span data-ttu-id="68d08-123">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="68d08-124">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="68d08-124">`0` - disabled</span></span><br/><span data-ttu-id="68d08-125">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="68d08-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="68d08-126">GUID Profiler</span><span class="sxs-lookup"><span data-stu-id="68d08-126">Profiler GUID</span></span>

- <span data-ttu-id="68d08-127">Specifica il GUID del profiler da caricare nel processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68d08-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="68d08-128">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="68d08-128">Setting name</span></span> | <span data-ttu-id="68d08-129">Valori</span><span class="sxs-lookup"><span data-stu-id="68d08-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="68d08-130">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="68d08-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="68d08-131">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-131">N/A</span></span> | <span data-ttu-id="68d08-132">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-132">N/A</span></span> |
| <span data-ttu-id="68d08-133">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="68d08-134">*stringa-GUID*</span><span class="sxs-lookup"><span data-stu-id="68d08-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="68d08-135">Percorso Profiler</span><span class="sxs-lookup"><span data-stu-id="68d08-135">Profiler location</span></span>

- <span data-ttu-id="68d08-136">Specifica il percorso della DLL del profiler da caricare nel processo attualmente in esecuzione (o processo a 32 bit o a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="68d08-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="68d08-137">Se è impostata più di una variabile, le variabili specifiche di bit hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="68d08-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="68d08-138">Specificano il bit del profiler da caricare.</span><span class="sxs-lookup"><span data-stu-id="68d08-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="68d08-139">Per ulteriori informazioni, vedere [ricerca della libreria del profiler](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="68d08-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="68d08-140">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="68d08-140">Setting name</span></span> | <span data-ttu-id="68d08-141">Valori</span><span class="sxs-lookup"><span data-stu-id="68d08-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="68d08-142">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="68d08-143">*percorso stringa*</span><span class="sxs-lookup"><span data-stu-id="68d08-143">*string-path*</span></span> |
| <span data-ttu-id="68d08-144">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="68d08-145">*percorso stringa*</span><span class="sxs-lookup"><span data-stu-id="68d08-145">*string-path*</span></span> |
| <span data-ttu-id="68d08-146">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="68d08-147">*percorso stringa*</span><span class="sxs-lookup"><span data-stu-id="68d08-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="68d08-148">Mappa delle prestazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="68d08-148">Write perf map</span></span>

- <span data-ttu-id="68d08-149">Abilita o Disabilita la scrittura */tmp/perf-$PID. map* nei sistemi Linux.</span><span class="sxs-lookup"><span data-stu-id="68d08-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="68d08-150">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="68d08-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="68d08-151">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="68d08-151">Setting name</span></span> | <span data-ttu-id="68d08-152">Valori</span><span class="sxs-lookup"><span data-stu-id="68d08-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="68d08-153">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="68d08-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="68d08-154">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-154">N/A</span></span> | <span data-ttu-id="68d08-155">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-155">N/A</span></span> |
| <span data-ttu-id="68d08-156">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="68d08-157">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="68d08-157">`0` - disabled</span></span><br/><span data-ttu-id="68d08-158">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="68d08-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="68d08-159">Marcatori log prestazioni</span><span class="sxs-lookup"><span data-stu-id="68d08-159">Perf log markers</span></span>

- <span data-ttu-id="68d08-160">Quando `COMPlus_PerfMapEnabled` è impostato su `1`, Abilita o Disabilita il segnale specificato da accettare e ignorare come marcatore nei log delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="68d08-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="68d08-161">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="68d08-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="68d08-162">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="68d08-162">Setting name</span></span> | <span data-ttu-id="68d08-163">Valori</span><span class="sxs-lookup"><span data-stu-id="68d08-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="68d08-164">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="68d08-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="68d08-165">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-165">N/A</span></span> | <span data-ttu-id="68d08-166">N/D</span><span class="sxs-lookup"><span data-stu-id="68d08-166">N/A</span></span> |
| <span data-ttu-id="68d08-167">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="68d08-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="68d08-168">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="68d08-168">`0` - disabled</span></span><br/><span data-ttu-id="68d08-169">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="68d08-169">`1` - enabled</span></span> |
