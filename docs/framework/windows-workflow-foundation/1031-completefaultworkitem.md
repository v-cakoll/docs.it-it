---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="febd3-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="febd3-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="febd3-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="febd3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="febd3-104">ID</span><span class="sxs-lookup"><span data-stu-id="febd3-104">ID</span></span>|<span data-ttu-id="febd3-105">1031</span><span class="sxs-lookup"><span data-stu-id="febd3-105">1031</span></span>|  
|<span data-ttu-id="febd3-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="febd3-106">Keywords</span></span>|<span data-ttu-id="febd3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="febd3-107">WFRuntime</span></span>|  
|<span data-ttu-id="febd3-108">Livello</span><span class="sxs-lookup"><span data-stu-id="febd3-108">Level</span></span>|<span data-ttu-id="febd3-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="febd3-109">Verbose</span></span>|  
|<span data-ttu-id="febd3-110">Canale</span><span class="sxs-lookup"><span data-stu-id="febd3-110">Channel</span></span>|<span data-ttu-id="febd3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="febd3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="febd3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="febd3-112">Description</span></span>  
 <span data-ttu-id="febd3-113">Indica che FaultWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="febd3-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="febd3-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="febd3-114">Message</span></span>  
 <span data-ttu-id="febd3-115">FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="febd3-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="febd3-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="febd3-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="febd3-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="febd3-117">Details</span></span>  
  
|<span data-ttu-id="febd3-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="febd3-118">Data Item Name</span></span>|<span data-ttu-id="febd3-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="febd3-119">Data Item Type</span></span>|<span data-ttu-id="febd3-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="febd3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="febd3-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="febd3-121">FaultActivity</span></span>|<span data-ttu-id="febd3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-122">xs:string</span></span>|<span data-ttu-id="febd3-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="febd3-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="febd3-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="febd3-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="febd3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-125">xs:string</span></span>|<span data-ttu-id="febd3-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="febd3-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="febd3-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="febd3-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="febd3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-128">xs:string</span></span>|<span data-ttu-id="febd3-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="febd3-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="febd3-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="febd3-130">ExceptionActivity</span></span>|<span data-ttu-id="febd3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-131">xs:string</span></span>|<span data-ttu-id="febd3-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="febd3-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="febd3-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="febd3-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="febd3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-134">xs:string</span></span>|<span data-ttu-id="febd3-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="febd3-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="febd3-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="febd3-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="febd3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-137">xs:string</span></span>|<span data-ttu-id="febd3-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="febd3-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="febd3-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="febd3-139">Exception</span></span>|<span data-ttu-id="febd3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-140">xs:string</span></span>|<span data-ttu-id="febd3-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="febd3-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="febd3-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="febd3-142">AppDomain</span></span>|<span data-ttu-id="febd3-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="febd3-143">xs:string</span></span>|<span data-ttu-id="febd3-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="febd3-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
