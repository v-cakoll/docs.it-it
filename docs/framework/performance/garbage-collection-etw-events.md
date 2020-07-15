---
title: Eventi ETW di Garbage Collection
description: Visualizzare informazioni dettagliate sugli eventi ETW Garbage Collection. Gli eventi trattati includono GCStart_V1, GCEnd_V1, GCHeapStats_V1, GCCreateSegment_V1 e altro ancora.
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
ms.openlocfilehash: 58ad874ef6a12c18c404640aa66577c391573534
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309742"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="4f295-104">Eventi ETW di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="4f295-104">Garbage Collection ETW Events</span></span>

<span data-ttu-id="4f295-105">Questi eventi raccolgono informazioni relative alla Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="4f295-105">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="4f295-106">ai fini della diagnostica e del debug, tra cui stabilire quante volte è stato eseguito il processo di Garbage Collection, la quantità di memoria liberata durante la procedura di Garbage Collection e così via.</span><span class="sxs-lookup"><span data-stu-id="4f295-106">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="4f295-107">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="4f295-107">This category consists of the following events:</span></span>

- [<span data-ttu-id="4f295-108">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-108">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="4f295-109">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-109">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="4f295-110">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-110">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="4f295-111">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-111">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="4f295-112">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-112">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="4f295-113">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-113">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="4f295-114">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-114">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="4f295-115">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-115">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="4f295-116">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-116">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="4f295-117">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-117">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="4f295-118">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-118">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="4f295-119">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-119">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="4f295-120">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-120">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="4f295-121">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-121">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="4f295-122">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-122">GCStart_V1 Event</span></span>  

<span data-ttu-id="4f295-123">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="4f295-123">The following table shows the keyword and level.</span></span> <span data-ttu-id="4f295-124">Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4f295-124">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="4f295-125">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-125">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-126">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-127">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-127">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-128">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-128">Informational (4)</span></span>|

<span data-ttu-id="4f295-129">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-129">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-130">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-130">Event</span></span>|<span data-ttu-id="4f295-131">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-131">Event ID</span></span>|<span data-ttu-id="4f295-132">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="4f295-133">1</span><span class="sxs-lookup"><span data-stu-id="4f295-133">1</span></span>|<span data-ttu-id="4f295-134">È stata avviata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-134">A garbage collection has started.</span></span>|

<span data-ttu-id="4f295-135">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-135">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-136">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-136">Field name</span></span>|<span data-ttu-id="4f295-137">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-137">Data type</span></span>|<span data-ttu-id="4f295-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-138">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-139">Conteggio</span><span class="sxs-lookup"><span data-stu-id="4f295-139">Count</span></span>|<span data-ttu-id="4f295-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-140">win:UInt32</span></span>|<span data-ttu-id="4f295-141">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-141">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="4f295-142">Livello nidificazione</span><span class="sxs-lookup"><span data-stu-id="4f295-142">Depth</span></span>|<span data-ttu-id="4f295-143">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-143">win:UInt32</span></span>|<span data-ttu-id="4f295-144">La generazione che viene raccolta.</span><span class="sxs-lookup"><span data-stu-id="4f295-144">The generation that is being collected.</span></span>|
|<span data-ttu-id="4f295-145">Motivo</span><span class="sxs-lookup"><span data-stu-id="4f295-145">Reason</span></span>|<span data-ttu-id="4f295-146">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-146">win:UInt32</span></span>|<span data-ttu-id="4f295-147">Motivo per cui è stata attivata la Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="4f295-147">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="4f295-148">0x0 - Allocazione heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="4f295-148">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="4f295-149">0x1 - Indotto.</span><span class="sxs-lookup"><span data-stu-id="4f295-149">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="4f295-150">0x2 - Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="4f295-150">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="4f295-151">0x3 - Vuoto.</span><span class="sxs-lookup"><span data-stu-id="4f295-151">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="4f295-152">0x4 - Allocazione heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="4f295-152">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="4f295-153">0x5 - Spazio esaurito (per heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="4f295-153">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="4f295-154">0x6 - Spazio esaurito (per heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="4f295-154">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="4f295-155">0x7 - Indotto ma non forzato come blocco.</span><span class="sxs-lookup"><span data-stu-id="4f295-155">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="4f295-156">Type</span><span class="sxs-lookup"><span data-stu-id="4f295-156">Type</span></span>|<span data-ttu-id="4f295-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-157">win:UInt32</span></span>|<span data-ttu-id="4f295-158">0x0 - Un'operazione di Garbage Collection bloccante è stata eseguita all'esterno della procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="4f295-158">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="4f295-159">0x1 - Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="4f295-159">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="4f295-160">0x2 - Un'operazione di Garbage Collection bloccante è stata eseguita durante la procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="4f295-160">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="4f295-161">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-161">ClrInstanceID</span></span>|<span data-ttu-id="4f295-162">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-162">win:UInt16</span></span>|<span data-ttu-id="4f295-163">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-163">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="4f295-164">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-164">GCEnd_V1 Event</span></span>

<span data-ttu-id="4f295-165">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-165">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-166">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-166">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-167">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-167">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-168">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-168">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-169">Informational (4)</span></span>|

<span data-ttu-id="4f295-170">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-170">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-171">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-171">Event</span></span>|<span data-ttu-id="4f295-172">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-172">Event ID</span></span>|<span data-ttu-id="4f295-173">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-173">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="4f295-174">2</span><span class="sxs-lookup"><span data-stu-id="4f295-174">2</span></span>|<span data-ttu-id="4f295-175">È stata terminata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-175">The garbage collection has ended.</span></span>|

<span data-ttu-id="4f295-176">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-176">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-177">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-177">Field name</span></span>|<span data-ttu-id="4f295-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-178">Data type</span></span>|<span data-ttu-id="4f295-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-179">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-180">Conteggio</span><span class="sxs-lookup"><span data-stu-id="4f295-180">Count</span></span>|<span data-ttu-id="4f295-181">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-181">win:UInt32</span></span>|<span data-ttu-id="4f295-182">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-182">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="4f295-183">Livello nidificazione</span><span class="sxs-lookup"><span data-stu-id="4f295-183">Depth</span></span>|<span data-ttu-id="4f295-184">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-184">win:UInt32</span></span>|<span data-ttu-id="4f295-185">La generazione che è stata raccolta.</span><span class="sxs-lookup"><span data-stu-id="4f295-185">The generation that was collected.</span></span>|
|<span data-ttu-id="4f295-186">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-186">ClrInstanceID</span></span>|<span data-ttu-id="4f295-187">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-187">win:UInt16</span></span>|<span data-ttu-id="4f295-188">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-188">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="4f295-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-189">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="4f295-190">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-190">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-191">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-191">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-192">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-192">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-194">Informational (4)</span></span>|

<span data-ttu-id="4f295-195">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-195">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-196">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-196">Event</span></span>|<span data-ttu-id="4f295-197">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-197">Event ID</span></span>|<span data-ttu-id="4f295-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-198">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="4f295-199">4</span><span class="sxs-lookup"><span data-stu-id="4f295-199">4</span></span>|<span data-ttu-id="4f295-200">Mostra le statistiche heap alla fine di ogni Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-200">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="4f295-201">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-201">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-202">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-202">Field name</span></span>|<span data-ttu-id="4f295-203">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-203">Data type</span></span>|<span data-ttu-id="4f295-204">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-204">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="4f295-205">GenerationSize0</span></span>|<span data-ttu-id="4f295-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-206">win:UInt64</span></span>|<span data-ttu-id="4f295-207">Dimensione, in byte, della memoria della generazione 0.</span><span class="sxs-lookup"><span data-stu-id="4f295-207">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="4f295-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="4f295-208">TotalPromotedSize0</span></span>|<span data-ttu-id="4f295-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-209">win:UInt64</span></span>|<span data-ttu-id="4f295-210">Numero di byte promossi dalla generazione 0 alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="4f295-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="4f295-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="4f295-211">GenerationSize1</span></span>|<span data-ttu-id="4f295-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-212">win:UInt64</span></span>|<span data-ttu-id="4f295-213">Dimensione, in byte, della memoria di generazione 1.</span><span class="sxs-lookup"><span data-stu-id="4f295-213">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="4f295-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="4f295-214">TotalPromotedSize1</span></span>|<span data-ttu-id="4f295-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-215">win:UInt64</span></span>|<span data-ttu-id="4f295-216">Numero di byte promossi dalla generazione 1 alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="4f295-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="4f295-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="4f295-217">GenerationSize2</span></span>|<span data-ttu-id="4f295-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-218">win:UInt64</span></span>|<span data-ttu-id="4f295-219">Dimensione, in byte, della memoria della generazione 2.</span><span class="sxs-lookup"><span data-stu-id="4f295-219">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="4f295-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="4f295-220">TotalPromotedSize2</span></span>|<span data-ttu-id="4f295-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-221">win:UInt64</span></span>|<span data-ttu-id="4f295-222">Numero di byte rimasti nella generazione 2 dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="4f295-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="4f295-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="4f295-223">GenerationSize3</span></span>|<span data-ttu-id="4f295-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-224">win:UInt64</span></span>|<span data-ttu-id="4f295-225">Dimensione, in byte, dell'heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="4f295-225">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="4f295-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="4f295-226">TotalPromotedSize3</span></span>|<span data-ttu-id="4f295-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-227">win:UInt64</span></span>|<span data-ttu-id="4f295-228">Numero di byte rimasti nell'heap oggetto grande dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="4f295-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="4f295-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="4f295-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="4f295-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-230">win:UInt64</span></span>|<span data-ttu-id="4f295-231">Dimensione totale, in byte, degli oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f295-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="4f295-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="4f295-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="4f295-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-233">win:UInt64</span></span>|<span data-ttu-id="4f295-234">Numero di oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="4f295-234">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="4f295-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="4f295-235">PinnedObjectCount</span></span>|<span data-ttu-id="4f295-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-236">win:UInt32</span></span>|<span data-ttu-id="4f295-237">Numero di oggetti bloccati (fissi).</span><span class="sxs-lookup"><span data-stu-id="4f295-237">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="4f295-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="4f295-238">SinkBlockCount</span></span>|<span data-ttu-id="4f295-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-239">win:UInt32</span></span>|<span data-ttu-id="4f295-240">Numero di blocchi di sincronizzazione in uso.</span><span class="sxs-lookup"><span data-stu-id="4f295-240">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="4f295-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="4f295-241">GCHandleCount</span></span>|<span data-ttu-id="4f295-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-242">win:UInt32</span></span>|<span data-ttu-id="4f295-243">Numero di handle di Garbage Collection in uso.</span><span class="sxs-lookup"><span data-stu-id="4f295-243">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="4f295-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-244">ClrInstanceID</span></span>|<span data-ttu-id="4f295-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-245">win:UInt16</span></span>|<span data-ttu-id="4f295-246">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="4f295-247">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-247">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="4f295-248">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-248">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-249">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-249">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-250">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-250">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-251">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-251">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-252">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-252">Informational (4)</span></span>|

<span data-ttu-id="4f295-253">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-253">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-254">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-254">Event</span></span>|<span data-ttu-id="4f295-255">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-255">Event ID</span></span>|<span data-ttu-id="4f295-256">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-256">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="4f295-257">5</span><span class="sxs-lookup"><span data-stu-id="4f295-257">5</span></span>|<span data-ttu-id="4f295-258">È stato creato un nuovo segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-258">A new garbage collection segment has been created.</span></span> <span data-ttu-id="4f295-259">Inoltre, quando la traccia è attivata su un processo già in esecuzione, questo evento viene generato per ogni segmento esistente.</span><span class="sxs-lookup"><span data-stu-id="4f295-259">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="4f295-260">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-260">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-261">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-261">Field name</span></span>|<span data-ttu-id="4f295-262">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-262">Data type</span></span>|<span data-ttu-id="4f295-263">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-263">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-264">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="4f295-264">Address</span></span>|<span data-ttu-id="4f295-265">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-265">win:UInt64</span></span>|<span data-ttu-id="4f295-266">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="4f295-266">The address of the segment.</span></span>|
|<span data-ttu-id="4f295-267">Dimensione</span><span class="sxs-lookup"><span data-stu-id="4f295-267">Size</span></span>|<span data-ttu-id="4f295-268">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-268">win:UInt64</span></span>|<span data-ttu-id="4f295-269">Dimensione del segmento.</span><span class="sxs-lookup"><span data-stu-id="4f295-269">The size of the segment.</span></span>|
|<span data-ttu-id="4f295-270">Type</span><span class="sxs-lookup"><span data-stu-id="4f295-270">Type</span></span>|<span data-ttu-id="4f295-271">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-271">win:UInt32</span></span>|<span data-ttu-id="4f295-272">0x0 - Heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="4f295-272">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="4f295-273">0x1 - Heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="4f295-273">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="4f295-274">0x2 - Heap di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4f295-274">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="4f295-275">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-275">ClrInstanceID</span></span>|<span data-ttu-id="4f295-276">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-276">win:UInt16</span></span>|<span data-ttu-id="4f295-277">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-277">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="4f295-278">Si noti che la dimensione dei segmenti allocati dal Garbage Collector è specifico dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici.</span><span class="sxs-lookup"><span data-stu-id="4f295-278">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="4f295-279">L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.</span><span class="sxs-lookup"><span data-stu-id="4f295-279">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="4f295-280">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-280">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="4f295-281">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-281">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-282">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-282">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-283">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-283">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-284">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-284">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-285">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-285">Informational (4)</span></span>|

<span data-ttu-id="4f295-286">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-286">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-287">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-287">Event</span></span>|<span data-ttu-id="4f295-288">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-288">Event ID</span></span>|<span data-ttu-id="4f295-289">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-289">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="4f295-290">6</span><span class="sxs-lookup"><span data-stu-id="4f295-290">6</span></span>|<span data-ttu-id="4f295-291">È stato rilasciato un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-291">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="4f295-292">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-292">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-293">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-293">Field name</span></span>|<span data-ttu-id="4f295-294">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-294">Data type</span></span>|<span data-ttu-id="4f295-295">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-295">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-296">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="4f295-296">Address</span></span>|<span data-ttu-id="4f295-297">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-297">win:UInt64</span></span>|<span data-ttu-id="4f295-298">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="4f295-298">The address of the segment.</span></span>|
|<span data-ttu-id="4f295-299">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-299">ClrInstanceID</span></span>|<span data-ttu-id="4f295-300">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-300">win:UInt16</span></span>|<span data-ttu-id="4f295-301">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-301">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="4f295-302">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-302">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="4f295-303">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-303">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-304">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-304">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-305">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-305">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-306">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-306">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-307">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-307">Informational (4)</span></span>|

<span data-ttu-id="4f295-308">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-308">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-309">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-309">Event</span></span>|<span data-ttu-id="4f295-310">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-310">Event ID</span></span>|<span data-ttu-id="4f295-311">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-311">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="4f295-312">7</span><span class="sxs-lookup"><span data-stu-id="4f295-312">7</span></span>|<span data-ttu-id="4f295-313">Il ripristino dalla sospensione di Common Language Runtime è iniziato.</span><span class="sxs-lookup"><span data-stu-id="4f295-313">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="4f295-314">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f295-314">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="4f295-315">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-315">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="4f295-316">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-316">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-317">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-317">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-318">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-318">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-319">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-319">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-320">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-320">Informational (4)</span></span>|

<span data-ttu-id="4f295-321">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-321">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-322">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-322">Event</span></span>|<span data-ttu-id="4f295-323">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-323">Event Id</span></span>|<span data-ttu-id="4f295-324">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-324">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="4f295-325">3</span><span class="sxs-lookup"><span data-stu-id="4f295-325">3</span></span>|<span data-ttu-id="4f295-326">Il ripristino dalla sospensione di Common Language Runtime è terminato.</span><span class="sxs-lookup"><span data-stu-id="4f295-326">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="4f295-327">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f295-327">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="4f295-328">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-328">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="4f295-329">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-329">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-330">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-330">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-331">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-331">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-332">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-332">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-333">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-333">Informational (4)</span></span>|

<span data-ttu-id="4f295-334">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-334">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-335">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-335">Event</span></span>|<span data-ttu-id="4f295-336">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-336">Event ID</span></span>|<span data-ttu-id="4f295-337">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-337">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="4f295-338">9</span><span class="sxs-lookup"><span data-stu-id="4f295-338">9</span></span>|<span data-ttu-id="4f295-339">Inizio della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-339">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="4f295-340">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-340">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-341">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-341">Field name</span></span>|<span data-ttu-id="4f295-342">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-342">Data type</span></span>|<span data-ttu-id="4f295-343">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-343">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-344">Motivo</span><span class="sxs-lookup"><span data-stu-id="4f295-344">Reason</span></span>|<span data-ttu-id="4f295-345">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-345">win:UInt16</span></span>|<span data-ttu-id="4f295-346">0x0 - Altro.</span><span class="sxs-lookup"><span data-stu-id="4f295-346">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="4f295-347">0x1 - Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-347">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="4f295-348">0x2 - Arresto del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="4f295-348">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="4f295-349">0x3. - Lancio del codice.</span><span class="sxs-lookup"><span data-stu-id="4f295-349">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="4f295-350">0x4 - Arresto.</span><span class="sxs-lookup"><span data-stu-id="4f295-350">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="4f295-351">0x5 - Debugger.</span><span class="sxs-lookup"><span data-stu-id="4f295-351">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="4f295-352">0x6 - Preparazione per l'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-352">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="4f295-353">Conteggio</span><span class="sxs-lookup"><span data-stu-id="4f295-353">Count</span></span>|<span data-ttu-id="4f295-354">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-354">win:UInt32</span></span>|<span data-ttu-id="4f295-355">Il conteggio di Garbage Collection al momento.</span><span class="sxs-lookup"><span data-stu-id="4f295-355">The GC count at the time.</span></span> <span data-ttu-id="4f295-356">In genere, dopo di questo si assiste a un evento di avvio GC successivo. Il conteggio corrisponde al conteggio corrente + 1 quando si aumenta l'indice di GC durante un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-356">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="4f295-357">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-357">ClrInstanceID</span></span>|<span data-ttu-id="4f295-358">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-358">win:UInt16</span></span>|<span data-ttu-id="4f295-359">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-359">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="4f295-360">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-360">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="4f295-361">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-361">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-362">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-362">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-363">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-363">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-364">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-364">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-365">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-365">Informational (4)</span></span>|

<span data-ttu-id="4f295-366">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-366">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-367">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-367">Event</span></span>|<span data-ttu-id="4f295-368">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-368">Event ID</span></span>|<span data-ttu-id="4f295-369">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-369">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="4f295-370">8</span><span class="sxs-lookup"><span data-stu-id="4f295-370">8</span></span>|<span data-ttu-id="4f295-371">Fine della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f295-371">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="4f295-372">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f295-372">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="4f295-373">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-373">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="4f295-374">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-374">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-375">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-375">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-376">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-376">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-377">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-377">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-378">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-378">Informational (4)</span></span>|

<span data-ttu-id="4f295-379">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-379">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-380">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-380">Event</span></span>|<span data-ttu-id="4f295-381">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-381">Event ID</span></span>|<span data-ttu-id="4f295-382">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-382">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="4f295-383">10</span><span class="sxs-lookup"><span data-stu-id="4f295-383">10</span></span>|<span data-ttu-id="4f295-384">Ogni volta vengono allocati circa 100 KB.</span><span class="sxs-lookup"><span data-stu-id="4f295-384">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="4f295-385">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-385">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-386">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-386">Field name</span></span>|<span data-ttu-id="4f295-387">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-387">Data type</span></span>|<span data-ttu-id="4f295-388">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-388">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-389">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="4f295-389">AllocationAmount</span></span>|<span data-ttu-id="4f295-390">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-390">win:UInt32</span></span>|<span data-ttu-id="4f295-391">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="4f295-391">The allocation size, in bytes.</span></span> <span data-ttu-id="4f295-392">Questo valore è preciso per le allocazioni minori della lunghezza di un ULONG (4.294.967.295 byte).</span><span class="sxs-lookup"><span data-stu-id="4f295-392">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="4f295-393">Se l'allocazione è maggiore, questo campo contiene un valore troncato.</span><span class="sxs-lookup"><span data-stu-id="4f295-393">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="4f295-394">Usare `AllocationAmount64` per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="4f295-394">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="4f295-395">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="4f295-395">AllocationKind</span></span>|<span data-ttu-id="4f295-396">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-396">win:UInt32</span></span>|<span data-ttu-id="4f295-397">0x0 - Allocazione di oggetti piccoli (l'allocazione è nell'heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="4f295-397">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="4f295-398">0x1 - Allocazione di oggetti grandi (l'allocazione è nell'heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="4f295-398">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="4f295-399">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-399">ClrInstanceID</span></span>|<span data-ttu-id="4f295-400">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-400">win:UInt16</span></span>|<span data-ttu-id="4f295-401">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-401">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="4f295-402">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="4f295-402">AllocationAmount64</span></span>|<span data-ttu-id="4f295-403">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4f295-403">win:UInt64</span></span>|<span data-ttu-id="4f295-404">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="4f295-404">The allocation size, in bytes.</span></span> <span data-ttu-id="4f295-405">Questo valore è preciso per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="4f295-405">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="4f295-406">TypeId</span><span class="sxs-lookup"><span data-stu-id="4f295-406">TypeId</span></span>|<span data-ttu-id="4f295-407">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4f295-407">win:Pointer</span></span>|<span data-ttu-id="4f295-408">Indirizzo di MethodTable.</span><span class="sxs-lookup"><span data-stu-id="4f295-408">The address of the MethodTable.</span></span> <span data-ttu-id="4f295-409">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è l'indirizzo di MethodTable che corrisponde all'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="4f295-409">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="4f295-410">TypeName</span><span class="sxs-lookup"><span data-stu-id="4f295-410">TypeName</span></span>|<span data-ttu-id="4f295-411">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4f295-411">win:UnicodeString</span></span>|<span data-ttu-id="4f295-412">Nome del tipo che è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="4f295-412">The name of the type that was allocated.</span></span> <span data-ttu-id="4f295-413">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è il tipo dell'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="4f295-413">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="4f295-414">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="4f295-414">HeapIndex</span></span>|<span data-ttu-id="4f295-415">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-415">win:UInt32</span></span>|<span data-ttu-id="4f295-416">Heap in cui l'oggetto è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="4f295-416">The heap where the object was allocated.</span></span> <span data-ttu-id="4f295-417">Questo valore è 0 (zero) durante l'esecuzione della procedura di Garbage Collection per workstation.</span><span class="sxs-lookup"><span data-stu-id="4f295-417">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="4f295-418">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-418">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="4f295-419">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-419">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-420">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-420">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-421">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-421">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-422">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-422">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-423">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-423">Informational (4)</span></span>|

<span data-ttu-id="4f295-424">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-424">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-425">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-425">Event</span></span>|<span data-ttu-id="4f295-426">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-426">Event ID</span></span>|<span data-ttu-id="4f295-427">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-427">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="4f295-428">14</span><span class="sxs-lookup"><span data-stu-id="4f295-428">14</span></span>|<span data-ttu-id="4f295-429">Inizio dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="4f295-429">The start of running finalizers.</span></span>|

<span data-ttu-id="4f295-430">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f295-430">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="4f295-431">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-431">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="4f295-432">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-432">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-433">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-433">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-434">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-434">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-435">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-435">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-436">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-436">Informational (4)</span></span>|

<span data-ttu-id="4f295-437">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-437">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-438">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-438">Event</span></span>|<span data-ttu-id="4f295-439">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-439">Event ID</span></span>|<span data-ttu-id="4f295-440">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-440">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="4f295-441">13</span><span class="sxs-lookup"><span data-stu-id="4f295-441">13</span></span>|<span data-ttu-id="4f295-442">Fine dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="4f295-442">The end of running finalizers.</span></span>|

<span data-ttu-id="4f295-443">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-443">The following table shows the event data:</span></span>

|<span data-ttu-id="4f295-444">Nome campo</span><span class="sxs-lookup"><span data-stu-id="4f295-444">Field name</span></span>|<span data-ttu-id="4f295-445">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4f295-445">Data type</span></span>|<span data-ttu-id="4f295-446">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f295-446">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="4f295-447">Conteggio</span><span class="sxs-lookup"><span data-stu-id="4f295-447">Count</span></span>|<span data-ttu-id="4f295-448">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4f295-448">win:UInt32</span></span>|<span data-ttu-id="4f295-449">Numero di finalizzatori eseguiti.</span><span class="sxs-lookup"><span data-stu-id="4f295-449">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="4f295-450">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4f295-450">ClrInstanceID</span></span>|<span data-ttu-id="4f295-451">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4f295-451">win:UInt16</span></span>|<span data-ttu-id="4f295-452">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4f295-452">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="4f295-453">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-453">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="4f295-454">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-454">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-455">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-455">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-456">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-456">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-457">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-457">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-458">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-458">Informational (4)</span></span>|
|<span data-ttu-id="4f295-459">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4f295-459">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4f295-460">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-460">Informational (4)</span></span>|

<span data-ttu-id="4f295-461">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-461">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-462">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-462">Event</span></span>|<span data-ttu-id="4f295-463">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-463">Event ID</span></span>|<span data-ttu-id="4f295-464">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-464">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="4f295-465">11</span><span class="sxs-lookup"><span data-stu-id="4f295-465">11</span></span>|<span data-ttu-id="4f295-466">È stato creato il thread di Garbage Collection in modalità simultanea</span><span class="sxs-lookup"><span data-stu-id="4f295-466">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="4f295-467">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f295-467">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="4f295-468">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="4f295-468">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="4f295-469">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="4f295-469">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="4f295-470">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="4f295-470">Keyword for raising the event</span></span>|<span data-ttu-id="4f295-471">Livello</span><span class="sxs-lookup"><span data-stu-id="4f295-471">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="4f295-472">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4f295-472">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4f295-473">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-473">Informational (4)</span></span>|
|<span data-ttu-id="4f295-474">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4f295-474">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4f295-475">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4f295-475">Informational (4)</span></span>|

<span data-ttu-id="4f295-476">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="4f295-476">The following table shows the event information:</span></span>

|<span data-ttu-id="4f295-477">Evento</span><span class="sxs-lookup"><span data-stu-id="4f295-477">Event</span></span>|<span data-ttu-id="4f295-478">ID evento</span><span class="sxs-lookup"><span data-stu-id="4f295-478">Event ID</span></span>|<span data-ttu-id="4f295-479">Generato quando</span><span class="sxs-lookup"><span data-stu-id="4f295-479">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="4f295-480">12</span><span class="sxs-lookup"><span data-stu-id="4f295-480">12</span></span>|<span data-ttu-id="4f295-481">È stato terminato il thread di Garbage Collection in modalità simultanea.</span><span class="sxs-lookup"><span data-stu-id="4f295-481">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="4f295-482">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f295-482">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f295-483">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f295-483">See also</span></span>

- [<span data-ttu-id="4f295-484">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="4f295-484">CLR ETW Events</span></span>](clr-etw-events.md)
