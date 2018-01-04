---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe006534e0199888668145be9da3f964055cc464
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="44dbf-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="44dbf-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="44dbf-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="44dbf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44dbf-104">ID</span><span class="sxs-lookup"><span data-stu-id="44dbf-104">ID</span></span>|<span data-ttu-id="44dbf-105">1011</span><span class="sxs-lookup"><span data-stu-id="44dbf-105">1011</span></span>|  
|<span data-ttu-id="44dbf-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="44dbf-106">Keywords</span></span>|<span data-ttu-id="44dbf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="44dbf-107">WFRuntime</span></span>|  
|<span data-ttu-id="44dbf-108">Livello</span><span class="sxs-lookup"><span data-stu-id="44dbf-108">Level</span></span>|<span data-ttu-id="44dbf-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="44dbf-109">Verbose</span></span>|  
|<span data-ttu-id="44dbf-110">Canale</span><span class="sxs-lookup"><span data-stu-id="44dbf-110">Channel</span></span>|<span data-ttu-id="44dbf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="44dbf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44dbf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44dbf-112">Description</span></span>  
 <span data-ttu-id="44dbf-113">Indica che ExecuteActivityWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="44dbf-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44dbf-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="44dbf-114">Message</span></span>  
 <span data-ttu-id="44dbf-115">ExecuteActivityWorkItem pianificato per l'attività '%1, DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="44dbf-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44dbf-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="44dbf-116">Details</span></span>  
  
|<span data-ttu-id="44dbf-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="44dbf-117">Data Item Name</span></span>|<span data-ttu-id="44dbf-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="44dbf-118">Data Item Type</span></span>|<span data-ttu-id="44dbf-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44dbf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44dbf-120">Attività</span><span class="sxs-lookup"><span data-stu-id="44dbf-120">Activity</span></span>|<span data-ttu-id="44dbf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="44dbf-121">xs:string</span></span>|<span data-ttu-id="44dbf-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="44dbf-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="44dbf-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="44dbf-123">DisplayName</span></span>|<span data-ttu-id="44dbf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="44dbf-124">xs:string</span></span>|<span data-ttu-id="44dbf-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="44dbf-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="44dbf-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="44dbf-126">InstanceId</span></span>|<span data-ttu-id="44dbf-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="44dbf-127">xs:string</span></span>|<span data-ttu-id="44dbf-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="44dbf-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="44dbf-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="44dbf-129">AppDomain</span></span>|<span data-ttu-id="44dbf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="44dbf-130">xs:string</span></span>|<span data-ttu-id="44dbf-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="44dbf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
