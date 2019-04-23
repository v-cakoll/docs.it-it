---
title: Eventi ETW di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a19dce496423883e5fed62375c6db8ed5efdb1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134030"
---
# <a name="security-etw-events"></a><span data-ttu-id="7fe89-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7fe89-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="7fe89-103">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="7fe89-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="7fe89-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="7fe89-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="7fe89-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="7fe89-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="7fe89-106">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="7fe89-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="7fe89-107">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="7fe89-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="7fe89-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="7fe89-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="7fe89-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="7fe89-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="7fe89-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="7fe89-110">Keyword for raising the event</span></span>|<span data-ttu-id="7fe89-111">Livello</span><span class="sxs-lookup"><span data-stu-id="7fe89-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7fe89-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="7fe89-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="7fe89-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="7fe89-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="7fe89-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="7fe89-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7fe89-115">event</span><span class="sxs-lookup"><span data-stu-id="7fe89-115">Event</span></span>|<span data-ttu-id="7fe89-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="7fe89-116">Event ID</span></span>|<span data-ttu-id="7fe89-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="7fe89-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="7fe89-118">181</span><span class="sxs-lookup"><span data-stu-id="7fe89-118">181</span></span>|<span data-ttu-id="7fe89-119">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="7fe89-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="7fe89-120">182</span><span class="sxs-lookup"><span data-stu-id="7fe89-120">182</span></span>|<span data-ttu-id="7fe89-121">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="7fe89-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="7fe89-122">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7fe89-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7fe89-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="7fe89-123">Field name</span></span>|<span data-ttu-id="7fe89-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fe89-124">Data type</span></span>|<span data-ttu-id="7fe89-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fe89-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7fe89-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="7fe89-126">VerificationFlags</span></span>|<span data-ttu-id="7fe89-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7fe89-127">win:UInt32</span></span>|<span data-ttu-id="7fe89-128">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="7fe89-128">The verification flags.</span></span>|  
|<span data-ttu-id="7fe89-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="7fe89-129">ErrorCode</span></span>|<span data-ttu-id="7fe89-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7fe89-130">win:UInt32</span></span>|<span data-ttu-id="7fe89-131">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="7fe89-131">The HResult error code.</span></span>|  
|<span data-ttu-id="7fe89-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7fe89-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="7fe89-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7fe89-133">win:UnicodeString</span></span>|<span data-ttu-id="7fe89-134">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7fe89-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="7fe89-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7fe89-135">ClrInstanceID</span></span>|<span data-ttu-id="7fe89-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7fe89-136">win:UInt16</span></span>|<span data-ttu-id="7fe89-137">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7fe89-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="7fe89-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="7fe89-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="7fe89-139">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="7fe89-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="7fe89-140">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="7fe89-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="7fe89-141">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="7fe89-141">Keyword for raising the event</span></span>|<span data-ttu-id="7fe89-142">Livello</span><span class="sxs-lookup"><span data-stu-id="7fe89-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="7fe89-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="7fe89-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="7fe89-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="7fe89-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="7fe89-145">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="7fe89-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="7fe89-146">event</span><span class="sxs-lookup"><span data-stu-id="7fe89-146">Event</span></span>|<span data-ttu-id="7fe89-147">ID evento</span><span class="sxs-lookup"><span data-stu-id="7fe89-147">Event ID</span></span>|<span data-ttu-id="7fe89-148">Generato quando</span><span class="sxs-lookup"><span data-stu-id="7fe89-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="7fe89-149">183</span><span class="sxs-lookup"><span data-stu-id="7fe89-149">183</span></span>|<span data-ttu-id="7fe89-150">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="7fe89-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="7fe89-151">184</span><span class="sxs-lookup"><span data-stu-id="7fe89-151">184</span></span>|<span data-ttu-id="7fe89-152">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="7fe89-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="7fe89-153">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7fe89-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="7fe89-154">Nome campo</span><span class="sxs-lookup"><span data-stu-id="7fe89-154">Field name</span></span>|<span data-ttu-id="7fe89-155">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fe89-155">Data type</span></span>|<span data-ttu-id="7fe89-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fe89-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="7fe89-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="7fe89-157">VerificationFlags</span></span>|<span data-ttu-id="7fe89-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7fe89-158">win:UInt32</span></span>|<span data-ttu-id="7fe89-159">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="7fe89-159">The verification flags.</span></span>|  
|<span data-ttu-id="7fe89-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="7fe89-160">ErrorCode</span></span>|<span data-ttu-id="7fe89-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="7fe89-161">win:UInt32</span></span>|<span data-ttu-id="7fe89-162">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="7fe89-162">The HResult error code.</span></span>|  
|<span data-ttu-id="7fe89-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="7fe89-163">ModulePath</span></span>|<span data-ttu-id="7fe89-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="7fe89-164">win:UnicodeString</span></span>|<span data-ttu-id="7fe89-165">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="7fe89-165">The module path.</span></span>|  
|<span data-ttu-id="7fe89-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="7fe89-166">ClrInstanceID</span></span>|<span data-ttu-id="7fe89-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="7fe89-167">win:UInt16</span></span>|<span data-ttu-id="7fe89-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="7fe89-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7fe89-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fe89-169">See also</span></span>

- [<span data-ttu-id="7fe89-170">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="7fe89-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
