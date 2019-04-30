---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982267"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="49d6a-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="49d6a-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="49d6a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="49d6a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49d6a-104">Id</span><span class="sxs-lookup"><span data-stu-id="49d6a-104">ID</span></span>|<span data-ttu-id="49d6a-105">1014</span><span class="sxs-lookup"><span data-stu-id="49d6a-105">1014</span></span>|  
|<span data-ttu-id="49d6a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="49d6a-106">Keywords</span></span>|<span data-ttu-id="49d6a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="49d6a-107">WFRuntime</span></span>|  
|<span data-ttu-id="49d6a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="49d6a-108">Level</span></span>|<span data-ttu-id="49d6a-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="49d6a-109">Verbose</span></span>|  
|<span data-ttu-id="49d6a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="49d6a-110">Channel</span></span>|<span data-ttu-id="49d6a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="49d6a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49d6a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49d6a-112">Description</span></span>  
 <span data-ttu-id="49d6a-113">Indica che un elemento CompletionWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="49d6a-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49d6a-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="49d6a-114">Message</span></span>  
 <span data-ttu-id="49d6a-115">CompletionWorkItem pianificato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="49d6a-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="49d6a-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="49d6a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="49d6a-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="49d6a-117">Details</span></span>  
  
|<span data-ttu-id="49d6a-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="49d6a-118">Data Item Name</span></span>|<span data-ttu-id="49d6a-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="49d6a-119">Data Item Type</span></span>|<span data-ttu-id="49d6a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49d6a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49d6a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="49d6a-121">ParentActivity</span></span>|<span data-ttu-id="49d6a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-122">xs:string</span></span>|<span data-ttu-id="49d6a-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="49d6a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="49d6a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="49d6a-124">ParentDisplayName</span></span>|<span data-ttu-id="49d6a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-125">xs:string</span></span>|<span data-ttu-id="49d6a-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="49d6a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="49d6a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="49d6a-127">ParentInstanceId</span></span>|<span data-ttu-id="49d6a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-128">xs:string</span></span>|<span data-ttu-id="49d6a-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="49d6a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="49d6a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="49d6a-130">CompletedActivity</span></span>|<span data-ttu-id="49d6a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-131">xs:string</span></span>|<span data-ttu-id="49d6a-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="49d6a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="49d6a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="49d6a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="49d6a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-134">xs:string</span></span>|<span data-ttu-id="49d6a-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="49d6a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="49d6a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="49d6a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="49d6a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-137">xs:string</span></span>|<span data-ttu-id="49d6a-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="49d6a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="49d6a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="49d6a-139">AppDomain</span></span>|<span data-ttu-id="49d6a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="49d6a-140">xs:string</span></span>|<span data-ttu-id="49d6a-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="49d6a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
