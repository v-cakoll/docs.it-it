---
title: Eventi ETW di Garbage Collection
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7f9bf0e309ec8c77d4b1d6afbf111e7eeae629ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149734"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="71272-102">Eventi ETW di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="71272-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="71272-103">Questi eventi raccolgono informazioni relative alla Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="71272-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="71272-104">ai fini della diagnostica e del debug, tra cui stabilire quante volte è stato eseguito il processo di Garbage Collection, la quantità di memoria liberata durante la procedura di Garbage Collection e così via.</span><span class="sxs-lookup"><span data-stu-id="71272-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="71272-105">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="71272-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="71272-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="71272-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="71272-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="71272-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="71272-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="71272-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="71272-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="71272-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="71272-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="71272-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="71272-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="71272-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="71272-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="71272-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="71272-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="71272-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="71272-121">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="71272-122">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="71272-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="71272-123">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-123">Keyword for raising the event</span></span>|<span data-ttu-id="71272-124">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-127">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-128">event</span><span class="sxs-lookup"><span data-stu-id="71272-128">Event</span></span>|<span data-ttu-id="71272-129">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-129">Event ID</span></span>|<span data-ttu-id="71272-130">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="71272-131">1</span><span class="sxs-lookup"><span data-stu-id="71272-131">1</span></span>|<span data-ttu-id="71272-132">È stata avviata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="71272-133">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-134">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-134">Field name</span></span>|<span data-ttu-id="71272-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-135">Data type</span></span>|<span data-ttu-id="71272-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-137">Conteggio</span><span class="sxs-lookup"><span data-stu-id="71272-137">Count</span></span>|<span data-ttu-id="71272-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-138">win:UInt32</span></span>|<span data-ttu-id="71272-139">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="71272-140">Profondità</span><span class="sxs-lookup"><span data-stu-id="71272-140">Depth</span></span>|<span data-ttu-id="71272-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-141">win:UInt32</span></span>|<span data-ttu-id="71272-142">La generazione che viene raccolta.</span><span class="sxs-lookup"><span data-stu-id="71272-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="71272-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="71272-143">Reason</span></span>|<span data-ttu-id="71272-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-144">win:UInt32</span></span>|<span data-ttu-id="71272-145">Motivo per cui è stata attivata la Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="71272-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="71272-146">0x0 - Allocazione heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="71272-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="71272-147">0x1 - Indotto.</span><span class="sxs-lookup"><span data-stu-id="71272-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="71272-148">0x2 - Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="71272-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="71272-149">0x3 - Vuoto.</span><span class="sxs-lookup"><span data-stu-id="71272-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="71272-150">0x4 - Allocazione heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="71272-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="71272-151">0x5 - Spazio esaurito (per heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="71272-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="71272-152">0x6 - Spazio esaurito (per heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="71272-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="71272-153">0x7 - Indotto ma non forzato come blocco.</span><span class="sxs-lookup"><span data-stu-id="71272-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="71272-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="71272-154">Type</span></span>|<span data-ttu-id="71272-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-155">win:UInt32</span></span>|<span data-ttu-id="71272-156">0x0 - Un'operazione di Garbage Collection bloccante è stata eseguita all'esterno della procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="71272-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="71272-157">0x1 - Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="71272-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="71272-158">0x2 - Un'operazione di Garbage Collection bloccante è stata eseguita durante la procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="71272-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="71272-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-159">ClrInstanceID</span></span>|<span data-ttu-id="71272-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-160">win:UInt16</span></span>|<span data-ttu-id="71272-161">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71272-162">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="71272-163">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="71272-164">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-165">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-165">Keyword for raising the event</span></span>|<span data-ttu-id="71272-166">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-169">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-170">event</span><span class="sxs-lookup"><span data-stu-id="71272-170">Event</span></span>|<span data-ttu-id="71272-171">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-171">Event ID</span></span>|<span data-ttu-id="71272-172">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="71272-173">2</span><span class="sxs-lookup"><span data-stu-id="71272-173">2</span></span>|<span data-ttu-id="71272-174">È stata terminata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="71272-175">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-176">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-176">Field name</span></span>|<span data-ttu-id="71272-177">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-177">Data type</span></span>|<span data-ttu-id="71272-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-179">Conteggio</span><span class="sxs-lookup"><span data-stu-id="71272-179">Count</span></span>|<span data-ttu-id="71272-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-180">win:UInt32</span></span>|<span data-ttu-id="71272-181">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="71272-182">Profondità</span><span class="sxs-lookup"><span data-stu-id="71272-182">Depth</span></span>|<span data-ttu-id="71272-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-183">win:UInt32</span></span>|<span data-ttu-id="71272-184">La generazione che è stata raccolta.</span><span class="sxs-lookup"><span data-stu-id="71272-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="71272-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-185">ClrInstanceID</span></span>|<span data-ttu-id="71272-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-186">win:UInt16</span></span>|<span data-ttu-id="71272-187">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71272-188">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="71272-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="71272-190">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-191">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-191">Keyword for raising the event</span></span>|<span data-ttu-id="71272-192">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-195">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-196">event</span><span class="sxs-lookup"><span data-stu-id="71272-196">Event</span></span>|<span data-ttu-id="71272-197">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-197">Event ID</span></span>|<span data-ttu-id="71272-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="71272-199">4</span><span class="sxs-lookup"><span data-stu-id="71272-199">4</span></span>|<span data-ttu-id="71272-200">Mostra le statistiche heap alla fine di ogni Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="71272-201">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-202">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-202">Field name</span></span>|<span data-ttu-id="71272-203">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-203">Data type</span></span>|<span data-ttu-id="71272-204">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="71272-205">GenerationSize0</span></span>|<span data-ttu-id="71272-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-206">win:UInt64</span></span>|<span data-ttu-id="71272-207">Dimensione, in byte, della memoria della generazione 0.</span><span class="sxs-lookup"><span data-stu-id="71272-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="71272-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="71272-208">TotalPromotedSize0</span></span>|<span data-ttu-id="71272-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-209">win:UInt64</span></span>|<span data-ttu-id="71272-210">Numero di byte promossi dalla generazione 0 alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="71272-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="71272-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="71272-211">GenerationSize1</span></span>|<span data-ttu-id="71272-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-212">win:UInt64</span></span>|<span data-ttu-id="71272-213">Dimensione, in byte, della memoria di generazione 1.</span><span class="sxs-lookup"><span data-stu-id="71272-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="71272-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="71272-214">TotalPromotedSize1</span></span>|<span data-ttu-id="71272-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-215">win:UInt64</span></span>|<span data-ttu-id="71272-216">Numero di byte promossi dalla generazione 1 alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="71272-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="71272-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="71272-217">GenerationSize2</span></span>|<span data-ttu-id="71272-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-218">win:UInt64</span></span>|<span data-ttu-id="71272-219">Dimensione, in byte, della memoria della generazione 2.</span><span class="sxs-lookup"><span data-stu-id="71272-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="71272-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="71272-220">TotalPromotedSize2</span></span>|<span data-ttu-id="71272-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-221">win:UInt64</span></span>|<span data-ttu-id="71272-222">Numero di byte rimasti nella generazione 2 dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="71272-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="71272-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="71272-223">GenerationSize3</span></span>|<span data-ttu-id="71272-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-224">win:UInt64</span></span>|<span data-ttu-id="71272-225">Dimensione, in byte, dell'heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="71272-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="71272-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="71272-226">TotalPromotedSize3</span></span>|<span data-ttu-id="71272-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-227">win:UInt64</span></span>|<span data-ttu-id="71272-228">Numero di byte rimasti nell'heap oggetto grande dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="71272-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="71272-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="71272-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="71272-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-230">win:UInt64</span></span>|<span data-ttu-id="71272-231">Dimensione totale, in byte, degli oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="71272-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="71272-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="71272-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="71272-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-233">win:UInt64</span></span>|<span data-ttu-id="71272-234">Numero di oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="71272-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="71272-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="71272-235">PinnedObjectCount</span></span>|<span data-ttu-id="71272-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-236">win:UInt32</span></span>|<span data-ttu-id="71272-237">Numero di oggetti bloccati (fissi).</span><span class="sxs-lookup"><span data-stu-id="71272-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="71272-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="71272-238">SinkBlockCount</span></span>|<span data-ttu-id="71272-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-239">win:UInt32</span></span>|<span data-ttu-id="71272-240">Numero di blocchi di sincronizzazione in uso.</span><span class="sxs-lookup"><span data-stu-id="71272-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="71272-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="71272-241">GCHandleCount</span></span>|<span data-ttu-id="71272-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-242">win:UInt32</span></span>|<span data-ttu-id="71272-243">Numero di handle di Garbage Collection in uso.</span><span class="sxs-lookup"><span data-stu-id="71272-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="71272-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-244">ClrInstanceID</span></span>|<span data-ttu-id="71272-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-245">win:UInt16</span></span>|<span data-ttu-id="71272-246">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71272-247">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="71272-248">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="71272-249">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-250">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-250">Keyword for raising the event</span></span>|<span data-ttu-id="71272-251">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-254">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-255">event</span><span class="sxs-lookup"><span data-stu-id="71272-255">Event</span></span>|<span data-ttu-id="71272-256">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-256">Event ID</span></span>|<span data-ttu-id="71272-257">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="71272-258">5</span><span class="sxs-lookup"><span data-stu-id="71272-258">5</span></span>|<span data-ttu-id="71272-259">È stato creato un nuovo segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="71272-260">Inoltre, quando la traccia è attivata su un processo già in esecuzione, questo evento viene generato per ogni segmento esistente.</span><span class="sxs-lookup"><span data-stu-id="71272-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="71272-261">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-262">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-262">Field name</span></span>|<span data-ttu-id="71272-263">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-263">Data type</span></span>|<span data-ttu-id="71272-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-265">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="71272-265">Address</span></span>|<span data-ttu-id="71272-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-266">win:UInt64</span></span>|<span data-ttu-id="71272-267">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="71272-267">The address of the segment.</span></span>|  
|<span data-ttu-id="71272-268">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="71272-268">Size</span></span>|<span data-ttu-id="71272-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-269">win:UInt64</span></span>|<span data-ttu-id="71272-270">Dimensione del segmento.</span><span class="sxs-lookup"><span data-stu-id="71272-270">The size of the segment.</span></span>|  
|<span data-ttu-id="71272-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="71272-271">Type</span></span>|<span data-ttu-id="71272-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-272">win:UInt32</span></span>|<span data-ttu-id="71272-273">0x0 - Heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="71272-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="71272-274">0x1 - Heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="71272-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="71272-275">0x2 - Heap di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="71272-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="71272-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-276">ClrInstanceID</span></span>|<span data-ttu-id="71272-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-277">win:UInt16</span></span>|<span data-ttu-id="71272-278">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="71272-279">Si noti che la dimensione dei segmenti allocati dal Garbage Collector è specifico dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici.</span><span class="sxs-lookup"><span data-stu-id="71272-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="71272-280">L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.</span><span class="sxs-lookup"><span data-stu-id="71272-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="71272-281">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="71272-282">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="71272-283">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-284">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-284">Keyword for raising the event</span></span>|<span data-ttu-id="71272-285">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-288">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-289">event</span><span class="sxs-lookup"><span data-stu-id="71272-289">Event</span></span>|<span data-ttu-id="71272-290">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-290">Event ID</span></span>|<span data-ttu-id="71272-291">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="71272-292">6</span><span class="sxs-lookup"><span data-stu-id="71272-292">6</span></span>|<span data-ttu-id="71272-293">È stato rilasciato un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="71272-294">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-295">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-295">Field name</span></span>|<span data-ttu-id="71272-296">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-296">Data type</span></span>|<span data-ttu-id="71272-297">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-298">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="71272-298">Address</span></span>|<span data-ttu-id="71272-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-299">win:UInt64</span></span>|<span data-ttu-id="71272-300">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="71272-300">The address of the segment.</span></span>|  
|<span data-ttu-id="71272-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-301">ClrInstanceID</span></span>|<span data-ttu-id="71272-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-302">win:UInt16</span></span>|<span data-ttu-id="71272-303">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71272-304">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="71272-305">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="71272-306">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-307">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-307">Keyword for raising the event</span></span>|<span data-ttu-id="71272-308">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-311">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-312">event</span><span class="sxs-lookup"><span data-stu-id="71272-312">Event</span></span>|<span data-ttu-id="71272-313">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-313">Event ID</span></span>|<span data-ttu-id="71272-314">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="71272-315">7</span><span class="sxs-lookup"><span data-stu-id="71272-315">7</span></span>|<span data-ttu-id="71272-316">Il ripristino dalla sospensione di Common Language Runtime è iniziato.</span><span class="sxs-lookup"><span data-stu-id="71272-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="71272-317">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-317">No event data.</span></span>  
  
 [<span data-ttu-id="71272-318">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="71272-319">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="71272-320">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-321">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-321">Keyword for raising the event</span></span>|<span data-ttu-id="71272-322">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-325">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-326">event</span><span class="sxs-lookup"><span data-stu-id="71272-326">Event</span></span>|<span data-ttu-id="71272-327">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-327">Event Id</span></span>|<span data-ttu-id="71272-328">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="71272-329">3</span><span class="sxs-lookup"><span data-stu-id="71272-329">3</span></span>|<span data-ttu-id="71272-330">Il ripristino dalla sospensione di Common Language Runtime è terminato.</span><span class="sxs-lookup"><span data-stu-id="71272-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="71272-331">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-331">No event data.</span></span>  
  
 [<span data-ttu-id="71272-332">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="71272-333">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="71272-334">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-335">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-335">Keyword for raising the event</span></span>|<span data-ttu-id="71272-336">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-339">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-340">event</span><span class="sxs-lookup"><span data-stu-id="71272-340">Event</span></span>|<span data-ttu-id="71272-341">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-341">Event ID</span></span>|<span data-ttu-id="71272-342">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="71272-343">9</span><span class="sxs-lookup"><span data-stu-id="71272-343">9</span></span>|<span data-ttu-id="71272-344">Inizio della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="71272-345">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-346">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-346">Field name</span></span>|<span data-ttu-id="71272-347">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-347">Data type</span></span>|<span data-ttu-id="71272-348">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="71272-349">Reason</span></span>|<span data-ttu-id="71272-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-350">win:UInt16</span></span>|<span data-ttu-id="71272-351">0x0 - Altro.</span><span class="sxs-lookup"><span data-stu-id="71272-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="71272-352">0x1 - Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="71272-353">0x2 - Arresto del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="71272-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="71272-354">0x3. - Lancio del codice.</span><span class="sxs-lookup"><span data-stu-id="71272-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="71272-355">0x4 - Arresto.</span><span class="sxs-lookup"><span data-stu-id="71272-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="71272-356">0x5 - Debugger.</span><span class="sxs-lookup"><span data-stu-id="71272-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="71272-357">0x6 - Preparazione per l'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="71272-358">Conteggio</span><span class="sxs-lookup"><span data-stu-id="71272-358">Count</span></span>|<span data-ttu-id="71272-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-359">win:UInt32</span></span>|<span data-ttu-id="71272-360">Il conteggio di Garbage Collection al momento.</span><span class="sxs-lookup"><span data-stu-id="71272-360">The GC count at the time.</span></span> <span data-ttu-id="71272-361">In genere, dopo di questo si assiste a un evento di avvio GC successivo. Il conteggio corrisponde al conteggio corrente + 1 quando si aumenta l'indice di GC durante un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="71272-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-362">ClrInstanceID</span></span>|<span data-ttu-id="71272-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-363">win:UInt16</span></span>|<span data-ttu-id="71272-364">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71272-365">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="71272-366">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="71272-367">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="71272-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="71272-368">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-368">Keyword for raising the event</span></span>|<span data-ttu-id="71272-369">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-372">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="71272-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="71272-373">event</span><span class="sxs-lookup"><span data-stu-id="71272-373">Event</span></span>|<span data-ttu-id="71272-374">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-374">Event ID</span></span>|<span data-ttu-id="71272-375">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="71272-376">8</span><span class="sxs-lookup"><span data-stu-id="71272-376">8</span></span>|<span data-ttu-id="71272-377">Fine della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="71272-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="71272-378">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-378">No event data.</span></span>  
  
 [<span data-ttu-id="71272-379">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="71272-380">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="71272-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="71272-381">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-382">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-382">Keyword for raising the event</span></span>|<span data-ttu-id="71272-383">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-386">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-387">event</span><span class="sxs-lookup"><span data-stu-id="71272-387">Event</span></span>|<span data-ttu-id="71272-388">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-388">Event ID</span></span>|<span data-ttu-id="71272-389">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="71272-390">10</span><span class="sxs-lookup"><span data-stu-id="71272-390">10</span></span>|<span data-ttu-id="71272-391">Ogni volta vengono allocati circa 100 KB.</span><span class="sxs-lookup"><span data-stu-id="71272-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="71272-392">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-393">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-393">Field name</span></span>|<span data-ttu-id="71272-394">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-394">Data type</span></span>|<span data-ttu-id="71272-395">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="71272-396">AllocationAmount</span></span>|<span data-ttu-id="71272-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-397">win:UInt32</span></span>|<span data-ttu-id="71272-398">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="71272-398">The allocation size, in bytes.</span></span> <span data-ttu-id="71272-399">Questo valore è preciso per le allocazioni minori della lunghezza di un ULONG (4.294.967.295 byte).</span><span class="sxs-lookup"><span data-stu-id="71272-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="71272-400">Se l'allocazione è maggiore, questo campo contiene un valore troncato.</span><span class="sxs-lookup"><span data-stu-id="71272-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="71272-401">Usare `AllocationAmount64` per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="71272-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="71272-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="71272-402">AllocationKind</span></span>|<span data-ttu-id="71272-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-403">win:UInt32</span></span>|<span data-ttu-id="71272-404">0x0 - Allocazione di oggetti piccoli (l'allocazione è nell'heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="71272-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="71272-405">0x1 - Allocazione di oggetti grandi (l'allocazione è nell'heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="71272-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="71272-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-406">ClrInstanceID</span></span>|<span data-ttu-id="71272-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-407">win:UInt16</span></span>|<span data-ttu-id="71272-408">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="71272-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="71272-409">AllocationAmount64</span></span>|<span data-ttu-id="71272-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71272-410">win:UInt64</span></span>|<span data-ttu-id="71272-411">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="71272-411">The allocation size, in bytes.</span></span> <span data-ttu-id="71272-412">Questo valore è preciso per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="71272-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="71272-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="71272-413">TypeId</span></span>|<span data-ttu-id="71272-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="71272-414">win:Pointer</span></span>|<span data-ttu-id="71272-415">Indirizzo di MethodTable.</span><span class="sxs-lookup"><span data-stu-id="71272-415">The address of the MethodTable.</span></span> <span data-ttu-id="71272-416">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è l'indirizzo di MethodTable che corrisponde all'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="71272-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="71272-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="71272-417">TypeName</span></span>|<span data-ttu-id="71272-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71272-418">win:UnicodeString</span></span>|<span data-ttu-id="71272-419">Nome del tipo che è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="71272-419">The name of the type that was allocated.</span></span> <span data-ttu-id="71272-420">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è il tipo dell'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="71272-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="71272-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="71272-421">HeapIndex</span></span>|<span data-ttu-id="71272-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-422">win:UInt32</span></span>|<span data-ttu-id="71272-423">Heap in cui l'oggetto è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="71272-423">The heap where the object was allocated.</span></span> <span data-ttu-id="71272-424">Questo valore è 0 (zero) durante l'esecuzione della procedura di Garbage Collection per workstation.</span><span class="sxs-lookup"><span data-stu-id="71272-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="71272-425">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="71272-426">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="71272-427">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-428">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-428">Keyword for raising the event</span></span>|<span data-ttu-id="71272-429">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-432">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-433">event</span><span class="sxs-lookup"><span data-stu-id="71272-433">Event</span></span>|<span data-ttu-id="71272-434">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-434">Event ID</span></span>|<span data-ttu-id="71272-435">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="71272-436">14</span><span class="sxs-lookup"><span data-stu-id="71272-436">14</span></span>|<span data-ttu-id="71272-437">Inizio dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="71272-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="71272-438">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-438">No event data.</span></span>  
  
 [<span data-ttu-id="71272-439">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="71272-440">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="71272-441">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-442">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-442">Keyword for raising the event</span></span>|<span data-ttu-id="71272-443">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-446">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-447">event</span><span class="sxs-lookup"><span data-stu-id="71272-447">Event</span></span>|<span data-ttu-id="71272-448">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-448">Event ID</span></span>|<span data-ttu-id="71272-449">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="71272-450">13</span><span class="sxs-lookup"><span data-stu-id="71272-450">13</span></span>|<span data-ttu-id="71272-451">Fine dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="71272-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="71272-452">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71272-453">Nome campo</span><span class="sxs-lookup"><span data-stu-id="71272-453">Field name</span></span>|<span data-ttu-id="71272-454">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="71272-454">Data type</span></span>|<span data-ttu-id="71272-455">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71272-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71272-456">Conteggio</span><span class="sxs-lookup"><span data-stu-id="71272-456">Count</span></span>|<span data-ttu-id="71272-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71272-457">win:UInt32</span></span>|<span data-ttu-id="71272-458">Numero di finalizzatori eseguiti.</span><span class="sxs-lookup"><span data-stu-id="71272-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="71272-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71272-459">ClrInstanceID</span></span>|<span data-ttu-id="71272-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71272-460">win:UInt16</span></span>|<span data-ttu-id="71272-461">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="71272-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71272-462">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="71272-463">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="71272-464">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-465">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-465">Keyword for raising the event</span></span>|<span data-ttu-id="71272-466">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-468">Informational (4)</span></span>|  
|<span data-ttu-id="71272-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="71272-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="71272-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-471">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-472">event</span><span class="sxs-lookup"><span data-stu-id="71272-472">Event</span></span>|<span data-ttu-id="71272-473">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-473">Event ID</span></span>|<span data-ttu-id="71272-474">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="71272-475">11</span><span class="sxs-lookup"><span data-stu-id="71272-475">11</span></span>|<span data-ttu-id="71272-476">È stato creato il thread di Garbage Collection in modalità simultanea</span><span class="sxs-lookup"><span data-stu-id="71272-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="71272-477">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-477">No event data.</span></span>  
  
 [<span data-ttu-id="71272-478">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="71272-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="71272-479">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="71272-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="71272-480">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="71272-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71272-481">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="71272-481">Keyword for raising the event</span></span>|<span data-ttu-id="71272-482">Livello</span><span class="sxs-lookup"><span data-stu-id="71272-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71272-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="71272-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="71272-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-484">Informational (4)</span></span>|  
|<span data-ttu-id="71272-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="71272-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="71272-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="71272-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="71272-487">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71272-488">event</span><span class="sxs-lookup"><span data-stu-id="71272-488">Event</span></span>|<span data-ttu-id="71272-489">ID evento</span><span class="sxs-lookup"><span data-stu-id="71272-489">Event ID</span></span>|<span data-ttu-id="71272-490">Generato quando</span><span class="sxs-lookup"><span data-stu-id="71272-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="71272-491">12</span><span class="sxs-lookup"><span data-stu-id="71272-491">12</span></span>|<span data-ttu-id="71272-492">È stato terminato il thread di Garbage Collection in modalità simultanea.</span><span class="sxs-lookup"><span data-stu-id="71272-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="71272-493">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71272-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71272-494">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71272-494">See also</span></span>

- [<span data-ttu-id="71272-495">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="71272-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
