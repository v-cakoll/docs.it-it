---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509743"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="a5c5f-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="a5c5f-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a5c5f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a5c5f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5c5f-104">ID</span><span class="sxs-lookup"><span data-stu-id="a5c5f-104">ID</span></span>|<span data-ttu-id="a5c5f-105">1031</span><span class="sxs-lookup"><span data-stu-id="a5c5f-105">1031</span></span>|  
|<span data-ttu-id="a5c5f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a5c5f-106">Keywords</span></span>|<span data-ttu-id="a5c5f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a5c5f-107">WFRuntime</span></span>|  
|<span data-ttu-id="a5c5f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a5c5f-108">Level</span></span>|<span data-ttu-id="a5c5f-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="a5c5f-109">Verbose</span></span>|  
|<span data-ttu-id="a5c5f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a5c5f-110">Channel</span></span>|<span data-ttu-id="a5c5f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a5c5f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a5c5f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5c5f-112">Description</span></span>  
 <span data-ttu-id="a5c5f-113">Indica che FaultWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a5c5f-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a5c5f-114">Message</span></span>  
 <span data-ttu-id="a5c5f-115">FaultWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="a5c5f-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a5c5f-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a5c5f-117">Details</span></span>  
  
|<span data-ttu-id="a5c5f-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a5c5f-118">Data Item Name</span></span>|<span data-ttu-id="a5c5f-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a5c5f-119">Data Item Type</span></span>|<span data-ttu-id="a5c5f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5c5f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a5c5f-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="a5c5f-121">FaultActivity</span></span>|<span data-ttu-id="a5c5f-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-122">xs:string</span></span>|<span data-ttu-id="a5c5f-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="a5c5f-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a5c5f-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="a5c5f-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-125">xs:string</span></span>|<span data-ttu-id="a5c5f-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="a5c5f-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a5c5f-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="a5c5f-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-128">xs:string</span></span>|<span data-ttu-id="a5c5f-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="a5c5f-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="a5c5f-130">ExceptionActivity</span></span>|<span data-ttu-id="a5c5f-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-131">xs:string</span></span>|<span data-ttu-id="a5c5f-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a5c5f-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a5c5f-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="a5c5f-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-134">xs:string</span></span>|<span data-ttu-id="a5c5f-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a5c5f-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a5c5f-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="a5c5f-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-137">xs:string</span></span>|<span data-ttu-id="a5c5f-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a5c5f-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="a5c5f-139">Exception</span></span>|<span data-ttu-id="a5c5f-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-140">xs:string</span></span>|<span data-ttu-id="a5c5f-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="a5c5f-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a5c5f-142">AppDomain</span></span>|<span data-ttu-id="a5c5f-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="a5c5f-143">xs:string</span></span>|<span data-ttu-id="a5c5f-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a5c5f-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
