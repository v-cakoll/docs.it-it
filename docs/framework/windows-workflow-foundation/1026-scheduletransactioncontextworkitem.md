---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83c99ddf9c5d4a8fa468303fb198abc349ace6d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="953e4-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="953e4-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="953e4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="953e4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="953e4-104">ID</span><span class="sxs-lookup"><span data-stu-id="953e4-104">ID</span></span>|<span data-ttu-id="953e4-105">1026</span><span class="sxs-lookup"><span data-stu-id="953e4-105">1026</span></span>|  
|<span data-ttu-id="953e4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="953e4-106">Keywords</span></span>|<span data-ttu-id="953e4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="953e4-107">WFRuntime</span></span>|  
|<span data-ttu-id="953e4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="953e4-108">Level</span></span>|<span data-ttu-id="953e4-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="953e4-109">Verbose</span></span>|  
|<span data-ttu-id="953e4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="953e4-110">Channel</span></span>|<span data-ttu-id="953e4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="953e4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="953e4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="953e4-112">Description</span></span>  
 <span data-ttu-id="953e4-113">Indica che un elemento TransactionContextWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="953e4-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="953e4-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="953e4-114">Message</span></span>  
 <span data-ttu-id="953e4-115">TransactionContextWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="953e4-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="953e4-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="953e4-116">Details</span></span>  
  
|<span data-ttu-id="953e4-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="953e4-117">Data Item Name</span></span>|<span data-ttu-id="953e4-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="953e4-118">Data Item Type</span></span>|<span data-ttu-id="953e4-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="953e4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="953e4-120">Attività</span><span class="sxs-lookup"><span data-stu-id="953e4-120">Activity</span></span>|<span data-ttu-id="953e4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="953e4-121">xs:string</span></span>|<span data-ttu-id="953e4-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="953e4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="953e4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="953e4-123">DisplayName</span></span>|<span data-ttu-id="953e4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="953e4-124">xs:string</span></span>|<span data-ttu-id="953e4-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="953e4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="953e4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="953e4-126">InstanceId</span></span>|<span data-ttu-id="953e4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="953e4-127">xs:string</span></span>|<span data-ttu-id="953e4-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="953e4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="953e4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="953e4-129">AppDomain</span></span>|<span data-ttu-id="953e4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="953e4-130">xs:string</span></span>|<span data-ttu-id="953e4-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="953e4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
