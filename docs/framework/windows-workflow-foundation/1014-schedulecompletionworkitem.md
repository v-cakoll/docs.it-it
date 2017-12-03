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
ms.openlocfilehash: 3d483a681cae6328dd6111b320a12b5a064d3ff5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="0eced-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="0eced-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0eced-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0eced-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0eced-104">ID</span><span class="sxs-lookup"><span data-stu-id="0eced-104">ID</span></span>|<span data-ttu-id="0eced-105">1014</span><span class="sxs-lookup"><span data-stu-id="0eced-105">1014</span></span>|  
|<span data-ttu-id="0eced-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0eced-106">Keywords</span></span>|<span data-ttu-id="0eced-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0eced-107">WFRuntime</span></span>|  
|<span data-ttu-id="0eced-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0eced-108">Level</span></span>|<span data-ttu-id="0eced-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="0eced-109">Verbose</span></span>|  
|<span data-ttu-id="0eced-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0eced-110">Channel</span></span>|<span data-ttu-id="0eced-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0eced-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0eced-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0eced-112">Description</span></span>  
 <span data-ttu-id="0eced-113">Indica che un elemento CompletionWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="0eced-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0eced-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0eced-114">Message</span></span>  
 <span data-ttu-id="0eced-115">CompletionWorkItem pianificato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0eced-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="0eced-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="0eced-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0eced-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0eced-117">Details</span></span>  
  
|<span data-ttu-id="0eced-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0eced-118">Data Item Name</span></span>|<span data-ttu-id="0eced-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0eced-119">Data Item Type</span></span>|<span data-ttu-id="0eced-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0eced-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0eced-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0eced-121">ParentActivity</span></span>|<span data-ttu-id="0eced-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-122">xs:string</span></span>|<span data-ttu-id="0eced-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0eced-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0eced-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0eced-124">ParentDisplayName</span></span>|<span data-ttu-id="0eced-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-125">xs:string</span></span>|<span data-ttu-id="0eced-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0eced-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0eced-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0eced-127">ParentInstanceId</span></span>|<span data-ttu-id="0eced-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-128">xs:string</span></span>|<span data-ttu-id="0eced-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0eced-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0eced-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="0eced-130">CompletedActivity</span></span>|<span data-ttu-id="0eced-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-131">xs:string</span></span>|<span data-ttu-id="0eced-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="0eced-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="0eced-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="0eced-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="0eced-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-134">xs:string</span></span>|<span data-ttu-id="0eced-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="0eced-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="0eced-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="0eced-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="0eced-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-137">xs:string</span></span>|<span data-ttu-id="0eced-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="0eced-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="0eced-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0eced-139">AppDomain</span></span>|<span data-ttu-id="0eced-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="0eced-140">xs:string</span></span>|<span data-ttu-id="0eced-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0eced-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
