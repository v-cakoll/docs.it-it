---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789859"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="dfaac-103">Opzioni di configurazione in fase di esecuzione per il threading</span><span class="sxs-lookup"><span data-stu-id="dfaac-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="dfaac-104">Gruppi CPU</span><span class="sxs-lookup"><span data-stu-id="dfaac-104">CPU groups</span></span>

- <span data-ttu-id="dfaac-105">Configura se i thread vengono distribuiti automaticamente tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="dfaac-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="dfaac-106">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="dfaac-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="dfaac-107">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="dfaac-107">Setting name</span></span> | <span data-ttu-id="dfaac-108">Valori</span><span class="sxs-lookup"><span data-stu-id="dfaac-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dfaac-109">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="dfaac-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="dfaac-110">N/D</span><span class="sxs-lookup"><span data-stu-id="dfaac-110">N/A</span></span> | <span data-ttu-id="dfaac-111">N/D</span><span class="sxs-lookup"><span data-stu-id="dfaac-111">N/A</span></span> |
| <span data-ttu-id="dfaac-112">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="dfaac-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="dfaac-113">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="dfaac-113">`0` - disabled</span></span><br/><span data-ttu-id="dfaac-114">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="dfaac-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="dfaac-115">Numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="dfaac-115">Minimum threads</span></span>

- <span data-ttu-id="dfaac-116">Specifica il numero minimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dfaac-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="dfaac-117">Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dfaac-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="dfaac-118">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="dfaac-118">Setting name</span></span> | <span data-ttu-id="dfaac-119">Valori</span><span class="sxs-lookup"><span data-stu-id="dfaac-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dfaac-120">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="dfaac-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="dfaac-121">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="dfaac-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="dfaac-122">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="dfaac-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="dfaac-123">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="dfaac-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="dfaac-124">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="dfaac-124">**Environment variable**</span></span> | <span data-ttu-id="dfaac-125">N/D</span><span class="sxs-lookup"><span data-stu-id="dfaac-125">N/A</span></span> | <span data-ttu-id="dfaac-126">N/D</span><span class="sxs-lookup"><span data-stu-id="dfaac-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="dfaac-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="dfaac-127">Examples</span></span>

<span data-ttu-id="dfaac-128">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="dfaac-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="dfaac-129">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="dfaac-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="dfaac-130">Numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="dfaac-130">Maximum threads</span></span>

- <span data-ttu-id="dfaac-131">Specifica il numero massimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="dfaac-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="dfaac-132">Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dfaac-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="dfaac-133">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="dfaac-133">Setting name</span></span> | <span data-ttu-id="dfaac-134">Valori</span><span class="sxs-lookup"><span data-stu-id="dfaac-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="dfaac-135">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="dfaac-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="dfaac-136">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="dfaac-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="dfaac-137">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="dfaac-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="dfaac-138">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="dfaac-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="dfaac-139">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="dfaac-139">**Environment variable**</span></span> | <span data-ttu-id="dfaac-140">N/D</span><span class="sxs-lookup"><span data-stu-id="dfaac-140">N/A</span></span> | <span data-ttu-id="dfaac-141">N/D</span><span class="sxs-lookup"><span data-stu-id="dfaac-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="dfaac-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="dfaac-142">Examples</span></span>

<span data-ttu-id="dfaac-143">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="dfaac-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="dfaac-144">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="dfaac-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
