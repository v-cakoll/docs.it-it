---
title: Impostazioni di configurazione Threading
description: Informazioni sulle impostazioni della fase di esecuzione che configurano il threading per le app .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802764"
---
# <a name="run-time-configuration-options-for-threading"></a><span data-ttu-id="51246-103">Opzioni di configurazione in fase di esecuzione per il threading</span><span class="sxs-lookup"><span data-stu-id="51246-103">Run-time configuration options for threading</span></span>

## <a name="cpu-groups"></a><span data-ttu-id="51246-104">Gruppi CPU</span><span class="sxs-lookup"><span data-stu-id="51246-104">CPU groups</span></span>

- <span data-ttu-id="51246-105">Configura se i thread vengono distribuiti automaticamente tra gruppi di CPU.</span><span class="sxs-lookup"><span data-stu-id="51246-105">Configures whether threads are automatically distributed across CPU groups.</span></span>
- <span data-ttu-id="51246-106">Impostazione predefinita: disabilitato (`0`).</span><span class="sxs-lookup"><span data-stu-id="51246-106">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="51246-107">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="51246-107">Setting name</span></span> | <span data-ttu-id="51246-108">Valori</span><span class="sxs-lookup"><span data-stu-id="51246-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="51246-109">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="51246-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="51246-110">N/D</span><span class="sxs-lookup"><span data-stu-id="51246-110">N/A</span></span> | <span data-ttu-id="51246-111">N/D</span><span class="sxs-lookup"><span data-stu-id="51246-111">N/A</span></span> |
| <span data-ttu-id="51246-112">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="51246-112">**Environment variable**</span></span> | `COMPlus_Thread_UseAllCpuGroups` | <span data-ttu-id="51246-113">`0` disabilitato</span><span class="sxs-lookup"><span data-stu-id="51246-113">`0` - disabled</span></span><br/><span data-ttu-id="51246-114">Abilitazione di `1`</span><span class="sxs-lookup"><span data-stu-id="51246-114">`1` - enabled</span></span> |

## <a name="minimum-threads"></a><span data-ttu-id="51246-115">Numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="51246-115">Minimum threads</span></span>

- <span data-ttu-id="51246-116">Specifica il numero minimo di thread per il ThreadPool del ruolo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="51246-116">Specifies the minimum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="51246-117">Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51246-117">Corresponds to the <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="51246-118">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="51246-118">Setting name</span></span> | <span data-ttu-id="51246-119">Valori</span><span class="sxs-lookup"><span data-stu-id="51246-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="51246-120">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="51246-120">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MinThreads` | <span data-ttu-id="51246-121">Intero che rappresenta il numero minimo di thread</span><span class="sxs-lookup"><span data-stu-id="51246-121">An integer that represents the minimum number of threads</span></span> |
| <span data-ttu-id="51246-122">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="51246-122">**Environment variable**</span></span> | <span data-ttu-id="51246-123">N/D</span><span class="sxs-lookup"><span data-stu-id="51246-123">N/A</span></span> | <span data-ttu-id="51246-124">N/D</span><span class="sxs-lookup"><span data-stu-id="51246-124">N/A</span></span> |

## <a name="maximum-threads"></a><span data-ttu-id="51246-125">Numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="51246-125">Maximum threads</span></span>

- <span data-ttu-id="51246-126">Specifica il numero massimo di thread per il ThreadPool di lavoro.</span><span class="sxs-lookup"><span data-stu-id="51246-126">Specifies the maximum number of threads for the worker threadpool.</span></span>
- <span data-ttu-id="51246-127">Corrisponde al metodo <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51246-127">Corresponds to the <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="51246-128">Nome impostazione</span><span class="sxs-lookup"><span data-stu-id="51246-128">Setting name</span></span> | <span data-ttu-id="51246-129">Valori</span><span class="sxs-lookup"><span data-stu-id="51246-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="51246-130">**runtimeconfig. JSON**</span><span class="sxs-lookup"><span data-stu-id="51246-130">**runtimeconfig.json**</span></span> | `System.Threading.ThreadPool.MaxThreads` | <span data-ttu-id="51246-131">Intero che rappresenta il numero massimo di thread</span><span class="sxs-lookup"><span data-stu-id="51246-131">An integer that represents the maximum number of threads</span></span> |
| <span data-ttu-id="51246-132">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="51246-132">**Environment variable**</span></span> | <span data-ttu-id="51246-133">N/D</span><span class="sxs-lookup"><span data-stu-id="51246-133">N/A</span></span> | <span data-ttu-id="51246-134">N/D</span><span class="sxs-lookup"><span data-stu-id="51246-134">N/A</span></span> |
