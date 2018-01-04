---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a80406ce56000703555f7834714222e03d2b65f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="3caae-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="3caae-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3caae-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3caae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3caae-104">ID</span><span class="sxs-lookup"><span data-stu-id="3caae-104">ID</span></span>|<span data-ttu-id="3caae-105">1014</span><span class="sxs-lookup"><span data-stu-id="3caae-105">1014</span></span>|  
|<span data-ttu-id="3caae-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3caae-106">Keywords</span></span>|<span data-ttu-id="3caae-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3caae-107">WFRuntime</span></span>|  
|<span data-ttu-id="3caae-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3caae-108">Level</span></span>|<span data-ttu-id="3caae-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="3caae-109">Verbose</span></span>|  
|<span data-ttu-id="3caae-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3caae-110">Channel</span></span>|<span data-ttu-id="3caae-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3caae-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3caae-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3caae-112">Description</span></span>  
 <span data-ttu-id="3caae-113">Indica che un elemento CompletionWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="3caae-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3caae-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3caae-114">Message</span></span>  
 <span data-ttu-id="3caae-115">CompletionWorkItem pianificato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3caae-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3caae-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="3caae-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3caae-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3caae-117">Details</span></span>  
  
|<span data-ttu-id="3caae-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3caae-118">Data Item Name</span></span>|<span data-ttu-id="3caae-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3caae-119">Data Item Type</span></span>|<span data-ttu-id="3caae-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3caae-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3caae-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="3caae-121">ParentActivity</span></span>|<span data-ttu-id="3caae-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-122">xs:string</span></span>|<span data-ttu-id="3caae-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3caae-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="3caae-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="3caae-124">ParentDisplayName</span></span>|<span data-ttu-id="3caae-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-125">xs:string</span></span>|<span data-ttu-id="3caae-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3caae-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="3caae-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="3caae-127">ParentInstanceId</span></span>|<span data-ttu-id="3caae-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-128">xs:string</span></span>|<span data-ttu-id="3caae-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3caae-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="3caae-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="3caae-130">CompletedActivity</span></span>|<span data-ttu-id="3caae-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-131">xs:string</span></span>|<span data-ttu-id="3caae-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="3caae-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="3caae-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="3caae-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="3caae-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-134">xs:string</span></span>|<span data-ttu-id="3caae-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="3caae-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="3caae-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="3caae-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="3caae-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-137">xs:string</span></span>|<span data-ttu-id="3caae-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="3caae-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="3caae-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3caae-139">AppDomain</span></span>|<span data-ttu-id="3caae-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="3caae-140">xs:string</span></span>|<span data-ttu-id="3caae-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3caae-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
