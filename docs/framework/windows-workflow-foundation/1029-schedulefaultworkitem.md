---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509730"
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="a0399-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="a0399-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a0399-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a0399-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0399-104">ID</span><span class="sxs-lookup"><span data-stu-id="a0399-104">ID</span></span>|<span data-ttu-id="a0399-105">1029</span><span class="sxs-lookup"><span data-stu-id="a0399-105">1029</span></span>|  
|<span data-ttu-id="a0399-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a0399-106">Keywords</span></span>|<span data-ttu-id="a0399-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a0399-107">WFRuntime</span></span>|  
|<span data-ttu-id="a0399-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a0399-108">Level</span></span>|<span data-ttu-id="a0399-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="a0399-109">Verbose</span></span>|  
|<span data-ttu-id="a0399-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a0399-110">Channel</span></span>|<span data-ttu-id="a0399-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a0399-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a0399-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0399-112">Description</span></span>  
 <span data-ttu-id="a0399-113">Indica che un elemento FaultWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="a0399-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a0399-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a0399-114">Message</span></span>  
 <span data-ttu-id="a0399-115">FaultWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a0399-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="a0399-116">Eccezione propagata dall'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="a0399-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a0399-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a0399-117">Details</span></span>  
  
|<span data-ttu-id="a0399-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a0399-118">Data Item Name</span></span>|<span data-ttu-id="a0399-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a0399-119">Data Item Type</span></span>|<span data-ttu-id="a0399-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0399-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0399-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="a0399-121">FaultActivity</span></span>|<span data-ttu-id="a0399-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-122">xs:string</span></span>|<span data-ttu-id="a0399-123">Il nome del tipo di attività fault.</span><span class="sxs-lookup"><span data-stu-id="a0399-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="a0399-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a0399-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="a0399-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-125">xs:string</span></span>|<span data-ttu-id="a0399-126">Nome visualizzato dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="a0399-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="a0399-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a0399-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="a0399-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-128">xs:string</span></span>|<span data-ttu-id="a0399-129">ID dell'istanza dell'attività fault.</span><span class="sxs-lookup"><span data-stu-id="a0399-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="a0399-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="a0399-130">ExceptionActivity</span></span>|<span data-ttu-id="a0399-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-131">xs:string</span></span>|<span data-ttu-id="a0399-132">Il nome del tipo di attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0399-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a0399-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="a0399-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="a0399-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-134">xs:string</span></span>|<span data-ttu-id="a0399-135">Il nome visualizzato dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0399-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a0399-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="a0399-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="a0399-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-137">xs:string</span></span>|<span data-ttu-id="a0399-138">ID dell'istanza dell'attività che ha generato l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0399-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="a0399-139">Eccezione</span><span class="sxs-lookup"><span data-stu-id="a0399-139">Exception</span></span>|<span data-ttu-id="a0399-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-140">xs:string</span></span>|<span data-ttu-id="a0399-141">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a0399-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="a0399-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a0399-142">AppDomain</span></span>|<span data-ttu-id="a0399-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="a0399-143">xs:string</span></span>|<span data-ttu-id="a0399-144">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a0399-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
