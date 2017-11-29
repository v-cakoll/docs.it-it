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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3fcd93dbc30b20f7822a54babde8277e32d8335
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="d4dac-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="d4dac-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="d4dac-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d4dac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4dac-104">ID</span><span class="sxs-lookup"><span data-stu-id="d4dac-104">ID</span></span>|<span data-ttu-id="d4dac-105">1035</span><span class="sxs-lookup"><span data-stu-id="d4dac-105">1035</span></span>|  
|<span data-ttu-id="d4dac-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d4dac-106">Keywords</span></span>|<span data-ttu-id="d4dac-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d4dac-107">WFRuntime</span></span>|  
|<span data-ttu-id="d4dac-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d4dac-108">Level</span></span>|<span data-ttu-id="d4dac-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="d4dac-109">Verbose</span></span>|  
|<span data-ttu-id="d4dac-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d4dac-110">Channel</span></span>|<span data-ttu-id="d4dac-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d4dac-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4dac-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4dac-112">Description</span></span>  
 <span data-ttu-id="d4dac-113">Indica che un'attività ha impostato la transazione runtime.</span><span class="sxs-lookup"><span data-stu-id="d4dac-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4dac-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d4dac-114">Message</span></span>  
 <span data-ttu-id="d4dac-115">La transazione di runtime è stata impostata dall'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="d4dac-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="d4dac-116">Esecuzione isolata all'attività '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="d4dac-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4dac-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d4dac-117">Details</span></span>  
  
|<span data-ttu-id="d4dac-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d4dac-118">Data Item Name</span></span>|<span data-ttu-id="d4dac-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d4dac-119">Data Item Type</span></span>|<span data-ttu-id="d4dac-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d4dac-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4dac-121">Attività</span><span class="sxs-lookup"><span data-stu-id="d4dac-121">Activity</span></span>|<span data-ttu-id="d4dac-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-122">xs:string</span></span>|<span data-ttu-id="d4dac-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="d4dac-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="d4dac-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d4dac-124">DisplayName</span></span>|<span data-ttu-id="d4dac-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-125">xs:string</span></span>|<span data-ttu-id="d4dac-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d4dac-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="d4dac-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d4dac-127">InstanceId</span></span>|<span data-ttu-id="d4dac-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-128">xs:string</span></span>|<span data-ttu-id="d4dac-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d4dac-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d4dac-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="d4dac-130">IsolatedActivity</span></span>|<span data-ttu-id="d4dac-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-131">xs:string</span></span>|<span data-ttu-id="d4dac-132">Il nome del tipo di attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="d4dac-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="d4dac-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="d4dac-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="d4dac-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-134">xs:string</span></span>|<span data-ttu-id="d4dac-135">Il nome visualizzato dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="d4dac-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="d4dac-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="d4dac-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="d4dac-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-137">xs:string</span></span>|<span data-ttu-id="d4dac-138">L'ID istanza dell'attività che la transazione su cui è isolata.</span><span class="sxs-lookup"><span data-stu-id="d4dac-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="d4dac-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4dac-139">AppDomain</span></span>|<span data-ttu-id="d4dac-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4dac-140">xs:string</span></span>|<span data-ttu-id="d4dac-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d4dac-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
