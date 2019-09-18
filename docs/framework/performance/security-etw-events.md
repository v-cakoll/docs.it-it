---
title: Eventi ETW di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d09b5b76c39f33848d44beb43d9b09c5e6ed13b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046168"
---
# <a name="security-etw-events"></a><span data-ttu-id="b3dfc-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b3dfc-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="b3dfc-103">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="b3dfc-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="b3dfc-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="b3dfc-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b3dfc-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="b3dfc-106">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b3dfc-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="b3dfc-107">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b3dfc-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="b3dfc-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="b3dfc-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="b3dfc-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b3dfc-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b3dfc-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="b3dfc-110">Keyword for raising the event</span></span>|<span data-ttu-id="b3dfc-111">Level</span><span class="sxs-lookup"><span data-stu-id="b3dfc-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b3dfc-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="b3dfc-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="b3dfc-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b3dfc-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="b3dfc-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b3dfc-115">event</span><span class="sxs-lookup"><span data-stu-id="b3dfc-115">Event</span></span>|<span data-ttu-id="b3dfc-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="b3dfc-116">Event ID</span></span>|<span data-ttu-id="b3dfc-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="b3dfc-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="b3dfc-118">181</span><span class="sxs-lookup"><span data-stu-id="b3dfc-118">181</span></span>|<span data-ttu-id="b3dfc-119">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="b3dfc-120">182</span><span class="sxs-lookup"><span data-stu-id="b3dfc-120">182</span></span>|<span data-ttu-id="b3dfc-121">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="b3dfc-122">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b3dfc-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="b3dfc-123">Field name</span></span>|<span data-ttu-id="b3dfc-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b3dfc-124">Data type</span></span>|<span data-ttu-id="b3dfc-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b3dfc-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b3dfc-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="b3dfc-126">VerificationFlags</span></span>|<span data-ttu-id="b3dfc-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b3dfc-127">win:UInt32</span></span>|<span data-ttu-id="b3dfc-128">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-128">The verification flags.</span></span>|  
|<span data-ttu-id="b3dfc-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="b3dfc-129">ErrorCode</span></span>|<span data-ttu-id="b3dfc-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b3dfc-130">win:UInt32</span></span>|<span data-ttu-id="b3dfc-131">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-131">The HResult error code.</span></span>|  
|<span data-ttu-id="b3dfc-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="b3dfc-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="b3dfc-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b3dfc-133">win:UnicodeString</span></span>|<span data-ttu-id="b3dfc-134">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="b3dfc-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b3dfc-135">ClrInstanceID</span></span>|<span data-ttu-id="b3dfc-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b3dfc-136">win:UInt16</span></span>|<span data-ttu-id="b3dfc-137">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b3dfc-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b3dfc-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="b3dfc-139">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b3dfc-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="b3dfc-140">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="b3dfc-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b3dfc-141">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="b3dfc-141">Keyword for raising the event</span></span>|<span data-ttu-id="b3dfc-142">Level</span><span class="sxs-lookup"><span data-stu-id="b3dfc-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b3dfc-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="b3dfc-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="b3dfc-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b3dfc-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="b3dfc-145">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b3dfc-146">event</span><span class="sxs-lookup"><span data-stu-id="b3dfc-146">Event</span></span>|<span data-ttu-id="b3dfc-147">ID evento</span><span class="sxs-lookup"><span data-stu-id="b3dfc-147">Event ID</span></span>|<span data-ttu-id="b3dfc-148">Generato quando</span><span class="sxs-lookup"><span data-stu-id="b3dfc-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="b3dfc-149">183</span><span class="sxs-lookup"><span data-stu-id="b3dfc-149">183</span></span>|<span data-ttu-id="b3dfc-150">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="b3dfc-151">184</span><span class="sxs-lookup"><span data-stu-id="b3dfc-151">184</span></span>|<span data-ttu-id="b3dfc-152">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="b3dfc-153">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b3dfc-154">Nome campo</span><span class="sxs-lookup"><span data-stu-id="b3dfc-154">Field name</span></span>|<span data-ttu-id="b3dfc-155">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b3dfc-155">Data type</span></span>|<span data-ttu-id="b3dfc-156">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="b3dfc-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b3dfc-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="b3dfc-157">VerificationFlags</span></span>|<span data-ttu-id="b3dfc-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b3dfc-158">win:UInt32</span></span>|<span data-ttu-id="b3dfc-159">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-159">The verification flags.</span></span>|  
|<span data-ttu-id="b3dfc-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="b3dfc-160">ErrorCode</span></span>|<span data-ttu-id="b3dfc-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b3dfc-161">win:UInt32</span></span>|<span data-ttu-id="b3dfc-162">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-162">The HResult error code.</span></span>|  
|<span data-ttu-id="b3dfc-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="b3dfc-163">ModulePath</span></span>|<span data-ttu-id="b3dfc-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b3dfc-164">win:UnicodeString</span></span>|<span data-ttu-id="b3dfc-165">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-165">The module path.</span></span>|  
|<span data-ttu-id="b3dfc-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b3dfc-166">ClrInstanceID</span></span>|<span data-ttu-id="b3dfc-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b3dfc-167">win:UInt16</span></span>|<span data-ttu-id="b3dfc-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b3dfc-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3dfc-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3dfc-169">See also</span></span>

- [<span data-ttu-id="b3dfc-170">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="b3dfc-170">CLR ETW Events</span></span>](clr-etw-events.md)
