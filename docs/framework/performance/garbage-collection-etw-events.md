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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61722939"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="c523d-102">Eventi ETW di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c523d-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="c523d-103">Questi eventi raccolgono informazioni relative alla Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c523d-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="c523d-104">ai fini della diagnostica e del debug, tra cui stabilire quante volte è stato eseguito il processo di Garbage Collection, la quantità di memoria liberata durante la procedura di Garbage Collection e così via.</span><span class="sxs-lookup"><span data-stu-id="c523d-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="c523d-105">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="c523d-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="c523d-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
- [<span data-ttu-id="c523d-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
- [<span data-ttu-id="c523d-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
- [<span data-ttu-id="c523d-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
- [<span data-ttu-id="c523d-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
- [<span data-ttu-id="c523d-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
- [<span data-ttu-id="c523d-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
- [<span data-ttu-id="c523d-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
- [<span data-ttu-id="c523d-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
- [<span data-ttu-id="c523d-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
- [<span data-ttu-id="c523d-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
- [<span data-ttu-id="c523d-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
- [<span data-ttu-id="c523d-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
- [<span data-ttu-id="c523d-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="c523d-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="c523d-121">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="c523d-122">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c523d-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="c523d-123">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-123">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-124">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-127">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-128">event</span><span class="sxs-lookup"><span data-stu-id="c523d-128">Event</span></span>|<span data-ttu-id="c523d-129">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-129">Event ID</span></span>|<span data-ttu-id="c523d-130">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="c523d-131">1</span><span class="sxs-lookup"><span data-stu-id="c523d-131">1</span></span>|<span data-ttu-id="c523d-132">È stata avviata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="c523d-133">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-134">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-134">Field name</span></span>|<span data-ttu-id="c523d-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-135">Data type</span></span>|<span data-ttu-id="c523d-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-137">Conteggio</span><span class="sxs-lookup"><span data-stu-id="c523d-137">Count</span></span>|<span data-ttu-id="c523d-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-138">win:UInt32</span></span>|<span data-ttu-id="c523d-139">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="c523d-140">Profondità</span><span class="sxs-lookup"><span data-stu-id="c523d-140">Depth</span></span>|<span data-ttu-id="c523d-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-141">win:UInt32</span></span>|<span data-ttu-id="c523d-142">La generazione che viene raccolta.</span><span class="sxs-lookup"><span data-stu-id="c523d-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="c523d-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="c523d-143">Reason</span></span>|<span data-ttu-id="c523d-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-144">win:UInt32</span></span>|<span data-ttu-id="c523d-145">Motivo per cui è stata attivata la Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="c523d-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="c523d-146">0x0 - Allocazione heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="c523d-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="c523d-147">0x1 - Indotto.</span><span class="sxs-lookup"><span data-stu-id="c523d-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="c523d-148">0x2 - Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="c523d-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="c523d-149">0x3 - Vuoto.</span><span class="sxs-lookup"><span data-stu-id="c523d-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="c523d-150">0x4 - Allocazione heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="c523d-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="c523d-151">0x5 - Spazio esaurito (per heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="c523d-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="c523d-152">0x6 - Spazio esaurito (per heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="c523d-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="c523d-153">0x7 - Indotto ma non forzato come blocco.</span><span class="sxs-lookup"><span data-stu-id="c523d-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="c523d-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="c523d-154">Type</span></span>|<span data-ttu-id="c523d-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-155">win:UInt32</span></span>|<span data-ttu-id="c523d-156">0x0 - Un'operazione di Garbage Collection bloccante è stata eseguita all'esterno della procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="c523d-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="c523d-157">0x1 - Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="c523d-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="c523d-158">0x2 - Un'operazione di Garbage Collection bloccante è stata eseguita durante la procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="c523d-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="c523d-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-159">ClrInstanceID</span></span>|<span data-ttu-id="c523d-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-160">win:UInt16</span></span>|<span data-ttu-id="c523d-161">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c523d-162">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="c523d-163">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="c523d-164">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-165">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-165">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-166">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-169">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-170">event</span><span class="sxs-lookup"><span data-stu-id="c523d-170">Event</span></span>|<span data-ttu-id="c523d-171">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-171">Event ID</span></span>|<span data-ttu-id="c523d-172">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="c523d-173">2</span><span class="sxs-lookup"><span data-stu-id="c523d-173">2</span></span>|<span data-ttu-id="c523d-174">È stata terminata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="c523d-175">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-176">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-176">Field name</span></span>|<span data-ttu-id="c523d-177">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-177">Data type</span></span>|<span data-ttu-id="c523d-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-179">Conteggio</span><span class="sxs-lookup"><span data-stu-id="c523d-179">Count</span></span>|<span data-ttu-id="c523d-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-180">win:UInt32</span></span>|<span data-ttu-id="c523d-181">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="c523d-182">Profondità</span><span class="sxs-lookup"><span data-stu-id="c523d-182">Depth</span></span>|<span data-ttu-id="c523d-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-183">win:UInt32</span></span>|<span data-ttu-id="c523d-184">La generazione che è stata raccolta.</span><span class="sxs-lookup"><span data-stu-id="c523d-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="c523d-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-185">ClrInstanceID</span></span>|<span data-ttu-id="c523d-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-186">win:UInt16</span></span>|<span data-ttu-id="c523d-187">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c523d-188">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="c523d-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="c523d-190">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-191">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-191">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-192">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-195">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-196">event</span><span class="sxs-lookup"><span data-stu-id="c523d-196">Event</span></span>|<span data-ttu-id="c523d-197">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-197">Event ID</span></span>|<span data-ttu-id="c523d-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="c523d-199">4</span><span class="sxs-lookup"><span data-stu-id="c523d-199">4</span></span>|<span data-ttu-id="c523d-200">Mostra le statistiche heap alla fine di ogni Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="c523d-201">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-202">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-202">Field name</span></span>|<span data-ttu-id="c523d-203">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-203">Data type</span></span>|<span data-ttu-id="c523d-204">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="c523d-205">GenerationSize0</span></span>|<span data-ttu-id="c523d-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-206">win:UInt64</span></span>|<span data-ttu-id="c523d-207">Dimensione, in byte, della memoria della generazione 0.</span><span class="sxs-lookup"><span data-stu-id="c523d-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="c523d-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="c523d-208">TotalPromotedSize0</span></span>|<span data-ttu-id="c523d-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-209">win:UInt64</span></span>|<span data-ttu-id="c523d-210">Numero di byte promossi dalla generazione 0 alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="c523d-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="c523d-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="c523d-211">GenerationSize1</span></span>|<span data-ttu-id="c523d-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-212">win:UInt64</span></span>|<span data-ttu-id="c523d-213">Dimensione, in byte, della memoria di generazione 1.</span><span class="sxs-lookup"><span data-stu-id="c523d-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="c523d-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="c523d-214">TotalPromotedSize1</span></span>|<span data-ttu-id="c523d-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-215">win:UInt64</span></span>|<span data-ttu-id="c523d-216">Numero di byte promossi dalla generazione 1 alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="c523d-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="c523d-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="c523d-217">GenerationSize2</span></span>|<span data-ttu-id="c523d-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-218">win:UInt64</span></span>|<span data-ttu-id="c523d-219">Dimensione, in byte, della memoria della generazione 2.</span><span class="sxs-lookup"><span data-stu-id="c523d-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="c523d-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="c523d-220">TotalPromotedSize2</span></span>|<span data-ttu-id="c523d-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-221">win:UInt64</span></span>|<span data-ttu-id="c523d-222">Numero di byte rimasti nella generazione 2 dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="c523d-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="c523d-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="c523d-223">GenerationSize3</span></span>|<span data-ttu-id="c523d-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-224">win:UInt64</span></span>|<span data-ttu-id="c523d-225">Dimensione, in byte, dell'heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="c523d-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="c523d-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="c523d-226">TotalPromotedSize3</span></span>|<span data-ttu-id="c523d-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-227">win:UInt64</span></span>|<span data-ttu-id="c523d-228">Numero di byte rimasti nell'heap oggetto grande dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="c523d-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="c523d-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="c523d-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="c523d-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-230">win:UInt64</span></span>|<span data-ttu-id="c523d-231">Dimensione totale, in byte, degli oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="c523d-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="c523d-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="c523d-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="c523d-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-233">win:UInt64</span></span>|<span data-ttu-id="c523d-234">Numero di oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="c523d-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="c523d-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="c523d-235">PinnedObjectCount</span></span>|<span data-ttu-id="c523d-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-236">win:UInt32</span></span>|<span data-ttu-id="c523d-237">Numero di oggetti bloccati (fissi).</span><span class="sxs-lookup"><span data-stu-id="c523d-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="c523d-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="c523d-238">SinkBlockCount</span></span>|<span data-ttu-id="c523d-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-239">win:UInt32</span></span>|<span data-ttu-id="c523d-240">Numero di blocchi di sincronizzazione in uso.</span><span class="sxs-lookup"><span data-stu-id="c523d-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="c523d-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="c523d-241">GCHandleCount</span></span>|<span data-ttu-id="c523d-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-242">win:UInt32</span></span>|<span data-ttu-id="c523d-243">Numero di handle di Garbage Collection in uso.</span><span class="sxs-lookup"><span data-stu-id="c523d-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="c523d-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-244">ClrInstanceID</span></span>|<span data-ttu-id="c523d-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-245">win:UInt16</span></span>|<span data-ttu-id="c523d-246">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c523d-247">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="c523d-248">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="c523d-249">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-250">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-250">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-251">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-254">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-255">event</span><span class="sxs-lookup"><span data-stu-id="c523d-255">Event</span></span>|<span data-ttu-id="c523d-256">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-256">Event ID</span></span>|<span data-ttu-id="c523d-257">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="c523d-258">5</span><span class="sxs-lookup"><span data-stu-id="c523d-258">5</span></span>|<span data-ttu-id="c523d-259">È stato creato un nuovo segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="c523d-260">Inoltre, quando la traccia è attivata su un processo già in esecuzione, questo evento viene generato per ogni segmento esistente.</span><span class="sxs-lookup"><span data-stu-id="c523d-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="c523d-261">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-262">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-262">Field name</span></span>|<span data-ttu-id="c523d-263">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-263">Data type</span></span>|<span data-ttu-id="c523d-264">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-265">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="c523d-265">Address</span></span>|<span data-ttu-id="c523d-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-266">win:UInt64</span></span>|<span data-ttu-id="c523d-267">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="c523d-267">The address of the segment.</span></span>|  
|<span data-ttu-id="c523d-268">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="c523d-268">Size</span></span>|<span data-ttu-id="c523d-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-269">win:UInt64</span></span>|<span data-ttu-id="c523d-270">Dimensione del segmento.</span><span class="sxs-lookup"><span data-stu-id="c523d-270">The size of the segment.</span></span>|  
|<span data-ttu-id="c523d-271">Tipo</span><span class="sxs-lookup"><span data-stu-id="c523d-271">Type</span></span>|<span data-ttu-id="c523d-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-272">win:UInt32</span></span>|<span data-ttu-id="c523d-273">0x0 - Heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="c523d-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="c523d-274">0x1 - Heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="c523d-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="c523d-275">0x2 - Heap di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c523d-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="c523d-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-276">ClrInstanceID</span></span>|<span data-ttu-id="c523d-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-277">win:UInt16</span></span>|<span data-ttu-id="c523d-278">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="c523d-279">Si noti che la dimensione dei segmenti allocati dal Garbage Collector è specifico dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici.</span><span class="sxs-lookup"><span data-stu-id="c523d-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="c523d-280">L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.</span><span class="sxs-lookup"><span data-stu-id="c523d-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="c523d-281">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="c523d-282">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="c523d-283">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-284">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-284">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-285">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-288">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-289">event</span><span class="sxs-lookup"><span data-stu-id="c523d-289">Event</span></span>|<span data-ttu-id="c523d-290">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-290">Event ID</span></span>|<span data-ttu-id="c523d-291">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="c523d-292">6</span><span class="sxs-lookup"><span data-stu-id="c523d-292">6</span></span>|<span data-ttu-id="c523d-293">È stato rilasciato un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="c523d-294">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-295">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-295">Field name</span></span>|<span data-ttu-id="c523d-296">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-296">Data type</span></span>|<span data-ttu-id="c523d-297">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-298">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="c523d-298">Address</span></span>|<span data-ttu-id="c523d-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-299">win:UInt64</span></span>|<span data-ttu-id="c523d-300">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="c523d-300">The address of the segment.</span></span>|  
|<span data-ttu-id="c523d-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-301">ClrInstanceID</span></span>|<span data-ttu-id="c523d-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-302">win:UInt16</span></span>|<span data-ttu-id="c523d-303">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c523d-304">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="c523d-305">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="c523d-306">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-307">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-307">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-308">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-311">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-312">event</span><span class="sxs-lookup"><span data-stu-id="c523d-312">Event</span></span>|<span data-ttu-id="c523d-313">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-313">Event ID</span></span>|<span data-ttu-id="c523d-314">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="c523d-315">7</span><span class="sxs-lookup"><span data-stu-id="c523d-315">7</span></span>|<span data-ttu-id="c523d-316">Il ripristino dalla sospensione di Common Language Runtime è iniziato.</span><span class="sxs-lookup"><span data-stu-id="c523d-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="c523d-317">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-317">No event data.</span></span>  
  
 [<span data-ttu-id="c523d-318">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="c523d-319">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="c523d-320">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-321">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-321">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-322">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-325">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-326">event</span><span class="sxs-lookup"><span data-stu-id="c523d-326">Event</span></span>|<span data-ttu-id="c523d-327">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-327">Event Id</span></span>|<span data-ttu-id="c523d-328">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="c523d-329">3</span><span class="sxs-lookup"><span data-stu-id="c523d-329">3</span></span>|<span data-ttu-id="c523d-330">Il ripristino dalla sospensione di Common Language Runtime è terminato.</span><span class="sxs-lookup"><span data-stu-id="c523d-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="c523d-331">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-331">No event data.</span></span>  
  
 [<span data-ttu-id="c523d-332">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="c523d-333">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="c523d-334">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-335">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-335">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-336">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-339">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-340">event</span><span class="sxs-lookup"><span data-stu-id="c523d-340">Event</span></span>|<span data-ttu-id="c523d-341">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-341">Event ID</span></span>|<span data-ttu-id="c523d-342">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="c523d-343">9</span><span class="sxs-lookup"><span data-stu-id="c523d-343">9</span></span>|<span data-ttu-id="c523d-344">Inizio della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="c523d-345">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-346">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-346">Field name</span></span>|<span data-ttu-id="c523d-347">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-347">Data type</span></span>|<span data-ttu-id="c523d-348">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="c523d-349">Reason</span></span>|<span data-ttu-id="c523d-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-350">win:UInt16</span></span>|<span data-ttu-id="c523d-351">0x0 - Altro.</span><span class="sxs-lookup"><span data-stu-id="c523d-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="c523d-352">0x1 - Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="c523d-353">0x2 - Arresto del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c523d-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="c523d-354">0x3. - Lancio del codice.</span><span class="sxs-lookup"><span data-stu-id="c523d-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="c523d-355">0x4 - Arresto.</span><span class="sxs-lookup"><span data-stu-id="c523d-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="c523d-356">0x5 - Debugger.</span><span class="sxs-lookup"><span data-stu-id="c523d-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="c523d-357">0x6 - Preparazione per l'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="c523d-358">Conteggio</span><span class="sxs-lookup"><span data-stu-id="c523d-358">Count</span></span>|<span data-ttu-id="c523d-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-359">win:UInt32</span></span>|<span data-ttu-id="c523d-360">Il conteggio di Garbage Collection al momento.</span><span class="sxs-lookup"><span data-stu-id="c523d-360">The GC count at the time.</span></span> <span data-ttu-id="c523d-361">In genere, dopo di questo si assiste a un evento di avvio GC successivo. Il conteggio corrisponde al conteggio corrente + 1 quando si aumenta l'indice di GC durante un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="c523d-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-362">ClrInstanceID</span></span>|<span data-ttu-id="c523d-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-363">win:UInt16</span></span>|<span data-ttu-id="c523d-364">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c523d-365">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="c523d-366">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="c523d-367">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="c523d-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="c523d-368">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-368">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-369">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-372">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="c523d-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="c523d-373">event</span><span class="sxs-lookup"><span data-stu-id="c523d-373">Event</span></span>|<span data-ttu-id="c523d-374">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-374">Event ID</span></span>|<span data-ttu-id="c523d-375">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="c523d-376">8</span><span class="sxs-lookup"><span data-stu-id="c523d-376">8</span></span>|<span data-ttu-id="c523d-377">Fine della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c523d-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="c523d-378">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-378">No event data.</span></span>  
  
 [<span data-ttu-id="c523d-379">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="c523d-380">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="c523d-381">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-382">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-382">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-383">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-386">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-387">event</span><span class="sxs-lookup"><span data-stu-id="c523d-387">Event</span></span>|<span data-ttu-id="c523d-388">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-388">Event ID</span></span>|<span data-ttu-id="c523d-389">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="c523d-390">10</span><span class="sxs-lookup"><span data-stu-id="c523d-390">10</span></span>|<span data-ttu-id="c523d-391">Ogni volta vengono allocati circa 100 KB.</span><span class="sxs-lookup"><span data-stu-id="c523d-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="c523d-392">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-393">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-393">Field name</span></span>|<span data-ttu-id="c523d-394">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-394">Data type</span></span>|<span data-ttu-id="c523d-395">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="c523d-396">AllocationAmount</span></span>|<span data-ttu-id="c523d-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-397">win:UInt32</span></span>|<span data-ttu-id="c523d-398">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="c523d-398">The allocation size, in bytes.</span></span> <span data-ttu-id="c523d-399">Questo valore è preciso per le allocazioni minori della lunghezza di un ULONG (4.294.967.295 byte).</span><span class="sxs-lookup"><span data-stu-id="c523d-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="c523d-400">Se l'allocazione è maggiore, questo campo contiene un valore troncato.</span><span class="sxs-lookup"><span data-stu-id="c523d-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="c523d-401">Usare `AllocationAmount64` per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="c523d-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="c523d-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="c523d-402">AllocationKind</span></span>|<span data-ttu-id="c523d-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-403">win:UInt32</span></span>|<span data-ttu-id="c523d-404">0x0 - Allocazione di oggetti piccoli (l'allocazione è nell'heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="c523d-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="c523d-405">0x1 - Allocazione di oggetti grandi (l'allocazione è nell'heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="c523d-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="c523d-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-406">ClrInstanceID</span></span>|<span data-ttu-id="c523d-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-407">win:UInt16</span></span>|<span data-ttu-id="c523d-408">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="c523d-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="c523d-409">AllocationAmount64</span></span>|<span data-ttu-id="c523d-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="c523d-410">win:UInt64</span></span>|<span data-ttu-id="c523d-411">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="c523d-411">The allocation size, in bytes.</span></span> <span data-ttu-id="c523d-412">Questo valore è preciso per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="c523d-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="c523d-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="c523d-413">TypeId</span></span>|<span data-ttu-id="c523d-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="c523d-414">win:Pointer</span></span>|<span data-ttu-id="c523d-415">Indirizzo di MethodTable.</span><span class="sxs-lookup"><span data-stu-id="c523d-415">The address of the MethodTable.</span></span> <span data-ttu-id="c523d-416">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è l'indirizzo di MethodTable che corrisponde all'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="c523d-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="c523d-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="c523d-417">TypeName</span></span>|<span data-ttu-id="c523d-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="c523d-418">win:UnicodeString</span></span>|<span data-ttu-id="c523d-419">Nome del tipo che è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="c523d-419">The name of the type that was allocated.</span></span> <span data-ttu-id="c523d-420">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è il tipo dell'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="c523d-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="c523d-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="c523d-421">HeapIndex</span></span>|<span data-ttu-id="c523d-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-422">win:UInt32</span></span>|<span data-ttu-id="c523d-423">Heap in cui l'oggetto è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="c523d-423">The heap where the object was allocated.</span></span> <span data-ttu-id="c523d-424">Questo valore è 0 (zero) durante l'esecuzione della procedura di Garbage Collection per workstation.</span><span class="sxs-lookup"><span data-stu-id="c523d-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="c523d-425">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="c523d-426">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="c523d-427">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-428">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-428">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-429">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-432">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-433">event</span><span class="sxs-lookup"><span data-stu-id="c523d-433">Event</span></span>|<span data-ttu-id="c523d-434">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-434">Event ID</span></span>|<span data-ttu-id="c523d-435">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="c523d-436">14</span><span class="sxs-lookup"><span data-stu-id="c523d-436">14</span></span>|<span data-ttu-id="c523d-437">Inizio dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="c523d-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="c523d-438">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-438">No event data.</span></span>  
  
 [<span data-ttu-id="c523d-439">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="c523d-440">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="c523d-441">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-442">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-442">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-443">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-446">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-447">event</span><span class="sxs-lookup"><span data-stu-id="c523d-447">Event</span></span>|<span data-ttu-id="c523d-448">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-448">Event ID</span></span>|<span data-ttu-id="c523d-449">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="c523d-450">13</span><span class="sxs-lookup"><span data-stu-id="c523d-450">13</span></span>|<span data-ttu-id="c523d-451">Fine dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="c523d-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="c523d-452">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="c523d-453">Nome campo</span><span class="sxs-lookup"><span data-stu-id="c523d-453">Field name</span></span>|<span data-ttu-id="c523d-454">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c523d-454">Data type</span></span>|<span data-ttu-id="c523d-455">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c523d-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="c523d-456">Conteggio</span><span class="sxs-lookup"><span data-stu-id="c523d-456">Count</span></span>|<span data-ttu-id="c523d-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="c523d-457">win:UInt32</span></span>|<span data-ttu-id="c523d-458">Numero di finalizzatori eseguiti.</span><span class="sxs-lookup"><span data-stu-id="c523d-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="c523d-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="c523d-459">ClrInstanceID</span></span>|<span data-ttu-id="c523d-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="c523d-460">win:UInt16</span></span>|<span data-ttu-id="c523d-461">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="c523d-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="c523d-462">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="c523d-463">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="c523d-464">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-465">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-465">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-466">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-468">Informational (4)</span></span>|  
|<span data-ttu-id="c523d-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c523d-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c523d-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-471">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-472">event</span><span class="sxs-lookup"><span data-stu-id="c523d-472">Event</span></span>|<span data-ttu-id="c523d-473">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-473">Event ID</span></span>|<span data-ttu-id="c523d-474">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="c523d-475">11</span><span class="sxs-lookup"><span data-stu-id="c523d-475">11</span></span>|<span data-ttu-id="c523d-476">È stato creato il thread di Garbage Collection in modalità simultanea</span><span class="sxs-lookup"><span data-stu-id="c523d-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="c523d-477">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-477">No event data.</span></span>  
  
 [<span data-ttu-id="c523d-478">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="c523d-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="c523d-479">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="c523d-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="c523d-480">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="c523d-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="c523d-481">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="c523d-481">Keyword for raising the event</span></span>|<span data-ttu-id="c523d-482">Livello</span><span class="sxs-lookup"><span data-stu-id="c523d-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="c523d-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="c523d-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="c523d-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-484">Informational (4)</span></span>|  
|<span data-ttu-id="c523d-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="c523d-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="c523d-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="c523d-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="c523d-487">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="c523d-488">event</span><span class="sxs-lookup"><span data-stu-id="c523d-488">Event</span></span>|<span data-ttu-id="c523d-489">ID evento</span><span class="sxs-lookup"><span data-stu-id="c523d-489">Event ID</span></span>|<span data-ttu-id="c523d-490">Generato quando</span><span class="sxs-lookup"><span data-stu-id="c523d-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="c523d-491">12</span><span class="sxs-lookup"><span data-stu-id="c523d-491">12</span></span>|<span data-ttu-id="c523d-492">È stato terminato il thread di Garbage Collection in modalità simultanea.</span><span class="sxs-lookup"><span data-stu-id="c523d-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="c523d-493">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c523d-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c523d-494">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c523d-494">See also</span></span>

- [<span data-ttu-id="c523d-495">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="c523d-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
