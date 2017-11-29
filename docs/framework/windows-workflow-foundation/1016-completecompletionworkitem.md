---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a7c6b6060e8dd3256d23db7350299d2670f6caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="37a06-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="37a06-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="37a06-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37a06-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37a06-104">ID</span><span class="sxs-lookup"><span data-stu-id="37a06-104">ID</span></span>|<span data-ttu-id="37a06-105">1016</span><span class="sxs-lookup"><span data-stu-id="37a06-105">1016</span></span>|  
|<span data-ttu-id="37a06-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="37a06-106">Keywords</span></span>|<span data-ttu-id="37a06-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="37a06-107">WFRuntime</span></span>|  
|<span data-ttu-id="37a06-108">Livello</span><span class="sxs-lookup"><span data-stu-id="37a06-108">Level</span></span>|<span data-ttu-id="37a06-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="37a06-109">Verbose</span></span>|  
|<span data-ttu-id="37a06-110">Canale</span><span class="sxs-lookup"><span data-stu-id="37a06-110">Channel</span></span>|<span data-ttu-id="37a06-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="37a06-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37a06-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37a06-112">Description</span></span>  
 <span data-ttu-id="37a06-113">Indica che CompletionWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="37a06-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37a06-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="37a06-114">Message</span></span>  
 <span data-ttu-id="37a06-115">CompletionWorkItem completato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="37a06-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="37a06-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="37a06-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37a06-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="37a06-117">Details</span></span>  
  
|<span data-ttu-id="37a06-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="37a06-118">Data Item Name</span></span>|<span data-ttu-id="37a06-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="37a06-119">Data Item Type</span></span>|<span data-ttu-id="37a06-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37a06-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37a06-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="37a06-121">ParentActivity</span></span>|<span data-ttu-id="37a06-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-122">xs:string</span></span>|<span data-ttu-id="37a06-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="37a06-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="37a06-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="37a06-124">ParentDisplayName</span></span>|<span data-ttu-id="37a06-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-125">xs:string</span></span>|<span data-ttu-id="37a06-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="37a06-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="37a06-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="37a06-127">ParentInstanceId</span></span>|<span data-ttu-id="37a06-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-128">xs:string</span></span>|<span data-ttu-id="37a06-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="37a06-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="37a06-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="37a06-130">CompletedActivity</span></span>|<span data-ttu-id="37a06-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-131">xs:string</span></span>|<span data-ttu-id="37a06-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="37a06-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="37a06-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="37a06-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="37a06-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-134">xs:string</span></span>|<span data-ttu-id="37a06-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="37a06-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="37a06-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="37a06-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="37a06-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-137">xs:string</span></span>|<span data-ttu-id="37a06-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="37a06-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="37a06-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37a06-139">AppDomain</span></span>|<span data-ttu-id="37a06-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="37a06-140">xs:string</span></span>|<span data-ttu-id="37a06-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="37a06-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
