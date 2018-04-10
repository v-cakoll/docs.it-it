---
title: Schema delle impostazioni di traccia e debug
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6d9e5ca97e4d5940dd9de3f3ffbd4db4183196c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="a3fd7-102">Schema delle impostazioni di traccia e debug</span><span class="sxs-lookup"><span data-stu-id="a3fd7-102">Trace and Debug Settings Schema</span></span>
<span data-ttu-id="a3fd7-103">Le impostazioni di traccia e debug specificano i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-103">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="a3fd7-104">La tabella seguente descrive la funzione di ogni elemento delle impostazioni di traccia e debug.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-104">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="a3fd7-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3fd7-105">Element</span></span>|<span data-ttu-id="a3fd7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3fd7-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3fd7-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a3fd7-107">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="a3fd7-108">Aggiunge un listener alla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-108">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="a3fd7-109">\<add></span><span class="sxs-lookup"><span data-stu-id="a3fd7-109">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="a3fd7-110">Aggiunge un listener alla raccolta `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-110">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="a3fd7-111">\<add></span><span class="sxs-lookup"><span data-stu-id="a3fd7-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|<span data-ttu-id="a3fd7-112">Aggiunge un listener alla raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-112">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="a3fd7-113">\<add></span><span class="sxs-lookup"><span data-stu-id="a3fd7-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="a3fd7-114">Specifica il livello in cui viene impostata un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-114">Specifies the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="a3fd7-115">\<assert></span><span class="sxs-lookup"><span data-stu-id="a3fd7-115">\<assert></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<span data-ttu-id="a3fd7-116">Specifica se visualizzare una finestra di messaggio quando si chiama il metodo <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Specifica anche il nome del file in cui scrivere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-116">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="a3fd7-117">\<clear></span><span class="sxs-lookup"><span data-stu-id="a3fd7-117">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="a3fd7-118">Cancella la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-118">Clears the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="a3fd7-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="a3fd7-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="a3fd7-120">Cancella la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="a3fd7-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="a3fd7-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="a3fd7-122">Aggiunge un filtro a un listener nella raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-122">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="a3fd7-123">\<filter></span><span class="sxs-lookup"><span data-stu-id="a3fd7-123">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="a3fd7-124">Aggiunge un filtro a un listener nella raccolta `Listeners` per la traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-124">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="a3fd7-125">\<filter></span><span class="sxs-lookup"><span data-stu-id="a3fd7-125">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="a3fd7-126">Aggiunge un filtro a un listener nella raccolta `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-126">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="a3fd7-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="a3fd7-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="a3fd7-128">Specifica i listener per la raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-128">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="a3fd7-129">\<listeners></span><span class="sxs-lookup"><span data-stu-id="a3fd7-129">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="a3fd7-130">Specifica i listener per la raccolta `Listeners` per una traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-130">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="a3fd7-131">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="a3fd7-131">\<performanceCounters></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|<span data-ttu-id="a3fd7-132">Specifica le dimensioni della memoria globale condivisa dai contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-132">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="a3fd7-133">\<remove></span><span class="sxs-lookup"><span data-stu-id="a3fd7-133">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="a3fd7-134">Rimuove un listener dalla raccolta `Listeners` per la traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-134">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="a3fd7-135">\<remove></span><span class="sxs-lookup"><span data-stu-id="a3fd7-135">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="a3fd7-136">Rimuove un listener dalla raccolta `Listeners` per un'origine di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-136">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="a3fd7-137">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="a3fd7-137">\<sharedListeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|<span data-ttu-id="a3fd7-138">Contiene i listener a cui può fare riferimento qualsiasi origine o elemento di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-138">Contains listeners that any source or trace element can reference.</span></span>|  
|[<span data-ttu-id="a3fd7-139">\<sources></span><span class="sxs-lookup"><span data-stu-id="a3fd7-139">\<sources></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|<span data-ttu-id="a3fd7-140">Contiene le origini di traccia che avviano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-140">Contains trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="a3fd7-141">\<source></span><span class="sxs-lookup"><span data-stu-id="a3fd7-141">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="a3fd7-142">Specifica un'origine di traccia che avvia i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-142">Specifies a trace source that initiates tracing messages.</span></span>|  
|[<span data-ttu-id="a3fd7-143">\<switches></span><span class="sxs-lookup"><span data-stu-id="a3fd7-143">\<switches></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|<span data-ttu-id="a3fd7-144">Contiene le opzioni di traccia e il livello in cui vengono impostate le opzioni di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-144">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[<span data-ttu-id="a3fd7-145">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a3fd7-145">\<system.diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|<span data-ttu-id="a3fd7-146">Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-146">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="a3fd7-147">\<trace></span><span class="sxs-lookup"><span data-stu-id="a3fd7-147">\<trace></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|<span data-ttu-id="a3fd7-148">Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.</span><span class="sxs-lookup"><span data-stu-id="a3fd7-148">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3fd7-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3fd7-149">See Also</span></span>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.Debug>  
 [<span data-ttu-id="a3fd7-150">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a3fd7-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
