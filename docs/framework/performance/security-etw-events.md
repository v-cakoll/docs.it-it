---
title: Eventi ETW di sicurezza
description: Informazioni sugli eventi ETW di sicurezza, generati durante la verifica del nome sicuro e la verifica Authenticode in .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474215"
---
# <a name="security-etw-events"></a><span data-ttu-id="30e9f-103">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="30e9f-103">Security ETW Events</span></span>

<span data-ttu-id="30e9f-104">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="30e9f-104">Security events are raised during strong name verification and Authenticode verification.</span></span>  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a><span data-ttu-id="30e9f-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="30e9f-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="30e9f-106">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="30e9f-106">The following table shows the keyword and level.</span></span> <span data-ttu-id="30e9f-107">Per altre informazioni, vedere [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="30e9f-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="30e9f-108">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="30e9f-108">Keyword for raising the event</span></span>|<span data-ttu-id="30e9f-109">Level</span><span class="sxs-lookup"><span data-stu-id="30e9f-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30e9f-110">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="30e9f-110">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="30e9f-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="30e9f-111">Informational(4)</span></span>|  
  
 <span data-ttu-id="30e9f-112">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="30e9f-112">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30e9f-113">Evento</span><span class="sxs-lookup"><span data-stu-id="30e9f-113">Event</span></span>|<span data-ttu-id="30e9f-114">ID evento</span><span class="sxs-lookup"><span data-stu-id="30e9f-114">Event ID</span></span>|<span data-ttu-id="30e9f-115">Generato quando</span><span class="sxs-lookup"><span data-stu-id="30e9f-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="30e9f-116">181</span><span class="sxs-lookup"><span data-stu-id="30e9f-116">181</span></span>|<span data-ttu-id="30e9f-117">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="30e9f-117">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="30e9f-118">182</span><span class="sxs-lookup"><span data-stu-id="30e9f-118">182</span></span>|<span data-ttu-id="30e9f-119">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="30e9f-119">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="30e9f-120">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="30e9f-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30e9f-121">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="30e9f-121">Field name</span></span>|<span data-ttu-id="30e9f-122">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="30e9f-122">Data type</span></span>|<span data-ttu-id="30e9f-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30e9f-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30e9f-124">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="30e9f-124">VerificationFlags</span></span>|<span data-ttu-id="30e9f-125">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30e9f-125">win:UInt32</span></span>|<span data-ttu-id="30e9f-126">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="30e9f-126">The verification flags.</span></span>|  
|<span data-ttu-id="30e9f-127">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="30e9f-127">ErrorCode</span></span>|<span data-ttu-id="30e9f-128">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30e9f-128">win:UInt32</span></span>|<span data-ttu-id="30e9f-129">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="30e9f-129">The HResult error code.</span></span>|  
|<span data-ttu-id="30e9f-130">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="30e9f-130">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="30e9f-131">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="30e9f-131">win:UnicodeString</span></span>|<span data-ttu-id="30e9f-132">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="30e9f-132">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="30e9f-133">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30e9f-133">ClrInstanceID</span></span>|<span data-ttu-id="30e9f-134">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30e9f-134">win:UInt16</span></span>|<span data-ttu-id="30e9f-135">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30e9f-135">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a><span data-ttu-id="30e9f-136">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="30e9f-136">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="30e9f-137">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="30e9f-137">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="30e9f-138">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="30e9f-138">Keyword for raising the event</span></span>|<span data-ttu-id="30e9f-139">Level</span><span class="sxs-lookup"><span data-stu-id="30e9f-139">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="30e9f-140">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="30e9f-140">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="30e9f-141">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="30e9f-141">Informational(4)</span></span>|  
  
 <span data-ttu-id="30e9f-142">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="30e9f-142">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="30e9f-143">Evento</span><span class="sxs-lookup"><span data-stu-id="30e9f-143">Event</span></span>|<span data-ttu-id="30e9f-144">ID evento</span><span class="sxs-lookup"><span data-stu-id="30e9f-144">Event ID</span></span>|<span data-ttu-id="30e9f-145">Generato quando</span><span class="sxs-lookup"><span data-stu-id="30e9f-145">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="30e9f-146">183</span><span class="sxs-lookup"><span data-stu-id="30e9f-146">183</span></span>|<span data-ttu-id="30e9f-147">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="30e9f-147">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="30e9f-148">184</span><span class="sxs-lookup"><span data-stu-id="30e9f-148">184</span></span>|<span data-ttu-id="30e9f-149">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="30e9f-149">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="30e9f-150">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="30e9f-150">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="30e9f-151">Nome del campo</span><span class="sxs-lookup"><span data-stu-id="30e9f-151">Field name</span></span>|<span data-ttu-id="30e9f-152">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="30e9f-152">Data type</span></span>|<span data-ttu-id="30e9f-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30e9f-153">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="30e9f-154">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="30e9f-154">VerificationFlags</span></span>|<span data-ttu-id="30e9f-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30e9f-155">win:UInt32</span></span>|<span data-ttu-id="30e9f-156">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="30e9f-156">The verification flags.</span></span>|  
|<span data-ttu-id="30e9f-157">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="30e9f-157">ErrorCode</span></span>|<span data-ttu-id="30e9f-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="30e9f-158">win:UInt32</span></span>|<span data-ttu-id="30e9f-159">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="30e9f-159">The HResult error code.</span></span>|  
|<span data-ttu-id="30e9f-160">ModulePath</span><span class="sxs-lookup"><span data-stu-id="30e9f-160">ModulePath</span></span>|<span data-ttu-id="30e9f-161">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="30e9f-161">win:UnicodeString</span></span>|<span data-ttu-id="30e9f-162">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="30e9f-162">The module path.</span></span>|  
|<span data-ttu-id="30e9f-163">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="30e9f-163">ClrInstanceID</span></span>|<span data-ttu-id="30e9f-164">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="30e9f-164">win:UInt16</span></span>|<span data-ttu-id="30e9f-165">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="30e9f-165">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30e9f-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30e9f-166">See also</span></span>

- [<span data-ttu-id="30e9f-167">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="30e9f-167">CLR ETW Events</span></span>](clr-etw-events.md)
