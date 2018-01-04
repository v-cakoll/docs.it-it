---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81cc73a5ab58e90f1a0ee5bdaf9a491d20206fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="ade47-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="ade47-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ade47-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ade47-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ade47-104">ID</span><span class="sxs-lookup"><span data-stu-id="ade47-104">ID</span></span>|<span data-ttu-id="ade47-105">1032</span><span class="sxs-lookup"><span data-stu-id="ade47-105">1032</span></span>|  
|<span data-ttu-id="ade47-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ade47-106">Keywords</span></span>|<span data-ttu-id="ade47-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ade47-107">WFRuntime</span></span>|  
|<span data-ttu-id="ade47-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ade47-108">Level</span></span>|<span data-ttu-id="ade47-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="ade47-109">Verbose</span></span>|  
|<span data-ttu-id="ade47-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ade47-110">Channel</span></span>|<span data-ttu-id="ade47-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ade47-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ade47-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade47-112">Description</span></span>  
 <span data-ttu-id="ade47-113">Indica che un elemento RuntimeWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="ade47-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ade47-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ade47-114">Message</span></span>  
 <span data-ttu-id="ade47-115">Elemento di lavoro del runtime pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ade47-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ade47-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ade47-116">Details</span></span>  
  
|<span data-ttu-id="ade47-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ade47-117">Data Item Name</span></span>|<span data-ttu-id="ade47-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ade47-118">Data Item Type</span></span>|<span data-ttu-id="ade47-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ade47-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ade47-120">Attività</span><span class="sxs-lookup"><span data-stu-id="ade47-120">Activity</span></span>|<span data-ttu-id="ade47-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ade47-121">xs:string</span></span>|<span data-ttu-id="ade47-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="ade47-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ade47-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ade47-123">DisplayName</span></span>|<span data-ttu-id="ade47-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ade47-124">xs:string</span></span>|<span data-ttu-id="ade47-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ade47-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ade47-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ade47-126">InstanceId</span></span>|<span data-ttu-id="ade47-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ade47-127">xs:string</span></span>|<span data-ttu-id="ade47-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ade47-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ade47-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ade47-129">AppDomain</span></span>|<span data-ttu-id="ade47-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ade47-130">xs:string</span></span>|<span data-ttu-id="ade47-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ade47-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
