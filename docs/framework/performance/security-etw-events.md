---
title: Eventi ETW di sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2ea19c88ff8b854b09ed372b35bf8c45d994585
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583659"
---
# <a name="security-etw-events"></a><span data-ttu-id="b641f-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b641f-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="b641f-103">Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b641f-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="b641f-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="b641f-104">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="b641f-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b641f-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
- [<span data-ttu-id="b641f-106">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b641f-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="b641f-107">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b641f-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="b641f-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="b641f-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="b641f-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b641f-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b641f-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="b641f-110">Keyword for raising the event</span></span>|<span data-ttu-id="b641f-111">Livello</span><span class="sxs-lookup"><span data-stu-id="b641f-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b641f-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="b641f-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="b641f-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b641f-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="b641f-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="b641f-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b641f-115">event</span><span class="sxs-lookup"><span data-stu-id="b641f-115">Event</span></span>|<span data-ttu-id="b641f-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="b641f-116">Event ID</span></span>|<span data-ttu-id="b641f-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="b641f-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="b641f-118">181</span><span class="sxs-lookup"><span data-stu-id="b641f-118">181</span></span>|<span data-ttu-id="b641f-119">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b641f-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="b641f-120">182</span><span class="sxs-lookup"><span data-stu-id="b641f-120">182</span></span>|<span data-ttu-id="b641f-121">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="b641f-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="b641f-122">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b641f-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b641f-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="b641f-123">Field name</span></span>|<span data-ttu-id="b641f-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b641f-124">Data type</span></span>|<span data-ttu-id="b641f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b641f-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b641f-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="b641f-126">VerificationFlags</span></span>|<span data-ttu-id="b641f-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b641f-127">win:UInt32</span></span>|<span data-ttu-id="b641f-128">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="b641f-128">The verification flags.</span></span>|  
|<span data-ttu-id="b641f-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="b641f-129">ErrorCode</span></span>|<span data-ttu-id="b641f-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b641f-130">win:UInt32</span></span>|<span data-ttu-id="b641f-131">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="b641f-131">The HResult error code.</span></span>|  
|<span data-ttu-id="b641f-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="b641f-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="b641f-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b641f-133">win:UnicodeString</span></span>|<span data-ttu-id="b641f-134">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="b641f-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="b641f-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b641f-135">ClrInstanceID</span></span>|<span data-ttu-id="b641f-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b641f-136">win:UInt16</span></span>|<span data-ttu-id="b641f-137">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b641f-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b641f-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="b641f-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="b641f-139">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="b641f-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="b641f-140">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="b641f-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b641f-141">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="b641f-141">Keyword for raising the event</span></span>|<span data-ttu-id="b641f-142">Livello</span><span class="sxs-lookup"><span data-stu-id="b641f-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b641f-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="b641f-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="b641f-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="b641f-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="b641f-145">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="b641f-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b641f-146">event</span><span class="sxs-lookup"><span data-stu-id="b641f-146">Event</span></span>|<span data-ttu-id="b641f-147">ID evento</span><span class="sxs-lookup"><span data-stu-id="b641f-147">Event ID</span></span>|<span data-ttu-id="b641f-148">Generato quando</span><span class="sxs-lookup"><span data-stu-id="b641f-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="b641f-149">183</span><span class="sxs-lookup"><span data-stu-id="b641f-149">183</span></span>|<span data-ttu-id="b641f-150">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b641f-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="b641f-151">184</span><span class="sxs-lookup"><span data-stu-id="b641f-151">184</span></span>|<span data-ttu-id="b641f-152">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="b641f-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="b641f-153">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b641f-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b641f-154">Nome campo</span><span class="sxs-lookup"><span data-stu-id="b641f-154">Field name</span></span>|<span data-ttu-id="b641f-155">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b641f-155">Data type</span></span>|<span data-ttu-id="b641f-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b641f-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b641f-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="b641f-157">VerificationFlags</span></span>|<span data-ttu-id="b641f-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b641f-158">win:UInt32</span></span>|<span data-ttu-id="b641f-159">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="b641f-159">The verification flags.</span></span>|  
|<span data-ttu-id="b641f-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="b641f-160">ErrorCode</span></span>|<span data-ttu-id="b641f-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b641f-161">win:UInt32</span></span>|<span data-ttu-id="b641f-162">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="b641f-162">The HResult error code.</span></span>|  
|<span data-ttu-id="b641f-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="b641f-163">ModulePath</span></span>|<span data-ttu-id="b641f-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b641f-164">win:UnicodeString</span></span>|<span data-ttu-id="b641f-165">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="b641f-165">The module path.</span></span>|  
|<span data-ttu-id="b641f-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b641f-166">ClrInstanceID</span></span>|<span data-ttu-id="b641f-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b641f-167">win:UInt16</span></span>|<span data-ttu-id="b641f-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="b641f-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b641f-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b641f-169">See also</span></span>

- [<span data-ttu-id="b641f-170">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="b641f-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
