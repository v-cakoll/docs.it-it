---
title: Eventi ETW di interoperabilità
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 787c6221b651a53dbb932a5a9d0edea123e1d97d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046432"
---
# <a name="interop-etw-events"></a><span data-ttu-id="d3df0-102">Eventi ETW di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="d3df0-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="d3df0-103">Gli eventi di interoperabilità acquisiscono informazioni sulla generazione di stub e la memorizzazione nella cache di Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d3df0-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="d3df0-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="d3df0-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="d3df0-105">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="d3df0-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
- [<span data-ttu-id="d3df0-106">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="d3df0-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="d3df0-107">Evento ILStubGenerated</span><span class="sxs-lookup"><span data-stu-id="d3df0-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="d3df0-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="d3df0-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="d3df0-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d3df0-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="d3df0-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="d3df0-110">Keyword for raising the event</span></span>|<span data-ttu-id="d3df0-111">Level</span><span class="sxs-lookup"><span data-stu-id="d3df0-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d3df0-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="d3df0-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="d3df0-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d3df0-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="d3df0-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="d3df0-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d3df0-115">event</span><span class="sxs-lookup"><span data-stu-id="d3df0-115">Event</span></span>|<span data-ttu-id="d3df0-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="d3df0-116">Event ID</span></span>|<span data-ttu-id="d3df0-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="d3df0-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="d3df0-118">88</span><span class="sxs-lookup"><span data-stu-id="d3df0-118">88</span></span>|<span data-ttu-id="d3df0-119">È stato generato lo stub MSIL.</span><span class="sxs-lookup"><span data-stu-id="d3df0-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="d3df0-120">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d3df0-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d3df0-121">Nome campo</span><span class="sxs-lookup"><span data-stu-id="d3df0-121">Field name</span></span>|<span data-ttu-id="d3df0-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d3df0-122">Data type</span></span>|<span data-ttu-id="d3df0-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3df0-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d3df0-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="d3df0-124">ModuleID</span></span>|<span data-ttu-id="d3df0-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3df0-125">win:UInt16</span></span>|<span data-ttu-id="d3df0-126">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="d3df0-126">The module identifier.</span></span>|  
|<span data-ttu-id="d3df0-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="d3df0-127">StubMethodID</span></span>|<span data-ttu-id="d3df0-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d3df0-128">win:UInt64</span></span>|<span data-ttu-id="d3df0-129">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d3df0-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="d3df0-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="d3df0-130">StubFlags</span></span>|<span data-ttu-id="d3df0-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d3df0-131">win:UInt64</span></span>|<span data-ttu-id="d3df0-132">Flag per lo stub:</span><span class="sxs-lookup"><span data-stu-id="d3df0-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="d3df0-133">0x1 - Interoperabilità inversa.</span><span class="sxs-lookup"><span data-stu-id="d3df0-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="d3df0-134">0x2 - interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="d3df0-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="d3df0-135">0x4 - stub generato da NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="d3df0-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="d3df0-136">0x8 - Delegato.</span><span class="sxs-lookup"><span data-stu-id="d3df0-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="d3df0-137">0x10-argomento della variabile.</span><span class="sxs-lookup"><span data-stu-id="d3df0-137">0x10 - Variable argument.</span></span><br /><br /> <span data-ttu-id="d3df0-138">0x20 - Computer chiamato non gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="d3df0-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="d3df0-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="d3df0-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d3df0-140">win:UInt32</span></span>|<span data-ttu-id="d3df0-141">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="d3df0-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="d3df0-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-143">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-144">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="d3df0-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="d3df0-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-146">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-147">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3df0-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="d3df0-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-149">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-150">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3df0-151">NativeMethodSignature</span></span>|<span data-ttu-id="d3df0-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-152">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-153">La firma del metodo nativo.</span><span class="sxs-lookup"><span data-stu-id="d3df0-153">The native method signature.</span></span>|  
|<span data-ttu-id="d3df0-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3df0-154">StubMethodSignature</span></span>|<span data-ttu-id="d3df0-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-155">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-156">La firma del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d3df0-156">The stub method signature.</span></span>|  
|<span data-ttu-id="d3df0-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="d3df0-157">StubMethodILCode</span></span>|<span data-ttu-id="d3df0-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-158">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-159">Il codice MSIL per il metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d3df0-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="d3df0-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d3df0-160">ClrInstanceID</span></span>|<span data-ttu-id="d3df0-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3df0-161">win:UInt16</span></span>|<span data-ttu-id="d3df0-162">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d3df0-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d3df0-163">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="d3df0-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="d3df0-164">Evento ILStubCacheHit</span><span class="sxs-lookup"><span data-stu-id="d3df0-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="d3df0-165">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="d3df0-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="d3df0-166">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="d3df0-166">Keyword for raising the event</span></span>|<span data-ttu-id="d3df0-167">Level</span><span class="sxs-lookup"><span data-stu-id="d3df0-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="d3df0-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="d3df0-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="d3df0-169">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="d3df0-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="d3df0-170">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="d3df0-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="d3df0-171">event</span><span class="sxs-lookup"><span data-stu-id="d3df0-171">Event</span></span>|<span data-ttu-id="d3df0-172">ID evento</span><span class="sxs-lookup"><span data-stu-id="d3df0-172">Event ID</span></span>|<span data-ttu-id="d3df0-173">Generato quando</span><span class="sxs-lookup"><span data-stu-id="d3df0-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="d3df0-174">89</span><span class="sxs-lookup"><span data-stu-id="d3df0-174">89</span></span>|<span data-ttu-id="d3df0-175">La cache MSIL ha avuto accesso.</span><span class="sxs-lookup"><span data-stu-id="d3df0-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="d3df0-176">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="d3df0-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="d3df0-177">Nome campo</span><span class="sxs-lookup"><span data-stu-id="d3df0-177">Field name</span></span>|<span data-ttu-id="d3df0-178">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d3df0-178">Data type</span></span>|<span data-ttu-id="d3df0-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3df0-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="d3df0-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="d3df0-180">ModuleID</span></span>|<span data-ttu-id="d3df0-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3df0-181">win:UInt16</span></span>|<span data-ttu-id="d3df0-182">L’identificatore del modulo.</span><span class="sxs-lookup"><span data-stu-id="d3df0-182">The module identifier.</span></span>|  
|<span data-ttu-id="d3df0-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="d3df0-183">StubMethodID</span></span>|<span data-ttu-id="d3df0-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="d3df0-184">win:UInt64</span></span>|<span data-ttu-id="d3df0-185">L’identificatore del metodo stub.</span><span class="sxs-lookup"><span data-stu-id="d3df0-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="d3df0-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="d3df0-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="d3df0-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="d3df0-187">win:UInt32</span></span>|<span data-ttu-id="d3df0-188">Il token per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="d3df0-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="d3df0-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-190">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-191">Lo spazio dei nomi per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="d3df0-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="d3df0-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-193">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-194">Il nome per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="d3df0-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="d3df0-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="d3df0-196">win:UnicodeString</span></span>|<span data-ttu-id="d3df0-197">La firma per il metodo di interoperabilità gestito.</span><span class="sxs-lookup"><span data-stu-id="d3df0-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="d3df0-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="d3df0-198">ClrInstanceID</span></span>|<span data-ttu-id="d3df0-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="d3df0-199">win:UInt16</span></span>|<span data-ttu-id="d3df0-200">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="d3df0-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="d3df0-201">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="d3df0-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="d3df0-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3df0-202">See also</span></span>

- [<span data-ttu-id="d3df0-203">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="d3df0-203">CLR ETW Events</span></span>](clr-etw-events.md)
