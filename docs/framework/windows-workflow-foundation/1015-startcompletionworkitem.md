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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7457b65f81e9e26b9de6055df474a83ce4264846
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="e1458-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="e1458-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e1458-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e1458-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1458-104">ID</span><span class="sxs-lookup"><span data-stu-id="e1458-104">ID</span></span>|<span data-ttu-id="e1458-105">1015</span><span class="sxs-lookup"><span data-stu-id="e1458-105">1015</span></span>|  
|<span data-ttu-id="e1458-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e1458-106">Keywords</span></span>|<span data-ttu-id="e1458-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e1458-107">WFRuntime</span></span>|  
|<span data-ttu-id="e1458-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e1458-108">Level</span></span>|<span data-ttu-id="e1458-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="e1458-109">Verbose</span></span>|  
|<span data-ttu-id="e1458-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e1458-110">Channel</span></span>|<span data-ttu-id="e1458-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e1458-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1458-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1458-112">Description</span></span>  
 <span data-ttu-id="e1458-113">Indica che viene avviata l'esecuzione di CompletionWorkItem.</span><span class="sxs-lookup"><span data-stu-id="e1458-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1458-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e1458-114">Message</span></span>  
 <span data-ttu-id="e1458-115">Avvio dell'esecuzione di CompletionWorkItem per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="e1458-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="e1458-116">Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.</span><span class="sxs-lookup"><span data-stu-id="e1458-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1458-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e1458-117">Details</span></span>  
  
|<span data-ttu-id="e1458-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e1458-118">Data Item Name</span></span>|<span data-ttu-id="e1458-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e1458-119">Data Item Type</span></span>|<span data-ttu-id="e1458-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1458-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1458-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="e1458-121">ParentActivity</span></span>|<span data-ttu-id="e1458-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-122">xs:string</span></span>|<span data-ttu-id="e1458-123">Nome tipo dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e1458-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="e1458-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1458-124">ParentDisplayName</span></span>|<span data-ttu-id="e1458-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-125">xs:string</span></span>|<span data-ttu-id="e1458-126">Nome visualizzato dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e1458-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="e1458-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1458-127">ParentInstanceId</span></span>|<span data-ttu-id="e1458-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-128">xs:string</span></span>|<span data-ttu-id="e1458-129">ID dell'istanza dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="e1458-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="e1458-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="e1458-130">CompletedActivity</span></span>|<span data-ttu-id="e1458-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-131">xs:string</span></span>|<span data-ttu-id="e1458-132">Nome tipo dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="e1458-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="e1458-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="e1458-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="e1458-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-134">xs:string</span></span>|<span data-ttu-id="e1458-135">Nome visualizzato dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="e1458-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="e1458-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="e1458-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="e1458-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-137">xs:string</span></span>|<span data-ttu-id="e1458-138">L'ID dell'istanza dell'attività completata.</span><span class="sxs-lookup"><span data-stu-id="e1458-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="e1458-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1458-139">AppDomain</span></span>|<span data-ttu-id="e1458-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1458-140">xs:string</span></span>|<span data-ttu-id="e1458-141">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1458-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
