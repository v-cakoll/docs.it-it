---
title: 1020 - CreateBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0584c6eeaf0e08e92ad94e01e1fca765616440f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="cc1dd-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="cc1dd-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="cc1dd-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cc1dd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc1dd-104">ID</span><span class="sxs-lookup"><span data-stu-id="cc1dd-104">ID</span></span>|<span data-ttu-id="cc1dd-105">1020</span><span class="sxs-lookup"><span data-stu-id="cc1dd-105">1020</span></span>|  
|<span data-ttu-id="cc1dd-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cc1dd-106">Keywords</span></span>|<span data-ttu-id="cc1dd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cc1dd-107">WFRuntime</span></span>|  
|<span data-ttu-id="cc1dd-108">Livello</span><span class="sxs-lookup"><span data-stu-id="cc1dd-108">Level</span></span>|<span data-ttu-id="cc1dd-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="cc1dd-109">Verbose</span></span>|  
|<span data-ttu-id="cc1dd-110">Canale</span><span class="sxs-lookup"><span data-stu-id="cc1dd-110">Channel</span></span>|<span data-ttu-id="cc1dd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cc1dd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cc1dd-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc1dd-112">Description</span></span>  
 <span data-ttu-id="cc1dd-113">Indica che un bookmark è stato creato per un'attività.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cc1dd-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="cc1dd-114">Message</span></span>  
 <span data-ttu-id="cc1dd-115">È stato creato un segnalibro per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="cc1dd-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cc1dd-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cc1dd-117">Details</span></span>  
  
|<span data-ttu-id="cc1dd-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="cc1dd-118">Data Item Name</span></span>|<span data-ttu-id="cc1dd-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="cc1dd-119">Data Item Type</span></span>|<span data-ttu-id="cc1dd-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc1dd-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cc1dd-121">Attività</span><span class="sxs-lookup"><span data-stu-id="cc1dd-121">Activity</span></span>|<span data-ttu-id="cc1dd-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc1dd-122">xs:string</span></span>|<span data-ttu-id="cc1dd-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="cc1dd-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cc1dd-124">DisplayName</span></span>|<span data-ttu-id="cc1dd-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc1dd-125">xs:string</span></span>|<span data-ttu-id="cc1dd-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="cc1dd-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="cc1dd-127">InstanceId</span></span>|<span data-ttu-id="cc1dd-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc1dd-128">xs:string</span></span>|<span data-ttu-id="cc1dd-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="cc1dd-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="cc1dd-130">BookmarkName</span></span>|<span data-ttu-id="cc1dd-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc1dd-131">xs:string</span></span>|<span data-ttu-id="cc1dd-132">Nome del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="cc1dd-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="cc1dd-133">BookmarkScope</span></span>|<span data-ttu-id="cc1dd-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc1dd-134">xs:string</span></span>|<span data-ttu-id="cc1dd-135">Ambito del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="cc1dd-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cc1dd-136">AppDomain</span></span>|<span data-ttu-id="cc1dd-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="cc1dd-137">xs:string</span></span>|<span data-ttu-id="cc1dd-138">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cc1dd-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
