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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6d348ec18b4d5eff7156d1e9809eb793ac1681d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="f6c59-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f6c59-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f6c59-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f6c59-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6c59-104">ID</span><span class="sxs-lookup"><span data-stu-id="f6c59-104">ID</span></span>|<span data-ttu-id="f6c59-105">1017</span><span class="sxs-lookup"><span data-stu-id="f6c59-105">1017</span></span>|  
|<span data-ttu-id="f6c59-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f6c59-106">Keywords</span></span>|<span data-ttu-id="f6c59-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f6c59-107">WFRuntime</span></span>|  
|<span data-ttu-id="f6c59-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f6c59-108">Level</span></span>|<span data-ttu-id="f6c59-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="f6c59-109">Verbose</span></span>|  
|<span data-ttu-id="f6c59-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f6c59-110">Channel</span></span>|<span data-ttu-id="f6c59-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f6c59-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f6c59-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6c59-112">Description</span></span>  
 <span data-ttu-id="f6c59-113">Indica che un elemento CancelActivityWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="f6c59-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f6c59-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f6c59-114">Message</span></span>  
 <span data-ttu-id="f6c59-115">CancelActivityWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f6c59-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f6c59-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f6c59-116">Details</span></span>  
  
|<span data-ttu-id="f6c59-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f6c59-117">Data Item Name</span></span>|<span data-ttu-id="f6c59-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f6c59-118">Data Item Type</span></span>|<span data-ttu-id="f6c59-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6c59-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f6c59-120">Attività</span><span class="sxs-lookup"><span data-stu-id="f6c59-120">Activity</span></span>|<span data-ttu-id="f6c59-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6c59-121">xs:string</span></span>|<span data-ttu-id="f6c59-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="f6c59-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f6c59-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f6c59-123">DisplayName</span></span>|<span data-ttu-id="f6c59-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6c59-124">xs:string</span></span>|<span data-ttu-id="f6c59-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f6c59-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f6c59-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f6c59-126">InstanceId</span></span>|<span data-ttu-id="f6c59-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6c59-127">xs:string</span></span>|<span data-ttu-id="f6c59-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f6c59-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f6c59-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f6c59-129">AppDomain</span></span>|<span data-ttu-id="f6c59-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f6c59-130">xs:string</span></span>|<span data-ttu-id="f6c59-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f6c59-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
