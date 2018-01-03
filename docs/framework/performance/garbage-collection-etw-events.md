---
title: Eventi ETW di Garbage Collection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 133d48baa9613ea698b6d6a21f0dfe88a798859c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="1af2a-102">Eventi ETW di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="1af2a-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="1af2a-103">Questi eventi raccolgono informazioni relative alla Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="1af2a-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="1af2a-104">ai fini della diagnostica e del debug, tra cui stabilire quante volte è stato eseguito il processo di Garbage Collection, la quantità di memoria liberata durante la procedura di Garbage Collection e così via.</span><span class="sxs-lookup"><span data-stu-id="1af2a-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="1af2a-105">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="1af2a-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="1af2a-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="1af2a-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="1af2a-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="1af2a-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="1af2a-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="1af2a-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="1af2a-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="1af2a-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="1af2a-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="1af2a-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="1af2a-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="1af2a-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="1af2a-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="1af2a-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="1af2a-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="1af2a-121">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="1af2a-122">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1af2a-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="1af2a-123">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-123">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-124">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-127">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-128">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-128">Event</span></span>|<span data-ttu-id="1af2a-129">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-129">Event ID</span></span>|<span data-ttu-id="1af2a-130">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="1af2a-131">1</span><span class="sxs-lookup"><span data-stu-id="1af2a-131">1</span></span>|<span data-ttu-id="1af2a-132">È stata avviata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="1af2a-133">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-134">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-134">Field name</span></span>|<span data-ttu-id="1af2a-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-135">Data type</span></span>|<span data-ttu-id="1af2a-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-137">Conteggio</span><span class="sxs-lookup"><span data-stu-id="1af2a-137">Count</span></span>|<span data-ttu-id="1af2a-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-138">win:UInt32</span></span>|<span data-ttu-id="1af2a-139">L' *n*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="1af2a-140">Profondità</span><span class="sxs-lookup"><span data-stu-id="1af2a-140">Depth</span></span>|<span data-ttu-id="1af2a-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-141">win:UInt32</span></span>|<span data-ttu-id="1af2a-142">La generazione che viene raccolta.</span><span class="sxs-lookup"><span data-stu-id="1af2a-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="1af2a-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="1af2a-143">Reason</span></span>|<span data-ttu-id="1af2a-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-144">win:UInt32</span></span>|<span data-ttu-id="1af2a-145">Motivo per cui è stata attivata la Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="1af2a-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="1af2a-146">0x0 - Allocazione heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="1af2a-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="1af2a-147">0x1 - Indotto.</span><span class="sxs-lookup"><span data-stu-id="1af2a-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="1af2a-148">0x2 - Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="1af2a-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="1af2a-149">0x3 - Vuoto.</span><span class="sxs-lookup"><span data-stu-id="1af2a-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="1af2a-150">0x4 - Allocazione heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="1af2a-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="1af2a-151">0x5 - Spazio esaurito (per heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="1af2a-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="1af2a-152">0x6 - Spazio esaurito (per heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="1af2a-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="1af2a-153">0x7 - Indotto ma non forzato come blocco.</span><span class="sxs-lookup"><span data-stu-id="1af2a-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="1af2a-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="1af2a-154">Type</span></span>|<span data-ttu-id="1af2a-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-155">win:UInt32</span></span>|<span data-ttu-id="1af2a-156">0x0 - Un'operazione di Garbage Collection bloccante è stata eseguita all'esterno della procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="1af2a-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="1af2a-157">0x1 - Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="1af2a-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="1af2a-158">0x2 - Un'operazione di Garbage Collection bloccante è stata eseguita durante la procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="1af2a-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="1af2a-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-159">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-160">win:UInt16</span></span>|<span data-ttu-id="1af2a-161">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1af2a-162">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="1af2a-163">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="1af2a-164">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-165">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-165">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-166">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-169">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-170">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-170">Event</span></span>|<span data-ttu-id="1af2a-171">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-171">Event ID</span></span>|<span data-ttu-id="1af2a-172">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="1af2a-173">2</span><span class="sxs-lookup"><span data-stu-id="1af2a-173">2</span></span>|<span data-ttu-id="1af2a-174">È stata terminata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="1af2a-175">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-176">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-176">Field name</span></span>|<span data-ttu-id="1af2a-177">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-177">Data type</span></span>|<span data-ttu-id="1af2a-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-179">Conteggio</span><span class="sxs-lookup"><span data-stu-id="1af2a-179">Count</span></span>|<span data-ttu-id="1af2a-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-180">win:UInt32</span></span>|<span data-ttu-id="1af2a-181">L' *n*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="1af2a-182">Profondità</span><span class="sxs-lookup"><span data-stu-id="1af2a-182">Depth</span></span>|<span data-ttu-id="1af2a-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-183">win:UInt32</span></span>|<span data-ttu-id="1af2a-184">La generazione che è stata raccolta.</span><span class="sxs-lookup"><span data-stu-id="1af2a-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="1af2a-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-185">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-186">win:UInt16</span></span>|<span data-ttu-id="1af2a-187">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1af2a-188">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="1af2a-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="1af2a-190">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-191">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-191">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-192">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-195">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-196">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-196">Event</span></span>|<span data-ttu-id="1af2a-197">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-197">Event ID</span></span>|<span data-ttu-id="1af2a-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="1af2a-199">4</span><span class="sxs-lookup"><span data-stu-id="1af2a-199">4</span></span>|<span data-ttu-id="1af2a-200">Mostra le statistiche heap alla fine di ogni Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="1af2a-201">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-202">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-202">Field name</span></span>|<span data-ttu-id="1af2a-203">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-203">Data type</span></span>|<span data-ttu-id="1af2a-204">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="1af2a-205">GenerationSize0</span></span>|<span data-ttu-id="1af2a-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-206">win:UInt64</span></span>|<span data-ttu-id="1af2a-207">Dimensione, in byte, della memoria della generazione 0.</span><span class="sxs-lookup"><span data-stu-id="1af2a-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="1af2a-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="1af2a-208">TotalPromotedSize0</span></span>|<span data-ttu-id="1af2a-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-209">win:UInt64</span></span>|<span data-ttu-id="1af2a-210">Numero di byte promossi dalla generazione 0 alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="1af2a-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="1af2a-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="1af2a-211">GenerationSize1</span></span>|<span data-ttu-id="1af2a-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-212">win:UInt64</span></span>|<span data-ttu-id="1af2a-213">Dimensione, in byte, della memoria di generazione 1.</span><span class="sxs-lookup"><span data-stu-id="1af2a-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="1af2a-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="1af2a-214">TotalPromotedSize1</span></span>|<span data-ttu-id="1af2a-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-215">win:UInt64</span></span>|<span data-ttu-id="1af2a-216">Numero di byte promossi dalla generazione 1 alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="1af2a-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="1af2a-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="1af2a-217">GenerationSize2</span></span>|<span data-ttu-id="1af2a-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-218">win:UInt64</span></span>|<span data-ttu-id="1af2a-219">Dimensione, in byte, della memoria della generazione 2.</span><span class="sxs-lookup"><span data-stu-id="1af2a-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="1af2a-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="1af2a-220">TotalPromotedSize2</span></span>|<span data-ttu-id="1af2a-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-221">win:UInt64</span></span>|<span data-ttu-id="1af2a-222">Numero di byte rimasti nella generazione 2 dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="1af2a-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="1af2a-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="1af2a-223">GenerationSize3</span></span>|<span data-ttu-id="1af2a-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-224">win:UInt64</span></span>|<span data-ttu-id="1af2a-225">Dimensione, in byte, dell'heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="1af2a-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="1af2a-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="1af2a-226">TotalPromotedSize3</span></span>|<span data-ttu-id="1af2a-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-227">win:UInt64</span></span>|<span data-ttu-id="1af2a-228">Numero di byte rimasti nell'heap oggetto grande dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="1af2a-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="1af2a-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="1af2a-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="1af2a-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-230">win:UInt64</span></span>|<span data-ttu-id="1af2a-231">Dimensione totale, in byte, degli oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="1af2a-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="1af2a-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="1af2a-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="1af2a-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-233">win:UInt64</span></span>|<span data-ttu-id="1af2a-234">Numero di oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="1af2a-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="1af2a-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="1af2a-235">PinnedObjectCount</span></span>|<span data-ttu-id="1af2a-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-236">win:UInt32</span></span>|<span data-ttu-id="1af2a-237">Numero di oggetti bloccati (fissi).</span><span class="sxs-lookup"><span data-stu-id="1af2a-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="1af2a-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="1af2a-238">SinkBlockCount</span></span>|<span data-ttu-id="1af2a-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-239">win:UInt32</span></span>|<span data-ttu-id="1af2a-240">Numero di blocchi di sincronizzazione in uso.</span><span class="sxs-lookup"><span data-stu-id="1af2a-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="1af2a-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="1af2a-241">GCHandleCount</span></span>|<span data-ttu-id="1af2a-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-242">win:UInt32</span></span>|<span data-ttu-id="1af2a-243">Numero di handle di Garbage Collection in uso.</span><span class="sxs-lookup"><span data-stu-id="1af2a-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="1af2a-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-244">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-245">win:UInt16</span></span>|<span data-ttu-id="1af2a-246">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1af2a-247">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="1af2a-248">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="1af2a-249">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-250">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-250">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-251">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-254">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-255">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-255">Event</span></span>|<span data-ttu-id="1af2a-256">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-256">Event ID</span></span>|<span data-ttu-id="1af2a-257">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="1af2a-258">5</span><span class="sxs-lookup"><span data-stu-id="1af2a-258">5</span></span>|<span data-ttu-id="1af2a-259">È stato creato un nuovo segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="1af2a-260">Inoltre, quando la traccia è attivata su un processo già in esecuzione, questo evento viene generato per ogni segmento esistente.</span><span class="sxs-lookup"><span data-stu-id="1af2a-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="1af2a-261">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-262">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-262">Field name</span></span>|<span data-ttu-id="1af2a-263">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-263">Data type</span></span>|<span data-ttu-id="1af2a-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-265">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="1af2a-265">Address</span></span>|<span data-ttu-id="1af2a-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-266">win:UInt64</span></span>|<span data-ttu-id="1af2a-267">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-267">The address of the segment.</span></span>|  
|<span data-ttu-id="1af2a-268">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="1af2a-268">Size</span></span>|<span data-ttu-id="1af2a-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-269">win:UInt64</span></span>|<span data-ttu-id="1af2a-270">Dimensione del segmento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-270">The size of the segment.</span></span>|  
|<span data-ttu-id="1af2a-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="1af2a-271">Type</span></span>|<span data-ttu-id="1af2a-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-272">win:UInt32</span></span>|<span data-ttu-id="1af2a-273">0x0 - Heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="1af2a-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="1af2a-274">0x1 - Heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="1af2a-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="1af2a-275">0x2 - Heap di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1af2a-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="1af2a-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-276">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-277">win:UInt16</span></span>|<span data-ttu-id="1af2a-278">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="1af2a-279">Si noti che la dimensione dei segmenti allocati dal Garbage Collector è specifico dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici.</span><span class="sxs-lookup"><span data-stu-id="1af2a-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="1af2a-280">L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.</span><span class="sxs-lookup"><span data-stu-id="1af2a-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="1af2a-281">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="1af2a-282">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="1af2a-283">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-284">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-284">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-285">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-288">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-289">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-289">Event</span></span>|<span data-ttu-id="1af2a-290">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-290">Event ID</span></span>|<span data-ttu-id="1af2a-291">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="1af2a-292">6</span><span class="sxs-lookup"><span data-stu-id="1af2a-292">6</span></span>|<span data-ttu-id="1af2a-293">È stato rilasciato un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="1af2a-294">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-295">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-295">Field name</span></span>|<span data-ttu-id="1af2a-296">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-296">Data type</span></span>|<span data-ttu-id="1af2a-297">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-298">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="1af2a-298">Address</span></span>|<span data-ttu-id="1af2a-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-299">win:UInt64</span></span>|<span data-ttu-id="1af2a-300">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-300">The address of the segment.</span></span>|  
|<span data-ttu-id="1af2a-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-301">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-302">win:UInt16</span></span>|<span data-ttu-id="1af2a-303">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1af2a-304">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="1af2a-305">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="1af2a-306">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-307">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-307">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-308">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-311">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-312">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-312">Event</span></span>|<span data-ttu-id="1af2a-313">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-313">Event ID</span></span>|<span data-ttu-id="1af2a-314">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="1af2a-315">7</span><span class="sxs-lookup"><span data-stu-id="1af2a-315">7</span></span>|<span data-ttu-id="1af2a-316">Il ripristino dalla sospensione di Common Language Runtime è iniziato.</span><span class="sxs-lookup"><span data-stu-id="1af2a-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="1af2a-317">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-317">No event data.</span></span>  
  
 [<span data-ttu-id="1af2a-318">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="1af2a-319">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="1af2a-320">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-321">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-321">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-322">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-325">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-326">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-326">Event</span></span>|<span data-ttu-id="1af2a-327">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-327">Event Id</span></span>|<span data-ttu-id="1af2a-328">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="1af2a-329">3</span><span class="sxs-lookup"><span data-stu-id="1af2a-329">3</span></span>|<span data-ttu-id="1af2a-330">Il ripristino dalla sospensione di Common Language Runtime è terminato.</span><span class="sxs-lookup"><span data-stu-id="1af2a-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="1af2a-331">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-331">No event data.</span></span>  
  
 [<span data-ttu-id="1af2a-332">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="1af2a-333">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="1af2a-334">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-335">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-335">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-336">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-339">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-340">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-340">Event</span></span>|<span data-ttu-id="1af2a-341">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-341">Event ID</span></span>|<span data-ttu-id="1af2a-342">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="1af2a-343">9</span><span class="sxs-lookup"><span data-stu-id="1af2a-343">9</span></span>|<span data-ttu-id="1af2a-344">Inizio della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="1af2a-345">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-346">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-346">Field name</span></span>|<span data-ttu-id="1af2a-347">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-347">Data type</span></span>|<span data-ttu-id="1af2a-348">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="1af2a-349">Reason</span></span>|<span data-ttu-id="1af2a-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-350">win:UInt16</span></span>|<span data-ttu-id="1af2a-351">0x0 - Altro.</span><span class="sxs-lookup"><span data-stu-id="1af2a-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="1af2a-352">0x1 - Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="1af2a-353">0x2 - Arresto del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="1af2a-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="1af2a-354">0x3. - Lancio del codice.</span><span class="sxs-lookup"><span data-stu-id="1af2a-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="1af2a-355">0x4 - Arresto.</span><span class="sxs-lookup"><span data-stu-id="1af2a-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="1af2a-356">0x5 - Debugger.</span><span class="sxs-lookup"><span data-stu-id="1af2a-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="1af2a-357">0x6 - Preparazione per l'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="1af2a-358">Conteggio</span><span class="sxs-lookup"><span data-stu-id="1af2a-358">Count</span></span>|<span data-ttu-id="1af2a-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-359">win:UInt32</span></span>|<span data-ttu-id="1af2a-360">Il conteggio di Garbage Collection al momento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-360">The GC count at the time.</span></span> <span data-ttu-id="1af2a-361">In genere, dopo di questo si assiste a un evento di avvio GC successivo. Il conteggio corrisponde al conteggio corrente + 1 quando si aumenta l'indice di GC durante un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="1af2a-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-362">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-363">win:UInt16</span></span>|<span data-ttu-id="1af2a-364">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1af2a-365">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="1af2a-366">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="1af2a-367">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="1af2a-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="1af2a-368">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-368">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-369">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-372">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="1af2a-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="1af2a-373">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-373">Event</span></span>|<span data-ttu-id="1af2a-374">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-374">Event ID</span></span>|<span data-ttu-id="1af2a-375">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="1af2a-376">8</span><span class="sxs-lookup"><span data-stu-id="1af2a-376">8</span></span>|<span data-ttu-id="1af2a-377">Fine della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1af2a-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="1af2a-378">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-378">No event data.</span></span>  
  
 [<span data-ttu-id="1af2a-379">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="1af2a-380">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="1af2a-381">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-382">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-382">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-383">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-386">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-387">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-387">Event</span></span>|<span data-ttu-id="1af2a-388">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-388">Event ID</span></span>|<span data-ttu-id="1af2a-389">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="1af2a-390">10</span><span class="sxs-lookup"><span data-stu-id="1af2a-390">10</span></span>|<span data-ttu-id="1af2a-391">Ogni volta vengono allocati circa 100 KB.</span><span class="sxs-lookup"><span data-stu-id="1af2a-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="1af2a-392">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-393">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-393">Field name</span></span>|<span data-ttu-id="1af2a-394">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-394">Data type</span></span>|<span data-ttu-id="1af2a-395">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="1af2a-396">AllocationAmount</span></span>|<span data-ttu-id="1af2a-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-397">win:UInt32</span></span>|<span data-ttu-id="1af2a-398">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="1af2a-398">The allocation size, in bytes.</span></span> <span data-ttu-id="1af2a-399">Questo valore è preciso per le allocazioni minori della lunghezza di un ULONG (4.294.967.295 byte).</span><span class="sxs-lookup"><span data-stu-id="1af2a-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="1af2a-400">Se l'allocazione è maggiore, questo campo contiene un valore troncato.</span><span class="sxs-lookup"><span data-stu-id="1af2a-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="1af2a-401">Usare `AllocationAmount64` per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="1af2a-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="1af2a-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="1af2a-402">AllocationKind</span></span>|<span data-ttu-id="1af2a-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-403">win:UInt32</span></span>|<span data-ttu-id="1af2a-404">0x0 - Allocazione di oggetti piccoli (l'allocazione è nell'heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="1af2a-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="1af2a-405">0x1 - Allocazione di oggetti grandi (l'allocazione è nell'heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="1af2a-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="1af2a-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-406">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-407">win:UInt16</span></span>|<span data-ttu-id="1af2a-408">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="1af2a-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="1af2a-409">AllocationAmount64</span></span>|<span data-ttu-id="1af2a-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="1af2a-410">win:UInt64</span></span>|<span data-ttu-id="1af2a-411">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="1af2a-411">The allocation size, in bytes.</span></span> <span data-ttu-id="1af2a-412">Questo valore è preciso per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="1af2a-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="1af2a-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="1af2a-413">TypeId</span></span>|<span data-ttu-id="1af2a-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="1af2a-414">win:Pointer</span></span>|<span data-ttu-id="1af2a-415">Indirizzo di MethodTable.</span><span class="sxs-lookup"><span data-stu-id="1af2a-415">The address of the MethodTable.</span></span> <span data-ttu-id="1af2a-416">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è l'indirizzo di MethodTable che corrisponde all'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="1af2a-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="1af2a-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="1af2a-417">TypeName</span></span>|<span data-ttu-id="1af2a-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="1af2a-418">win:UnicodeString</span></span>|<span data-ttu-id="1af2a-419">Nome del tipo che è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="1af2a-419">The name of the type that was allocated.</span></span> <span data-ttu-id="1af2a-420">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è il tipo dell'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="1af2a-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="1af2a-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="1af2a-421">HeapIndex</span></span>|<span data-ttu-id="1af2a-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-422">win:UInt32</span></span>|<span data-ttu-id="1af2a-423">Heap in cui l'oggetto è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="1af2a-423">The heap where the object was allocated.</span></span> <span data-ttu-id="1af2a-424">Questo valore è 0 (zero) durante l'esecuzione della procedura di Garbage Collection per workstation.</span><span class="sxs-lookup"><span data-stu-id="1af2a-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="1af2a-425">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="1af2a-426">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="1af2a-427">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-428">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-428">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-429">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-432">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-433">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-433">Event</span></span>|<span data-ttu-id="1af2a-434">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-434">Event ID</span></span>|<span data-ttu-id="1af2a-435">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="1af2a-436">14</span><span class="sxs-lookup"><span data-stu-id="1af2a-436">14</span></span>|<span data-ttu-id="1af2a-437">Inizio dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="1af2a-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="1af2a-438">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-438">No event data.</span></span>  
  
 [<span data-ttu-id="1af2a-439">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="1af2a-440">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="1af2a-441">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-442">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-442">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-443">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-446">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-447">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-447">Event</span></span>|<span data-ttu-id="1af2a-448">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-448">Event ID</span></span>|<span data-ttu-id="1af2a-449">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="1af2a-450">13</span><span class="sxs-lookup"><span data-stu-id="1af2a-450">13</span></span>|<span data-ttu-id="1af2a-451">Fine dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="1af2a-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="1af2a-452">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="1af2a-453">Nome campo</span><span class="sxs-lookup"><span data-stu-id="1af2a-453">Field name</span></span>|<span data-ttu-id="1af2a-454">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1af2a-454">Data type</span></span>|<span data-ttu-id="1af2a-455">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af2a-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="1af2a-456">Conteggio</span><span class="sxs-lookup"><span data-stu-id="1af2a-456">Count</span></span>|<span data-ttu-id="1af2a-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="1af2a-457">win:UInt32</span></span>|<span data-ttu-id="1af2a-458">Numero di finalizzatori eseguiti.</span><span class="sxs-lookup"><span data-stu-id="1af2a-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="1af2a-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="1af2a-459">ClrInstanceID</span></span>|<span data-ttu-id="1af2a-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="1af2a-460">win:UInt16</span></span>|<span data-ttu-id="1af2a-461">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="1af2a-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="1af2a-462">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="1af2a-463">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="1af2a-464">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-465">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-465">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-466">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-468">Informational (4)</span></span>|  
|<span data-ttu-id="1af2a-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1af2a-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1af2a-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-471">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-472">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-472">Event</span></span>|<span data-ttu-id="1af2a-473">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-473">Event ID</span></span>|<span data-ttu-id="1af2a-474">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="1af2a-475">11</span><span class="sxs-lookup"><span data-stu-id="1af2a-475">11</span></span>|<span data-ttu-id="1af2a-476">È stato creato il thread di Garbage Collection in modalità simultanea</span><span class="sxs-lookup"><span data-stu-id="1af2a-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="1af2a-477">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-477">No event data.</span></span>  
  
 [<span data-ttu-id="1af2a-478">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="1af2a-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="1af2a-479">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="1af2a-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="1af2a-480">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="1af2a-481">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-481">Keyword for raising the event</span></span>|<span data-ttu-id="1af2a-482">Livello</span><span class="sxs-lookup"><span data-stu-id="1af2a-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="1af2a-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="1af2a-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="1af2a-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-484">Informational (4)</span></span>|  
|<span data-ttu-id="1af2a-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="1af2a-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="1af2a-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="1af2a-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="1af2a-487">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="1af2a-488">Evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-488">Event</span></span>|<span data-ttu-id="1af2a-489">ID evento</span><span class="sxs-lookup"><span data-stu-id="1af2a-489">Event ID</span></span>|<span data-ttu-id="1af2a-490">Generato quando</span><span class="sxs-lookup"><span data-stu-id="1af2a-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="1af2a-491">12</span><span class="sxs-lookup"><span data-stu-id="1af2a-491">12</span></span>|<span data-ttu-id="1af2a-492">È stato terminato il thread di Garbage Collection in modalità simultanea.</span><span class="sxs-lookup"><span data-stu-id="1af2a-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="1af2a-493">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="1af2a-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1af2a-494">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1af2a-494">See Also</span></span>  
 [<span data-ttu-id="1af2a-495">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="1af2a-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
