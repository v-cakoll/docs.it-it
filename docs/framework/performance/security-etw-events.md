---
title: Eventi ETW di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e02274b63ddf7df42d26621791de0286df9655b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395512"
---
# <a name="security-etw-events"></a><span data-ttu-id="dd71d-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="dd71d-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="dd71d-103">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dd71d-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="dd71d-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="dd71d-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="dd71d-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dd71d-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="dd71d-106">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dd71d-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="dd71d-107">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dd71d-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="dd71d-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="dd71d-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="dd71d-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="dd71d-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="dd71d-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="dd71d-110">Keyword for raising the event</span></span>|<span data-ttu-id="dd71d-111">Livello</span><span class="sxs-lookup"><span data-stu-id="dd71d-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="dd71d-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="dd71d-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="dd71d-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="dd71d-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="dd71d-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="dd71d-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="dd71d-115">Evento</span><span class="sxs-lookup"><span data-stu-id="dd71d-115">Event</span></span>|<span data-ttu-id="dd71d-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="dd71d-116">Event ID</span></span>|<span data-ttu-id="dd71d-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="dd71d-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="dd71d-118">181</span><span class="sxs-lookup"><span data-stu-id="dd71d-118">181</span></span>|<span data-ttu-id="dd71d-119">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="dd71d-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="dd71d-120">182</span><span class="sxs-lookup"><span data-stu-id="dd71d-120">182</span></span>|<span data-ttu-id="dd71d-121">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="dd71d-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="dd71d-122">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="dd71d-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="dd71d-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="dd71d-123">Field name</span></span>|<span data-ttu-id="dd71d-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="dd71d-124">Data type</span></span>|<span data-ttu-id="dd71d-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd71d-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="dd71d-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="dd71d-126">VerificationFlags</span></span>|<span data-ttu-id="dd71d-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dd71d-127">win:UInt32</span></span>|<span data-ttu-id="dd71d-128">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="dd71d-128">The verification flags.</span></span>|  
|<span data-ttu-id="dd71d-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="dd71d-129">ErrorCode</span></span>|<span data-ttu-id="dd71d-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dd71d-130">win:UInt32</span></span>|<span data-ttu-id="dd71d-131">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="dd71d-131">The HResult error code.</span></span>|  
|<span data-ttu-id="dd71d-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="dd71d-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="dd71d-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="dd71d-133">win:UnicodeString</span></span>|<span data-ttu-id="dd71d-134">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="dd71d-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="dd71d-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="dd71d-135">ClrInstanceID</span></span>|<span data-ttu-id="dd71d-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="dd71d-136">win:UInt16</span></span>|<span data-ttu-id="dd71d-137">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="dd71d-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="dd71d-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="dd71d-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="dd71d-139">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="dd71d-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="dd71d-140">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="dd71d-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="dd71d-141">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="dd71d-141">Keyword for raising the event</span></span>|<span data-ttu-id="dd71d-142">Livello</span><span class="sxs-lookup"><span data-stu-id="dd71d-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="dd71d-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="dd71d-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="dd71d-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="dd71d-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="dd71d-145">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="dd71d-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="dd71d-146">Evento</span><span class="sxs-lookup"><span data-stu-id="dd71d-146">Event</span></span>|<span data-ttu-id="dd71d-147">ID evento</span><span class="sxs-lookup"><span data-stu-id="dd71d-147">Event ID</span></span>|<span data-ttu-id="dd71d-148">Generato quando</span><span class="sxs-lookup"><span data-stu-id="dd71d-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="dd71d-149">183</span><span class="sxs-lookup"><span data-stu-id="dd71d-149">183</span></span>|<span data-ttu-id="dd71d-150">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dd71d-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="dd71d-151">184</span><span class="sxs-lookup"><span data-stu-id="dd71d-151">184</span></span>|<span data-ttu-id="dd71d-152">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dd71d-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="dd71d-153">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="dd71d-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="dd71d-154">Nome campo</span><span class="sxs-lookup"><span data-stu-id="dd71d-154">Field name</span></span>|<span data-ttu-id="dd71d-155">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="dd71d-155">Data type</span></span>|<span data-ttu-id="dd71d-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd71d-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="dd71d-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="dd71d-157">VerificationFlags</span></span>|<span data-ttu-id="dd71d-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dd71d-158">win:UInt32</span></span>|<span data-ttu-id="dd71d-159">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="dd71d-159">The verification flags.</span></span>|  
|<span data-ttu-id="dd71d-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="dd71d-160">ErrorCode</span></span>|<span data-ttu-id="dd71d-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="dd71d-161">win:UInt32</span></span>|<span data-ttu-id="dd71d-162">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="dd71d-162">The HResult error code.</span></span>|  
|<span data-ttu-id="dd71d-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="dd71d-163">ModulePath</span></span>|<span data-ttu-id="dd71d-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="dd71d-164">win:UnicodeString</span></span>|<span data-ttu-id="dd71d-165">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="dd71d-165">The module path.</span></span>|  
|<span data-ttu-id="dd71d-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="dd71d-166">ClrInstanceID</span></span>|<span data-ttu-id="dd71d-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="dd71d-167">win:UInt16</span></span>|<span data-ttu-id="dd71d-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="dd71d-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd71d-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd71d-169">See Also</span></span>  
 [<span data-ttu-id="dd71d-170">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="dd71d-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
