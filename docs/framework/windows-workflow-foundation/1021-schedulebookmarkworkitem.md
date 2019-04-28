---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924423"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="918bb-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="918bb-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="918bb-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="918bb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="918bb-104">Id</span><span class="sxs-lookup"><span data-stu-id="918bb-104">ID</span></span>|<span data-ttu-id="918bb-105">1021</span><span class="sxs-lookup"><span data-stu-id="918bb-105">1021</span></span>|  
|<span data-ttu-id="918bb-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="918bb-106">Keywords</span></span>|<span data-ttu-id="918bb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="918bb-107">WFRuntime</span></span>|  
|<span data-ttu-id="918bb-108">Livello</span><span class="sxs-lookup"><span data-stu-id="918bb-108">Level</span></span>|<span data-ttu-id="918bb-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="918bb-109">Verbose</span></span>|  
|<span data-ttu-id="918bb-110">Canale</span><span class="sxs-lookup"><span data-stu-id="918bb-110">Channel</span></span>|<span data-ttu-id="918bb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="918bb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="918bb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="918bb-112">Description</span></span>  
 <span data-ttu-id="918bb-113">Indica che un elemento BookmarkWorkItem è stato pianificato.</span><span class="sxs-lookup"><span data-stu-id="918bb-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="918bb-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="918bb-114">Message</span></span>  
 <span data-ttu-id="918bb-115">BookmarkWorkItem pianificato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="918bb-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="918bb-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="918bb-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="918bb-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="918bb-117">Details</span></span>  
  
|<span data-ttu-id="918bb-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="918bb-118">Data Item Name</span></span>|<span data-ttu-id="918bb-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="918bb-119">Data Item Type</span></span>|<span data-ttu-id="918bb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="918bb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="918bb-121">Attività</span><span class="sxs-lookup"><span data-stu-id="918bb-121">Activity</span></span>|<span data-ttu-id="918bb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="918bb-122">xs:string</span></span>|<span data-ttu-id="918bb-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="918bb-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="918bb-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="918bb-124">DisplayName</span></span>|<span data-ttu-id="918bb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="918bb-125">xs:string</span></span>|<span data-ttu-id="918bb-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="918bb-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="918bb-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="918bb-127">InstanceId</span></span>|<span data-ttu-id="918bb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="918bb-128">xs:string</span></span>|<span data-ttu-id="918bb-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="918bb-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="918bb-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="918bb-130">BookmarkName</span></span>|<span data-ttu-id="918bb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="918bb-131">xs:string</span></span>|<span data-ttu-id="918bb-132">Nome del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="918bb-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="918bb-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="918bb-133">BookmarkScope</span></span>|<span data-ttu-id="918bb-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="918bb-134">xs:string</span></span>|<span data-ttu-id="918bb-135">Ambito del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="918bb-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="918bb-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="918bb-136">AppDomain</span></span>|<span data-ttu-id="918bb-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="918bb-137">xs:string</span></span>|<span data-ttu-id="918bb-138">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="918bb-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
