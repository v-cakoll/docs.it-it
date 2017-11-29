---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9aaabbdca455d31d22b232ae2b08edef0687ac30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="a515b-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="a515b-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a515b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a515b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a515b-104">ID</span><span class="sxs-lookup"><span data-stu-id="a515b-104">ID</span></span>|<span data-ttu-id="a515b-105">1022</span><span class="sxs-lookup"><span data-stu-id="a515b-105">1022</span></span>|  
|<span data-ttu-id="a515b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a515b-106">Keywords</span></span>|<span data-ttu-id="a515b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a515b-107">WFRuntime</span></span>|  
|<span data-ttu-id="a515b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a515b-108">Level</span></span>|<span data-ttu-id="a515b-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="a515b-109">Verbose</span></span>|  
|<span data-ttu-id="a515b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a515b-110">Channel</span></span>|<span data-ttu-id="a515b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a515b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a515b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a515b-112">Description</span></span>  
 <span data-ttu-id="a515b-113">Indica che viene avviata l'esecuzione di BookmarkWorkItem.</span><span class="sxs-lookup"><span data-stu-id="a515b-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a515b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a515b-114">Message</span></span>  
 <span data-ttu-id="a515b-115">Avvio dell'esecuzione di BookmarkWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a515b-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="a515b-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="a515b-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a515b-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a515b-117">Details</span></span>  
  
|<span data-ttu-id="a515b-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a515b-118">Data Item Name</span></span>|<span data-ttu-id="a515b-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a515b-119">Data Item Type</span></span>|<span data-ttu-id="a515b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a515b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a515b-121">Attività</span><span class="sxs-lookup"><span data-stu-id="a515b-121">Activity</span></span>|<span data-ttu-id="a515b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="a515b-122">xs:string</span></span>|<span data-ttu-id="a515b-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="a515b-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="a515b-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a515b-124">DisplayName</span></span>|<span data-ttu-id="a515b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="a515b-125">xs:string</span></span>|<span data-ttu-id="a515b-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a515b-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="a515b-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a515b-127">InstanceId</span></span>|<span data-ttu-id="a515b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="a515b-128">xs:string</span></span>|<span data-ttu-id="a515b-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="a515b-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a515b-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="a515b-130">BookmarkName</span></span>|<span data-ttu-id="a515b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="a515b-131">xs:string</span></span>|<span data-ttu-id="a515b-132">Nome del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="a515b-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="a515b-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="a515b-133">BookmarkScope</span></span>|<span data-ttu-id="a515b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="a515b-134">xs:string</span></span>|<span data-ttu-id="a515b-135">Ambito del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="a515b-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="a515b-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a515b-136">AppDomain</span></span>|<span data-ttu-id="a515b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="a515b-137">xs:string</span></span>|<span data-ttu-id="a515b-138">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a515b-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
