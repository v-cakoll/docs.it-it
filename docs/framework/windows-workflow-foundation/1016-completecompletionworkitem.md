---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510296"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="02224-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="02224-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="02224-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="02224-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02224-104">ID</span><span class="sxs-lookup"><span data-stu-id="02224-104">ID</span></span>|<span data-ttu-id="02224-105">1016</span><span class="sxs-lookup"><span data-stu-id="02224-105">1016</span></span>|  
|<span data-ttu-id="02224-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="02224-106">Keywords</span></span>|<span data-ttu-id="02224-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="02224-107">WFRuntime</span></span>|  
|<span data-ttu-id="02224-108">Livello</span><span class="sxs-lookup"><span data-stu-id="02224-108">Level</span></span>|<span data-ttu-id="02224-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="02224-109">Verbose</span></span>|  
|<span data-ttu-id="02224-110">Canale</span><span class="sxs-lookup"><span data-stu-id="02224-110">Channel</span></span>|<span data-ttu-id="02224-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="02224-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02224-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02224-112">Description</span></span>  
 <span data-ttu-id="02224-113">Indica che CompletionWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="02224-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02224-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="02224-114">Message</span></span>  
 <span data-ttu-id="02224-115">CompletionWorkItem completato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="02224-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="02224-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="02224-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02224-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="02224-117">Details</span></span>  
  
|<span data-ttu-id="02224-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="02224-118">Data Item Name</span></span>|<span data-ttu-id="02224-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="02224-119">Data Item Type</span></span>|<span data-ttu-id="02224-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02224-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02224-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="02224-121">ParentActivity</span></span>|<span data-ttu-id="02224-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-122">xs:string</span></span>|<span data-ttu-id="02224-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="02224-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="02224-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="02224-124">ParentDisplayName</span></span>|<span data-ttu-id="02224-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-125">xs:string</span></span>|<span data-ttu-id="02224-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="02224-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="02224-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="02224-127">ParentInstanceId</span></span>|<span data-ttu-id="02224-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-128">xs:string</span></span>|<span data-ttu-id="02224-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="02224-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="02224-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="02224-130">CompletedActivity</span></span>|<span data-ttu-id="02224-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-131">xs:string</span></span>|<span data-ttu-id="02224-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="02224-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="02224-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="02224-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="02224-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-134">xs:string</span></span>|<span data-ttu-id="02224-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="02224-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="02224-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="02224-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="02224-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-137">xs:string</span></span>|<span data-ttu-id="02224-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="02224-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="02224-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02224-139">AppDomain</span></span>|<span data-ttu-id="02224-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="02224-140">xs:string</span></span>|<span data-ttu-id="02224-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="02224-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
