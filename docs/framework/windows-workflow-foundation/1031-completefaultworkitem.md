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
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="1af11-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="1af11-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1af11-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1af11-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1af11-104">ID</span><span class="sxs-lookup"><span data-stu-id="1af11-104">ID</span></span>|<span data-ttu-id="1af11-105">1031</span><span class="sxs-lookup"><span data-stu-id="1af11-105">1031</span></span>|  
|<span data-ttu-id="1af11-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1af11-106">Keywords</span></span>|<span data-ttu-id="1af11-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1af11-107">WFRuntime</span></span>|  
|<span data-ttu-id="1af11-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1af11-108">Level</span></span>|<span data-ttu-id="1af11-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="1af11-109">Verbose</span></span>|  
|<span data-ttu-id="1af11-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1af11-110">Channel</span></span>|<span data-ttu-id="1af11-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1af11-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1af11-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af11-112">Description</span></span>  
 <span data-ttu-id="1af11-113">Indica che FaultWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="1af11-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1af11-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1af11-114">Message</span></span>  
 <span data-ttu-id="1af11-115">FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="1af11-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="1af11-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="1af11-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1af11-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1af11-117">Details</span></span>  
  
|<span data-ttu-id="1af11-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1af11-118">Data Item Name</span></span>|<span data-ttu-id="1af11-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1af11-119">Data Item Type</span></span>|<span data-ttu-id="1af11-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1af11-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1af11-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="1af11-121">FaultActivity</span></span>|<span data-ttu-id="1af11-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-122">xs:string</span></span>|<span data-ttu-id="1af11-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="1af11-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="1af11-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="1af11-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="1af11-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-125">xs:string</span></span>|<span data-ttu-id="1af11-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="1af11-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="1af11-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="1af11-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="1af11-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-128">xs:string</span></span>|<span data-ttu-id="1af11-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="1af11-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="1af11-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="1af11-130">ExceptionActivity</span></span>|<span data-ttu-id="1af11-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-131">xs:string</span></span>|<span data-ttu-id="1af11-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1af11-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="1af11-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="1af11-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="1af11-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-134">xs:string</span></span>|<span data-ttu-id="1af11-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1af11-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="1af11-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="1af11-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="1af11-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-137">xs:string</span></span>|<span data-ttu-id="1af11-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1af11-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="1af11-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="1af11-139">Exception</span></span>|<span data-ttu-id="1af11-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-140">xs:string</span></span>|<span data-ttu-id="1af11-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1af11-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="1af11-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1af11-142">AppDomain</span></span>|<span data-ttu-id="1af11-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="1af11-143">xs:string</span></span>|<span data-ttu-id="1af11-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1af11-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
