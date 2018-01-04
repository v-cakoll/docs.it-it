---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="03e45-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="03e45-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="03e45-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="03e45-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03e45-104">ID</span><span class="sxs-lookup"><span data-stu-id="03e45-104">ID</span></span>|<span data-ttu-id="03e45-105">1029</span><span class="sxs-lookup"><span data-stu-id="03e45-105">1029</span></span>|  
|<span data-ttu-id="03e45-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="03e45-106">Keywords</span></span>|<span data-ttu-id="03e45-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="03e45-107">WFRuntime</span></span>|  
|<span data-ttu-id="03e45-108">Livello</span><span class="sxs-lookup"><span data-stu-id="03e45-108">Level</span></span>|<span data-ttu-id="03e45-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="03e45-109">Verbose</span></span>|  
|<span data-ttu-id="03e45-110">Canale</span><span class="sxs-lookup"><span data-stu-id="03e45-110">Channel</span></span>|<span data-ttu-id="03e45-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="03e45-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="03e45-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03e45-112">Description</span></span>  
 <span data-ttu-id="03e45-113">Indica che un elemento FaultWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="03e45-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="03e45-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="03e45-114">Message</span></span>  
 <span data-ttu-id="03e45-115">FaultWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="03e45-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="03e45-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="03e45-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="03e45-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="03e45-117">Details</span></span>  
  
|<span data-ttu-id="03e45-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="03e45-118">Data Item Name</span></span>|<span data-ttu-id="03e45-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="03e45-119">Data Item Type</span></span>|<span data-ttu-id="03e45-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03e45-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="03e45-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="03e45-121">FaultActivity</span></span>|<span data-ttu-id="03e45-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-122">xs:string</span></span>|<span data-ttu-id="03e45-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="03e45-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="03e45-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="03e45-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="03e45-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-125">xs:string</span></span>|<span data-ttu-id="03e45-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="03e45-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="03e45-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="03e45-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="03e45-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-128">xs:string</span></span>|<span data-ttu-id="03e45-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="03e45-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="03e45-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="03e45-130">ExceptionActivity</span></span>|<span data-ttu-id="03e45-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-131">xs:string</span></span>|<span data-ttu-id="03e45-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03e45-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="03e45-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="03e45-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="03e45-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-134">xs:string</span></span>|<span data-ttu-id="03e45-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03e45-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="03e45-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="03e45-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="03e45-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-137">xs:string</span></span>|<span data-ttu-id="03e45-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03e45-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="03e45-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="03e45-139">Exception</span></span>|<span data-ttu-id="03e45-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-140">xs:string</span></span>|<span data-ttu-id="03e45-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="03e45-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="03e45-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="03e45-142">AppDomain</span></span>|<span data-ttu-id="03e45-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="03e45-143">xs:string</span></span>|<span data-ttu-id="03e45-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="03e45-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
