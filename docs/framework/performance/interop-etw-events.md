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
ms.openlocfilehash: 55097e38161ea5c76f4e46584241344ec5a52cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="f2188-102">Eventi ETW di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f2188-102">Interop ETW Events</span></span>
<span data-ttu-id="f2188-103"><a name="top"></a> Gli eventi di interoperabilità acquisiscono informazioni sulla generazione di stub e la memorizzazione nella cache di Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="f2188-103"><a name="top"></a> Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="f2188-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="f2188-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="f2188-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="f2188-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="f2188-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="f2188-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="f2188-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="f2188-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="f2188-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="f2188-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="f2188-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f2188-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="f2188-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="f2188-110">Keyword for raising the event</span></span>|<span data-ttu-id="f2188-111">Livello</span><span class="sxs-lookup"><span data-stu-id="f2188-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f2188-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="f2188-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="f2188-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f2188-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="f2188-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="f2188-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f2188-115">Evento</span><span class="sxs-lookup"><span data-stu-id="f2188-115">Event</span></span>|<span data-ttu-id="f2188-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="f2188-116">Event ID</span></span>|<span data-ttu-id="f2188-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="f2188-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="f2188-118">88</span><span class="sxs-lookup"><span data-stu-id="f2188-118">88</span></span>|<span data-ttu-id="f2188-119">È stato generato lo stub MSIL.</span><span class="sxs-lookup"><span data-stu-id="f2188-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="f2188-120">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f2188-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f2188-121">Nome campo</span><span class="sxs-lookup"><span data-stu-id="f2188-121">Field name</span></span>|<span data-ttu-id="f2188-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f2188-122">Data type</span></span>|<span data-ttu-id="f2188-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2188-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f2188-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="f2188-124">ModuleID</span></span>|<span data-ttu-id="f2188-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f2188-125">win:UInt16</span></span>|<span data-ttu-id="f2188-126">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="f2188-126">The module identifier.</span></span>|  
|<span data-ttu-id="f2188-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="f2188-127">StubMethodID</span></span>|<span data-ttu-id="f2188-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f2188-128">win:UInt64</span></span>|<span data-ttu-id="f2188-129">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="f2188-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="f2188-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="f2188-130">StubFlags</span></span>|<span data-ttu-id="f2188-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f2188-131">win:UInt64</span></span>|<span data-ttu-id="f2188-132">Flag per lo stub:</span><span class="sxs-lookup"><span data-stu-id="f2188-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="f2188-133">0x1 - Interoperabilità inversa.</span><span class="sxs-lookup"><span data-stu-id="f2188-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="f2188-134">0x2 - interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="f2188-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="f2188-135">0x4 - stub generato da NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="f2188-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="f2188-136">0x8 - Delegato.</span><span class="sxs-lookup"><span data-stu-id="f2188-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="f2188-137">0x10 - Argomento variabile.</span><span class="sxs-lookup"><span data-stu-id="f2188-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="f2188-138">0x20 - Computer chiamato non gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="f2188-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="f2188-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="f2188-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f2188-140">win:UInt32</span></span>|<span data-ttu-id="f2188-141">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="f2188-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="f2188-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-143">win:UnicodeString</span></span>|<span data-ttu-id="f2188-144">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f2188-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="f2188-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-146">win:UnicodeString</span></span>|<span data-ttu-id="f2188-147">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f2188-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="f2188-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-149">win:UnicodeString</span></span>|<span data-ttu-id="f2188-150">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f2188-151">NativeMethodSignature</span></span>|<span data-ttu-id="f2188-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-152">win:UnicodeString</span></span>|<span data-ttu-id="f2188-153">La firma del metodo nativo.</span><span class="sxs-lookup"><span data-stu-id="f2188-153">The native method signature.</span></span>|  
|<span data-ttu-id="f2188-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f2188-154">StubMethodSignature</span></span>|<span data-ttu-id="f2188-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-155">win:UnicodeString</span></span>|<span data-ttu-id="f2188-156">La firma del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="f2188-156">The stub method signature.</span></span>|  
|<span data-ttu-id="f2188-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="f2188-157">StubMethodILCode</span></span>|<span data-ttu-id="f2188-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-158">win:UnicodeString</span></span>|<span data-ttu-id="f2188-159">Il codice MSIL per il metodo stub.</span><span class="sxs-lookup"><span data-stu-id="f2188-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="f2188-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f2188-160">ClrInstanceID</span></span>|<span data-ttu-id="f2188-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f2188-161">win:UInt16</span></span>|<span data-ttu-id="f2188-162">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f2188-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f2188-163">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="f2188-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="f2188-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="f2188-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="f2188-165">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="f2188-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="f2188-166">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="f2188-166">Keyword for raising the event</span></span>|<span data-ttu-id="f2188-167">Livello</span><span class="sxs-lookup"><span data-stu-id="f2188-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="f2188-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="f2188-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="f2188-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f2188-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="f2188-170">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="f2188-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="f2188-171">Evento</span><span class="sxs-lookup"><span data-stu-id="f2188-171">Event</span></span>|<span data-ttu-id="f2188-172">ID evento</span><span class="sxs-lookup"><span data-stu-id="f2188-172">Event ID</span></span>|<span data-ttu-id="f2188-173">Generato quando</span><span class="sxs-lookup"><span data-stu-id="f2188-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="f2188-174">89</span><span class="sxs-lookup"><span data-stu-id="f2188-174">89</span></span>|<span data-ttu-id="f2188-175">La cache MSIL ha avuto accesso.</span><span class="sxs-lookup"><span data-stu-id="f2188-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="f2188-176">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f2188-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="f2188-177">Nome campo</span><span class="sxs-lookup"><span data-stu-id="f2188-177">Field name</span></span>|<span data-ttu-id="f2188-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f2188-178">Data type</span></span>|<span data-ttu-id="f2188-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2188-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="f2188-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="f2188-180">ModuleID</span></span>|<span data-ttu-id="f2188-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f2188-181">win:UInt16</span></span>|<span data-ttu-id="f2188-182">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="f2188-182">The module identifier.</span></span>|  
|<span data-ttu-id="f2188-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="f2188-183">StubMethodID</span></span>|<span data-ttu-id="f2188-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="f2188-184">win:UInt64</span></span>|<span data-ttu-id="f2188-185">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="f2188-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="f2188-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="f2188-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="f2188-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="f2188-187">win:UInt32</span></span>|<span data-ttu-id="f2188-188">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="f2188-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="f2188-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-190">win:UnicodeString</span></span>|<span data-ttu-id="f2188-191">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="f2188-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="f2188-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-193">win:UnicodeString</span></span>|<span data-ttu-id="f2188-194">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="f2188-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="f2188-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="f2188-196">win:UnicodeString</span></span>|<span data-ttu-id="f2188-197">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="f2188-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="f2188-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="f2188-198">ClrInstanceID</span></span>|<span data-ttu-id="f2188-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="f2188-199">win:UInt16</span></span>|<span data-ttu-id="f2188-200">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f2188-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="f2188-201">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="f2188-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="f2188-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2188-202">See Also</span></span>  
 [<span data-ttu-id="f2188-203">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="f2188-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
