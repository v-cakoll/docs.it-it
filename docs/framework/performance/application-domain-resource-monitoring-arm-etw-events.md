---
title: Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e4002ae248022a9e4380c79174109494b5e4ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046776"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="afa26-102">Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)</span><span class="sxs-lookup"><span data-stu-id="afa26-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="afa26-103">Questi eventi forniscono informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="afa26-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="afa26-104">È possibile usare questi eventi o la funzionalità di monitoraggio delle risorse del dominio applicazione (ARM) per ottenere le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="afa26-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="afa26-105">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="afa26-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="afa26-106">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="afa26-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
- [<span data-ttu-id="afa26-107">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="afa26-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
- [<span data-ttu-id="afa26-108">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="afa26-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
- [<span data-ttu-id="afa26-109">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="afa26-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
- [<span data-ttu-id="afa26-110">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="afa26-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="afa26-111">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="afa26-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="afa26-112">Questo evento viene generato anche nel provider di rundown come `ThreadDC` (sotto la parola chiave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="afa26-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="afa26-113">Questo è l'unico evento che viene generato nel provider di rundown in questa categoria.</span><span class="sxs-lookup"><span data-stu-id="afa26-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="afa26-114">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="afa26-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="afa26-115">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="afa26-115">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="afa26-116">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="afa26-116">Keyword for raising the event</span></span>|<span data-ttu-id="afa26-117">Level</span><span class="sxs-lookup"><span data-stu-id="afa26-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="afa26-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="afa26-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="afa26-119">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-119">Informational(4)</span></span>|  
|<span data-ttu-id="afa26-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="afa26-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="afa26-121">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="afa26-122">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="afa26-123">event</span><span class="sxs-lookup"><span data-stu-id="afa26-123">Event</span></span>|<span data-ttu-id="afa26-124">ID evento</span><span class="sxs-lookup"><span data-stu-id="afa26-124">Event ID</span></span>|<span data-ttu-id="afa26-125">Generato quando</span><span class="sxs-lookup"><span data-stu-id="afa26-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="afa26-126">85</span><span class="sxs-lookup"><span data-stu-id="afa26-126">85</span></span>|<span data-ttu-id="afa26-127">Un thread è stato creato per il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="afa26-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="afa26-128">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="afa26-129">Nome campo</span><span class="sxs-lookup"><span data-stu-id="afa26-129">Field name</span></span>|<span data-ttu-id="afa26-130">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="afa26-130">Data type</span></span>|<span data-ttu-id="afa26-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afa26-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="afa26-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="afa26-132">ThreadID</span></span>|<span data-ttu-id="afa26-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-133">win:UInt64</span></span>|<span data-ttu-id="afa26-134">ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="afa26-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="afa26-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="afa26-135">AppDomainID</span></span>|<span data-ttu-id="afa26-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-136">win:UInt64</span></span>|<span data-ttu-id="afa26-137">Identificatore del dominio dell'applicazione per la quale l’attività thread viene segnalata.</span><span class="sxs-lookup"><span data-stu-id="afa26-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="afa26-138">Flags</span><span class="sxs-lookup"><span data-stu-id="afa26-138">Flags</span></span>|<span data-ttu-id="afa26-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="afa26-139">win:UInt32</span></span>|<span data-ttu-id="afa26-140">Flag di creazione del thread.</span><span class="sxs-lookup"><span data-stu-id="afa26-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="afa26-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="afa26-141">ManagedThreadIndex</span></span>|<span data-ttu-id="afa26-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="afa26-142">win:UInt32</span></span>|<span data-ttu-id="afa26-143">Indice gestito del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="afa26-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="afa26-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="afa26-144">OSThreadID</span></span>|<span data-ttu-id="afa26-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="afa26-145">win:UInt32</span></span>|<span data-ttu-id="afa26-146">ID del sistema operativo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="afa26-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="afa26-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="afa26-147">ClrInstanceID</span></span>|<span data-ttu-id="afa26-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="afa26-148">win:UInt16</span></span>|<span data-ttu-id="afa26-149">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="afa26-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="afa26-150">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="afa26-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="afa26-151">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="afa26-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="afa26-152">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="afa26-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="afa26-153">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="afa26-153">Keyword for raising the event</span></span>|<span data-ttu-id="afa26-154">Level</span><span class="sxs-lookup"><span data-stu-id="afa26-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="afa26-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="afa26-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="afa26-156">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="afa26-157">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="afa26-158">event</span><span class="sxs-lookup"><span data-stu-id="afa26-158">Event</span></span>|<span data-ttu-id="afa26-159">ID evento</span><span class="sxs-lookup"><span data-stu-id="afa26-159">Event ID</span></span>|<span data-ttu-id="afa26-160">Generato quando</span><span class="sxs-lookup"><span data-stu-id="afa26-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="afa26-161">83</span><span class="sxs-lookup"><span data-stu-id="afa26-161">83</span></span>|<span data-ttu-id="afa26-162">Ogni 4 MB di memoria (approssimativamente) viene allocato nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="afa26-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="afa26-163">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="afa26-164">Nome campo</span><span class="sxs-lookup"><span data-stu-id="afa26-164">Field name</span></span>|<span data-ttu-id="afa26-165">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="afa26-165">Data type</span></span>|<span data-ttu-id="afa26-166">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="afa26-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="afa26-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="afa26-167">AppDomainID</span></span>|<span data-ttu-id="afa26-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-168">win:UInt64</span></span>|<span data-ttu-id="afa26-169">Identificatore del dominio dell'applicazione per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="afa26-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="afa26-170">Allocato</span><span class="sxs-lookup"><span data-stu-id="afa26-170">Allocated</span></span>|<span data-ttu-id="afa26-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-171">win:UInt64</span></span>|<span data-ttu-id="afa26-172">Il numero totale di byte allocati in questo dominio applicazione, poiché è stato creato il dominio dell'applicazione (non viene sottratta la quantità di memoria liberata).</span><span class="sxs-lookup"><span data-stu-id="afa26-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="afa26-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="afa26-173">ClrInstanceID</span></span>|<span data-ttu-id="afa26-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="afa26-174">win:UInt16</span></span>|<span data-ttu-id="afa26-175">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="afa26-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="afa26-176">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="afa26-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="afa26-177">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="afa26-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="afa26-178">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="afa26-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="afa26-179">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="afa26-179">Keyword for raising the event</span></span>|<span data-ttu-id="afa26-180">Level</span><span class="sxs-lookup"><span data-stu-id="afa26-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="afa26-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="afa26-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="afa26-182">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="afa26-183">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="afa26-184">event</span><span class="sxs-lookup"><span data-stu-id="afa26-184">Event</span></span>|<span data-ttu-id="afa26-185">ID evento</span><span class="sxs-lookup"><span data-stu-id="afa26-185">Event ID</span></span>|<span data-ttu-id="afa26-186">Generato quando</span><span class="sxs-lookup"><span data-stu-id="afa26-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="afa26-187">84</span><span class="sxs-lookup"><span data-stu-id="afa26-187">84</span></span>|<span data-ttu-id="afa26-188">Ogni operazione di Garbage Collection è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="afa26-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="afa26-189">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="afa26-190">Nome campo</span><span class="sxs-lookup"><span data-stu-id="afa26-190">Field name</span></span>|<span data-ttu-id="afa26-191">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="afa26-191">Data type</span></span>|<span data-ttu-id="afa26-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afa26-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="afa26-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="afa26-193">AppDomainID</span></span>|<span data-ttu-id="afa26-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-194">win:UInt64</span></span>|<span data-ttu-id="afa26-195">Identificatore del dominio per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="afa26-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="afa26-196">Survived</span><span class="sxs-lookup"><span data-stu-id="afa26-196">Survived</span></span>|<span data-ttu-id="afa26-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-197">win:UInt64</span></span>|<span data-ttu-id="afa26-198">Il numero di byte rimasti dall'ultima raccolta e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="afa26-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="afa26-199">Questo numero è preciso e completo dopo una raccolta completa, ma può essere incompleto dopo una raccolta temporanea.</span><span class="sxs-lookup"><span data-stu-id="afa26-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="afa26-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="afa26-200">ProcessSurvived</span></span>|<span data-ttu-id="afa26-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-201">win:UInt64</span></span>|<span data-ttu-id="afa26-202">I byte totali rimasti dall'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="afa26-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="afa26-203">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="afa26-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="afa26-204">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.</span><span class="sxs-lookup"><span data-stu-id="afa26-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="afa26-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="afa26-205">ClrInstanceID</span></span>|<span data-ttu-id="afa26-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="afa26-206">win:UInt16</span></span>|<span data-ttu-id="afa26-207">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="afa26-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="afa26-208">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="afa26-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="afa26-209">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="afa26-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="afa26-210">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="afa26-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="afa26-211">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="afa26-211">Keyword for raising the event</span></span>|<span data-ttu-id="afa26-212">Level</span><span class="sxs-lookup"><span data-stu-id="afa26-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="afa26-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="afa26-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="afa26-214">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-214">Informational(4)</span></span>|  
|<span data-ttu-id="afa26-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="afa26-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="afa26-216">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="afa26-217">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="afa26-218">event</span><span class="sxs-lookup"><span data-stu-id="afa26-218">Event</span></span>|<span data-ttu-id="afa26-219">ID evento</span><span class="sxs-lookup"><span data-stu-id="afa26-219">Event ID</span></span>|<span data-ttu-id="afa26-220">Generato quando</span><span class="sxs-lookup"><span data-stu-id="afa26-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="afa26-221">87</span><span class="sxs-lookup"><span data-stu-id="afa26-221">87</span></span>|<span data-ttu-id="afa26-222">Un thread immette un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="afa26-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="afa26-223">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="afa26-224">Nome campo</span><span class="sxs-lookup"><span data-stu-id="afa26-224">Field name</span></span>|<span data-ttu-id="afa26-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="afa26-225">Data type</span></span>|<span data-ttu-id="afa26-226">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afa26-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="afa26-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="afa26-227">ThreadID</span></span>|<span data-ttu-id="afa26-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-228">win:UInt64</span></span>|<span data-ttu-id="afa26-229">L'identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="afa26-229">The thread identifier.</span></span>|  
|<span data-ttu-id="afa26-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="afa26-230">AppDomainID</span></span>|<span data-ttu-id="afa26-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-231">win:UInt64</span></span>|<span data-ttu-id="afa26-232">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="afa26-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="afa26-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="afa26-233">ClrInstanceID</span></span>|<span data-ttu-id="afa26-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="afa26-234">win:UInt16</span></span>|<span data-ttu-id="afa26-235">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="afa26-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="afa26-236">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="afa26-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="afa26-237">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="afa26-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="afa26-238">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="afa26-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="afa26-239">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="afa26-239">Keyword for raising the event</span></span>|<span data-ttu-id="afa26-240">Level</span><span class="sxs-lookup"><span data-stu-id="afa26-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="afa26-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="afa26-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="afa26-242">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-242">Informational(4)</span></span>|  
|<span data-ttu-id="afa26-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="afa26-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="afa26-244">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="afa26-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="afa26-245">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="afa26-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="afa26-246">event</span><span class="sxs-lookup"><span data-stu-id="afa26-246">Event</span></span>|<span data-ttu-id="afa26-247">ID evento</span><span class="sxs-lookup"><span data-stu-id="afa26-247">Event ID</span></span>|<span data-ttu-id="afa26-248">Generato quando</span><span class="sxs-lookup"><span data-stu-id="afa26-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="afa26-249">86</span><span class="sxs-lookup"><span data-stu-id="afa26-249">86</span></span>|<span data-ttu-id="afa26-250">Termina un thread.</span><span class="sxs-lookup"><span data-stu-id="afa26-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="afa26-251">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="afa26-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="afa26-252">Nome campo</span><span class="sxs-lookup"><span data-stu-id="afa26-252">Field name</span></span>|<span data-ttu-id="afa26-253">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="afa26-253">Data type</span></span>|<span data-ttu-id="afa26-254">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afa26-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="afa26-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="afa26-255">ThreadID</span></span>|<span data-ttu-id="afa26-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-256">win:UInt64</span></span>|<span data-ttu-id="afa26-257">L'identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="afa26-257">The thread identifier.</span></span>|  
|<span data-ttu-id="afa26-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="afa26-258">AppDomainID</span></span>|<span data-ttu-id="afa26-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="afa26-259">win:UInt64</span></span>|<span data-ttu-id="afa26-260">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="afa26-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="afa26-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="afa26-261">ClrInstanceID</span></span>|<span data-ttu-id="afa26-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="afa26-262">win:UInt16</span></span>|<span data-ttu-id="afa26-263">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="afa26-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afa26-264">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afa26-264">See also</span></span>

- [<span data-ttu-id="afa26-265">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="afa26-265">CLR ETW Events</span></span>](clr-etw-events.md)
