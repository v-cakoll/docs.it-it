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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949201"
---
# <a name="security-etw-events"></a><span data-ttu-id="fc76c-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="fc76c-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="fc76c-103">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fc76c-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="fc76c-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="fc76c-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="fc76c-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fc76c-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="fc76c-106">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fc76c-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="fc76c-107">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fc76c-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="fc76c-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="fc76c-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="fc76c-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="fc76c-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="fc76c-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="fc76c-110">Keyword for raising the event</span></span>|<span data-ttu-id="fc76c-111">Livello</span><span class="sxs-lookup"><span data-stu-id="fc76c-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="fc76c-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="fc76c-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="fc76c-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="fc76c-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="fc76c-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="fc76c-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="fc76c-115">event</span><span class="sxs-lookup"><span data-stu-id="fc76c-115">Event</span></span>|<span data-ttu-id="fc76c-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="fc76c-116">Event ID</span></span>|<span data-ttu-id="fc76c-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="fc76c-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="fc76c-118">181</span><span class="sxs-lookup"><span data-stu-id="fc76c-118">181</span></span>|<span data-ttu-id="fc76c-119">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="fc76c-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="fc76c-120">182</span><span class="sxs-lookup"><span data-stu-id="fc76c-120">182</span></span>|<span data-ttu-id="fc76c-121">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="fc76c-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="fc76c-122">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fc76c-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="fc76c-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="fc76c-123">Field name</span></span>|<span data-ttu-id="fc76c-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="fc76c-124">Data type</span></span>|<span data-ttu-id="fc76c-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc76c-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="fc76c-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="fc76c-126">VerificationFlags</span></span>|<span data-ttu-id="fc76c-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fc76c-127">win:UInt32</span></span>|<span data-ttu-id="fc76c-128">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="fc76c-128">The verification flags.</span></span>|  
|<span data-ttu-id="fc76c-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="fc76c-129">ErrorCode</span></span>|<span data-ttu-id="fc76c-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fc76c-130">win:UInt32</span></span>|<span data-ttu-id="fc76c-131">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="fc76c-131">The HResult error code.</span></span>|  
|<span data-ttu-id="fc76c-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="fc76c-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="fc76c-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fc76c-133">win:UnicodeString</span></span>|<span data-ttu-id="fc76c-134">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fc76c-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="fc76c-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fc76c-135">ClrInstanceID</span></span>|<span data-ttu-id="fc76c-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fc76c-136">win:UInt16</span></span>|<span data-ttu-id="fc76c-137">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fc76c-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="fc76c-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="fc76c-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="fc76c-139">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="fc76c-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="fc76c-140">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="fc76c-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="fc76c-141">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="fc76c-141">Keyword for raising the event</span></span>|<span data-ttu-id="fc76c-142">Livello</span><span class="sxs-lookup"><span data-stu-id="fc76c-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="fc76c-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="fc76c-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="fc76c-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="fc76c-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="fc76c-145">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="fc76c-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="fc76c-146">event</span><span class="sxs-lookup"><span data-stu-id="fc76c-146">Event</span></span>|<span data-ttu-id="fc76c-147">ID evento</span><span class="sxs-lookup"><span data-stu-id="fc76c-147">Event ID</span></span>|<span data-ttu-id="fc76c-148">Generato quando</span><span class="sxs-lookup"><span data-stu-id="fc76c-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="fc76c-149">183</span><span class="sxs-lookup"><span data-stu-id="fc76c-149">183</span></span>|<span data-ttu-id="fc76c-150">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fc76c-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="fc76c-151">184</span><span class="sxs-lookup"><span data-stu-id="fc76c-151">184</span></span>|<span data-ttu-id="fc76c-152">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="fc76c-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="fc76c-153">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fc76c-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="fc76c-154">Nome campo</span><span class="sxs-lookup"><span data-stu-id="fc76c-154">Field name</span></span>|<span data-ttu-id="fc76c-155">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="fc76c-155">Data type</span></span>|<span data-ttu-id="fc76c-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc76c-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="fc76c-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="fc76c-157">VerificationFlags</span></span>|<span data-ttu-id="fc76c-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fc76c-158">win:UInt32</span></span>|<span data-ttu-id="fc76c-159">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="fc76c-159">The verification flags.</span></span>|  
|<span data-ttu-id="fc76c-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="fc76c-160">ErrorCode</span></span>|<span data-ttu-id="fc76c-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fc76c-161">win:UInt32</span></span>|<span data-ttu-id="fc76c-162">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="fc76c-162">The HResult error code.</span></span>|  
|<span data-ttu-id="fc76c-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="fc76c-163">ModulePath</span></span>|<span data-ttu-id="fc76c-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fc76c-164">win:UnicodeString</span></span>|<span data-ttu-id="fc76c-165">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="fc76c-165">The module path.</span></span>|  
|<span data-ttu-id="fc76c-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fc76c-166">ClrInstanceID</span></span>|<span data-ttu-id="fc76c-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fc76c-167">win:UInt16</span></span>|<span data-ttu-id="fc76c-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fc76c-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc76c-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc76c-169">See also</span></span>

- [<span data-ttu-id="fc76c-170">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="fc76c-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
