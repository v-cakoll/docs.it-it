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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="14ec0-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="14ec0-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="14ec0-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="14ec0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14ec0-104">ID</span><span class="sxs-lookup"><span data-stu-id="14ec0-104">ID</span></span>|<span data-ttu-id="14ec0-105">1031</span><span class="sxs-lookup"><span data-stu-id="14ec0-105">1031</span></span>|  
|<span data-ttu-id="14ec0-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="14ec0-106">Keywords</span></span>|<span data-ttu-id="14ec0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="14ec0-107">WFRuntime</span></span>|  
|<span data-ttu-id="14ec0-108">Livello</span><span class="sxs-lookup"><span data-stu-id="14ec0-108">Level</span></span>|<span data-ttu-id="14ec0-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="14ec0-109">Verbose</span></span>|  
|<span data-ttu-id="14ec0-110">Canale</span><span class="sxs-lookup"><span data-stu-id="14ec0-110">Channel</span></span>|<span data-ttu-id="14ec0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="14ec0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="14ec0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14ec0-112">Description</span></span>  
 <span data-ttu-id="14ec0-113">Indica che FaultWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="14ec0-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="14ec0-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="14ec0-114">Message</span></span>  
 <span data-ttu-id="14ec0-115">FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="14ec0-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="14ec0-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="14ec0-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="14ec0-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="14ec0-117">Details</span></span>  
  
|<span data-ttu-id="14ec0-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="14ec0-118">Data Item Name</span></span>|<span data-ttu-id="14ec0-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="14ec0-119">Data Item Type</span></span>|<span data-ttu-id="14ec0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14ec0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="14ec0-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="14ec0-121">FaultActivity</span></span>|<span data-ttu-id="14ec0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-122">xs:string</span></span>|<span data-ttu-id="14ec0-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="14ec0-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="14ec0-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="14ec0-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="14ec0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-125">xs:string</span></span>|<span data-ttu-id="14ec0-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="14ec0-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="14ec0-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="14ec0-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="14ec0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-128">xs:string</span></span>|<span data-ttu-id="14ec0-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="14ec0-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="14ec0-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="14ec0-130">ExceptionActivity</span></span>|<span data-ttu-id="14ec0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-131">xs:string</span></span>|<span data-ttu-id="14ec0-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="14ec0-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="14ec0-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="14ec0-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="14ec0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-134">xs:string</span></span>|<span data-ttu-id="14ec0-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="14ec0-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="14ec0-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="14ec0-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="14ec0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-137">xs:string</span></span>|<span data-ttu-id="14ec0-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="14ec0-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="14ec0-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="14ec0-139">Exception</span></span>|<span data-ttu-id="14ec0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-140">xs:string</span></span>|<span data-ttu-id="14ec0-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="14ec0-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="14ec0-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="14ec0-142">AppDomain</span></span>|<span data-ttu-id="14ec0-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="14ec0-143">xs:string</span></span>|<span data-ttu-id="14ec0-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="14ec0-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
