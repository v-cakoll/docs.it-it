---
title: "Eventi ETW di interoperabilità"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5670eb910406626096f776d3b4192e2d58d7ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="225ed-102">Eventi ETW di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="225ed-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="225ed-103">Gli eventi di interoperabilità acquisiscono informazioni sulla generazione di stub e la memorizzazione nella cache di Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="225ed-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="225ed-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="225ed-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="225ed-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="225ed-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="225ed-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="225ed-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="225ed-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="225ed-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="225ed-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="225ed-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="225ed-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="225ed-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="225ed-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="225ed-110">Keyword for raising the event</span></span>|<span data-ttu-id="225ed-111">Livello</span><span class="sxs-lookup"><span data-stu-id="225ed-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="225ed-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="225ed-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="225ed-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="225ed-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="225ed-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="225ed-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="225ed-115">Evento</span><span class="sxs-lookup"><span data-stu-id="225ed-115">Event</span></span>|<span data-ttu-id="225ed-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="225ed-116">Event ID</span></span>|<span data-ttu-id="225ed-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="225ed-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="225ed-118">88</span><span class="sxs-lookup"><span data-stu-id="225ed-118">88</span></span>|<span data-ttu-id="225ed-119">È stato generato lo stub MSIL.</span><span class="sxs-lookup"><span data-stu-id="225ed-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="225ed-120">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="225ed-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="225ed-121">Nome campo</span><span class="sxs-lookup"><span data-stu-id="225ed-121">Field name</span></span>|<span data-ttu-id="225ed-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="225ed-122">Data type</span></span>|<span data-ttu-id="225ed-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="225ed-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="225ed-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="225ed-124">ModuleID</span></span>|<span data-ttu-id="225ed-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="225ed-125">win:UInt16</span></span>|<span data-ttu-id="225ed-126">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="225ed-126">The module identifier.</span></span>|  
|<span data-ttu-id="225ed-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="225ed-127">StubMethodID</span></span>|<span data-ttu-id="225ed-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="225ed-128">win:UInt64</span></span>|<span data-ttu-id="225ed-129">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="225ed-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="225ed-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="225ed-130">StubFlags</span></span>|<span data-ttu-id="225ed-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="225ed-131">win:UInt64</span></span>|<span data-ttu-id="225ed-132">Flag per lo stub:</span><span class="sxs-lookup"><span data-stu-id="225ed-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="225ed-133">0x1 - Interoperabilità inversa.</span><span class="sxs-lookup"><span data-stu-id="225ed-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="225ed-134">0x2 - interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="225ed-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="225ed-135">0x4 - stub generato da NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="225ed-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="225ed-136">0x8 - Delegato.</span><span class="sxs-lookup"><span data-stu-id="225ed-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="225ed-137">0x10 - Argomento variabile.</span><span class="sxs-lookup"><span data-stu-id="225ed-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="225ed-138">0x20 - Computer chiamato non gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="225ed-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="225ed-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="225ed-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="225ed-140">win:UInt32</span></span>|<span data-ttu-id="225ed-141">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="225ed-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="225ed-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-143">win:UnicodeString</span></span>|<span data-ttu-id="225ed-144">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="225ed-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="225ed-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-146">win:UnicodeString</span></span>|<span data-ttu-id="225ed-147">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="225ed-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="225ed-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-149">win:UnicodeString</span></span>|<span data-ttu-id="225ed-150">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="225ed-151">NativeMethodSignature</span></span>|<span data-ttu-id="225ed-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-152">win:UnicodeString</span></span>|<span data-ttu-id="225ed-153">La firma del metodo nativo.</span><span class="sxs-lookup"><span data-stu-id="225ed-153">The native method signature.</span></span>|  
|<span data-ttu-id="225ed-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="225ed-154">StubMethodSignature</span></span>|<span data-ttu-id="225ed-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-155">win:UnicodeString</span></span>|<span data-ttu-id="225ed-156">La firma del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="225ed-156">The stub method signature.</span></span>|  
|<span data-ttu-id="225ed-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="225ed-157">StubMethodILCode</span></span>|<span data-ttu-id="225ed-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-158">win:UnicodeString</span></span>|<span data-ttu-id="225ed-159">Il codice MSIL per il metodo stub.</span><span class="sxs-lookup"><span data-stu-id="225ed-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="225ed-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="225ed-160">ClrInstanceID</span></span>|<span data-ttu-id="225ed-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="225ed-161">win:UInt16</span></span>|<span data-ttu-id="225ed-162">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="225ed-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="225ed-163">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="225ed-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="225ed-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="225ed-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="225ed-165">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="225ed-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="225ed-166">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="225ed-166">Keyword for raising the event</span></span>|<span data-ttu-id="225ed-167">Livello</span><span class="sxs-lookup"><span data-stu-id="225ed-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="225ed-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="225ed-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="225ed-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="225ed-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="225ed-170">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="225ed-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="225ed-171">Evento</span><span class="sxs-lookup"><span data-stu-id="225ed-171">Event</span></span>|<span data-ttu-id="225ed-172">ID evento</span><span class="sxs-lookup"><span data-stu-id="225ed-172">Event ID</span></span>|<span data-ttu-id="225ed-173">Generato quando</span><span class="sxs-lookup"><span data-stu-id="225ed-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="225ed-174">89</span><span class="sxs-lookup"><span data-stu-id="225ed-174">89</span></span>|<span data-ttu-id="225ed-175">La cache MSIL ha avuto accesso.</span><span class="sxs-lookup"><span data-stu-id="225ed-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="225ed-176">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="225ed-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="225ed-177">Nome campo</span><span class="sxs-lookup"><span data-stu-id="225ed-177">Field name</span></span>|<span data-ttu-id="225ed-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="225ed-178">Data type</span></span>|<span data-ttu-id="225ed-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="225ed-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="225ed-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="225ed-180">ModuleID</span></span>|<span data-ttu-id="225ed-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="225ed-181">win:UInt16</span></span>|<span data-ttu-id="225ed-182">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="225ed-182">The module identifier.</span></span>|  
|<span data-ttu-id="225ed-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="225ed-183">StubMethodID</span></span>|<span data-ttu-id="225ed-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="225ed-184">win:UInt64</span></span>|<span data-ttu-id="225ed-185">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="225ed-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="225ed-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="225ed-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="225ed-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="225ed-187">win:UInt32</span></span>|<span data-ttu-id="225ed-188">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="225ed-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="225ed-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-190">win:UnicodeString</span></span>|<span data-ttu-id="225ed-191">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="225ed-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="225ed-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-193">win:UnicodeString</span></span>|<span data-ttu-id="225ed-194">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="225ed-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="225ed-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="225ed-196">win:UnicodeString</span></span>|<span data-ttu-id="225ed-197">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="225ed-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="225ed-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="225ed-198">ClrInstanceID</span></span>|<span data-ttu-id="225ed-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="225ed-199">win:UInt16</span></span>|<span data-ttu-id="225ed-200">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="225ed-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="225ed-201">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="225ed-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="225ed-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="225ed-202">See Also</span></span>  
 [<span data-ttu-id="225ed-203">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="225ed-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
