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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="e8b94-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="e8b94-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e8b94-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e8b94-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8b94-104">ID</span><span class="sxs-lookup"><span data-stu-id="e8b94-104">ID</span></span>|<span data-ttu-id="e8b94-105">1029</span><span class="sxs-lookup"><span data-stu-id="e8b94-105">1029</span></span>|  
|<span data-ttu-id="e8b94-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e8b94-106">Keywords</span></span>|<span data-ttu-id="e8b94-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e8b94-107">WFRuntime</span></span>|  
|<span data-ttu-id="e8b94-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e8b94-108">Level</span></span>|<span data-ttu-id="e8b94-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="e8b94-109">Verbose</span></span>|  
|<span data-ttu-id="e8b94-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e8b94-110">Channel</span></span>|<span data-ttu-id="e8b94-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e8b94-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e8b94-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8b94-112">Description</span></span>  
 <span data-ttu-id="e8b94-113">Indica che un elemento FaultWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="e8b94-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e8b94-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e8b94-114">Message</span></span>  
 <span data-ttu-id="e8b94-115">FaultWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="e8b94-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="e8b94-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="e8b94-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e8b94-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e8b94-117">Details</span></span>  
  
|<span data-ttu-id="e8b94-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e8b94-118">Data Item Name</span></span>|<span data-ttu-id="e8b94-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e8b94-119">Data Item Type</span></span>|<span data-ttu-id="e8b94-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8b94-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e8b94-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="e8b94-121">FaultActivity</span></span>|<span data-ttu-id="e8b94-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-122">xs:string</span></span>|<span data-ttu-id="e8b94-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="e8b94-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="e8b94-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e8b94-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="e8b94-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-125">xs:string</span></span>|<span data-ttu-id="e8b94-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="e8b94-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="e8b94-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e8b94-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="e8b94-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-128">xs:string</span></span>|<span data-ttu-id="e8b94-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="e8b94-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="e8b94-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="e8b94-130">ExceptionActivity</span></span>|<span data-ttu-id="e8b94-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-131">xs:string</span></span>|<span data-ttu-id="e8b94-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e8b94-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e8b94-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e8b94-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="e8b94-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-134">xs:string</span></span>|<span data-ttu-id="e8b94-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e8b94-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e8b94-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e8b94-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="e8b94-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-137">xs:string</span></span>|<span data-ttu-id="e8b94-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e8b94-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="e8b94-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="e8b94-139">Exception</span></span>|<span data-ttu-id="e8b94-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-140">xs:string</span></span>|<span data-ttu-id="e8b94-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="e8b94-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="e8b94-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e8b94-142">AppDomain</span></span>|<span data-ttu-id="e8b94-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="e8b94-143">xs:string</span></span>|<span data-ttu-id="e8b94-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e8b94-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
