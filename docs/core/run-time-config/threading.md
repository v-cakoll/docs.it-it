---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 1c7c16993a07ef95223481791153b75ab2f61533
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761928"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="e2026-103">Opzioni di configurazione in fase di esecuzione per il threading</span><span class="sxs-lookup"><span data-stu-id="e2026-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="e2026-104">Gruppi CPU</span><span class="sxs-lookup"><span data-stu-id="e2026-104">CPU groups</span></span>

- <span data-ttu-id="e2026-105">Configura se i thread vengono distribuiti automaticamente tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e2026-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="e2026-106">Se si omette questa impostazione, i thread non verranno distribuiti tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="e2026-106">If you omit this setting, threads are not distributed across CPU groups.</span></span> <span data-ttu-id="e2026-107">Equivale a impostare il valore su `0` .</span><span class="sxs-lookup"><span data-stu-id="e2026-107">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="e2026-108">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e2026-108">Setting name</span></span> | <span data-ttu-id="e2026-109">Valori</span><span class="sxs-lookup"><span data-stu-id="e2026-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e2026-110">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e2026-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="e2026-111">N/D</span><span class="sxs-lookup"><span data-stu-id="e2026-111">N/A</span></span> | <span data-ttu-id="e2026-112">N/D</span><span class="sxs-lookup"><span data-stu-id="e2026-112">N/A</span></span> |
| <span data-ttu-id="e2026-113">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e2026-113">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="e2026-114">`0`-disabilitato</span><span class="sxs-lookup"><span data-stu-id="e2026-114">`0` - disabled</span></span><br/><span data-ttu-id="e2026-115">`1`-abilitato</span><span class="sxs-lookup"><span data-stu-id="e2026-115">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="e2026-116">Numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="e2026-116">Minimum threads</span></span>

- <span data-ttu-id="e2026-117">Specifica il numero minimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e2026-117">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="e2026-118">Corrisponde al <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="e2026-118">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="e2026-119">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e2026-119">Setting name</span></span> | <span data-ttu-id="e2026-120">Valori</span><span class="sxs-lookup"><span data-stu-id="e2026-120">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e2026-121">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e2026-121">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="e2026-122">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="e2026-122">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="e2026-123">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="e2026-123">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="e2026-124">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="e2026-124">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="e2026-125">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e2026-125">**Environment variable**</span></span> | <span data-ttu-id="e2026-126">N/D</span><span class="sxs-lookup"><span data-stu-id="e2026-126">N/A</span></span> | <span data-ttu-id="e2026-127">N/D</span><span class="sxs-lookup"><span data-stu-id="e2026-127">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="e2026-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="e2026-128">Examples</span></span>

<span data-ttu-id="e2026-129">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="e2026-129">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="e2026-130">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="e2026-130">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="e2026-131">Numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="e2026-131">Maximum threads</span></span>

- <span data-ttu-id="e2026-132">Specifica il numero massimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e2026-132">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="e2026-133">Corrisponde al <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="e2026-133">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="e2026-134">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="e2026-134">Setting name</span></span> | <span data-ttu-id="e2026-135">Valori</span><span class="sxs-lookup"><span data-stu-id="e2026-135">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e2026-136">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="e2026-136">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="e2026-137">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="e2026-137">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="e2026-138">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="e2026-138">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="e2026-139">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="e2026-139">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="e2026-140">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="e2026-140">**Environment variable**</span></span> | <span data-ttu-id="e2026-141">N/D</span><span class="sxs-lookup"><span data-stu-id="e2026-141">N/A</span></span> | <span data-ttu-id="e2026-142">N/D</span><span class="sxs-lookup"><span data-stu-id="e2026-142">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="e2026-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="e2026-143">Examples</span></span>

<span data-ttu-id="e2026-144">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="e2026-144">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="e2026-145">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="e2026-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
