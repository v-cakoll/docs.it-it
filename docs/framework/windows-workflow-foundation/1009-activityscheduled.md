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
ms.workload: dotnet
ms.openlocfilehash: 4a0d8cc3d17ecd13d9312b42554ef5347cccf213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="efb97-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="efb97-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="efb97-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="efb97-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efb97-104">ID</span><span class="sxs-lookup"><span data-stu-id="efb97-104">ID</span></span>|<span data-ttu-id="efb97-105">1009</span><span class="sxs-lookup"><span data-stu-id="efb97-105">1009</span></span>|  
|<span data-ttu-id="efb97-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="efb97-106">Keywords</span></span>|<span data-ttu-id="efb97-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="efb97-107">WFRuntime</span></span>|  
|<span data-ttu-id="efb97-108">Livello</span><span class="sxs-lookup"><span data-stu-id="efb97-108">Level</span></span>|<span data-ttu-id="efb97-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="efb97-109">Information</span></span>|  
|<span data-ttu-id="efb97-110">Canale</span><span class="sxs-lookup"><span data-stu-id="efb97-110">Channel</span></span>|<span data-ttu-id="efb97-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="efb97-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="efb97-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efb97-112">Description</span></span>  
 <span data-ttu-id="efb97-113">Indica che un'attività è pianificata per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="efb97-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="efb97-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="efb97-114">Message</span></span>  
 <span data-ttu-id="efb97-115">L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="efb97-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="efb97-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="efb97-116">Details</span></span>  
  
|<span data-ttu-id="efb97-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="efb97-117">Data Item Name</span></span>|<span data-ttu-id="efb97-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="efb97-118">Data Item Type</span></span>|<span data-ttu-id="efb97-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efb97-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="efb97-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="efb97-120">ParentActivity</span></span>|<span data-ttu-id="efb97-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-121">xs:string</span></span>|<span data-ttu-id="efb97-122">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="efb97-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="efb97-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="efb97-123">ParentDisplayName</span></span>|<span data-ttu-id="efb97-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-124">xs:string</span></span>|<span data-ttu-id="efb97-125">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="efb97-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="efb97-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="efb97-126">ParentInstanceId</span></span>|<span data-ttu-id="efb97-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-127">xs:string</span></span>|<span data-ttu-id="efb97-128">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="efb97-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="efb97-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="efb97-129">ChildActivity</span></span>|<span data-ttu-id="efb97-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-130">xs:string</span></span>|<span data-ttu-id="efb97-131">Nome del tipo dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="efb97-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="efb97-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="efb97-132">ChildDisplayName</span></span>|<span data-ttu-id="efb97-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-133">xs:string</span></span>|<span data-ttu-id="efb97-134">Nome visualizzato dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="efb97-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="efb97-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="efb97-135">ChildInstanceId</span></span>|<span data-ttu-id="efb97-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-136">xs:string</span></span>|<span data-ttu-id="efb97-137">ID istanza dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="efb97-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="efb97-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="efb97-138">AppDomain</span></span>|<span data-ttu-id="efb97-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="efb97-139">xs:string</span></span>|<span data-ttu-id="efb97-140">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="efb97-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
