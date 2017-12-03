---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdaa8ca4efeffb3895e0056303721b13cdc1ae27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="fe46f-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="fe46f-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="fe46f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fe46f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe46f-104">ID</span><span class="sxs-lookup"><span data-stu-id="fe46f-104">ID</span></span>|<span data-ttu-id="fe46f-105">1009</span><span class="sxs-lookup"><span data-stu-id="fe46f-105">1009</span></span>|  
|<span data-ttu-id="fe46f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fe46f-106">Keywords</span></span>|<span data-ttu-id="fe46f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fe46f-107">WFRuntime</span></span>|  
|<span data-ttu-id="fe46f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="fe46f-108">Level</span></span>|<span data-ttu-id="fe46f-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="fe46f-109">Information</span></span>|  
|<span data-ttu-id="fe46f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="fe46f-110">Channel</span></span>|<span data-ttu-id="fe46f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fe46f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe46f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe46f-112">Description</span></span>  
 <span data-ttu-id="fe46f-113">Indica che un'attività è pianificata per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fe46f-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe46f-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fe46f-114">Message</span></span>  
 <span data-ttu-id="fe46f-115">L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="fe46f-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe46f-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fe46f-116">Details</span></span>  
  
|<span data-ttu-id="fe46f-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="fe46f-117">Data Item Name</span></span>|<span data-ttu-id="fe46f-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="fe46f-118">Data Item Type</span></span>|<span data-ttu-id="fe46f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe46f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe46f-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="fe46f-120">ParentActivity</span></span>|<span data-ttu-id="fe46f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-121">xs:string</span></span>|<span data-ttu-id="fe46f-122">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="fe46f-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="fe46f-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="fe46f-123">ParentDisplayName</span></span>|<span data-ttu-id="fe46f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-124">xs:string</span></span>|<span data-ttu-id="fe46f-125">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="fe46f-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="fe46f-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="fe46f-126">ParentInstanceId</span></span>|<span data-ttu-id="fe46f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-127">xs:string</span></span>|<span data-ttu-id="fe46f-128">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="fe46f-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="fe46f-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="fe46f-129">ChildActivity</span></span>|<span data-ttu-id="fe46f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-130">xs:string</span></span>|<span data-ttu-id="fe46f-131">Nome del tipo dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="fe46f-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="fe46f-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="fe46f-132">ChildDisplayName</span></span>|<span data-ttu-id="fe46f-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-133">xs:string</span></span>|<span data-ttu-id="fe46f-134">Nome visualizzato dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="fe46f-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="fe46f-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="fe46f-135">ChildInstanceId</span></span>|<span data-ttu-id="fe46f-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-136">xs:string</span></span>|<span data-ttu-id="fe46f-137">ID istanza dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="fe46f-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="fe46f-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe46f-138">AppDomain</span></span>|<span data-ttu-id="fe46f-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe46f-139">xs:string</span></span>|<span data-ttu-id="fe46f-140">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fe46f-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
