---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510459"
---
# <a name="1020---createbookmark"></a><span data-ttu-id="052a0-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="052a0-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="052a0-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="052a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="052a0-104">ID</span><span class="sxs-lookup"><span data-stu-id="052a0-104">ID</span></span>|<span data-ttu-id="052a0-105">1020</span><span class="sxs-lookup"><span data-stu-id="052a0-105">1020</span></span>|  
|<span data-ttu-id="052a0-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="052a0-106">Keywords</span></span>|<span data-ttu-id="052a0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="052a0-107">WFRuntime</span></span>|  
|<span data-ttu-id="052a0-108">Livello</span><span class="sxs-lookup"><span data-stu-id="052a0-108">Level</span></span>|<span data-ttu-id="052a0-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="052a0-109">Verbose</span></span>|  
|<span data-ttu-id="052a0-110">Canale</span><span class="sxs-lookup"><span data-stu-id="052a0-110">Channel</span></span>|<span data-ttu-id="052a0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="052a0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="052a0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="052a0-112">Description</span></span>  
 <span data-ttu-id="052a0-113">Indica che un bookmark è stato creato per un'attività.</span><span class="sxs-lookup"><span data-stu-id="052a0-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="052a0-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="052a0-114">Message</span></span>  
 <span data-ttu-id="052a0-115">È stato creato un segnalibro per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="052a0-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="052a0-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="052a0-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="052a0-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="052a0-117">Details</span></span>  
  
|<span data-ttu-id="052a0-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="052a0-118">Data Item Name</span></span>|<span data-ttu-id="052a0-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="052a0-119">Data Item Type</span></span>|<span data-ttu-id="052a0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="052a0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="052a0-121">Attività</span><span class="sxs-lookup"><span data-stu-id="052a0-121">Activity</span></span>|<span data-ttu-id="052a0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="052a0-122">xs:string</span></span>|<span data-ttu-id="052a0-123">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="052a0-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="052a0-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="052a0-124">DisplayName</span></span>|<span data-ttu-id="052a0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="052a0-125">xs:string</span></span>|<span data-ttu-id="052a0-126">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="052a0-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="052a0-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="052a0-127">InstanceId</span></span>|<span data-ttu-id="052a0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="052a0-128">xs:string</span></span>|<span data-ttu-id="052a0-129">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="052a0-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="052a0-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="052a0-130">BookmarkName</span></span>|<span data-ttu-id="052a0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="052a0-131">xs:string</span></span>|<span data-ttu-id="052a0-132">Nome del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="052a0-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="052a0-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="052a0-133">BookmarkScope</span></span>|<span data-ttu-id="052a0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="052a0-134">xs:string</span></span>|<span data-ttu-id="052a0-135">Ambito del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="052a0-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="052a0-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="052a0-136">AppDomain</span></span>|<span data-ttu-id="052a0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="052a0-137">xs:string</span></span>|<span data-ttu-id="052a0-138">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="052a0-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
