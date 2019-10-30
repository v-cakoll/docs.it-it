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
ms.openlocfilehash: cd4a4699f115c5b134ea60e703607ff36c229a78
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040579"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="a94d0-102">Eventi ETW di Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a94d0-102">Garbage Collection ETW Events</span></span>

<span data-ttu-id="a94d0-103">Questi eventi raccolgono informazioni relative alla Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a94d0-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="a94d0-104">ai fini della diagnostica e del debug, tra cui stabilire quante volte è stato eseguito il processo di Garbage Collection, la quantità di memoria liberata durante la procedura di Garbage Collection e così via.</span><span class="sxs-lookup"><span data-stu-id="a94d0-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>

<span data-ttu-id="a94d0-105">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="a94d0-105">This category consists of the following events:</span></span>

- [<span data-ttu-id="a94d0-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-106">GCStart_V1 Event</span></span>](#gcstart_v1-event)
- [<span data-ttu-id="a94d0-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-107">GCEnd_V1 Event</span></span>](#gcend_v1-event)
- [<span data-ttu-id="a94d0-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1-event)
- [<span data-ttu-id="a94d0-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1-event)
- [<span data-ttu-id="a94d0-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1-event)
- [<span data-ttu-id="a94d0-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1-event)
- [<span data-ttu-id="a94d0-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1-event)
- [<span data-ttu-id="a94d0-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1-event)
- [<span data-ttu-id="a94d0-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1-event)
- [<span data-ttu-id="a94d0-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2-event)
- [<span data-ttu-id="a94d0-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1-event)
- [<span data-ttu-id="a94d0-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1-event)
- [<span data-ttu-id="a94d0-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1-event)
- [<span data-ttu-id="a94d0-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1-event)

## <a name="gcstart_v1-event"></a><span data-ttu-id="a94d0-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-120">GCStart_V1 Event</span></span>  

<span data-ttu-id="a94d0-121">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="a94d0-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="a94d0-122">Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a94d0-122">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="a94d0-123">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-123">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-124">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-124">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-126">Informational (4)</span></span>|

<span data-ttu-id="a94d0-127">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-127">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-128">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-128">Event</span></span>|<span data-ttu-id="a94d0-129">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-129">Event ID</span></span>|<span data-ttu-id="a94d0-130">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-130">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCStart_V1`|<span data-ttu-id="a94d0-131">1</span><span class="sxs-lookup"><span data-stu-id="a94d0-131">1</span></span>|<span data-ttu-id="a94d0-132">È stata avviata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-132">A garbage collection has started.</span></span>|

<span data-ttu-id="a94d0-133">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-133">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-134">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-134">Field name</span></span>|<span data-ttu-id="a94d0-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-135">Data type</span></span>|<span data-ttu-id="a94d0-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-136">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-137">Conteggio</span><span class="sxs-lookup"><span data-stu-id="a94d0-137">Count</span></span>|<span data-ttu-id="a94d0-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-138">win:UInt32</span></span>|<span data-ttu-id="a94d0-139">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-139">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="a94d0-140">Profondità</span><span class="sxs-lookup"><span data-stu-id="a94d0-140">Depth</span></span>|<span data-ttu-id="a94d0-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-141">win:UInt32</span></span>|<span data-ttu-id="a94d0-142">La generazione che viene raccolta.</span><span class="sxs-lookup"><span data-stu-id="a94d0-142">The generation that is being collected.</span></span>|
|<span data-ttu-id="a94d0-143">Motivo</span><span class="sxs-lookup"><span data-stu-id="a94d0-143">Reason</span></span>|<span data-ttu-id="a94d0-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-144">win:UInt32</span></span>|<span data-ttu-id="a94d0-145">Motivo per cui è stata attivata la Garbage Collection:</span><span class="sxs-lookup"><span data-stu-id="a94d0-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="a94d0-146">0x0 - Allocazione heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="a94d0-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="a94d0-147">0x1 - Indotto.</span><span class="sxs-lookup"><span data-stu-id="a94d0-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="a94d0-148">0x2 - Memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="a94d0-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="a94d0-149">0x3 - Vuoto.</span><span class="sxs-lookup"><span data-stu-id="a94d0-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="a94d0-150">0x4 - Allocazione heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="a94d0-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="a94d0-151">0x5 - Spazio esaurito (per heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="a94d0-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="a94d0-152">0x6 - Spazio esaurito (per heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="a94d0-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="a94d0-153">0x7 - Indotto ma non forzato come blocco.</span><span class="sxs-lookup"><span data-stu-id="a94d0-153">0x7 - Induced but not forced as blocking.</span></span>|
|<span data-ttu-id="a94d0-154">Digitare</span><span class="sxs-lookup"><span data-stu-id="a94d0-154">Type</span></span>|<span data-ttu-id="a94d0-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-155">win:UInt32</span></span>|<span data-ttu-id="a94d0-156">0x0 - Un'operazione di Garbage Collection bloccante è stata eseguita all'esterno della procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="a94d0-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="a94d0-157">0x1 - Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="a94d0-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="a94d0-158">0x2 - Un'operazione di Garbage Collection bloccante è stata eseguita durante la procedura di Garbage Collection in background.</span><span class="sxs-lookup"><span data-stu-id="a94d0-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|
|<span data-ttu-id="a94d0-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-159">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-160">win:UInt16</span></span>|<span data-ttu-id="a94d0-161">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcend_v1-event"></a><span data-ttu-id="a94d0-162">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-162">GCEnd_V1 Event</span></span>

<span data-ttu-id="a94d0-163">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-163">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-164">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-164">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-165">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-165">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-166">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-166">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-167">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-167">Informational (4)</span></span>|

<span data-ttu-id="a94d0-168">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-168">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-169">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-169">Event</span></span>|<span data-ttu-id="a94d0-170">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-170">Event ID</span></span>|<span data-ttu-id="a94d0-171">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-171">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCEnd_V1`|<span data-ttu-id="a94d0-172">2</span><span class="sxs-lookup"><span data-stu-id="a94d0-172">2</span></span>|<span data-ttu-id="a94d0-173">È stata terminata una procedura di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-173">The garbage collection has ended.</span></span>|

<span data-ttu-id="a94d0-174">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-174">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-175">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-175">Field name</span></span>|<span data-ttu-id="a94d0-176">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-176">Data type</span></span>|<span data-ttu-id="a94d0-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-177">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-178">Conteggio</span><span class="sxs-lookup"><span data-stu-id="a94d0-178">Count</span></span>|<span data-ttu-id="a94d0-179">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-179">win:UInt32</span></span>|<span data-ttu-id="a94d0-180">L' *ennesima*Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-180">The *n*th garbage collection.</span></span>|
|<span data-ttu-id="a94d0-181">Profondità</span><span class="sxs-lookup"><span data-stu-id="a94d0-181">Depth</span></span>|<span data-ttu-id="a94d0-182">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-182">win:UInt32</span></span>|<span data-ttu-id="a94d0-183">La generazione che è stata raccolta.</span><span class="sxs-lookup"><span data-stu-id="a94d0-183">The generation that was collected.</span></span>|
|<span data-ttu-id="a94d0-184">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-184">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-185">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-185">win:UInt16</span></span>|<span data-ttu-id="a94d0-186">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-186">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcheapstats_v1-event"></a><span data-ttu-id="a94d0-187">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-187">GCHeapStats_V1 Event</span></span>

<span data-ttu-id="a94d0-188">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-188">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-189">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-189">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-190">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-190">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-191">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-191">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-192">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-192">Informational (4)</span></span>|

<span data-ttu-id="a94d0-193">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-193">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-194">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-194">Event</span></span>|<span data-ttu-id="a94d0-195">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-195">Event ID</span></span>|<span data-ttu-id="a94d0-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-196">Description</span></span>|
|-----------|--------------|-----------------|
|`GCHeapStats_V1`|<span data-ttu-id="a94d0-197">4</span><span class="sxs-lookup"><span data-stu-id="a94d0-197">4</span></span>|<span data-ttu-id="a94d0-198">Mostra le statistiche heap alla fine di ogni Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-198">Shows the heap statistics at the end of each garbage collection.</span></span>|

<span data-ttu-id="a94d0-199">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-199">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-200">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-200">Field name</span></span>|<span data-ttu-id="a94d0-201">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-201">Data type</span></span>|<span data-ttu-id="a94d0-202">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-202">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-203">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="a94d0-203">GenerationSize0</span></span>|<span data-ttu-id="a94d0-204">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-204">win:UInt64</span></span>|<span data-ttu-id="a94d0-205">Dimensione, in byte, della memoria della generazione 0.</span><span class="sxs-lookup"><span data-stu-id="a94d0-205">The size, in bytes, of generation 0 memory.</span></span>|
|<span data-ttu-id="a94d0-206">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="a94d0-206">TotalPromotedSize0</span></span>|<span data-ttu-id="a94d0-207">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-207">win:UInt64</span></span>|<span data-ttu-id="a94d0-208">Numero di byte promossi dalla generazione 0 alla generazione 1.</span><span class="sxs-lookup"><span data-stu-id="a94d0-208">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|
|<span data-ttu-id="a94d0-209">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="a94d0-209">GenerationSize1</span></span>|<span data-ttu-id="a94d0-210">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-210">win:UInt64</span></span>|<span data-ttu-id="a94d0-211">Dimensione, in byte, della memoria di generazione 1.</span><span class="sxs-lookup"><span data-stu-id="a94d0-211">The size, in bytes, of generation 1 memory.</span></span>|
|<span data-ttu-id="a94d0-212">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="a94d0-212">TotalPromotedSize1</span></span>|<span data-ttu-id="a94d0-213">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-213">win:UInt64</span></span>|<span data-ttu-id="a94d0-214">Numero di byte promossi dalla generazione 1 alla generazione 2.</span><span class="sxs-lookup"><span data-stu-id="a94d0-214">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|
|<span data-ttu-id="a94d0-215">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="a94d0-215">GenerationSize2</span></span>|<span data-ttu-id="a94d0-216">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-216">win:UInt64</span></span>|<span data-ttu-id="a94d0-217">Dimensione, in byte, della memoria della generazione 2.</span><span class="sxs-lookup"><span data-stu-id="a94d0-217">The size, in bytes, of generation 2 memory.</span></span>|
|<span data-ttu-id="a94d0-218">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="a94d0-218">TotalPromotedSize2</span></span>|<span data-ttu-id="a94d0-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-219">win:UInt64</span></span>|<span data-ttu-id="a94d0-220">Numero di byte rimasti nella generazione 2 dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="a94d0-220">The number of bytes that survived in generation 2 after the last collection.</span></span>|
|<span data-ttu-id="a94d0-221">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="a94d0-221">GenerationSize3</span></span>|<span data-ttu-id="a94d0-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-222">win:UInt64</span></span>|<span data-ttu-id="a94d0-223">Dimensione, in byte, dell'heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="a94d0-223">The size, in bytes, of the large object heap.</span></span>|
|<span data-ttu-id="a94d0-224">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="a94d0-224">TotalPromotedSize3</span></span>|<span data-ttu-id="a94d0-225">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-225">win:UInt64</span></span>|<span data-ttu-id="a94d0-226">Numero di byte rimasti nell'heap oggetto grande dopo l'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="a94d0-226">The number of bytes that survived in the large object heap after the last collection.</span></span>|
|<span data-ttu-id="a94d0-227">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="a94d0-227">FinalizationPromotedSize</span></span>|<span data-ttu-id="a94d0-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-228">win:UInt64</span></span>|<span data-ttu-id="a94d0-229">Dimensione totale, in byte, degli oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a94d0-229">The total size, in bytes, of the objects that are ready for finalization.</span></span>|
|<span data-ttu-id="a94d0-230">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="a94d0-230">FinalizationPromotedCount</span></span>|<span data-ttu-id="a94d0-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-231">win:UInt64</span></span>|<span data-ttu-id="a94d0-232">Numero di oggetti pronti per la finalizzazione.</span><span class="sxs-lookup"><span data-stu-id="a94d0-232">The number of objects that are ready for finalization.</span></span>|
|<span data-ttu-id="a94d0-233">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="a94d0-233">PinnedObjectCount</span></span>|<span data-ttu-id="a94d0-234">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-234">win:UInt32</span></span>|<span data-ttu-id="a94d0-235">Numero di oggetti bloccati (fissi).</span><span class="sxs-lookup"><span data-stu-id="a94d0-235">The number of pinned (unmovable) objects.</span></span>|
|<span data-ttu-id="a94d0-236">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="a94d0-236">SinkBlockCount</span></span>|<span data-ttu-id="a94d0-237">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-237">win:UInt32</span></span>|<span data-ttu-id="a94d0-238">Numero di blocchi di sincronizzazione in uso.</span><span class="sxs-lookup"><span data-stu-id="a94d0-238">The number of synchronization blocks in use.</span></span>|
|<span data-ttu-id="a94d0-239">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="a94d0-239">GCHandleCount</span></span>|<span data-ttu-id="a94d0-240">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-240">win:UInt32</span></span>|<span data-ttu-id="a94d0-241">Numero di handle di Garbage Collection in uso.</span><span class="sxs-lookup"><span data-stu-id="a94d0-241">The number of garbage collection handles in use.</span></span>|
|<span data-ttu-id="a94d0-242">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-242">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-243">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-243">win:UInt16</span></span>|<span data-ttu-id="a94d0-244">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-244">Unique ID for the instance of CLR or CoreCLR.</span></span>|
  
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="a94d0-245">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-245">GCCreateSegment_V1 Event</span></span>

<span data-ttu-id="a94d0-246">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-246">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-247">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-247">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-248">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-248">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-249">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-249">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-250">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-250">Informational (4)</span></span>|

<span data-ttu-id="a94d0-251">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-251">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-252">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-252">Event</span></span>|<span data-ttu-id="a94d0-253">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-253">Event ID</span></span>|<span data-ttu-id="a94d0-254">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-254">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateSegment_V1`|<span data-ttu-id="a94d0-255">5</span><span class="sxs-lookup"><span data-stu-id="a94d0-255">5</span></span>|<span data-ttu-id="a94d0-256">È stato creato un nuovo segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-256">A new garbage collection segment has been created.</span></span> <span data-ttu-id="a94d0-257">Inoltre, quando la traccia è attivata su un processo già in esecuzione, questo evento viene generato per ogni segmento esistente.</span><span class="sxs-lookup"><span data-stu-id="a94d0-257">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|

<span data-ttu-id="a94d0-258">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-258">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-259">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-259">Field name</span></span>|<span data-ttu-id="a94d0-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-260">Data type</span></span>|<span data-ttu-id="a94d0-261">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-261">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-262">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="a94d0-262">Address</span></span>|<span data-ttu-id="a94d0-263">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-263">win:UInt64</span></span>|<span data-ttu-id="a94d0-264">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-264">The address of the segment.</span></span>|
|<span data-ttu-id="a94d0-265">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="a94d0-265">Size</span></span>|<span data-ttu-id="a94d0-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-266">win:UInt64</span></span>|<span data-ttu-id="a94d0-267">Dimensione del segmento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-267">The size of the segment.</span></span>|
|<span data-ttu-id="a94d0-268">Digitare</span><span class="sxs-lookup"><span data-stu-id="a94d0-268">Type</span></span>|<span data-ttu-id="a94d0-269">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-269">win:UInt32</span></span>|<span data-ttu-id="a94d0-270">0x0 - Heap oggetto piccolo.</span><span class="sxs-lookup"><span data-stu-id="a94d0-270">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="a94d0-271">0x1 - Heap oggetto grande.</span><span class="sxs-lookup"><span data-stu-id="a94d0-271">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="a94d0-272">0x2 - Heap di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a94d0-272">0x2 - Read-only heap.</span></span>|
|<span data-ttu-id="a94d0-273">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-273">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-274">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-274">win:UInt16</span></span>|<span data-ttu-id="a94d0-275">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-275">Unique ID for the instance of CLR or CoreCLR.</span></span>|

<span data-ttu-id="a94d0-276">Si noti che la dimensione dei segmenti allocati dal Garbage Collector è specifico dell'implementazione ed è soggetta a modifiche in qualsiasi momento, tra cui aggiornamenti periodici.</span><span class="sxs-lookup"><span data-stu-id="a94d0-276">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="a94d0-277">L'applicazione non deve dare per scontata o dipendere da una particolare dimensione del segmento, né provare a configurare la quantità di memoria disponibile per le allocazioni di segmenti.</span><span class="sxs-lookup"><span data-stu-id="a94d0-277">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>

## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="a94d0-278">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-278">GCFreeSegment_V1 Event</span></span>

<span data-ttu-id="a94d0-279">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-279">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-280">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-280">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-281">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-281">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-282">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-282">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-283">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-283">Informational (4)</span></span>|

<span data-ttu-id="a94d0-284">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-284">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-285">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-285">Event</span></span>|<span data-ttu-id="a94d0-286">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-286">Event ID</span></span>|<span data-ttu-id="a94d0-287">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-287">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFreeSegment_V1`|<span data-ttu-id="a94d0-288">6</span><span class="sxs-lookup"><span data-stu-id="a94d0-288">6</span></span>|<span data-ttu-id="a94d0-289">È stato rilasciato un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-289">A garbage collection segment has been released.</span></span>|

<span data-ttu-id="a94d0-290">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-290">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-291">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-291">Field name</span></span>|<span data-ttu-id="a94d0-292">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-292">Data type</span></span>|<span data-ttu-id="a94d0-293">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-293">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-294">Indirizzo</span><span class="sxs-lookup"><span data-stu-id="a94d0-294">Address</span></span>|<span data-ttu-id="a94d0-295">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-295">win:UInt64</span></span>|<span data-ttu-id="a94d0-296">Indirizzo del segmento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-296">The address of the segment.</span></span>|
|<span data-ttu-id="a94d0-297">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-297">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-298">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-298">win:UInt16</span></span>|<span data-ttu-id="a94d0-299">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-299">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="a94d0-300">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-300">GCRestartEEBegin_V1 Event</span></span>

<span data-ttu-id="a94d0-301">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-301">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-302">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-302">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-303">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-303">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-304">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-304">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-305">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-305">Informational (4)</span></span>|

<span data-ttu-id="a94d0-306">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-306">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-307">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-307">Event</span></span>|<span data-ttu-id="a94d0-308">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-308">Event ID</span></span>|<span data-ttu-id="a94d0-309">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-309">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEBegin_V1`|<span data-ttu-id="a94d0-310">7</span><span class="sxs-lookup"><span data-stu-id="a94d0-310">7</span></span>|<span data-ttu-id="a94d0-311">Il ripristino dalla sospensione di Common Language Runtime è iniziato.</span><span class="sxs-lookup"><span data-stu-id="a94d0-311">Resumption from common language runtime suspension has begun.</span></span>|

<span data-ttu-id="a94d0-312">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-312">No event data.</span></span>

## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="a94d0-313">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-313">GCRestartEEEnd_V1 Event</span></span>

<span data-ttu-id="a94d0-314">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-314">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-315">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-315">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-316">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-316">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-317">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-317">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-318">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-318">Informational (4)</span></span>|

<span data-ttu-id="a94d0-319">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-319">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-320">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-320">Event</span></span>|<span data-ttu-id="a94d0-321">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-321">Event Id</span></span>|<span data-ttu-id="a94d0-322">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-322">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCRestartEEEnd_V1`|<span data-ttu-id="a94d0-323">3\.</span><span class="sxs-lookup"><span data-stu-id="a94d0-323">3</span></span>|<span data-ttu-id="a94d0-324">Il ripristino dalla sospensione di Common Language Runtime è terminato.</span><span class="sxs-lookup"><span data-stu-id="a94d0-324">Resumption from common language runtime suspension has ended.</span></span>|

<span data-ttu-id="a94d0-325">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-325">No event data.</span></span>

## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="a94d0-326">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-326">GCSuspendEE_V1 Event</span></span>

<span data-ttu-id="a94d0-327">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-327">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-328">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-328">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-329">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-329">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-330">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-330">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-331">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-331">Informational (4)</span></span>|

<span data-ttu-id="a94d0-332">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-332">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-333">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-333">Event</span></span>|<span data-ttu-id="a94d0-334">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-334">Event ID</span></span>|<span data-ttu-id="a94d0-335">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-335">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEE_V1`|<span data-ttu-id="a94d0-336">9</span><span class="sxs-lookup"><span data-stu-id="a94d0-336">9</span></span>|<span data-ttu-id="a94d0-337">Inizio della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-337">Start of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="a94d0-338">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-338">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-339">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-339">Field name</span></span>|<span data-ttu-id="a94d0-340">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-340">Data type</span></span>|<span data-ttu-id="a94d0-341">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-341">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-342">Motivo</span><span class="sxs-lookup"><span data-stu-id="a94d0-342">Reason</span></span>|<span data-ttu-id="a94d0-343">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-343">win:UInt16</span></span>|<span data-ttu-id="a94d0-344">0x0 - Altro.</span><span class="sxs-lookup"><span data-stu-id="a94d0-344">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="a94d0-345">0x1 - Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-345">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="a94d0-346">0x2 - Arresto del dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="a94d0-346">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="a94d0-347">0x3. - Lancio del codice.</span><span class="sxs-lookup"><span data-stu-id="a94d0-347">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="a94d0-348">0x4 - Arresto.</span><span class="sxs-lookup"><span data-stu-id="a94d0-348">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="a94d0-349">0x5 - Debugger.</span><span class="sxs-lookup"><span data-stu-id="a94d0-349">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="a94d0-350">0x6 - Preparazione per l'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-350">0x6 - Preparation for garbage collection.</span></span>|
|<span data-ttu-id="a94d0-351">Conteggio</span><span class="sxs-lookup"><span data-stu-id="a94d0-351">Count</span></span>|<span data-ttu-id="a94d0-352">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-352">win:UInt32</span></span>|<span data-ttu-id="a94d0-353">Il conteggio di Garbage Collection al momento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-353">The GC count at the time.</span></span> <span data-ttu-id="a94d0-354">In genere, dopo di questo si assiste a un evento di avvio GC successivo. Il conteggio corrisponde al conteggio corrente + 1 quando si aumenta l'indice di GC durante un'operazione di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-354">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|
|<span data-ttu-id="a94d0-355">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-355">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-356">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-356">win:UInt16</span></span>|<span data-ttu-id="a94d0-357">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-357">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="a94d0-358">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-358">GCSuspendEEEnd_V1 Event</span></span>

<span data-ttu-id="a94d0-359">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-359">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-360">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-360">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-361">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-361">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-362">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-362">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-363">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-363">Informational (4)</span></span>|

<span data-ttu-id="a94d0-364">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-364">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-365">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-365">Event</span></span>|<span data-ttu-id="a94d0-366">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-366">Event ID</span></span>|<span data-ttu-id="a94d0-367">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-367">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCSuspendEEEnd_V1`|<span data-ttu-id="a94d0-368">8</span><span class="sxs-lookup"><span data-stu-id="a94d0-368">8</span></span>|<span data-ttu-id="a94d0-369">Fine della sospensione del motore di esecuzione di operazioni di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="a94d0-369">End of suspension of the execution engine for garbage collection.</span></span>|

<span data-ttu-id="a94d0-370">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-370">No event data.</span></span>

## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="a94d0-371">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-371">GCAllocationTick_V2 Event</span></span>

<span data-ttu-id="a94d0-372">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-372">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-373">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-373">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-374">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-374">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-375">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-375">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-376">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-376">Informational (4)</span></span>|

<span data-ttu-id="a94d0-377">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-377">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-378">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-378">Event</span></span>|<span data-ttu-id="a94d0-379">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-379">Event ID</span></span>|<span data-ttu-id="a94d0-380">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-380">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCAllocationTick_V2`|<span data-ttu-id="a94d0-381">10</span><span class="sxs-lookup"><span data-stu-id="a94d0-381">10</span></span>|<span data-ttu-id="a94d0-382">Ogni volta vengono allocati circa 100 KB.</span><span class="sxs-lookup"><span data-stu-id="a94d0-382">Each time approximately 100 KB is allocated.</span></span>|

<span data-ttu-id="a94d0-383">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-383">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-384">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-384">Field name</span></span>|<span data-ttu-id="a94d0-385">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-385">Data type</span></span>|<span data-ttu-id="a94d0-386">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-386">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-387">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="a94d0-387">AllocationAmount</span></span>|<span data-ttu-id="a94d0-388">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-388">win:UInt32</span></span>|<span data-ttu-id="a94d0-389">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="a94d0-389">The allocation size, in bytes.</span></span> <span data-ttu-id="a94d0-390">Questo valore è preciso per le allocazioni minori della lunghezza di un ULONG (4.294.967.295 byte).</span><span class="sxs-lookup"><span data-stu-id="a94d0-390">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="a94d0-391">Se l'allocazione è maggiore, questo campo contiene un valore troncato.</span><span class="sxs-lookup"><span data-stu-id="a94d0-391">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="a94d0-392">Usare `AllocationAmount64` per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="a94d0-392">Use `AllocationAmount64` for very large allocations.</span></span>|
|<span data-ttu-id="a94d0-393">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="a94d0-393">AllocationKind</span></span>|<span data-ttu-id="a94d0-394">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-394">win:UInt32</span></span>|<span data-ttu-id="a94d0-395">0x0 - Allocazione di oggetti piccoli (l'allocazione è nell'heap oggetto piccolo).</span><span class="sxs-lookup"><span data-stu-id="a94d0-395">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="a94d0-396">0x1 - Allocazione di oggetti grandi (l'allocazione è nell'heap oggetto grande).</span><span class="sxs-lookup"><span data-stu-id="a94d0-396">0x1 - Large object allocation (allocation is in large object heap).</span></span>|
|<span data-ttu-id="a94d0-397">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-397">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-398">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-398">win:UInt16</span></span>|<span data-ttu-id="a94d0-399">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-399">Unique ID for the instance of CLR or CoreCLR.</span></span>|
|<span data-ttu-id="a94d0-400">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="a94d0-400">AllocationAmount64</span></span>|<span data-ttu-id="a94d0-401">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a94d0-401">win:UInt64</span></span>|<span data-ttu-id="a94d0-402">Dimensione dell'allocazione, in byte.</span><span class="sxs-lookup"><span data-stu-id="a94d0-402">The allocation size, in bytes.</span></span> <span data-ttu-id="a94d0-403">Questo valore è preciso per le allocazioni di dimensioni molto grandi.</span><span class="sxs-lookup"><span data-stu-id="a94d0-403">This value is accurate for very large allocations.</span></span>|
|<span data-ttu-id="a94d0-404">TypeId</span><span class="sxs-lookup"><span data-stu-id="a94d0-404">TypeId</span></span>|<span data-ttu-id="a94d0-405">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="a94d0-405">win:Pointer</span></span>|<span data-ttu-id="a94d0-406">Indirizzo di MethodTable.</span><span class="sxs-lookup"><span data-stu-id="a94d0-406">The address of the MethodTable.</span></span> <span data-ttu-id="a94d0-407">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è l'indirizzo di MethodTable che corrisponde all'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="a94d0-407">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="a94d0-408">TypeName</span><span class="sxs-lookup"><span data-stu-id="a94d0-408">TypeName</span></span>|<span data-ttu-id="a94d0-409">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a94d0-409">win:UnicodeString</span></span>|<span data-ttu-id="a94d0-410">Nome del tipo che è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="a94d0-410">The name of the type that was allocated.</span></span> <span data-ttu-id="a94d0-411">Quando sono presenti diversi tipi di oggetti allocati durante questo evento, questo è il tipo dell'ultimo oggetto allocato (l'oggetto che ha causato il superamento della soglia di 100 KB).</span><span class="sxs-lookup"><span data-stu-id="a94d0-411">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|
|<span data-ttu-id="a94d0-412">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="a94d0-412">HeapIndex</span></span>|<span data-ttu-id="a94d0-413">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-413">win:UInt32</span></span>|<span data-ttu-id="a94d0-414">Heap in cui l'oggetto è stato allocato.</span><span class="sxs-lookup"><span data-stu-id="a94d0-414">The heap where the object was allocated.</span></span> <span data-ttu-id="a94d0-415">Questo valore è 0 (zero) durante l'esecuzione della procedura di Garbage Collection per workstation.</span><span class="sxs-lookup"><span data-stu-id="a94d0-415">This value is 0 (zero) when running with workstation garbage collection.</span></span>|

## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="a94d0-416">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-416">GCFinalizersBegin_V1 Event</span></span>

<span data-ttu-id="a94d0-417">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-417">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-418">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-418">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-419">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-419">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-420">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-420">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-421">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-421">Informational (4)</span></span>|

<span data-ttu-id="a94d0-422">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-422">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-423">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-423">Event</span></span>|<span data-ttu-id="a94d0-424">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-424">Event ID</span></span>|<span data-ttu-id="a94d0-425">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-425">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersBegin_V1`|<span data-ttu-id="a94d0-426">14</span><span class="sxs-lookup"><span data-stu-id="a94d0-426">14</span></span>|<span data-ttu-id="a94d0-427">Inizio dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="a94d0-427">The start of running finalizers.</span></span>|

<span data-ttu-id="a94d0-428">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-428">No event data.</span></span>

## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="a94d0-429">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-429">GCFinalizersEnd_V1 Event</span></span>

<span data-ttu-id="a94d0-430">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-430">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-431">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-431">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-432">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-432">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-433">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-433">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-434">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-434">Informational (4)</span></span>|

<span data-ttu-id="a94d0-435">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-435">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-436">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-436">Event</span></span>|<span data-ttu-id="a94d0-437">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-437">Event ID</span></span>|<span data-ttu-id="a94d0-438">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-438">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCFinalizersEnd_V1`|<span data-ttu-id="a94d0-439">13</span><span class="sxs-lookup"><span data-stu-id="a94d0-439">13</span></span>|<span data-ttu-id="a94d0-440">Fine dell'esecuzione dei finalizzatori.</span><span class="sxs-lookup"><span data-stu-id="a94d0-440">The end of running finalizers.</span></span>|

<span data-ttu-id="a94d0-441">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-441">The following table shows the event data:</span></span>

|<span data-ttu-id="a94d0-442">Nome campo</span><span class="sxs-lookup"><span data-stu-id="a94d0-442">Field name</span></span>|<span data-ttu-id="a94d0-443">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a94d0-443">Data type</span></span>|<span data-ttu-id="a94d0-444">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a94d0-444">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="a94d0-445">Conteggio</span><span class="sxs-lookup"><span data-stu-id="a94d0-445">Count</span></span>|<span data-ttu-id="a94d0-446">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a94d0-446">win:UInt32</span></span>|<span data-ttu-id="a94d0-447">Numero di finalizzatori eseguiti.</span><span class="sxs-lookup"><span data-stu-id="a94d0-447">The number of finalizers that were run.</span></span>|
|<span data-ttu-id="a94d0-448">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a94d0-448">ClrInstanceID</span></span>|<span data-ttu-id="a94d0-449">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a94d0-449">win:UInt16</span></span>|<span data-ttu-id="a94d0-450">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="a94d0-450">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="a94d0-451">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-451">GCCreateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="a94d0-452">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-452">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-453">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-453">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-454">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-454">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-455">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-455">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-456">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-456">Informational (4)</span></span>|
|<span data-ttu-id="a94d0-457">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a94d0-457">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a94d0-458">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-458">Informational (4)</span></span>|

<span data-ttu-id="a94d0-459">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-459">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-460">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-460">Event</span></span>|<span data-ttu-id="a94d0-461">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-461">Event ID</span></span>|<span data-ttu-id="a94d0-462">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-462">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="a94d0-463">11</span><span class="sxs-lookup"><span data-stu-id="a94d0-463">11</span></span>|<span data-ttu-id="a94d0-464">È stato creato il thread di Garbage Collection in modalità simultanea</span><span class="sxs-lookup"><span data-stu-id="a94d0-464">Concurrent garbage collection thread was created.</span></span>|

<span data-ttu-id="a94d0-465">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-465">No event data.</span></span>

## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="a94d0-466">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a94d0-466">GCTerminateConcurrentThread_V1 Event</span></span>

<span data-ttu-id="a94d0-467">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="a94d0-467">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="a94d0-468">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-468">Keyword for raising the event</span></span>|<span data-ttu-id="a94d0-469">Level</span><span class="sxs-lookup"><span data-stu-id="a94d0-469">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="a94d0-470">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a94d0-470">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a94d0-471">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-471">Informational (4)</span></span>|
|<span data-ttu-id="a94d0-472">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="a94d0-472">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a94d0-473">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="a94d0-473">Informational (4)</span></span>|

<span data-ttu-id="a94d0-474">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="a94d0-474">The following table shows the event information:</span></span>

|<span data-ttu-id="a94d0-475">event</span><span class="sxs-lookup"><span data-stu-id="a94d0-475">Event</span></span>|<span data-ttu-id="a94d0-476">ID evento</span><span class="sxs-lookup"><span data-stu-id="a94d0-476">Event ID</span></span>|<span data-ttu-id="a94d0-477">Generato quando</span><span class="sxs-lookup"><span data-stu-id="a94d0-477">Raised when</span></span>|
|-----------|--------------|-----------------|
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="a94d0-478">12</span><span class="sxs-lookup"><span data-stu-id="a94d0-478">12</span></span>|<span data-ttu-id="a94d0-479">È stato terminato il thread di Garbage Collection in modalità simultanea.</span><span class="sxs-lookup"><span data-stu-id="a94d0-479">Concurrent garbage collection thread was terminated.</span></span>|

<span data-ttu-id="a94d0-480">Nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a94d0-480">No event data.</span></span>

## <a name="see-also"></a><span data-ttu-id="a94d0-481">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a94d0-481">See also</span></span>

- [<span data-ttu-id="a94d0-482">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="a94d0-482">CLR ETW Events</span></span>](clr-etw-events.md)
