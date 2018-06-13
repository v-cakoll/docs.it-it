---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509756"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="46242-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="46242-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="46242-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="46242-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46242-104">ID</span><span class="sxs-lookup"><span data-stu-id="46242-104">ID</span></span>|<span data-ttu-id="46242-105">1021</span><span class="sxs-lookup"><span data-stu-id="46242-105">1021</span></span>|  
|<span data-ttu-id="46242-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="46242-106">Keywords</span></span>|<span data-ttu-id="46242-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="46242-107">WFRuntime</span></span>|  
|<span data-ttu-id="46242-108">Livello</span><span class="sxs-lookup"><span data-stu-id="46242-108">Level</span></span>|<span data-ttu-id="46242-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="46242-109">Verbose</span></span>|  
|<span data-ttu-id="46242-110">Canale</span><span class="sxs-lookup"><span data-stu-id="46242-110">Channel</span></span>|<span data-ttu-id="46242-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="46242-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="46242-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46242-112">Description</span></span>  
 <span data-ttu-id="46242-113">Indica che un elemento BookmarkWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="46242-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="46242-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="46242-114">Message</span></span>  
 <span data-ttu-id="46242-115">BookmarkWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="46242-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="46242-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="46242-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="46242-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="46242-117">Details</span></span>  
  
|<span data-ttu-id="46242-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="46242-118">Data Item Name</span></span>|<span data-ttu-id="46242-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="46242-119">Data Item Type</span></span>|<span data-ttu-id="46242-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46242-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="46242-121">Attività</span><span class="sxs-lookup"><span data-stu-id="46242-121">Activity</span></span>|<span data-ttu-id="46242-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="46242-122">xs:string</span></span>|<span data-ttu-id="46242-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="46242-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="46242-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="46242-124">DisplayName</span></span>|<span data-ttu-id="46242-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="46242-125">xs:string</span></span>|<span data-ttu-id="46242-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="46242-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="46242-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="46242-127">InstanceId</span></span>|<span data-ttu-id="46242-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="46242-128">xs:string</span></span>|<span data-ttu-id="46242-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="46242-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="46242-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="46242-130">BookmarkName</span></span>|<span data-ttu-id="46242-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="46242-131">xs:string</span></span>|<span data-ttu-id="46242-132">Nome del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="46242-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="46242-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="46242-133">BookmarkScope</span></span>|<span data-ttu-id="46242-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="46242-134">xs:string</span></span>|<span data-ttu-id="46242-135">Ambito del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="46242-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="46242-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="46242-136">AppDomain</span></span>|<span data-ttu-id="46242-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="46242-137">xs:string</span></span>|<span data-ttu-id="46242-138">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="46242-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
