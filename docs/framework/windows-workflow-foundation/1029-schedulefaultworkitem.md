---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924358"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="2e9d0-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="2e9d0-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2e9d0-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2e9d0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e9d0-104">Id</span><span class="sxs-lookup"><span data-stu-id="2e9d0-104">ID</span></span>|<span data-ttu-id="2e9d0-105">1029</span><span class="sxs-lookup"><span data-stu-id="2e9d0-105">1029</span></span>|  
|<span data-ttu-id="2e9d0-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2e9d0-106">Keywords</span></span>|<span data-ttu-id="2e9d0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2e9d0-107">WFRuntime</span></span>|  
|<span data-ttu-id="2e9d0-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2e9d0-108">Level</span></span>|<span data-ttu-id="2e9d0-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="2e9d0-109">Verbose</span></span>|  
|<span data-ttu-id="2e9d0-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2e9d0-110">Channel</span></span>|<span data-ttu-id="2e9d0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2e9d0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2e9d0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e9d0-112">Description</span></span>  
 <span data-ttu-id="2e9d0-113">Indica che un elemento FaultWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2e9d0-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2e9d0-114">Message</span></span>  
 <span data-ttu-id="2e9d0-115">FaultWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2e9d0-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2e9d0-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2e9d0-117">Details</span></span>  
  
|<span data-ttu-id="2e9d0-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2e9d0-118">Data Item Name</span></span>|<span data-ttu-id="2e9d0-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2e9d0-119">Data Item Type</span></span>|<span data-ttu-id="2e9d0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e9d0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2e9d0-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="2e9d0-121">FaultActivity</span></span>|<span data-ttu-id="2e9d0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-122">xs:string</span></span>|<span data-ttu-id="2e9d0-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="2e9d0-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2e9d0-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="2e9d0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-125">xs:string</span></span>|<span data-ttu-id="2e9d0-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="2e9d0-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2e9d0-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="2e9d0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-128">xs:string</span></span>|<span data-ttu-id="2e9d0-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="2e9d0-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="2e9d0-130">ExceptionActivity</span></span>|<span data-ttu-id="2e9d0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-131">xs:string</span></span>|<span data-ttu-id="2e9d0-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2e9d0-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2e9d0-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="2e9d0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-134">xs:string</span></span>|<span data-ttu-id="2e9d0-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2e9d0-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2e9d0-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="2e9d0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-137">xs:string</span></span>|<span data-ttu-id="2e9d0-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="2e9d0-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="2e9d0-139">Exception</span></span>|<span data-ttu-id="2e9d0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-140">xs:string</span></span>|<span data-ttu-id="2e9d0-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="2e9d0-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2e9d0-142">AppDomain</span></span>|<span data-ttu-id="2e9d0-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="2e9d0-143">xs:string</span></span>|<span data-ttu-id="2e9d0-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2e9d0-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
