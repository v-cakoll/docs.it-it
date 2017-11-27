---
title: Eventi ETW di sicurezza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e28eeabecfe0f1043328618f6e1be143f198a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="2c0df-102">Eventi ETW di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2c0df-102">Security ETW Events</span></span>
<span data-ttu-id="2c0df-103"><a name="top"></a> Gli eventi di sicurezza vengono generati durante la verifica del nome sicuro e la verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="2c0df-103"><a name="top"></a> Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="2c0df-104">Questa categoria include i seguenti eventi:</span><span class="sxs-lookup"><span data-stu-id="2c0df-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="2c0df-105">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="2c0df-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="2c0df-106">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="2c0df-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="2c0df-107">Eventi StrongNameVerificationStart_V1 e StrongNameVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="2c0df-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="2c0df-108">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="2c0df-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="2c0df-109">Per altre informazioni, vedere [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2c0df-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2c0df-110">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="2c0df-110">Keyword for raising the event</span></span>|<span data-ttu-id="2c0df-111">Livello</span><span class="sxs-lookup"><span data-stu-id="2c0df-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c0df-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="2c0df-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="2c0df-113">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2c0df-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c0df-114">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="2c0df-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c0df-115">Evento</span><span class="sxs-lookup"><span data-stu-id="2c0df-115">Event</span></span>|<span data-ttu-id="2c0df-116">ID evento</span><span class="sxs-lookup"><span data-stu-id="2c0df-116">Event ID</span></span>|<span data-ttu-id="2c0df-117">Generato quando</span><span class="sxs-lookup"><span data-stu-id="2c0df-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="2c0df-118">181</span><span class="sxs-lookup"><span data-stu-id="2c0df-118">181</span></span>|<span data-ttu-id="2c0df-119">Inizio della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2c0df-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="2c0df-120">182</span><span class="sxs-lookup"><span data-stu-id="2c0df-120">182</span></span>|<span data-ttu-id="2c0df-121">Fine della verifica del nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2c0df-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="2c0df-122">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2c0df-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2c0df-123">Nome campo</span><span class="sxs-lookup"><span data-stu-id="2c0df-123">Field name</span></span>|<span data-ttu-id="2c0df-124">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2c0df-124">Data type</span></span>|<span data-ttu-id="2c0df-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c0df-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c0df-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="2c0df-126">VerificationFlags</span></span>|<span data-ttu-id="2c0df-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c0df-127">win:UInt32</span></span>|<span data-ttu-id="2c0df-128">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="2c0df-128">The verification flags.</span></span>|  
|<span data-ttu-id="2c0df-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="2c0df-129">ErrorCode</span></span>|<span data-ttu-id="2c0df-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c0df-130">win:UInt32</span></span>|<span data-ttu-id="2c0df-131">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="2c0df-131">The HResult error code.</span></span>|  
|<span data-ttu-id="2c0df-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="2c0df-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="2c0df-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2c0df-133">win:UnicodeString</span></span>|<span data-ttu-id="2c0df-134">Nome completo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2c0df-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="2c0df-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c0df-135">ClrInstanceID</span></span>|<span data-ttu-id="2c0df-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c0df-136">win:UInt16</span></span>|<span data-ttu-id="2c0df-137">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2c0df-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2c0df-138">Torna all'inizio</span><span class="sxs-lookup"><span data-stu-id="2c0df-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="2c0df-139">Eventi AuthenticodeVerificationStart_V1 e AuthenticodeVerificationStop_V1</span><span class="sxs-lookup"><span data-stu-id="2c0df-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="2c0df-140">La tabella seguente illustra la parola chiave e il livello</span><span class="sxs-lookup"><span data-stu-id="2c0df-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2c0df-141">Parola chiave per la generazione dell'evento</span><span class="sxs-lookup"><span data-stu-id="2c0df-141">Keyword for raising the event</span></span>|<span data-ttu-id="2c0df-142">Livello</span><span class="sxs-lookup"><span data-stu-id="2c0df-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2c0df-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="2c0df-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="2c0df-144">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="2c0df-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="2c0df-145">La tabella seguente mostra le informazioni sull'evento.</span><span class="sxs-lookup"><span data-stu-id="2c0df-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2c0df-146">Evento</span><span class="sxs-lookup"><span data-stu-id="2c0df-146">Event</span></span>|<span data-ttu-id="2c0df-147">ID evento</span><span class="sxs-lookup"><span data-stu-id="2c0df-147">Event ID</span></span>|<span data-ttu-id="2c0df-148">Generato quando</span><span class="sxs-lookup"><span data-stu-id="2c0df-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="2c0df-149">183</span><span class="sxs-lookup"><span data-stu-id="2c0df-149">183</span></span>|<span data-ttu-id="2c0df-150">Inizio della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="2c0df-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="2c0df-151">184</span><span class="sxs-lookup"><span data-stu-id="2c0df-151">184</span></span>|<span data-ttu-id="2c0df-152">Fine della verifica Authenticode.</span><span class="sxs-lookup"><span data-stu-id="2c0df-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="2c0df-153">La tabella seguente mostra i dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2c0df-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2c0df-154">Nome campo</span><span class="sxs-lookup"><span data-stu-id="2c0df-154">Field name</span></span>|<span data-ttu-id="2c0df-155">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2c0df-155">Data type</span></span>|<span data-ttu-id="2c0df-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c0df-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2c0df-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="2c0df-157">VerificationFlags</span></span>|<span data-ttu-id="2c0df-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c0df-158">win:UInt32</span></span>|<span data-ttu-id="2c0df-159">Flag di verifica.</span><span class="sxs-lookup"><span data-stu-id="2c0df-159">The verification flags.</span></span>|  
|<span data-ttu-id="2c0df-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="2c0df-160">ErrorCode</span></span>|<span data-ttu-id="2c0df-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2c0df-161">win:UInt32</span></span>|<span data-ttu-id="2c0df-162">Codice errore HResult.</span><span class="sxs-lookup"><span data-stu-id="2c0df-162">The HResult error code.</span></span>|  
|<span data-ttu-id="2c0df-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="2c0df-163">ModulePath</span></span>|<span data-ttu-id="2c0df-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2c0df-164">win:UnicodeString</span></span>|<span data-ttu-id="2c0df-165">Percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="2c0df-165">The module path.</span></span>|  
|<span data-ttu-id="2c0df-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2c0df-166">ClrInstanceID</span></span>|<span data-ttu-id="2c0df-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2c0df-167">win:UInt16</span></span>|<span data-ttu-id="2c0df-168">ID univoco per l'istanza di CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="2c0df-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c0df-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c0df-169">See Also</span></span>  
 [<span data-ttu-id="2c0df-170">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="2c0df-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
