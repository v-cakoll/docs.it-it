---
title: 1009 - ActivityScheduled
ms.date: 03/30/2017
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
ms.openlocfilehash: 0e3ea53a7b0509fcb8b73b61193742d615ac7e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924657"
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="0d5d0-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="0d5d0-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="0d5d0-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0d5d0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d5d0-104">Id</span><span class="sxs-lookup"><span data-stu-id="0d5d0-104">ID</span></span>|<span data-ttu-id="0d5d0-105">1009</span><span class="sxs-lookup"><span data-stu-id="0d5d0-105">1009</span></span>|  
|<span data-ttu-id="0d5d0-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0d5d0-106">Keywords</span></span>|<span data-ttu-id="0d5d0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0d5d0-107">WFRuntime</span></span>|  
|<span data-ttu-id="0d5d0-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0d5d0-108">Level</span></span>|<span data-ttu-id="0d5d0-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="0d5d0-109">Information</span></span>|  
|<span data-ttu-id="0d5d0-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0d5d0-110">Channel</span></span>|<span data-ttu-id="0d5d0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0d5d0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d5d0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d5d0-112">Description</span></span>  
 <span data-ttu-id="0d5d0-113">Indica che un'attività è pianificata per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d5d0-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0d5d0-114">Message</span></span>  
 <span data-ttu-id="0d5d0-115">L'attività padre '%1', DisplayName: '%2', InstanceId: '%3' ha pianificato l'attività figlio '%4'', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d5d0-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0d5d0-116">Details</span></span>  
  
|<span data-ttu-id="0d5d0-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0d5d0-117">Data Item Name</span></span>|<span data-ttu-id="0d5d0-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0d5d0-118">Data Item Type</span></span>|<span data-ttu-id="0d5d0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d5d0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d5d0-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="0d5d0-120">ParentActivity</span></span>|<span data-ttu-id="0d5d0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-121">xs:string</span></span>|<span data-ttu-id="0d5d0-122">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="0d5d0-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="0d5d0-123">ParentDisplayName</span></span>|<span data-ttu-id="0d5d0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-124">xs:string</span></span>|<span data-ttu-id="0d5d0-125">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="0d5d0-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="0d5d0-126">ParentInstanceId</span></span>|<span data-ttu-id="0d5d0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-127">xs:string</span></span>|<span data-ttu-id="0d5d0-128">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="0d5d0-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="0d5d0-129">ChildActivity</span></span>|<span data-ttu-id="0d5d0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-130">xs:string</span></span>|<span data-ttu-id="0d5d0-131">Nome del tipo dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="0d5d0-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="0d5d0-132">ChildDisplayName</span></span>|<span data-ttu-id="0d5d0-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-133">xs:string</span></span>|<span data-ttu-id="0d5d0-134">Nome visualizzato dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="0d5d0-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="0d5d0-135">ChildInstanceId</span></span>|<span data-ttu-id="0d5d0-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-136">xs:string</span></span>|<span data-ttu-id="0d5d0-137">ID istanza dell'attività figlio pianificata.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="0d5d0-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0d5d0-138">AppDomain</span></span>|<span data-ttu-id="0d5d0-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="0d5d0-139">xs:string</span></span>|<span data-ttu-id="0d5d0-140">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0d5d0-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
