---
title: 1017 - ScheduleCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a632d59ddd75b375ff5e828a9f35aeecb0118f1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="6819d-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="6819d-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6819d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6819d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6819d-104">ID</span><span class="sxs-lookup"><span data-stu-id="6819d-104">ID</span></span>|<span data-ttu-id="6819d-105">1017</span><span class="sxs-lookup"><span data-stu-id="6819d-105">1017</span></span>|  
|<span data-ttu-id="6819d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6819d-106">Keywords</span></span>|<span data-ttu-id="6819d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6819d-107">WFRuntime</span></span>|  
|<span data-ttu-id="6819d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6819d-108">Level</span></span>|<span data-ttu-id="6819d-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="6819d-109">Verbose</span></span>|  
|<span data-ttu-id="6819d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6819d-110">Channel</span></span>|<span data-ttu-id="6819d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6819d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6819d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6819d-112">Description</span></span>  
 <span data-ttu-id="6819d-113">Indica che un elemento CancelActivityWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="6819d-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6819d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6819d-114">Message</span></span>  
 <span data-ttu-id="6819d-115">CancelActivityWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="6819d-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6819d-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6819d-116">Details</span></span>  
  
|<span data-ttu-id="6819d-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6819d-117">Data Item Name</span></span>|<span data-ttu-id="6819d-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6819d-118">Data Item Type</span></span>|<span data-ttu-id="6819d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6819d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6819d-120">Attività</span><span class="sxs-lookup"><span data-stu-id="6819d-120">Activity</span></span>|<span data-ttu-id="6819d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6819d-121">xs:string</span></span>|<span data-ttu-id="6819d-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="6819d-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="6819d-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6819d-123">DisplayName</span></span>|<span data-ttu-id="6819d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6819d-124">xs:string</span></span>|<span data-ttu-id="6819d-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6819d-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="6819d-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="6819d-126">InstanceId</span></span>|<span data-ttu-id="6819d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6819d-127">xs:string</span></span>|<span data-ttu-id="6819d-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6819d-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="6819d-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6819d-129">AppDomain</span></span>|<span data-ttu-id="6819d-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6819d-130">xs:string</span></span>|<span data-ttu-id="6819d-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6819d-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
