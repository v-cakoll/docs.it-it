---
title: Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e1c2a38be6f2c15a118b35925570119b474f096
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040570"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="ba782-102">Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)</span><span class="sxs-lookup"><span data-stu-id="ba782-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>

<span data-ttu-id="ba782-103">Questi eventi forniscono informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba782-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="ba782-104">È possibile usare questi eventi o la funzionalità di monitoraggio delle risorse del dominio applicazione (ARM) per ottenere le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="ba782-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>

## <a name="threadcreated-event"></a><span data-ttu-id="ba782-105">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="ba782-105">ThreadCreated Event</span></span>

<span data-ttu-id="ba782-106">Questo evento viene generato anche nel provider di rundown come `ThreadDC` (sotto la parola chiave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="ba782-106">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="ba782-107">Questo è l'unico evento che viene generato nel provider di rundown in questa categoria.</span><span class="sxs-lookup"><span data-stu-id="ba782-107">This is the only event that is raised under the rundown provider in this category.</span></span>

<span data-ttu-id="ba782-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="ba782-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="ba782-109">Per altre informazioni, vedere [parole chiave e livelli ETW di CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ba782-109">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="ba782-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="ba782-110">Keyword for raising the event</span></span>|<span data-ttu-id="ba782-111">Level</span><span class="sxs-lookup"><span data-stu-id="ba782-111">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ba782-112">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ba782-112">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ba782-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-113">Informational(4)</span></span>|
|<span data-ttu-id="ba782-114">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ba782-114">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ba782-115">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-115">Informational(4)</span></span>|

<span data-ttu-id="ba782-116">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-116">The following table shows the event information:</span></span>

|<span data-ttu-id="ba782-117">event</span><span class="sxs-lookup"><span data-stu-id="ba782-117">Event</span></span>|<span data-ttu-id="ba782-118">ID evento</span><span class="sxs-lookup"><span data-stu-id="ba782-118">Event ID</span></span>|<span data-ttu-id="ba782-119">Generato quando</span><span class="sxs-lookup"><span data-stu-id="ba782-119">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadCreated`|<span data-ttu-id="ba782-120">85</span><span class="sxs-lookup"><span data-stu-id="ba782-120">85</span></span>|<span data-ttu-id="ba782-121">Un thread è stato creato per il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba782-121">A thread was created for the application domain.</span></span>|

<span data-ttu-id="ba782-122">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-122">The following table shows the event data:</span></span>

|<span data-ttu-id="ba782-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="ba782-123">Field name</span></span>|<span data-ttu-id="ba782-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ba782-124">Data type</span></span>|<span data-ttu-id="ba782-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba782-125">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ba782-126">ThreadID</span><span class="sxs-lookup"><span data-stu-id="ba782-126">ThreadID</span></span>|<span data-ttu-id="ba782-127">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-127">win:UInt64</span></span>|<span data-ttu-id="ba782-128">ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ba782-128">ID of the thread that was created.</span></span>|
|<span data-ttu-id="ba782-129">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ba782-129">AppDomainID</span></span>|<span data-ttu-id="ba782-130">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-130">win:UInt64</span></span>|<span data-ttu-id="ba782-131">Identificatore del dominio dell'applicazione per la quale l’attività thread viene segnalata.</span><span class="sxs-lookup"><span data-stu-id="ba782-131">Identifier of the application domain for which thread activity is being reported.</span></span>|
|<span data-ttu-id="ba782-132">Flags</span><span class="sxs-lookup"><span data-stu-id="ba782-132">Flags</span></span>|<span data-ttu-id="ba782-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ba782-133">win:UInt32</span></span>|<span data-ttu-id="ba782-134">Flag di creazione del thread.</span><span class="sxs-lookup"><span data-stu-id="ba782-134">Thread creation flags.</span></span>|
|<span data-ttu-id="ba782-135">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="ba782-135">ManagedThreadIndex</span></span>|<span data-ttu-id="ba782-136">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ba782-136">win:UInt32</span></span>|<span data-ttu-id="ba782-137">Indice gestito del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ba782-137">Managed index of the thread that was created.</span></span>|
|<span data-ttu-id="ba782-138">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="ba782-138">OSThreadID</span></span>|<span data-ttu-id="ba782-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="ba782-139">win:UInt32</span></span>|<span data-ttu-id="ba782-140">ID del sistema operativo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ba782-140">Operating system ID of the thread that was created.</span></span>|
|<span data-ttu-id="ba782-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ba782-141">ClrInstanceID</span></span>|<span data-ttu-id="ba782-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ba782-142">win:UInt16</span></span>|<span data-ttu-id="ba782-143">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ba782-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemallocated-event"></a><span data-ttu-id="ba782-144">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="ba782-144">AppDomainMemAllocated Event</span></span>

<span data-ttu-id="ba782-145">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="ba782-145">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ba782-146">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="ba782-146">Keyword for raising the event</span></span>|<span data-ttu-id="ba782-147">Level</span><span class="sxs-lookup"><span data-stu-id="ba782-147">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ba782-148">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ba782-148">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ba782-149">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-149">Informational(4)</span></span>|

<span data-ttu-id="ba782-150">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-150">The following table shows the event information:</span></span>

|<span data-ttu-id="ba782-151">event</span><span class="sxs-lookup"><span data-stu-id="ba782-151">Event</span></span>|<span data-ttu-id="ba782-152">ID evento</span><span class="sxs-lookup"><span data-stu-id="ba782-152">Event ID</span></span>|<span data-ttu-id="ba782-153">Generato quando</span><span class="sxs-lookup"><span data-stu-id="ba782-153">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|<span data-ttu-id="ba782-154">83</span><span class="sxs-lookup"><span data-stu-id="ba782-154">83</span></span>|<span data-ttu-id="ba782-155">Ogni 4 MB di memoria (approssimativamente) viene allocato nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba782-155">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|

<span data-ttu-id="ba782-156">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-156">The following table shows the event data:</span></span>

|<span data-ttu-id="ba782-157">Nome campo</span><span class="sxs-lookup"><span data-stu-id="ba782-157">Field name</span></span>|<span data-ttu-id="ba782-158">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ba782-158">Data type</span></span>|<span data-ttu-id="ba782-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba782-159">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ba782-160">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ba782-160">AppDomainID</span></span>|<span data-ttu-id="ba782-161">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-161">win:UInt64</span></span>|<span data-ttu-id="ba782-162">Identificatore del dominio dell'applicazione per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="ba782-162">Identifier of the application domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="ba782-163">Allocato</span><span class="sxs-lookup"><span data-stu-id="ba782-163">Allocated</span></span>|<span data-ttu-id="ba782-164">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-164">win:UInt64</span></span>|<span data-ttu-id="ba782-165">Il numero totale di byte allocati in questo dominio applicazione, poiché è stato creato il dominio dell'applicazione (non viene sottratta la quantità di memoria liberata).</span><span class="sxs-lookup"><span data-stu-id="ba782-165">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|
|<span data-ttu-id="ba782-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ba782-166">ClrInstanceID</span></span>|<span data-ttu-id="ba782-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ba782-167">win:UInt16</span></span>|<span data-ttu-id="ba782-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ba782-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="ba782-169">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="ba782-169">AppDomainMemSurvived Event</span></span>

<span data-ttu-id="ba782-170">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="ba782-170">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ba782-171">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="ba782-171">Keyword for raising the event</span></span>|<span data-ttu-id="ba782-172">Level</span><span class="sxs-lookup"><span data-stu-id="ba782-172">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ba782-173">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ba782-173">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ba782-174">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-174">Informational(4)</span></span>|

<span data-ttu-id="ba782-175">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-175">The following table shows the event information:</span></span>

|<span data-ttu-id="ba782-176">event</span><span class="sxs-lookup"><span data-stu-id="ba782-176">Event</span></span>|<span data-ttu-id="ba782-177">ID evento</span><span class="sxs-lookup"><span data-stu-id="ba782-177">Event ID</span></span>|<span data-ttu-id="ba782-178">Generato quando</span><span class="sxs-lookup"><span data-stu-id="ba782-178">Raised when</span></span>|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|<span data-ttu-id="ba782-179">84</span><span class="sxs-lookup"><span data-stu-id="ba782-179">84</span></span>|<span data-ttu-id="ba782-180">Ogni operazione di Garbage Collection è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="ba782-180">Each garbage collection has ended.</span></span>|

<span data-ttu-id="ba782-181">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-181">The following table shows the event data:</span></span>

|<span data-ttu-id="ba782-182">Nome campo</span><span class="sxs-lookup"><span data-stu-id="ba782-182">Field name</span></span>|<span data-ttu-id="ba782-183">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ba782-183">Data type</span></span>|<span data-ttu-id="ba782-184">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba782-184">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ba782-185">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ba782-185">AppDomainID</span></span>|<span data-ttu-id="ba782-186">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-186">win:UInt64</span></span>|<span data-ttu-id="ba782-187">Identificatore del dominio per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="ba782-187">Identifier of the domain for which resource usage is being reported.</span></span>|
|<span data-ttu-id="ba782-188">Survived</span><span class="sxs-lookup"><span data-stu-id="ba782-188">Survived</span></span>|<span data-ttu-id="ba782-189">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-189">win:UInt64</span></span>|<span data-ttu-id="ba782-190">Il numero di byte rimasti dall'ultima raccolta e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ba782-190">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="ba782-191">Questo numero è preciso e completo dopo una raccolta completa, ma può essere incompleto dopo una raccolta temporanea.</span><span class="sxs-lookup"><span data-stu-id="ba782-191">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|
|<span data-ttu-id="ba782-192">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="ba782-192">ProcessSurvived</span></span>|<span data-ttu-id="ba782-193">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-193">win:UInt64</span></span>|<span data-ttu-id="ba782-194">I byte totali rimasti dall'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="ba782-194">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="ba782-195">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="ba782-195">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="ba782-196">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.</span><span class="sxs-lookup"><span data-stu-id="ba782-196">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|
|<span data-ttu-id="ba782-197">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ba782-197">ClrInstanceID</span></span>|<span data-ttu-id="ba782-198">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ba782-198">win:UInt16</span></span>|<span data-ttu-id="ba782-199">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ba782-199">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadappdomainenter-event"></a><span data-ttu-id="ba782-200">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="ba782-200">ThreadAppDomainEnter Event</span></span>

<span data-ttu-id="ba782-201">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="ba782-201">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ba782-202">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="ba782-202">Keyword for raising the event</span></span>|<span data-ttu-id="ba782-203">Level</span><span class="sxs-lookup"><span data-stu-id="ba782-203">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ba782-204">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ba782-204">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ba782-205">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-205">Informational(4)</span></span>|
|<span data-ttu-id="ba782-206">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ba782-206">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ba782-207">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-207">Informational(4)</span></span>|

<span data-ttu-id="ba782-208">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-208">The following table shows the event information:</span></span>

|<span data-ttu-id="ba782-209">event</span><span class="sxs-lookup"><span data-stu-id="ba782-209">Event</span></span>|<span data-ttu-id="ba782-210">ID evento</span><span class="sxs-lookup"><span data-stu-id="ba782-210">Event ID</span></span>|<span data-ttu-id="ba782-211">Generato quando</span><span class="sxs-lookup"><span data-stu-id="ba782-211">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|<span data-ttu-id="ba782-212">87</span><span class="sxs-lookup"><span data-stu-id="ba782-212">87</span></span>|<span data-ttu-id="ba782-213">Un thread immette un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba782-213">A thread enters an application domain.</span></span>|

<span data-ttu-id="ba782-214">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-214">The following table shows the event data:</span></span>

|<span data-ttu-id="ba782-215">Nome campo</span><span class="sxs-lookup"><span data-stu-id="ba782-215">Field name</span></span>|<span data-ttu-id="ba782-216">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ba782-216">Data type</span></span>|<span data-ttu-id="ba782-217">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba782-217">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ba782-218">ThreadID</span><span class="sxs-lookup"><span data-stu-id="ba782-218">ThreadID</span></span>|<span data-ttu-id="ba782-219">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-219">win:UInt64</span></span>|<span data-ttu-id="ba782-220">L'identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="ba782-220">The thread identifier.</span></span>|
|<span data-ttu-id="ba782-221">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ba782-221">AppDomainID</span></span>|<span data-ttu-id="ba782-222">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-222">win:UInt64</span></span>|<span data-ttu-id="ba782-223">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba782-223">The application domain identifier.</span></span>|
|<span data-ttu-id="ba782-224">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ba782-224">ClrInstanceID</span></span>|<span data-ttu-id="ba782-225">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ba782-225">win:UInt16</span></span>|<span data-ttu-id="ba782-226">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ba782-226">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="threadterminated-event"></a><span data-ttu-id="ba782-227">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="ba782-227">ThreadTerminated Event</span></span>

<span data-ttu-id="ba782-228">La tabella seguente illustra la parola chiave e il livello:</span><span class="sxs-lookup"><span data-stu-id="ba782-228">The following table shows the keyword and level:</span></span>

|<span data-ttu-id="ba782-229">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="ba782-229">Keyword for raising the event</span></span>|<span data-ttu-id="ba782-230">Level</span><span class="sxs-lookup"><span data-stu-id="ba782-230">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="ba782-231">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="ba782-231">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="ba782-232">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-232">Informational(4)</span></span>|
|<span data-ttu-id="ba782-233">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="ba782-233">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="ba782-234">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ba782-234">Informational(4)</span></span>|

<span data-ttu-id="ba782-235">La tabella seguente mostra le informazioni sull'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-235">The following table shows the event information:</span></span>

|<span data-ttu-id="ba782-236">event</span><span class="sxs-lookup"><span data-stu-id="ba782-236">Event</span></span>|<span data-ttu-id="ba782-237">ID evento</span><span class="sxs-lookup"><span data-stu-id="ba782-237">Event ID</span></span>|<span data-ttu-id="ba782-238">Generato quando</span><span class="sxs-lookup"><span data-stu-id="ba782-238">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ThreadTerminated`|<span data-ttu-id="ba782-239">86</span><span class="sxs-lookup"><span data-stu-id="ba782-239">86</span></span>|<span data-ttu-id="ba782-240">Termina un thread.</span><span class="sxs-lookup"><span data-stu-id="ba782-240">A thread terminates.</span></span>|

<span data-ttu-id="ba782-241">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="ba782-241">The following table shows the event data:</span></span>

|<span data-ttu-id="ba782-242">Nome campo</span><span class="sxs-lookup"><span data-stu-id="ba782-242">Field name</span></span>|<span data-ttu-id="ba782-243">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ba782-243">Data type</span></span>|<span data-ttu-id="ba782-244">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba782-244">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="ba782-245">ThreadID</span><span class="sxs-lookup"><span data-stu-id="ba782-245">ThreadID</span></span>|<span data-ttu-id="ba782-246">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-246">win:UInt64</span></span>|<span data-ttu-id="ba782-247">L'identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="ba782-247">The thread identifier.</span></span>|
|<span data-ttu-id="ba782-248">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="ba782-248">AppDomainID</span></span>|<span data-ttu-id="ba782-249">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="ba782-249">win:UInt64</span></span>|<span data-ttu-id="ba782-250">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="ba782-250">The application domain identifier.</span></span>|
|<span data-ttu-id="ba782-251">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="ba782-251">ClrInstanceID</span></span>|<span data-ttu-id="ba782-252">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="ba782-252">win:UInt16</span></span>|<span data-ttu-id="ba782-253">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ba782-253">Unique ID for the instance of CLR or CoreCLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ba782-254">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba782-254">See also</span></span>

- [<span data-ttu-id="ba782-255">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="ba782-255">CLR ETW Events</span></span>](clr-etw-events.md)
