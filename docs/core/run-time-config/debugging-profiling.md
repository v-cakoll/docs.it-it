---
title: Debug delle impostazioni di configurazione della profilatura
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il debug e la profilatura per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761993"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="f1a9b-103">Opzioni di configurazione in fase di esecuzione per il debug e la profilatura</span><span class="sxs-lookup"><span data-stu-id="f1a9b-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="f1a9b-104">Abilitare la diagnostica</span><span class="sxs-lookup"><span data-stu-id="f1a9b-104">Enable diagnostics</span></span>

- <span data-ttu-id="f1a9b-105">Configura se il debugger, il profiler e la diagnostica EventPipe sono abilitati o disabilitati.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="f1a9b-106">Se si omette questa impostazione, la diagnostica è abilitata.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-106">If you omit this setting, diagnostics are enabled.</span></span> <span data-ttu-id="f1a9b-107">Equivale a impostare il valore su `1` .</span><span class="sxs-lookup"><span data-stu-id="f1a9b-107">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="f1a9b-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1a9b-108">Setting name</span></span> | <span data-ttu-id="f1a9b-109">Valori</span><span class="sxs-lookup"><span data-stu-id="f1a9b-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1a9b-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1a9b-111">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-111">N/A</span></span> | <span data-ttu-id="f1a9b-112">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-112">N/A</span></span> |
| <span data-ttu-id="f1a9b-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-113">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="f1a9b-114">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-114">`1` - enabled</span></span><br/><span data-ttu-id="f1a9b-115">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-115">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="f1a9b-116">Abilita profilatura</span><span class="sxs-lookup"><span data-stu-id="f1a9b-116">Enable profiling</span></span>

- <span data-ttu-id="f1a9b-117">Configura se la profilatura è abilitata per il processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-117">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="f1a9b-118">Se si omette questa impostazione, la profilatura è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-118">If you omit this setting, profiling is disabled.</span></span> <span data-ttu-id="f1a9b-119">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="f1a9b-119">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="f1a9b-120">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1a9b-120">Setting name</span></span> | <span data-ttu-id="f1a9b-121">Valori</span><span class="sxs-lookup"><span data-stu-id="f1a9b-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1a9b-122">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-122">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1a9b-123">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-123">N/A</span></span> | <span data-ttu-id="f1a9b-124">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-124">N/A</span></span> |
| <span data-ttu-id="f1a9b-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-125">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="f1a9b-126">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-126">`0` - disabled</span></span><br/><span data-ttu-id="f1a9b-127">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-127">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="f1a9b-128">GUID Profiler</span><span class="sxs-lookup"><span data-stu-id="f1a9b-128">Profiler GUID</span></span>

- <span data-ttu-id="f1a9b-129">Specifica il GUID del profiler da caricare nel processo attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-129">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="f1a9b-130">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1a9b-130">Setting name</span></span> | <span data-ttu-id="f1a9b-131">Valori</span><span class="sxs-lookup"><span data-stu-id="f1a9b-131">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1a9b-132">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-132">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1a9b-133">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-133">N/A</span></span> | <span data-ttu-id="f1a9b-134">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-134">N/A</span></span> |
| <span data-ttu-id="f1a9b-135">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-135">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="f1a9b-136">*stringa-GUID*</span><span class="sxs-lookup"><span data-stu-id="f1a9b-136">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="f1a9b-137">Percorso Profiler</span><span class="sxs-lookup"><span data-stu-id="f1a9b-137">Profiler location</span></span>

- <span data-ttu-id="f1a9b-138">Specifica il percorso della DLL del profiler da caricare nel processo attualmente in esecuzione (o processo a 32 bit o a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="f1a9b-138">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="f1a9b-139">Se è impostata più di una variabile, le variabili specifiche di bit hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-139">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="f1a9b-140">Specificano il bit del profiler da caricare.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-140">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="f1a9b-141">Per ulteriori informazioni, vedere [ricerca della libreria del profiler](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span><span class="sxs-lookup"><span data-stu-id="f1a9b-141">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="f1a9b-142">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1a9b-142">Setting name</span></span> | <span data-ttu-id="f1a9b-143">Valori</span><span class="sxs-lookup"><span data-stu-id="f1a9b-143">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1a9b-144">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="f1a9b-145">*percorso stringa*</span><span class="sxs-lookup"><span data-stu-id="f1a9b-145">*string-path*</span></span> |
| <span data-ttu-id="f1a9b-146">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="f1a9b-147">*percorso stringa*</span><span class="sxs-lookup"><span data-stu-id="f1a9b-147">*string-path*</span></span> |
| <span data-ttu-id="f1a9b-148">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-148">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="f1a9b-149">*percorso stringa*</span><span class="sxs-lookup"><span data-stu-id="f1a9b-149">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="f1a9b-150">Mappa delle prestazioni di scrittura</span><span class="sxs-lookup"><span data-stu-id="f1a9b-150">Write perf map</span></span>

- <span data-ttu-id="f1a9b-151">Abilita o Disabilita la scrittura */tmp/perf-$PID. map* nei sistemi Linux.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-151">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="f1a9b-152">Se si omette questa impostazione, la scrittura della mappa delle prestazioni è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-152">If you omit this setting, writing the perf map is disabled.</span></span> <span data-ttu-id="f1a9b-153">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="f1a9b-153">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="f1a9b-154">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1a9b-154">Setting name</span></span> | <span data-ttu-id="f1a9b-155">Valori</span><span class="sxs-lookup"><span data-stu-id="f1a9b-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1a9b-156">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-156">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1a9b-157">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-157">N/A</span></span> | <span data-ttu-id="f1a9b-158">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-158">N/A</span></span> |
| <span data-ttu-id="f1a9b-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-159">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="f1a9b-160">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-160">`0` - disabled</span></span><br/><span data-ttu-id="f1a9b-161">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-161">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="f1a9b-162">Marcatori log prestazioni</span><span class="sxs-lookup"><span data-stu-id="f1a9b-162">Perf log markers</span></span>

- <span data-ttu-id="f1a9b-163">Abilita o Disabilita il segnale specificato da accettare e ignorare come marcatore nei log delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-163">Enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="f1a9b-164">Se si omette questa impostazione, il segnale specificato non verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="f1a9b-164">If you omit this setting, the specified signal is not ignored.</span></span> <span data-ttu-id="f1a9b-165">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="f1a9b-165">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="f1a9b-166">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="f1a9b-166">Setting name</span></span> | <span data-ttu-id="f1a9b-167">Valori</span><span class="sxs-lookup"><span data-stu-id="f1a9b-167">Values</span></span> |
| - | - | - |
| <span data-ttu-id="f1a9b-168">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-168">**runtimeconfig.json**</span></span> | <span data-ttu-id="f1a9b-169">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-169">N/A</span></span> | <span data-ttu-id="f1a9b-170">N/D</span><span class="sxs-lookup"><span data-stu-id="f1a9b-170">N/A</span></span> |
| <span data-ttu-id="f1a9b-171">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="f1a9b-171">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="f1a9b-172">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-172">`0` - disabled</span></span><br/><span data-ttu-id="f1a9b-173">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="f1a9b-173">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="f1a9b-174">Questa impostazione viene ignorata se [COMPlus_PerfMapEnabled](#write-perf-map) viene omesso o impostato su `0` (ovvero disabilitato).</span><span class="sxs-lookup"><span data-stu-id="f1a9b-174">This setting is ignored if [COMPlus_PerfMapEnabled](#write-perf-map) is omitted or set to `0` (that is, disabled).</span></span>
