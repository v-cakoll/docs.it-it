---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509680"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="2a989-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="2a989-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2a989-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2a989-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a989-104">ID</span><span class="sxs-lookup"><span data-stu-id="2a989-104">ID</span></span>|<span data-ttu-id="2a989-105">1030</span><span class="sxs-lookup"><span data-stu-id="2a989-105">1030</span></span>|  
|<span data-ttu-id="2a989-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2a989-106">Keywords</span></span>|<span data-ttu-id="2a989-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a989-107">WFRuntime</span></span>|  
|<span data-ttu-id="2a989-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2a989-108">Level</span></span>|<span data-ttu-id="2a989-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="2a989-109">Verbose</span></span>|  
|<span data-ttu-id="2a989-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2a989-110">Channel</span></span>|<span data-ttu-id="2a989-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2a989-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a989-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a989-112">Description</span></span>  
 <span data-ttu-id="2a989-113">Indica che viene avviata l'esecuzione di FaultWorkItem.</span><span class="sxs-lookup"><span data-stu-id="2a989-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a989-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2a989-114">Message</span></span>  
 <span data-ttu-id="2a989-115">Avvio dell'esecuzione di FaultWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2a989-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2a989-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2a989-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a989-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2a989-117">Details</span></span>  
  
|<span data-ttu-id="2a989-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2a989-118">Data Item Name</span></span>|<span data-ttu-id="2a989-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2a989-119">Data Item Type</span></span>|<span data-ttu-id="2a989-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2a989-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a989-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="2a989-121">FaultActivity</span></span>|<span data-ttu-id="2a989-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-122">xs:string</span></span>|<span data-ttu-id="2a989-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="2a989-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="2a989-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2a989-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="2a989-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-125">xs:string</span></span>|<span data-ttu-id="2a989-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="2a989-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="2a989-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2a989-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="2a989-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-128">xs:string</span></span>|<span data-ttu-id="2a989-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="2a989-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="2a989-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="2a989-130">ExceptionActivity</span></span>|<span data-ttu-id="2a989-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-131">xs:string</span></span>|<span data-ttu-id="2a989-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a989-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2a989-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2a989-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="2a989-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-134">xs:string</span></span>|<span data-ttu-id="2a989-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a989-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2a989-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2a989-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="2a989-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-137">xs:string</span></span>|<span data-ttu-id="2a989-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a989-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2a989-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="2a989-139">Exception</span></span>|<span data-ttu-id="2a989-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-140">xs:string</span></span>|<span data-ttu-id="2a989-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2a989-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="2a989-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a989-142">AppDomain</span></span>|<span data-ttu-id="2a989-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a989-143">xs:string</span></span>|<span data-ttu-id="2a989-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2a989-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
