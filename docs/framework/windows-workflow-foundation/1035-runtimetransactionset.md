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
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="2b8a6-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="2b8a6-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="2b8a6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2b8a6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b8a6-104">ID</span><span class="sxs-lookup"><span data-stu-id="2b8a6-104">ID</span></span>|<span data-ttu-id="2b8a6-105">1035</span><span class="sxs-lookup"><span data-stu-id="2b8a6-105">1035</span></span>|  
|<span data-ttu-id="2b8a6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2b8a6-106">Keywords</span></span>|<span data-ttu-id="2b8a6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2b8a6-107">WFRuntime</span></span>|  
|<span data-ttu-id="2b8a6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2b8a6-108">Level</span></span>|<span data-ttu-id="2b8a6-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="2b8a6-109">Verbose</span></span>|  
|<span data-ttu-id="2b8a6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2b8a6-110">Channel</span></span>|<span data-ttu-id="2b8a6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2b8a6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b8a6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b8a6-112">Description</span></span>  
 <span data-ttu-id="2b8a6-113">Indica che un'attività ha impostato la transazione runtime.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b8a6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2b8a6-114">Message</span></span>  
 <span data-ttu-id="2b8a6-115">La transazione di runtime è stata impostata dall'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="2b8a6-116">Esecuzione isolata all'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b8a6-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2b8a6-117">Details</span></span>  
  
|<span data-ttu-id="2b8a6-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2b8a6-118">Data Item Name</span></span>|<span data-ttu-id="2b8a6-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2b8a6-119">Data Item Type</span></span>|<span data-ttu-id="2b8a6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b8a6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2b8a6-121">Attività</span><span class="sxs-lookup"><span data-stu-id="2b8a6-121">Activity</span></span>|<span data-ttu-id="2b8a6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-122">xs:string</span></span>|<span data-ttu-id="2b8a6-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="2b8a6-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2b8a6-124">DisplayName</span></span>|<span data-ttu-id="2b8a6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-125">xs:string</span></span>|<span data-ttu-id="2b8a6-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="2b8a6-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2b8a6-127">InstanceId</span></span>|<span data-ttu-id="2b8a6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-128">xs:string</span></span>|<span data-ttu-id="2b8a6-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2b8a6-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="2b8a6-130">IsolatedActivity</span></span>|<span data-ttu-id="2b8a6-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-131">xs:string</span></span>|<span data-ttu-id="2b8a6-132">Il nome del tipo di attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2b8a6-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2b8a6-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="2b8a6-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-134">xs:string</span></span>|<span data-ttu-id="2b8a6-135">Il nome visualizzato dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2b8a6-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2b8a6-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="2b8a6-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-137">xs:string</span></span>|<span data-ttu-id="2b8a6-138">L'ID istanza dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="2b8a6-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2b8a6-139">AppDomain</span></span>|<span data-ttu-id="2b8a6-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2b8a6-140">xs:string</span></span>|<span data-ttu-id="2b8a6-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2b8a6-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
