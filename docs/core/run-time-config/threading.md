---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ed7688d4d8f7178440fe59afc6e2f5e0a11b2a5c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733427"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="3d527-103">Opzioni di configurazione in fase di esecuzione per il threading</span><span class="sxs-lookup"><span data-stu-id="3d527-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="3d527-104">Gruppi CPU</span><span class="sxs-lookup"><span data-stu-id="3d527-104">CPU groups</span></span>

- <span data-ttu-id="3d527-105">Configura se i thread vengono distribuiti automaticamente tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="3d527-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="3d527-106">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="3d527-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="3d527-107">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="3d527-107">Setting name</span></span> | <span data-ttu-id="3d527-108">Valori</span><span class="sxs-lookup"><span data-stu-id="3d527-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3d527-109">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="3d527-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="3d527-110">N/D</span><span class="sxs-lookup"><span data-stu-id="3d527-110">N/A</span></span> | <span data-ttu-id="3d527-111">N/D</span><span class="sxs-lookup"><span data-stu-id="3d527-111">N/A</span></span> |
| <span data-ttu-id="3d527-112">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="3d527-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="3d527-113">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="3d527-113">`0` - disabled</span></span><br/><span data-ttu-id="3d527-114">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="3d527-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="3d527-115">Numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="3d527-115">Minimum threads</span></span>

- <span data-ttu-id="3d527-116">Specifica il numero minimo di thread per il ThreadPool del ruolo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3d527-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="3d527-117">Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3d527-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="3d527-118">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="3d527-118">Setting name</span></span> | <span data-ttu-id="3d527-119">Valori</span><span class="sxs-lookup"><span data-stu-id="3d527-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3d527-120">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="3d527-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="3d527-121">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="3d527-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="3d527-122">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="3d527-122">**MSBuild property**</span></span> | `ThreadPoolMinThreads` | <span data-ttu-id="3d527-123">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="3d527-123">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="3d527-124">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="3d527-124">**Environment variable**</span></span> | <span data-ttu-id="3d527-125">N/D</span><span class="sxs-lookup"><span data-stu-id="3d527-125">N/A</span></span> | <span data-ttu-id="3d527-126">N/D</span><span class="sxs-lookup"><span data-stu-id="3d527-126">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="3d527-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="3d527-127">Examples</span></span>

<span data-ttu-id="3d527-128">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="3d527-128">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

<span data-ttu-id="3d527-129">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="3d527-129">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a><span data-ttu-id="3d527-130">Numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="3d527-130">Maximum threads</span></span>

- <span data-ttu-id="3d527-131">Specifica il numero massimo di thread per il ThreadPool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3d527-131">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="3d527-132">Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3d527-132">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="3d527-133">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="3d527-133">Setting name</span></span> | <span data-ttu-id="3d527-134">Valori</span><span class="sxs-lookup"><span data-stu-id="3d527-134">Values</span></span> |
| - | - | - |
| <span data-ttu-id="3d527-135">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="3d527-135">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="3d527-136">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="3d527-136">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="3d527-137">**MSBuild (proprietà)**</span><span class="sxs-lookup"><span data-stu-id="3d527-137">**MSBuild property**</span></span> | `ThreadPoolMaxThreads` | <span data-ttu-id="3d527-138">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="3d527-138">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="3d527-139">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="3d527-139">**Environment variable**</span></span> | <span data-ttu-id="3d527-140">N/D</span><span class="sxs-lookup"><span data-stu-id="3d527-140">N/A</span></span> | <span data-ttu-id="3d527-141">N/D</span><span class="sxs-lookup"><span data-stu-id="3d527-141">N/A</span></span> |

### <a name="examples"></a><span data-ttu-id="3d527-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="3d527-142">Examples</span></span>

<span data-ttu-id="3d527-143">file *runtimeconfig. JSON* :</span><span class="sxs-lookup"><span data-stu-id="3d527-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

<span data-ttu-id="3d527-144">File di progetto:</span><span class="sxs-lookup"><span data-stu-id="3d527-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
