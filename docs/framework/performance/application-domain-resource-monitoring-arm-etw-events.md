---
title: Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8442b8723476984b90f740beac912688719f1791
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689835"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a><span data-ttu-id="6337b-102">Eventi ETW di monitoraggio delle risorse del dominio applicazione (ARM)</span><span class="sxs-lookup"><span data-stu-id="6337b-102">Application Domain Resource Monitoring (ARM) ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="6337b-103">Questi eventi forniscono informazioni di diagnostica dettagliate sullo stato di un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6337b-103">These events provide detailed diagnostic information about the state of an application domain.</span></span> <span data-ttu-id="6337b-104">È possibile usare questi eventi o la funzionalità di monitoraggio delle risorse del dominio applicazione (ARM) per ottenere le stesse informazioni.</span><span class="sxs-lookup"><span data-stu-id="6337b-104">You can use these events or use the application domain resource monitoring (ARM) feature to obtain the same information.</span></span>  
  
 <span data-ttu-id="6337b-105">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="6337b-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="6337b-106">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="6337b-106">ThreadCreated Event</span></span>](#threadcreated_event)  
  
-   [<span data-ttu-id="6337b-107">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="6337b-107">AppDomainMemAllocated Event</span></span>](#appdomainmemallocated_event)  
  
-   [<span data-ttu-id="6337b-108">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="6337b-108">AppDomainMemSurvived Event</span></span>](#appdomainmemsurvived_event)  
  
-   [<span data-ttu-id="6337b-109">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="6337b-109">ThreadAppDomainEnter Event</span></span>](#threadappdomainenter_event)  
  
-   [<span data-ttu-id="6337b-110">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="6337b-110">ThreadTerminated Event</span></span>](#threadterminated_event)  
  
<a name="threadcreated_event"></a>   
## <a name="threadcreated-event"></a><span data-ttu-id="6337b-111">Evento ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="6337b-111">ThreadCreated Event</span></span>  
 <span data-ttu-id="6337b-112">Questo evento viene generato anche nel provider di rundown come `ThreadDC` (sotto la parola chiave `AppDomainResourceManagementRundownKeyword` ).</span><span class="sxs-lookup"><span data-stu-id="6337b-112">This event is also raised  under the rundown provider as `ThreadDC` (under the `AppDomainResourceManagementRundownKeyword` keyword).</span></span> <span data-ttu-id="6337b-113">Questo è l'unico evento che viene generato nel provider di rundown in questa categoria.</span><span class="sxs-lookup"><span data-stu-id="6337b-113">This is the only event that is raised under the rundown provider in this category.</span></span>  
  
 <span data-ttu-id="6337b-114">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="6337b-114">The following table shows the keyword and level.</span></span> <span data-ttu-id="6337b-115">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="6337b-115">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="6337b-116">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6337b-116">Keyword for raising the event</span></span>|<span data-ttu-id="6337b-117">Livello</span><span class="sxs-lookup"><span data-stu-id="6337b-117">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6337b-118">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6337b-118">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6337b-119">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-119">Informational(4)</span></span>|  
|<span data-ttu-id="6337b-120">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6337b-120">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6337b-121">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-121">Informational(4)</span></span>|  
  
 <span data-ttu-id="6337b-122">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-122">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6337b-123">Evento</span><span class="sxs-lookup"><span data-stu-id="6337b-123">Event</span></span>|<span data-ttu-id="6337b-124">ID evento</span><span class="sxs-lookup"><span data-stu-id="6337b-124">Event ID</span></span>|<span data-ttu-id="6337b-125">Generato quando</span><span class="sxs-lookup"><span data-stu-id="6337b-125">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadCreated`|<span data-ttu-id="6337b-126">85</span><span class="sxs-lookup"><span data-stu-id="6337b-126">85</span></span>|<span data-ttu-id="6337b-127">Un thread è stato creato per il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6337b-127">A thread was created for the application domain.</span></span>|  
  
 <span data-ttu-id="6337b-128">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-128">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6337b-129">Nome campo</span><span class="sxs-lookup"><span data-stu-id="6337b-129">Field name</span></span>|<span data-ttu-id="6337b-130">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6337b-130">Data type</span></span>|<span data-ttu-id="6337b-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6337b-131">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6337b-132">ThreadID</span><span class="sxs-lookup"><span data-stu-id="6337b-132">ThreadID</span></span>|<span data-ttu-id="6337b-133">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-133">win:UInt64</span></span>|<span data-ttu-id="6337b-134">ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="6337b-134">ID of the thread that was created.</span></span>|  
|<span data-ttu-id="6337b-135">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6337b-135">AppDomainID</span></span>|<span data-ttu-id="6337b-136">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-136">win:UInt64</span></span>|<span data-ttu-id="6337b-137">Identificatore del dominio dell'applicazione per la quale l’attività thread viene segnalata.</span><span class="sxs-lookup"><span data-stu-id="6337b-137">Identifier of the application domain for which thread activity is being reported.</span></span>|  
|<span data-ttu-id="6337b-138">Flags</span><span class="sxs-lookup"><span data-stu-id="6337b-138">Flags</span></span>|<span data-ttu-id="6337b-139">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6337b-139">win:UInt32</span></span>|<span data-ttu-id="6337b-140">Flag di creazione del thread.</span><span class="sxs-lookup"><span data-stu-id="6337b-140">Thread creation flags.</span></span>|  
|<span data-ttu-id="6337b-141">ManagedThreadIndex</span><span class="sxs-lookup"><span data-stu-id="6337b-141">ManagedThreadIndex</span></span>|<span data-ttu-id="6337b-142">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6337b-142">win:UInt32</span></span>|<span data-ttu-id="6337b-143">Indice gestito del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="6337b-143">Managed index of the thread that was created.</span></span>|  
|<span data-ttu-id="6337b-144">OSThreadID</span><span class="sxs-lookup"><span data-stu-id="6337b-144">OSThreadID</span></span>|<span data-ttu-id="6337b-145">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="6337b-145">win:UInt32</span></span>|<span data-ttu-id="6337b-146">ID del sistema operativo che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="6337b-146">Operating system ID of the thread that was created.</span></span>|  
|<span data-ttu-id="6337b-147">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6337b-147">ClrInstanceID</span></span>|<span data-ttu-id="6337b-148">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6337b-148">win:UInt16</span></span>|<span data-ttu-id="6337b-149">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6337b-149">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6337b-150">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="6337b-150">Back to top</span></span>](#top)  
  
<a name="appdomainmemallocated_event"></a>   
## <a name="appdomainmemallocated-event"></a><span data-ttu-id="6337b-151">Evento AppDomainMemAllocated</span><span class="sxs-lookup"><span data-stu-id="6337b-151">AppDomainMemAllocated Event</span></span>  
 <span data-ttu-id="6337b-152">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="6337b-152">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6337b-153">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6337b-153">Keyword for raising the event</span></span>|<span data-ttu-id="6337b-154">Livello</span><span class="sxs-lookup"><span data-stu-id="6337b-154">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6337b-155">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6337b-155">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6337b-156">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-156">Informational(4)</span></span>|  
  
 <span data-ttu-id="6337b-157">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-157">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6337b-158">Evento</span><span class="sxs-lookup"><span data-stu-id="6337b-158">Event</span></span>|<span data-ttu-id="6337b-159">ID evento</span><span class="sxs-lookup"><span data-stu-id="6337b-159">Event ID</span></span>|<span data-ttu-id="6337b-160">Generato quando</span><span class="sxs-lookup"><span data-stu-id="6337b-160">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemAllocated`|<span data-ttu-id="6337b-161">83</span><span class="sxs-lookup"><span data-stu-id="6337b-161">83</span></span>|<span data-ttu-id="6337b-162">Ogni 4 MB di memoria (approssimativamente) viene allocato nel dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6337b-162">Every 4 MB of memory (approximately) is allocated in the application domain.</span></span>|  
  
 <span data-ttu-id="6337b-163">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-163">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6337b-164">Nome campo</span><span class="sxs-lookup"><span data-stu-id="6337b-164">Field name</span></span>|<span data-ttu-id="6337b-165">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6337b-165">Data type</span></span>|<span data-ttu-id="6337b-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6337b-166">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6337b-167">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6337b-167">AppDomainID</span></span>|<span data-ttu-id="6337b-168">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-168">win:UInt64</span></span>|<span data-ttu-id="6337b-169">Identificatore del dominio dell'applicazione per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="6337b-169">Identifier of the application domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="6337b-170">Allocato</span><span class="sxs-lookup"><span data-stu-id="6337b-170">Allocated</span></span>|<span data-ttu-id="6337b-171">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-171">win:UInt64</span></span>|<span data-ttu-id="6337b-172">Il numero totale di byte allocati in questo dominio applicazione, poiché è stato creato il dominio dell'applicazione (non viene sottratta la quantità di memoria liberata).</span><span class="sxs-lookup"><span data-stu-id="6337b-172">The total number of bytes allocated in this application domain since the application domain was created (the amount of freed memory is not subtracted).</span></span>|  
|<span data-ttu-id="6337b-173">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6337b-173">ClrInstanceID</span></span>|<span data-ttu-id="6337b-174">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6337b-174">win:UInt16</span></span>|<span data-ttu-id="6337b-175">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6337b-175">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6337b-176">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="6337b-176">Back to top</span></span>](#top)  
  
<a name="appdomainmemsurvived_event"></a>   
## <a name="appdomainmemsurvived-event"></a><span data-ttu-id="6337b-177">Evento AppDomainMemSurvived</span><span class="sxs-lookup"><span data-stu-id="6337b-177">AppDomainMemSurvived Event</span></span>  
 <span data-ttu-id="6337b-178">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="6337b-178">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6337b-179">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6337b-179">Keyword for raising the event</span></span>|<span data-ttu-id="6337b-180">Livello</span><span class="sxs-lookup"><span data-stu-id="6337b-180">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6337b-181">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6337b-181">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6337b-182">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-182">Informational(4)</span></span>|  
  
 <span data-ttu-id="6337b-183">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-183">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6337b-184">Evento</span><span class="sxs-lookup"><span data-stu-id="6337b-184">Event</span></span>|<span data-ttu-id="6337b-185">ID evento</span><span class="sxs-lookup"><span data-stu-id="6337b-185">Event ID</span></span>|<span data-ttu-id="6337b-186">Generato quando</span><span class="sxs-lookup"><span data-stu-id="6337b-186">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AppDomainMemSurvived`|<span data-ttu-id="6337b-187">84</span><span class="sxs-lookup"><span data-stu-id="6337b-187">84</span></span>|<span data-ttu-id="6337b-188">Ogni operazione di Garbage Collection è stata terminata.</span><span class="sxs-lookup"><span data-stu-id="6337b-188">Each garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="6337b-189">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-189">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6337b-190">Nome campo</span><span class="sxs-lookup"><span data-stu-id="6337b-190">Field name</span></span>|<span data-ttu-id="6337b-191">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6337b-191">Data type</span></span>|<span data-ttu-id="6337b-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6337b-192">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6337b-193">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6337b-193">AppDomainID</span></span>|<span data-ttu-id="6337b-194">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-194">win:UInt64</span></span>|<span data-ttu-id="6337b-195">Identificatore del dominio per la quale viene segnalato l’utilizzo della risorsa.</span><span class="sxs-lookup"><span data-stu-id="6337b-195">Identifier of the domain for which resource usage is being reported.</span></span>|  
|<span data-ttu-id="6337b-196">Survived</span><span class="sxs-lookup"><span data-stu-id="6337b-196">Survived</span></span>|<span data-ttu-id="6337b-197">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-197">win:UInt64</span></span>|<span data-ttu-id="6337b-198">Il numero di byte rimasti dall'ultima raccolta e a cui fa riferimento il dominio applicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="6337b-198">The number of bytes that survived after the last collection and that are known to be held by this application domain.</span></span> <span data-ttu-id="6337b-199">Questo numero è preciso e completo dopo una raccolta completa, ma può essere incompleto dopo una raccolta temporanea.</span><span class="sxs-lookup"><span data-stu-id="6337b-199">This number is accurate and complete after a full collection, but may be incomplete after an ephemeral collection.</span></span>|  
|<span data-ttu-id="6337b-200">ProcessSurvived</span><span class="sxs-lookup"><span data-stu-id="6337b-200">ProcessSurvived</span></span>|<span data-ttu-id="6337b-201">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-201">win:UInt64</span></span>|<span data-ttu-id="6337b-202">I byte totali rimasti dall'ultima raccolta.</span><span class="sxs-lookup"><span data-stu-id="6337b-202">The total bytes that survived from the last collection.</span></span> <span data-ttu-id="6337b-203">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi negli heap gestiti.</span><span class="sxs-lookup"><span data-stu-id="6337b-203">After a full collection, this number represents the number of bytes being held live in managed heaps.</span></span> <span data-ttu-id="6337b-204">Dopo una raccolta completa, questo numero rappresenta il numero di byte mantenuti attivi in generazioni temporanee.</span><span class="sxs-lookup"><span data-stu-id="6337b-204">After an ephemeral collection, this number represents the number of bytes held live in ephemeral generations.</span></span>|  
|<span data-ttu-id="6337b-205">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6337b-205">ClrInstanceID</span></span>|<span data-ttu-id="6337b-206">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6337b-206">win:UInt16</span></span>|<span data-ttu-id="6337b-207">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6337b-207">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6337b-208">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="6337b-208">Back to top</span></span>](#top)  
  
<a name="threadappdomainenter_event"></a>   
## <a name="threadappdomainenter-event"></a><span data-ttu-id="6337b-209">Evento ThreadAppDomainEnter</span><span class="sxs-lookup"><span data-stu-id="6337b-209">ThreadAppDomainEnter Event</span></span>  
 <span data-ttu-id="6337b-210">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="6337b-210">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6337b-211">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6337b-211">Keyword for raising the event</span></span>|<span data-ttu-id="6337b-212">Livello</span><span class="sxs-lookup"><span data-stu-id="6337b-212">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6337b-213">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6337b-213">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6337b-214">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-214">Informational(4)</span></span>|  
|<span data-ttu-id="6337b-215">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6337b-215">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6337b-216">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-216">Informational(4)</span></span>|  
  
 <span data-ttu-id="6337b-217">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-217">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6337b-218">Evento</span><span class="sxs-lookup"><span data-stu-id="6337b-218">Event</span></span>|<span data-ttu-id="6337b-219">ID evento</span><span class="sxs-lookup"><span data-stu-id="6337b-219">Event ID</span></span>|<span data-ttu-id="6337b-220">Generato quando</span><span class="sxs-lookup"><span data-stu-id="6337b-220">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadAppDomainEnter`|<span data-ttu-id="6337b-221">87</span><span class="sxs-lookup"><span data-stu-id="6337b-221">87</span></span>|<span data-ttu-id="6337b-222">Un thread immette un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6337b-222">A thread enters an application domain.</span></span>|  
  
 <span data-ttu-id="6337b-223">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-223">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="6337b-224">Nome campo</span><span class="sxs-lookup"><span data-stu-id="6337b-224">Field name</span></span>|<span data-ttu-id="6337b-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6337b-225">Data type</span></span>|<span data-ttu-id="6337b-226">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6337b-226">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6337b-227">ThreadID</span><span class="sxs-lookup"><span data-stu-id="6337b-227">ThreadID</span></span>|<span data-ttu-id="6337b-228">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-228">win:UInt64</span></span>|<span data-ttu-id="6337b-229">L'identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="6337b-229">The thread identifier.</span></span>|  
|<span data-ttu-id="6337b-230">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6337b-230">AppDomainID</span></span>|<span data-ttu-id="6337b-231">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-231">win:UInt64</span></span>|<span data-ttu-id="6337b-232">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6337b-232">The application domain identifier.</span></span>|  
|<span data-ttu-id="6337b-233">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6337b-233">ClrInstanceID</span></span>|<span data-ttu-id="6337b-234">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6337b-234">win:UInt16</span></span>|<span data-ttu-id="6337b-235">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6337b-235">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="6337b-236">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="6337b-236">Back to top</span></span>](#top)  
  
<a name="threadterminated_event"></a>   
## <a name="threadterminated-event"></a><span data-ttu-id="6337b-237">Evento ThreadTerminated</span><span class="sxs-lookup"><span data-stu-id="6337b-237">ThreadTerminated Event</span></span>  
 <span data-ttu-id="6337b-238">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="6337b-238">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="6337b-239">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="6337b-239">Keyword for raising the event</span></span>|<span data-ttu-id="6337b-240">Livello</span><span class="sxs-lookup"><span data-stu-id="6337b-240">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="6337b-241">`AppDomainResourceManagementKeyword` (0x800)</span><span class="sxs-lookup"><span data-stu-id="6337b-241">`AppDomainResourceManagementKeyword` (0x800)</span></span>|<span data-ttu-id="6337b-242">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-242">Informational(4)</span></span>|  
|<span data-ttu-id="6337b-243">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="6337b-243">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="6337b-244">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="6337b-244">Informational(4)</span></span>|  
  
 <span data-ttu-id="6337b-245">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="6337b-245">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="6337b-246">Evento</span><span class="sxs-lookup"><span data-stu-id="6337b-246">Event</span></span>|<span data-ttu-id="6337b-247">ID evento</span><span class="sxs-lookup"><span data-stu-id="6337b-247">Event ID</span></span>|<span data-ttu-id="6337b-248">Generato quando</span><span class="sxs-lookup"><span data-stu-id="6337b-248">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadTerminated`|<span data-ttu-id="6337b-249">86</span><span class="sxs-lookup"><span data-stu-id="6337b-249">86</span></span>|<span data-ttu-id="6337b-250">Termina un thread.</span><span class="sxs-lookup"><span data-stu-id="6337b-250">A thread terminates.</span></span>|  
  
 <span data-ttu-id="6337b-251">La tabella seguente mostra i dati dell'evento:</span><span class="sxs-lookup"><span data-stu-id="6337b-251">The following table shows the event data:</span></span>  
  
|<span data-ttu-id="6337b-252">Nome campo</span><span class="sxs-lookup"><span data-stu-id="6337b-252">Field name</span></span>|<span data-ttu-id="6337b-253">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6337b-253">Data type</span></span>|<span data-ttu-id="6337b-254">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6337b-254">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="6337b-255">ThreadID</span><span class="sxs-lookup"><span data-stu-id="6337b-255">ThreadID</span></span>|<span data-ttu-id="6337b-256">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-256">win:UInt64</span></span>|<span data-ttu-id="6337b-257">L'identificatore del thread.</span><span class="sxs-lookup"><span data-stu-id="6337b-257">The thread identifier.</span></span>|  
|<span data-ttu-id="6337b-258">AppDomainID</span><span class="sxs-lookup"><span data-stu-id="6337b-258">AppDomainID</span></span>|<span data-ttu-id="6337b-259">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="6337b-259">win:UInt64</span></span>|<span data-ttu-id="6337b-260">L’identificatore di dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6337b-260">The application domain identifier.</span></span>|  
|<span data-ttu-id="6337b-261">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="6337b-261">ClrInstanceID</span></span>|<span data-ttu-id="6337b-262">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="6337b-262">win:UInt16</span></span>|<span data-ttu-id="6337b-263">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="6337b-263">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6337b-264">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6337b-264">See also</span></span>
- [<span data-ttu-id="6337b-265">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="6337b-265">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
