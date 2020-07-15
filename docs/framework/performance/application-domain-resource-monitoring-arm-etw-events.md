---
title: Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)
description: Informazioni sugli eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM) in .NET, ad esempio ThreadCreated, AppDomainMemAllocated, AppDomainMemSurvived e altro ancora.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309781"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="329d8-103">Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)</span><span class="sxs-lookup"><span data-stu-id="329d8-103">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="329d8-104">Questi eventi forniscono informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="329d8-104">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="329d8-105">È possibile usare questi eventi o la funzionalità di monitoraggio delle risorse del dominio applicazione (ARM) per ottenere le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="329d8-105">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="329d8-106">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="329d8-106">ThreadCreated Event</span></span>

<span data-ttu-id="329d8-107">Questo evento viene generato anche nel provider di rundown come `ThreadDC` (sotto la parola chiave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="329d8-107">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="329d8-108">Questo è l'unico evento che viene generato nel provider di rundown in questa categoria.</span><span class="sxs-lookup"><span data-stu-id="329d8-108">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="329d8-109">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="329d8-109">The following table shows the keyword and level.</span></span> <span data-ttu-id="329d8-110">Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="329d8-110">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="329d8-111">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="329d8-111">Keyword for raising the event</span></span>|<span data-ttu-id="329d8-112">Livello</span><span class="sxs-lookup"><span data-stu-id="329d8-112">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="329d8-113">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="329d8-113">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="329d8-114">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-114">Informational(4)</span></span>|
|<span data-ttu-id="329d8-115">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="329d8-115">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="329d8-116">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-116">Informational(4)</span></span>|

<span data-ttu-id="329d8-117">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-117">The following table shows the event information:</span></span>

|<span data-ttu-id="329d8-118">Evento</span><span class="sxs-lookup"><span data-stu-id="329d8-118">Event</span></span>|<span data-ttu-id="329d8-119">ID evento</span><span class="sxs-lookup"><span data-stu-id="329d8-119">Event ID</span></span>|<span data-ttu-id="329d8-120">Generato quando</span><span class="sxs-lookup"><span data-stu-id="329d8-120">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="329d8-121">85</span><span class="sxs-lookup"><span data-stu-id="329d8-121">85</span></span>|<span data-ttu-id="329d8-122">Un thread è stato creato per il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="329d8-122">A thread was created for the application domain.</span></span>|

<span data-ttu-id="329d8-123">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-123">The following table shows the event data:</span></span>

|<span data-ttu-id="329d8-124">Nome campo</span><span class="sxs-lookup"><span data-stu-id="329d8-124">Field name</span></span>|<span data-ttu-id="329d8-125">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="329d8-125">Data type</span></span>|<span data-ttu-id="329d8-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d8-126">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="329d8-127">ThreadID</span><span class="sxs-lookup"><span data-stu-id="329d8-127">ThreadID</span></span>|<span data-ttu-id="329d8-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-128">win:UInt64</span></span>|<span data-ttu-id="329d8-129">ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="329d8-129">ID of the thread that was created.</span></span>|
|<span data-ttu-id="329d8-130">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="329d8-130">AppDomainID</span></span>|<span data-ttu-id="329d8-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-131">win:UInt64</span></span>|<span data-ttu-id="329d8-132">Identificatore del dominio dell'applicazione per la quale l’attività thread viene segnalata.</span><span class="sxs-lookup"><span data-stu-id="329d8-132">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="329d8-133">Flags</span><span class="sxs-lookup"><span data-stu-id="329d8-133">Flags</span></span>|<span data-ttu-id="329d8-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="329d8-134">win:UInt32</span></span>|<span data-ttu-id="329d8-135">Flag di creazione del thread.</span><span class="sxs-lookup"><span data-stu-id="329d8-135">Thread creation flags.</span></span>|
|<span data-ttu-id="329d8-136">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="329d8-136">ManagedThreadIndex</span></span>|<span data-ttu-id="329d8-137">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="329d8-137">win:UInt32</span></span>|<span data-ttu-id="329d8-138">Indice gestito del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="329d8-138">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="329d8-139">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="329d8-139">OSThreadID</span></span>|<span data-ttu-id="329d8-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="329d8-140">win:UInt32</span></span>|<span data-ttu-id="329d8-141">ID del sistema operativo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="329d8-141">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="329d8-142">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="329d8-142">ClrInstanceID</span></span>|<span data-ttu-id="329d8-143">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="329d8-143">win:UInt16</span></span>|<span data-ttu-id="329d8-144">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="329d8-144">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="329d8-145">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="329d8-145">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="329d8-146">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="329d8-146">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="329d8-147">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="329d8-147">Keyword for raising the event</span></span>|<span data-ttu-id="329d8-148">Livello</span><span class="sxs-lookup"><span data-stu-id="329d8-148">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="329d8-149">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="329d8-149">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="329d8-150">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-150">Informational(4)</span></span>|

<span data-ttu-id="329d8-151">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-151">The following table shows the event information:</span></span>

|<span data-ttu-id="329d8-152">Evento</span><span class="sxs-lookup"><span data-stu-id="329d8-152">Event</span></span>|<span data-ttu-id="329d8-153">ID evento</span><span class="sxs-lookup"><span data-stu-id="329d8-153">Event ID</span></span>|<span data-ttu-id="329d8-154">Generato quando</span><span class="sxs-lookup"><span data-stu-id="329d8-154">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="329d8-155">83</span><span class="sxs-lookup"><span data-stu-id="329d8-155">83</span></span>|<span data-ttu-id="329d8-156">Ogni 4 MB di memoria (approssimativamente) viene allocato nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="329d8-156">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="329d8-157">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-157">The following table shows the event data:</span></span>

|<span data-ttu-id="329d8-158">Nome campo</span><span class="sxs-lookup"><span data-stu-id="329d8-158">Field name</span></span>|<span data-ttu-id="329d8-159">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="329d8-159">Data type</span></span>|<span data-ttu-id="329d8-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d8-160">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="329d8-161">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="329d8-161">AppDomainID</span></span>|<span data-ttu-id="329d8-162">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-162">win:UInt64</span></span>|<span data-ttu-id="329d8-163">Identificatore del dominio dell'applicazione per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="329d8-163">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="329d8-164">Allocato</span><span class="sxs-lookup"><span data-stu-id="329d8-164">Allocated</span></span>|<span data-ttu-id="329d8-165">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-165">win:UInt64</span></span>|<span data-ttu-id="329d8-166">Il numero totale di byte allocati in questo dominio applicazione, poiché è stato creato il dominio dell'applicazione (non viene sottratta la quantità di memoria liberata).</span><span class="sxs-lookup"><span data-stu-id="329d8-166">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="329d8-167">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="329d8-167">ClrInstanceID</span></span>|<span data-ttu-id="329d8-168">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="329d8-168">win:UInt16</span></span>|<span data-ttu-id="329d8-169">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="329d8-169">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="329d8-170">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="329d8-170">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="329d8-171">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="329d8-171">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="329d8-172">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="329d8-172">Keyword for raising the event</span></span>|<span data-ttu-id="329d8-173">Livello</span><span class="sxs-lookup"><span data-stu-id="329d8-173">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="329d8-174">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="329d8-174">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="329d8-175">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-175">Informational(4)</span></span>|

<span data-ttu-id="329d8-176">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-176">The following table shows the event information:</span></span>

|<span data-ttu-id="329d8-177">Evento</span><span class="sxs-lookup"><span data-stu-id="329d8-177">Event</span></span>|<span data-ttu-id="329d8-178">ID evento</span><span class="sxs-lookup"><span data-stu-id="329d8-178">Event ID</span></span>|<span data-ttu-id="329d8-179">Generato quando</span><span class="sxs-lookup"><span data-stu-id="329d8-179">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="329d8-180">84</span><span class="sxs-lookup"><span data-stu-id="329d8-180">84</span></span>|<span data-ttu-id="329d8-181">Ogni operazione di Garbage Collection è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="329d8-181">Each garbage collection has ended.</span></span>|

<span data-ttu-id="329d8-182">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-182">The following table shows the event data:</span></span>

|<span data-ttu-id="329d8-183">Nome campo</span><span class="sxs-lookup"><span data-stu-id="329d8-183">Field name</span></span>|<span data-ttu-id="329d8-184">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="329d8-184">Data type</span></span>|<span data-ttu-id="329d8-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d8-185">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="329d8-186">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="329d8-186">AppDomainID</span></span>|<span data-ttu-id="329d8-187">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-187">win:UInt64</span></span>|<span data-ttu-id="329d8-188">Identificatore del dominio per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="329d8-188">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="329d8-189">Survived</span><span class="sxs-lookup"><span data-stu-id="329d8-189">Survived</span></span>|<span data-ttu-id="329d8-190">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-190">win:UInt64</span></span>|<span data-ttu-id="329d8-191">Il numero di byte rimasti dall'ultima raccolta e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="329d8-191">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="329d8-192">Questo numero è preciso e completo dopo una raccolta completa, ma può essere incompleto dopo una raccolta temporanea.</span><span class="sxs-lookup"><span data-stu-id="329d8-192">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="329d8-193">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="329d8-193">ProcessSurvived</span></span>|<span data-ttu-id="329d8-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-194">win:UInt64</span></span>|<span data-ttu-id="329d8-195">I byte totali rimasti dall'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="329d8-195">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="329d8-196">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="329d8-196">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="329d8-197">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.</span><span class="sxs-lookup"><span data-stu-id="329d8-197">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="329d8-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="329d8-198">ClrInstanceID</span></span>|<span data-ttu-id="329d8-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="329d8-199">win:UInt16</span></span>|<span data-ttu-id="329d8-200">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="329d8-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="329d8-201">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="329d8-201">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="329d8-202">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="329d8-202">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="329d8-203">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="329d8-203">Keyword for raising the event</span></span>|<span data-ttu-id="329d8-204">Livello</span><span class="sxs-lookup"><span data-stu-id="329d8-204">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="329d8-205">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="329d8-205">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="329d8-206">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-206">Informational(4)</span></span>|
|<span data-ttu-id="329d8-207">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="329d8-207">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="329d8-208">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-208">Informational(4)</span></span>|

<span data-ttu-id="329d8-209">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-209">The following table shows the event information:</span></span>

|<span data-ttu-id="329d8-210">Evento</span><span class="sxs-lookup"><span data-stu-id="329d8-210">Event</span></span>|<span data-ttu-id="329d8-211">ID evento</span><span class="sxs-lookup"><span data-stu-id="329d8-211">Event ID</span></span>|<span data-ttu-id="329d8-212">Generato quando</span><span class="sxs-lookup"><span data-stu-id="329d8-212">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="329d8-213">87</span><span class="sxs-lookup"><span data-stu-id="329d8-213">87</span></span>|<span data-ttu-id="329d8-214">Un thread immette un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="329d8-214">A thread enters an application domain.</span></span>|

<span data-ttu-id="329d8-215">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-215">The following table shows the event data:</span></span>

|<span data-ttu-id="329d8-216">Nome campo</span><span class="sxs-lookup"><span data-stu-id="329d8-216">Field name</span></span>|<span data-ttu-id="329d8-217">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="329d8-217">Data type</span></span>|<span data-ttu-id="329d8-218">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d8-218">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="329d8-219">ThreadID</span><span class="sxs-lookup"><span data-stu-id="329d8-219">ThreadID</span></span>|<span data-ttu-id="329d8-220">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-220">win:UInt64</span></span>|<span data-ttu-id="329d8-221">Identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="329d8-221">The thread identifier.</span></span>|
|<span data-ttu-id="329d8-222">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="329d8-222">AppDomainID</span></span>|<span data-ttu-id="329d8-223">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-223">win:UInt64</span></span>|<span data-ttu-id="329d8-224">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="329d8-224">The application domain identifier.</span></span>|
|<span data-ttu-id="329d8-225">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="329d8-225">ClrInstanceID</span></span>|<span data-ttu-id="329d8-226">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="329d8-226">win:UInt16</span></span>|<span data-ttu-id="329d8-227">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="329d8-227">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="329d8-228">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="329d8-228">ThreadTerminated Event</span></span>

<span data-ttu-id="329d8-229">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="329d8-229">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="329d8-230">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="329d8-230">Keyword for raising the event</span></span>|<span data-ttu-id="329d8-231">Livello</span><span class="sxs-lookup"><span data-stu-id="329d8-231">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="329d8-232">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="329d8-232">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="329d8-233">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-233">Informational(4)</span></span>|
|<span data-ttu-id="329d8-234">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="329d8-234">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="329d8-235">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="329d8-235">Informational(4)</span></span>|

<span data-ttu-id="329d8-236">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-236">The following table shows the event information:</span></span>

|<span data-ttu-id="329d8-237">Evento</span><span class="sxs-lookup"><span data-stu-id="329d8-237">Event</span></span>|<span data-ttu-id="329d8-238">ID evento</span><span class="sxs-lookup"><span data-stu-id="329d8-238">Event ID</span></span>|<span data-ttu-id="329d8-239">Generato quando</span><span class="sxs-lookup"><span data-stu-id="329d8-239">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="329d8-240">86</span><span class="sxs-lookup"><span data-stu-id="329d8-240">86</span></span>|<span data-ttu-id="329d8-241">Termina un thread.</span><span class="sxs-lookup"><span data-stu-id="329d8-241">A thread terminates.</span></span>|

<span data-ttu-id="329d8-242">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="329d8-242">The following table shows the event data:</span></span>

|<span data-ttu-id="329d8-243">Nome campo</span><span class="sxs-lookup"><span data-stu-id="329d8-243">Field name</span></span>|<span data-ttu-id="329d8-244">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="329d8-244">Data type</span></span>|<span data-ttu-id="329d8-245">Descrizione</span><span class="sxs-lookup"><span data-stu-id="329d8-245">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="329d8-246">ThreadID</span><span class="sxs-lookup"><span data-stu-id="329d8-246">ThreadID</span></span>|<span data-ttu-id="329d8-247">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-247">win:UInt64</span></span>|<span data-ttu-id="329d8-248">Identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="329d8-248">The thread identifier.</span></span>|
|<span data-ttu-id="329d8-249">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="329d8-249">AppDomainID</span></span>|<span data-ttu-id="329d8-250">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="329d8-250">win:UInt64</span></span>|<span data-ttu-id="329d8-251">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="329d8-251">The application domain identifier.</span></span>|
|<span data-ttu-id="329d8-252">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="329d8-252">ClrInstanceID</span></span>|<span data-ttu-id="329d8-253">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="329d8-253">win:UInt16</span></span>|<span data-ttu-id="329d8-254">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="329d8-254">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="329d8-255">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="329d8-255">See also</span></span>

- [<span data-ttu-id="329d8-256">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="329d8-256">CLR ETW Events</span></span>](clr-etw-events.md)
