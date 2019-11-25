---
title: Eventi ETW di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1dad042595608a805f978673858acaa5c01130f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974873"
---
# <a name="security-etw-events"></a><span data-ttu-id="05afe-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="05afe-102">Security ETW Events</span></span>

<span data-ttu-id="05afe-103">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="05afe-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="05afe-104">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="05afe-104">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="05afe-105">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="05afe-105">The following table shows the keyword and level.</span></span> <span data-ttu-id="05afe-106">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="05afe-106">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="05afe-107">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="05afe-107">Keyword for raising the event</span></span>|<span data-ttu-id="05afe-108">Level</span><span class="sxs-lookup"><span data-stu-id="05afe-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="05afe-109">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="05afe-109">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="05afe-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="05afe-110">Informational(4)</span></span>|  
  
 <span data-ttu-id="05afe-111">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="05afe-111">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="05afe-112">event</span><span class="sxs-lookup"><span data-stu-id="05afe-112">Event</span></span>|<span data-ttu-id="05afe-113">ID evento</span><span class="sxs-lookup"><span data-stu-id="05afe-113">Event ID</span></span>|<span data-ttu-id="05afe-114">Generato quando</span><span class="sxs-lookup"><span data-stu-id="05afe-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="05afe-115">181</span><span class="sxs-lookup"><span data-stu-id="05afe-115">181</span></span>|<span data-ttu-id="05afe-116">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="05afe-116">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="05afe-117">182</span><span class="sxs-lookup"><span data-stu-id="05afe-117">182</span></span>|<span data-ttu-id="05afe-118">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="05afe-118">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="05afe-119">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="05afe-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="05afe-120">Nome campo</span><span class="sxs-lookup"><span data-stu-id="05afe-120">Field name</span></span>|<span data-ttu-id="05afe-121">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="05afe-121">Data type</span></span>|<span data-ttu-id="05afe-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05afe-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="05afe-123">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="05afe-123">VerificationFlags</span></span>|<span data-ttu-id="05afe-124">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="05afe-124">win:UInt32</span></span>|<span data-ttu-id="05afe-125">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="05afe-125">The verification flags.</span></span>|  
|<span data-ttu-id="05afe-126">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="05afe-126">ErrorCode</span></span>|<span data-ttu-id="05afe-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="05afe-127">win:UInt32</span></span>|<span data-ttu-id="05afe-128">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="05afe-128">The HResult error code.</span></span>|  
|<span data-ttu-id="05afe-129">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="05afe-129">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="05afe-130">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="05afe-130">win:UnicodeString</span></span>|<span data-ttu-id="05afe-131">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="05afe-131">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="05afe-132">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="05afe-132">ClrInstanceID</span></span>|<span data-ttu-id="05afe-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="05afe-133">win:UInt16</span></span>|<span data-ttu-id="05afe-134">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="05afe-134">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="05afe-135">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="05afe-135">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="05afe-136">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="05afe-136">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="05afe-137">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="05afe-137">Keyword for raising the event</span></span>|<span data-ttu-id="05afe-138">Level</span><span class="sxs-lookup"><span data-stu-id="05afe-138">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="05afe-139">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="05afe-139">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="05afe-140">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="05afe-140">Informational(4)</span></span>|  
  
 <span data-ttu-id="05afe-141">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="05afe-141">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="05afe-142">event</span><span class="sxs-lookup"><span data-stu-id="05afe-142">Event</span></span>|<span data-ttu-id="05afe-143">ID evento</span><span class="sxs-lookup"><span data-stu-id="05afe-143">Event ID</span></span>|<span data-ttu-id="05afe-144">Generato quando</span><span class="sxs-lookup"><span data-stu-id="05afe-144">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="05afe-145">183</span><span class="sxs-lookup"><span data-stu-id="05afe-145">183</span></span>|<span data-ttu-id="05afe-146">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="05afe-146">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="05afe-147">184</span><span class="sxs-lookup"><span data-stu-id="05afe-147">184</span></span>|<span data-ttu-id="05afe-148">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="05afe-148">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="05afe-149">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="05afe-149">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="05afe-150">Nome campo</span><span class="sxs-lookup"><span data-stu-id="05afe-150">Field name</span></span>|<span data-ttu-id="05afe-151">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="05afe-151">Data type</span></span>|<span data-ttu-id="05afe-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05afe-152">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="05afe-153">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="05afe-153">VerificationFlags</span></span>|<span data-ttu-id="05afe-154">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="05afe-154">win:UInt32</span></span>|<span data-ttu-id="05afe-155">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="05afe-155">The verification flags.</span></span>|  
|<span data-ttu-id="05afe-156">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="05afe-156">ErrorCode</span></span>|<span data-ttu-id="05afe-157">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="05afe-157">win:UInt32</span></span>|<span data-ttu-id="05afe-158">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="05afe-158">The HResult error code.</span></span>|  
|<span data-ttu-id="05afe-159">ModulePath</span><span class="sxs-lookup"><span data-stu-id="05afe-159">ModulePath</span></span>|<span data-ttu-id="05afe-160">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="05afe-160">win:UnicodeString</span></span>|<span data-ttu-id="05afe-161">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="05afe-161">The module path.</span></span>|  
|<span data-ttu-id="05afe-162">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="05afe-162">ClrInstanceID</span></span>|<span data-ttu-id="05afe-163">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="05afe-163">win:UInt16</span></span>|<span data-ttu-id="05afe-164">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="05afe-164">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05afe-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05afe-165">See also</span></span>

- [<span data-ttu-id="05afe-166">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="05afe-166">CLR ETW Events</span></span>](clr-etw-events.md)
