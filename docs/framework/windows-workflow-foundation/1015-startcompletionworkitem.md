---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 44ef71e254a2407b416a0efc4b560bf2f6013a74
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="4b57a-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="4b57a-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4b57a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4b57a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b57a-104">ID</span><span class="sxs-lookup"><span data-stu-id="4b57a-104">ID</span></span>|<span data-ttu-id="4b57a-105">1015</span><span class="sxs-lookup"><span data-stu-id="4b57a-105">1015</span></span>|  
|<span data-ttu-id="4b57a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="4b57a-106">Keywords</span></span>|<span data-ttu-id="4b57a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4b57a-107">WFRuntime</span></span>|  
|<span data-ttu-id="4b57a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="4b57a-108">Level</span></span>|<span data-ttu-id="4b57a-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="4b57a-109">Verbose</span></span>|  
|<span data-ttu-id="4b57a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="4b57a-110">Channel</span></span>|<span data-ttu-id="4b57a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4b57a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4b57a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b57a-112">Description</span></span>  
 <span data-ttu-id="4b57a-113">Indica che viene avviata l'esecuzione di CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="4b57a-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4b57a-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="4b57a-114">Message</span></span>  
 <span data-ttu-id="4b57a-115">Avvio dell'esecuzione di CompletionWorkItem per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4b57a-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="4b57a-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="4b57a-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4b57a-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4b57a-117">Details</span></span>  
  
|<span data-ttu-id="4b57a-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="4b57a-118">Data Item Name</span></span>|<span data-ttu-id="4b57a-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="4b57a-119">Data Item Type</span></span>|<span data-ttu-id="4b57a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b57a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4b57a-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="4b57a-121">ParentActivity</span></span>|<span data-ttu-id="4b57a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-122">xs:string</span></span>|<span data-ttu-id="4b57a-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="4b57a-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="4b57a-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="4b57a-124">ParentDisplayName</span></span>|<span data-ttu-id="4b57a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-125">xs:string</span></span>|<span data-ttu-id="4b57a-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="4b57a-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="4b57a-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="4b57a-127">ParentInstanceId</span></span>|<span data-ttu-id="4b57a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-128">xs:string</span></span>|<span data-ttu-id="4b57a-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="4b57a-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="4b57a-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="4b57a-130">CompletedActivity</span></span>|<span data-ttu-id="4b57a-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-131">xs:string</span></span>|<span data-ttu-id="4b57a-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="4b57a-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="4b57a-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="4b57a-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="4b57a-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-134">xs:string</span></span>|<span data-ttu-id="4b57a-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="4b57a-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="4b57a-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="4b57a-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="4b57a-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-137">xs:string</span></span>|<span data-ttu-id="4b57a-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="4b57a-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="4b57a-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4b57a-139">AppDomain</span></span>|<span data-ttu-id="4b57a-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="4b57a-140">xs:string</span></span>|<span data-ttu-id="4b57a-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4b57a-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
