---
title: Eventi ETW di interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09b2848619256a255cc27f0268d46e5e6db8cbe4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083608"
---
# <a name="interop-etw-events"></a><span data-ttu-id="d4e04-102">Eventi ETW di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="d4e04-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="d4e04-103">Gli eventi di interoperabilità acquisiscono informazioni sulla generazione di stub e la memorizzazione nella cache di Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d4e04-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="d4e04-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="d4e04-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="d4e04-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="d4e04-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="d4e04-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="d4e04-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="d4e04-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="d4e04-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="d4e04-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="d4e04-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="d4e04-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d4e04-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d4e04-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="d4e04-110">Keyword for raising the event</span></span>|<span data-ttu-id="d4e04-111">Livello</span><span class="sxs-lookup"><span data-stu-id="d4e04-111">Level</span></span>|  
|-----------------------------------|-----------|  
|`InteropKeyword` <span data-ttu-id="d4e04-112">(0x2000)</span><span class="sxs-lookup"><span data-stu-id="d4e04-112">(0x2000)</span></span>|<span data-ttu-id="d4e04-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d4e04-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="d4e04-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="d4e04-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d4e04-115">event</span><span class="sxs-lookup"><span data-stu-id="d4e04-115">Event</span></span>|<span data-ttu-id="d4e04-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="d4e04-116">Event ID</span></span>|<span data-ttu-id="d4e04-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="d4e04-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="d4e04-118">88</span><span class="sxs-lookup"><span data-stu-id="d4e04-118">88</span></span>|<span data-ttu-id="d4e04-119">È stato generato lo stub MSIL.</span><span class="sxs-lookup"><span data-stu-id="d4e04-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="d4e04-120">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d4e04-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d4e04-121">Nome campo</span><span class="sxs-lookup"><span data-stu-id="d4e04-121">Field name</span></span>|<span data-ttu-id="d4e04-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d4e04-122">Data type</span></span>|<span data-ttu-id="d4e04-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4e04-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d4e04-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="d4e04-124">ModuleID</span></span>|<span data-ttu-id="d4e04-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d4e04-125">win:UInt16</span></span>|<span data-ttu-id="d4e04-126">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="d4e04-126">The module identifier.</span></span>|  
|<span data-ttu-id="d4e04-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="d4e04-127">StubMethodID</span></span>|<span data-ttu-id="d4e04-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d4e04-128">win:UInt64</span></span>|<span data-ttu-id="d4e04-129">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d4e04-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="d4e04-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="d4e04-130">StubFlags</span></span>|<span data-ttu-id="d4e04-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d4e04-131">win:UInt64</span></span>|<span data-ttu-id="d4e04-132">Flag per lo stub:</span><span class="sxs-lookup"><span data-stu-id="d4e04-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="d4e04-133">0x1 - Interoperabilità inversa.</span><span class="sxs-lookup"><span data-stu-id="d4e04-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="d4e04-134">0x2 - interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="d4e04-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="d4e04-135">0x4 - stub generato da NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="d4e04-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="d4e04-136">0x8 - Delegato.</span><span class="sxs-lookup"><span data-stu-id="d4e04-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="d4e04-137">0x10 - Argomento variabile.</span><span class="sxs-lookup"><span data-stu-id="d4e04-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="d4e04-138">0x20 - Computer chiamato non gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="d4e04-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="d4e04-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="d4e04-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d4e04-140">win:UInt32</span></span>|<span data-ttu-id="d4e04-141">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="d4e04-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="d4e04-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-143">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-144">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="d4e04-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="d4e04-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-146">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-147">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d4e04-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="d4e04-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-149">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-150">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d4e04-151">NativeMethodSignature</span></span>|<span data-ttu-id="d4e04-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-152">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-153">La firma del metodo nativo.</span><span class="sxs-lookup"><span data-stu-id="d4e04-153">The native method signature.</span></span>|  
|<span data-ttu-id="d4e04-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d4e04-154">StubMethodSignature</span></span>|<span data-ttu-id="d4e04-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-155">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-156">La firma del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d4e04-156">The stub method signature.</span></span>|  
|<span data-ttu-id="d4e04-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="d4e04-157">StubMethodILCode</span></span>|<span data-ttu-id="d4e04-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-158">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-159">Il codice MSIL per il metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d4e04-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="d4e04-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d4e04-160">ClrInstanceID</span></span>|<span data-ttu-id="d4e04-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d4e04-161">win:UInt16</span></span>|<span data-ttu-id="d4e04-162">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d4e04-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d4e04-163">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="d4e04-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="d4e04-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="d4e04-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="d4e04-165">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="d4e04-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d4e04-166">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="d4e04-166">Keyword for raising the event</span></span>|<span data-ttu-id="d4e04-167">Livello</span><span class="sxs-lookup"><span data-stu-id="d4e04-167">Level</span></span>|  
|-----------------------------------|-----------|  
|`InteropKeyword` <span data-ttu-id="d4e04-168">(0x2000)</span><span class="sxs-lookup"><span data-stu-id="d4e04-168">(0x2000)</span></span>|<span data-ttu-id="d4e04-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d4e04-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="d4e04-170">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="d4e04-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d4e04-171">event</span><span class="sxs-lookup"><span data-stu-id="d4e04-171">Event</span></span>|<span data-ttu-id="d4e04-172">ID evento</span><span class="sxs-lookup"><span data-stu-id="d4e04-172">Event ID</span></span>|<span data-ttu-id="d4e04-173">Generato quando</span><span class="sxs-lookup"><span data-stu-id="d4e04-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="d4e04-174">89</span><span class="sxs-lookup"><span data-stu-id="d4e04-174">89</span></span>|<span data-ttu-id="d4e04-175">La cache MSIL ha avuto accesso.</span><span class="sxs-lookup"><span data-stu-id="d4e04-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="d4e04-176">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d4e04-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d4e04-177">Nome campo</span><span class="sxs-lookup"><span data-stu-id="d4e04-177">Field name</span></span>|<span data-ttu-id="d4e04-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d4e04-178">Data type</span></span>|<span data-ttu-id="d4e04-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4e04-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d4e04-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="d4e04-180">ModuleID</span></span>|<span data-ttu-id="d4e04-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d4e04-181">win:UInt16</span></span>|<span data-ttu-id="d4e04-182">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="d4e04-182">The module identifier.</span></span>|  
|<span data-ttu-id="d4e04-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="d4e04-183">StubMethodID</span></span>|<span data-ttu-id="d4e04-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d4e04-184">win:UInt64</span></span>|<span data-ttu-id="d4e04-185">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d4e04-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="d4e04-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="d4e04-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="d4e04-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d4e04-187">win:UInt32</span></span>|<span data-ttu-id="d4e04-188">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="d4e04-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="d4e04-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-190">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-191">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="d4e04-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="d4e04-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-193">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-194">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d4e04-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="d4e04-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d4e04-196">win:UnicodeString</span></span>|<span data-ttu-id="d4e04-197">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d4e04-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="d4e04-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d4e04-198">ClrInstanceID</span></span>|<span data-ttu-id="d4e04-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d4e04-199">win:UInt16</span></span>|<span data-ttu-id="d4e04-200">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d4e04-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d4e04-201">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="d4e04-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="d4e04-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4e04-202">See also</span></span>

- [<span data-ttu-id="d4e04-203">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="d4e04-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
