---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509972"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="3db9b-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="3db9b-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="3db9b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3db9b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3db9b-104">ID</span><span class="sxs-lookup"><span data-stu-id="3db9b-104">ID</span></span>|<span data-ttu-id="3db9b-105">1009</span><span class="sxs-lookup"><span data-stu-id="3db9b-105">1009</span></span>|  
|<span data-ttu-id="3db9b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3db9b-106">Keywords</span></span>|<span data-ttu-id="3db9b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3db9b-107">WFRuntime</span></span>|  
|<span data-ttu-id="3db9b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3db9b-108">Level</span></span>|<span data-ttu-id="3db9b-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="3db9b-109">Information</span></span>|  
|<span data-ttu-id="3db9b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3db9b-110">Channel</span></span>|<span data-ttu-id="3db9b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3db9b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3db9b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3db9b-112">Description</span></span>  
 <span data-ttu-id="3db9b-113">Indica che un'attività è pianificata per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3db9b-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3db9b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3db9b-114">Message</span></span>  
 <span data-ttu-id="3db9b-115">L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="3db9b-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3db9b-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3db9b-116">Details</span></span>  
  
|<span data-ttu-id="3db9b-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3db9b-117">Data Item Name</span></span>|<span data-ttu-id="3db9b-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3db9b-118">Data Item Type</span></span>|<span data-ttu-id="3db9b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3db9b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3db9b-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="3db9b-120">ParentActivity</span></span>|<span data-ttu-id="3db9b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-121">xs:string</span></span>|<span data-ttu-id="3db9b-122">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3db9b-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="3db9b-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="3db9b-123">ParentDisplayName</span></span>|<span data-ttu-id="3db9b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-124">xs:string</span></span>|<span data-ttu-id="3db9b-125">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3db9b-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="3db9b-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="3db9b-126">ParentInstanceId</span></span>|<span data-ttu-id="3db9b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-127">xs:string</span></span>|<span data-ttu-id="3db9b-128">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="3db9b-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="3db9b-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="3db9b-129">ChildActivity</span></span>|<span data-ttu-id="3db9b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-130">xs:string</span></span>|<span data-ttu-id="3db9b-131">Nome del tipo dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="3db9b-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="3db9b-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="3db9b-132">ChildDisplayName</span></span>|<span data-ttu-id="3db9b-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-133">xs:string</span></span>|<span data-ttu-id="3db9b-134">Nome visualizzato dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="3db9b-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="3db9b-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="3db9b-135">ChildInstanceId</span></span>|<span data-ttu-id="3db9b-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-136">xs:string</span></span>|<span data-ttu-id="3db9b-137">ID istanza dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="3db9b-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="3db9b-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3db9b-138">AppDomain</span></span>|<span data-ttu-id="3db9b-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db9b-139">xs:string</span></span>|<span data-ttu-id="3db9b-140">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3db9b-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
