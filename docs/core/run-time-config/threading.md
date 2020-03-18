---
title: Impostazioni di configurazione del threading
description: Informazioni sulle impostazioni di runtime che configurano il threading per le app .NET Core.Learn about run-time settings that configure threading for .NET Core apps.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 68b8e93ca6ec3f708a7a627307655ada1955500a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789859"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="ba4f1-103">Opzioni di configurazione in fase di esecuzione per il threadingRun-time configuration options for threading</span><span class="sxs-lookup"><span data-stu-id="ba4f1-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="ba4f1-104">Gruppi CPU</span><span class="sxs-lookup"><span data-stu-id="ba4f1-104">CPU groups</span></span>

- <span data-ttu-id="ba4f1-105">Configura se i thread vengono distribuiti automaticamente tra i gruppi della CPU.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="ba4f1-106">Impostazione predefinita: Disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="ba4f1-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="ba4f1-107">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="ba4f1-107">Setting name</span></span> | <span data-ttu-id="ba4f1-108">Valori</span><span class="sxs-lookup"><span data-stu-id="ba4f1-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ba4f1-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="ba4f1-110">N/D</span><span class="sxs-lookup"><span data-stu-id="ba4f1-110">N/A</span></span> | <span data-ttu-id="ba4f1-111">N/D</span><span class="sxs-lookup"><span data-stu-id="ba4f1-111">N/A</span></span> |
| <span data-ttu-id="ba4f1-112">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="ba4f1-113">`0`- disabilitato</span><span class="sxs-lookup"><span data-stu-id="ba4f1-113">`0` - disabled</span></span><br/><span data-ttu-id="ba4f1-114">`1`- abilitato</span><span class="sxs-lookup"><span data-stu-id="ba4f1-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="ba4f1-115">Numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="ba4f1-115">Minimum threads</span></span>

- <span data-ttu-id="ba4f1-116">Specifica il numero minimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-116">Specifies the minimum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="ba4f1-117">Corrisponde al <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="ba4f1-118">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="ba4f1-118">Setting name</span></span> | <span data-ttu-id="ba4f1-119">Valori</span><span class="sxs-lookup"><span data-stu-id="ba4f1-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ba4f1-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="ba4f1-121">Un numero intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="ba4f1-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="ba4f1-122">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="ba4f1-123">Un numero intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="ba4f1-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="ba4f1-124">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-124">**Environment variable**</span></span> | <span data-ttu-id="ba4f1-125">N/D</span><span class="sxs-lookup"><span data-stu-id="ba4f1-125">N/A</span></span> | <span data-ttu-id="ba4f1-126">N/D</span><span class="sxs-lookup"><span data-stu-id="ba4f1-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="ba4f1-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="ba4f1-127">Examples</span></span>

<span data-ttu-id="ba4f1-128">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="ba4f1-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="ba4f1-129">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="ba4f1-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="ba4f1-130">Numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="ba4f1-130">Maximum threads</span></span>

- <span data-ttu-id="ba4f1-131">Specifica il numero massimo di thread per il pool di thread di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-131">Specifies the maximum number of threads for the worker thread pool.</span></span>
- <span data-ttu-id="ba4f1-132">Corrisponde al <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="ba4f1-133">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="ba4f1-133">Setting name</span></span> | <span data-ttu-id="ba4f1-134">Valori</span><span class="sxs-lookup"><span data-stu-id="ba4f1-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ba4f1-135">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="ba4f1-136">Un numero intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="ba4f1-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="ba4f1-137">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="ba4f1-138">Un numero intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="ba4f1-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="ba4f1-139">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="ba4f1-139">**Environment variable**</span></span> | <span data-ttu-id="ba4f1-140">N/D</span><span class="sxs-lookup"><span data-stu-id="ba4f1-140">N/A</span></span> | <span data-ttu-id="ba4f1-141">N/D</span><span class="sxs-lookup"><span data-stu-id="ba4f1-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="ba4f1-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="ba4f1-142">Examples</span></span>

<span data-ttu-id="ba4f1-143">*runtimeconfig.json:*</span><span class="sxs-lookup"><span data-stu-id="ba4f1-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="ba4f1-144">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="ba4f1-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
