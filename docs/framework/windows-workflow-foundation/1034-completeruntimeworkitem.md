---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 63ab145b8a0688a7f7bbf7dbcbe8dfe612eab294
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="0863e-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="0863e-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0863e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0863e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0863e-104">ID</span><span class="sxs-lookup"><span data-stu-id="0863e-104">ID</span></span>|<span data-ttu-id="0863e-105">1034</span><span class="sxs-lookup"><span data-stu-id="0863e-105">1034</span></span>|  
|<span data-ttu-id="0863e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0863e-106">Keywords</span></span>|<span data-ttu-id="0863e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0863e-107">WFRuntime</span></span>|  
|<span data-ttu-id="0863e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0863e-108">Level</span></span>|<span data-ttu-id="0863e-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="0863e-109">Verbose</span></span>|  
|<span data-ttu-id="0863e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0863e-110">Channel</span></span>|<span data-ttu-id="0863e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0863e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0863e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0863e-112">Description</span></span>  
 <span data-ttu-id="0863e-113">Indica che RuntimeWorkItem è completato.</span><span class="sxs-lookup"><span data-stu-id="0863e-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0863e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0863e-114">Message</span></span>  
 <span data-ttu-id="0863e-115">Elemento di lavoro del runtime completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0863e-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0863e-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0863e-116">Details</span></span>  
  
|<span data-ttu-id="0863e-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0863e-117">Data Item Name</span></span>|<span data-ttu-id="0863e-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0863e-118">Data Item Type</span></span>|<span data-ttu-id="0863e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0863e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0863e-120">Attività</span><span class="sxs-lookup"><span data-stu-id="0863e-120">Activity</span></span>|<span data-ttu-id="0863e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0863e-121">xs:string</span></span>|<span data-ttu-id="0863e-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="0863e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0863e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0863e-123">DisplayName</span></span>|<span data-ttu-id="0863e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0863e-124">xs:string</span></span>|<span data-ttu-id="0863e-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0863e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0863e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0863e-126">InstanceId</span></span>|<span data-ttu-id="0863e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0863e-127">xs:string</span></span>|<span data-ttu-id="0863e-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0863e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0863e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0863e-129">AppDomain</span></span>|<span data-ttu-id="0863e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0863e-130">xs:string</span></span>|<span data-ttu-id="0863e-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0863e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
