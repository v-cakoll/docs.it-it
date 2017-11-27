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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9463fbf2e7f2ac3424488dc3fca322a91d11126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="dcee6-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="dcee6-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="dcee6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dcee6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dcee6-104">ID</span><span class="sxs-lookup"><span data-stu-id="dcee6-104">ID</span></span>|<span data-ttu-id="dcee6-105">1009</span><span class="sxs-lookup"><span data-stu-id="dcee6-105">1009</span></span>|  
|<span data-ttu-id="dcee6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dcee6-106">Keywords</span></span>|<span data-ttu-id="dcee6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dcee6-107">WFRuntime</span></span>|  
|<span data-ttu-id="dcee6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="dcee6-108">Level</span></span>|<span data-ttu-id="dcee6-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="dcee6-109">Information</span></span>|  
|<span data-ttu-id="dcee6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="dcee6-110">Channel</span></span>|<span data-ttu-id="dcee6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="dcee6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dcee6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcee6-112">Description</span></span>  
 <span data-ttu-id="dcee6-113">Indica che un'attività è pianificata per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dcee6-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dcee6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="dcee6-114">Message</span></span>  
 <span data-ttu-id="dcee6-115">L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="dcee6-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dcee6-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dcee6-116">Details</span></span>  
  
|<span data-ttu-id="dcee6-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="dcee6-117">Data Item Name</span></span>|<span data-ttu-id="dcee6-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="dcee6-118">Data Item Type</span></span>|<span data-ttu-id="dcee6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dcee6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dcee6-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="dcee6-120">ParentActivity</span></span>|<span data-ttu-id="dcee6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-121">xs:string</span></span>|<span data-ttu-id="dcee6-122">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="dcee6-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="dcee6-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="dcee6-123">ParentDisplayName</span></span>|<span data-ttu-id="dcee6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-124">xs:string</span></span>|<span data-ttu-id="dcee6-125">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="dcee6-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="dcee6-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="dcee6-126">ParentInstanceId</span></span>|<span data-ttu-id="dcee6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-127">xs:string</span></span>|<span data-ttu-id="dcee6-128">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="dcee6-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="dcee6-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="dcee6-129">ChildActivity</span></span>|<span data-ttu-id="dcee6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-130">xs:string</span></span>|<span data-ttu-id="dcee6-131">Nome del tipo dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="dcee6-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="dcee6-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="dcee6-132">ChildDisplayName</span></span>|<span data-ttu-id="dcee6-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-133">xs:string</span></span>|<span data-ttu-id="dcee6-134">Nome visualizzato dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="dcee6-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="dcee6-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="dcee6-135">ChildInstanceId</span></span>|<span data-ttu-id="dcee6-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-136">xs:string</span></span>|<span data-ttu-id="dcee6-137">ID istanza dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="dcee6-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="dcee6-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dcee6-138">AppDomain</span></span>|<span data-ttu-id="dcee6-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="dcee6-139">xs:string</span></span>|<span data-ttu-id="dcee6-140">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dcee6-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
