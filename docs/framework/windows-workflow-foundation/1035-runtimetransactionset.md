---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a64a8a4ab6212a5e83b59fd7523df9cd875e7b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="2590c-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="2590c-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="2590c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2590c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2590c-104">ID</span><span class="sxs-lookup"><span data-stu-id="2590c-104">ID</span></span>|<span data-ttu-id="2590c-105">1035</span><span class="sxs-lookup"><span data-stu-id="2590c-105">1035</span></span>|  
|<span data-ttu-id="2590c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2590c-106">Keywords</span></span>|<span data-ttu-id="2590c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2590c-107">WFRuntime</span></span>|  
|<span data-ttu-id="2590c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2590c-108">Level</span></span>|<span data-ttu-id="2590c-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="2590c-109">Verbose</span></span>|  
|<span data-ttu-id="2590c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2590c-110">Channel</span></span>|<span data-ttu-id="2590c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2590c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2590c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2590c-112">Description</span></span>  
 <span data-ttu-id="2590c-113">Indica che un'attività ha impostato la transazione runtime.</span><span class="sxs-lookup"><span data-stu-id="2590c-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2590c-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2590c-114">Message</span></span>  
 <span data-ttu-id="2590c-115">La transazione di runtime è stata impostata dall'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2590c-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2590c-116">Esecuzione isolata all'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2590c-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2590c-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2590c-117">Details</span></span>  
  
|<span data-ttu-id="2590c-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2590c-118">Data Item Name</span></span>|<span data-ttu-id="2590c-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2590c-119">Data Item Type</span></span>|<span data-ttu-id="2590c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2590c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2590c-121">Attività</span><span class="sxs-lookup"><span data-stu-id="2590c-121">Activity</span></span>|<span data-ttu-id="2590c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-122">xs:string</span></span>|<span data-ttu-id="2590c-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="2590c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2590c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2590c-124">DisplayName</span></span>|<span data-ttu-id="2590c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-125">xs:string</span></span>|<span data-ttu-id="2590c-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2590c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2590c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2590c-127">InstanceId</span></span>|<span data-ttu-id="2590c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-128">xs:string</span></span>|<span data-ttu-id="2590c-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2590c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2590c-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="2590c-130">IsolatedActivity</span></span>|<span data-ttu-id="2590c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-131">xs:string</span></span>|<span data-ttu-id="2590c-132">Il nome del tipo di attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="2590c-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2590c-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2590c-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="2590c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-134">xs:string</span></span>|<span data-ttu-id="2590c-135">Il nome visualizzato dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="2590c-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2590c-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2590c-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="2590c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-137">xs:string</span></span>|<span data-ttu-id="2590c-138">L'ID istanza dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="2590c-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2590c-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2590c-139">AppDomain</span></span>|<span data-ttu-id="2590c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2590c-140">xs:string</span></span>|<span data-ttu-id="2590c-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2590c-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
