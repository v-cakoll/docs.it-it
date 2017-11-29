---
title: 1030 - StartFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b25dbd5ced96b8e9ca3ef51e4de841a6238d2cbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="223fc-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="223fc-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="223fc-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="223fc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="223fc-104">ID</span><span class="sxs-lookup"><span data-stu-id="223fc-104">ID</span></span>|<span data-ttu-id="223fc-105">1030</span><span class="sxs-lookup"><span data-stu-id="223fc-105">1030</span></span>|  
|<span data-ttu-id="223fc-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="223fc-106">Keywords</span></span>|<span data-ttu-id="223fc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="223fc-107">WFRuntime</span></span>|  
|<span data-ttu-id="223fc-108">Livello</span><span class="sxs-lookup"><span data-stu-id="223fc-108">Level</span></span>|<span data-ttu-id="223fc-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="223fc-109">Verbose</span></span>|  
|<span data-ttu-id="223fc-110">Canale</span><span class="sxs-lookup"><span data-stu-id="223fc-110">Channel</span></span>|<span data-ttu-id="223fc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="223fc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="223fc-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="223fc-112">Description</span></span>  
 <span data-ttu-id="223fc-113">Indica che viene avviata l'esecuzione di FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="223fc-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="223fc-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="223fc-114">Message</span></span>  
 <span data-ttu-id="223fc-115">Avvio dell'esecuzione di FaultWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="223fc-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="223fc-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="223fc-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="223fc-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="223fc-117">Details</span></span>  
  
|<span data-ttu-id="223fc-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="223fc-118">Data Item Name</span></span>|<span data-ttu-id="223fc-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="223fc-119">Data Item Type</span></span>|<span data-ttu-id="223fc-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="223fc-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="223fc-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="223fc-121">FaultActivity</span></span>|<span data-ttu-id="223fc-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-122">xs:string</span></span>|<span data-ttu-id="223fc-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="223fc-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="223fc-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="223fc-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="223fc-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-125">xs:string</span></span>|<span data-ttu-id="223fc-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="223fc-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="223fc-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="223fc-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="223fc-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-128">xs:string</span></span>|<span data-ttu-id="223fc-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="223fc-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="223fc-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="223fc-130">ExceptionActivity</span></span>|<span data-ttu-id="223fc-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-131">xs:string</span></span>|<span data-ttu-id="223fc-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="223fc-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="223fc-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="223fc-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="223fc-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-134">xs:string</span></span>|<span data-ttu-id="223fc-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="223fc-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="223fc-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="223fc-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="223fc-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-137">xs:string</span></span>|<span data-ttu-id="223fc-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="223fc-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="223fc-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="223fc-139">Exception</span></span>|<span data-ttu-id="223fc-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-140">xs:string</span></span>|<span data-ttu-id="223fc-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="223fc-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="223fc-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="223fc-142">AppDomain</span></span>|<span data-ttu-id="223fc-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="223fc-143">xs:string</span></span>|<span data-ttu-id="223fc-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="223fc-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
