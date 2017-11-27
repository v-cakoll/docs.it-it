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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b6f58cf711a91a748d3516bdd0708cc89b02c623
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="c7740-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="c7740-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="c7740-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c7740-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7740-104">ID</span><span class="sxs-lookup"><span data-stu-id="c7740-104">ID</span></span>|<span data-ttu-id="c7740-105">1014</span><span class="sxs-lookup"><span data-stu-id="c7740-105">1014</span></span>|  
|<span data-ttu-id="c7740-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c7740-106">Keywords</span></span>|<span data-ttu-id="c7740-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c7740-107">WFRuntime</span></span>|  
|<span data-ttu-id="c7740-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c7740-108">Level</span></span>|<span data-ttu-id="c7740-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="c7740-109">Verbose</span></span>|  
|<span data-ttu-id="c7740-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c7740-110">Channel</span></span>|<span data-ttu-id="c7740-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c7740-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c7740-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7740-112">Description</span></span>  
 <span data-ttu-id="c7740-113">Indica che un elemento CompletionWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="c7740-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c7740-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c7740-114">Message</span></span>  
 <span data-ttu-id="c7740-115">CompletionWorkItem pianificato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c7740-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c7740-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="c7740-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c7740-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c7740-117">Details</span></span>  
  
|<span data-ttu-id="c7740-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c7740-118">Data Item Name</span></span>|<span data-ttu-id="c7740-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c7740-119">Data Item Type</span></span>|<span data-ttu-id="c7740-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7740-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c7740-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="c7740-121">ParentActivity</span></span>|<span data-ttu-id="c7740-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-122">xs:string</span></span>|<span data-ttu-id="c7740-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c7740-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="c7740-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="c7740-124">ParentDisplayName</span></span>|<span data-ttu-id="c7740-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-125">xs:string</span></span>|<span data-ttu-id="c7740-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c7740-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="c7740-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7740-127">ParentInstanceId</span></span>|<span data-ttu-id="c7740-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-128">xs:string</span></span>|<span data-ttu-id="c7740-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="c7740-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="c7740-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="c7740-130">CompletedActivity</span></span>|<span data-ttu-id="c7740-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-131">xs:string</span></span>|<span data-ttu-id="c7740-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="c7740-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="c7740-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c7740-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="c7740-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-134">xs:string</span></span>|<span data-ttu-id="c7740-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="c7740-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="c7740-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c7740-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="c7740-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-137">xs:string</span></span>|<span data-ttu-id="c7740-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="c7740-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="c7740-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c7740-139">AppDomain</span></span>|<span data-ttu-id="c7740-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7740-140">xs:string</span></span>|<span data-ttu-id="c7740-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c7740-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
