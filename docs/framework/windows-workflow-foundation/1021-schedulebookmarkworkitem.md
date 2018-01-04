---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61c67792f807907f58480f3bfa3d192b811766b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="4be0c-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="4be0c-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4be0c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4be0c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4be0c-104">ID</span><span class="sxs-lookup"><span data-stu-id="4be0c-104">ID</span></span>|<span data-ttu-id="4be0c-105">1021</span><span class="sxs-lookup"><span data-stu-id="4be0c-105">1021</span></span>|  
|<span data-ttu-id="4be0c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="4be0c-106">Keywords</span></span>|<span data-ttu-id="4be0c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4be0c-107">WFRuntime</span></span>|  
|<span data-ttu-id="4be0c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="4be0c-108">Level</span></span>|<span data-ttu-id="4be0c-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="4be0c-109">Verbose</span></span>|  
|<span data-ttu-id="4be0c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="4be0c-110">Channel</span></span>|<span data-ttu-id="4be0c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4be0c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4be0c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4be0c-112">Description</span></span>  
 <span data-ttu-id="4be0c-113">Indica che un elemento BookmarkWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="4be0c-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4be0c-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="4be0c-114">Message</span></span>  
 <span data-ttu-id="4be0c-115">BookmarkWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4be0c-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="4be0c-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="4be0c-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4be0c-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4be0c-117">Details</span></span>  
  
|<span data-ttu-id="4be0c-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="4be0c-118">Data Item Name</span></span>|<span data-ttu-id="4be0c-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="4be0c-119">Data Item Type</span></span>|<span data-ttu-id="4be0c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4be0c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4be0c-121">Attività</span><span class="sxs-lookup"><span data-stu-id="4be0c-121">Activity</span></span>|<span data-ttu-id="4be0c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4be0c-122">xs:string</span></span>|<span data-ttu-id="4be0c-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="4be0c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="4be0c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4be0c-124">DisplayName</span></span>|<span data-ttu-id="4be0c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4be0c-125">xs:string</span></span>|<span data-ttu-id="4be0c-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="4be0c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="4be0c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4be0c-127">InstanceId</span></span>|<span data-ttu-id="4be0c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="4be0c-128">xs:string</span></span>|<span data-ttu-id="4be0c-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="4be0c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4be0c-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="4be0c-130">BookmarkName</span></span>|<span data-ttu-id="4be0c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="4be0c-131">xs:string</span></span>|<span data-ttu-id="4be0c-132">Nome del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="4be0c-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="4be0c-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="4be0c-133">BookmarkScope</span></span>|<span data-ttu-id="4be0c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="4be0c-134">xs:string</span></span>|<span data-ttu-id="4be0c-135">Ambito del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="4be0c-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="4be0c-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4be0c-136">AppDomain</span></span>|<span data-ttu-id="4be0c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="4be0c-137">xs:string</span></span>|<span data-ttu-id="4be0c-138">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4be0c-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
