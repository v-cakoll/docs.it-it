---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fb5636057193fcfb59e5062f6f3833a62b4f3027
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="78db9-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="78db9-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="78db9-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="78db9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78db9-104">ID</span><span class="sxs-lookup"><span data-stu-id="78db9-104">ID</span></span>|<span data-ttu-id="78db9-105">3508</span><span class="sxs-lookup"><span data-stu-id="78db9-105">3508</span></span>|  
|<span data-ttu-id="78db9-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="78db9-106">Keywords</span></span>|<span data-ttu-id="78db9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="78db9-107">WFServices</span></span>|  
|<span data-ttu-id="78db9-108">Livello</span><span class="sxs-lookup"><span data-stu-id="78db9-108">Level</span></span>|<span data-ttu-id="78db9-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="78db9-109">Verbose</span></span>|  
|<span data-ttu-id="78db9-110">Canale</span><span class="sxs-lookup"><span data-stu-id="78db9-110">Channel</span></span>|<span data-ttu-id="78db9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="78db9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78db9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78db9-112">Description</span></span>  
 <span data-ttu-id="78db9-113">Indica che TrackingProfile non è presente nel file di configurazione o ActivityDefinitionId non corrisponde al profilo.</span><span class="sxs-lookup"><span data-stu-id="78db9-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78db9-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="78db9-114">Message</span></span>  
 <span data-ttu-id="78db9-115">Impossibile trovare TrackingProfile '%1' per ActivityDefinitionId '%2'.</span><span class="sxs-lookup"><span data-stu-id="78db9-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="78db9-116">TrackingProfile non incluso nel file di configurazione o ActivityDefinitionId non corrisponde.</span><span class="sxs-lookup"><span data-stu-id="78db9-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="78db9-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="78db9-117">Details</span></span>  
  
|<span data-ttu-id="78db9-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="78db9-118">Data Item Name</span></span>|<span data-ttu-id="78db9-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="78db9-119">Data Item Type</span></span>|<span data-ttu-id="78db9-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78db9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78db9-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="78db9-121">TrackingProfile</span></span>|<span data-ttu-id="78db9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="78db9-122">xs:string</span></span>|<span data-ttu-id="78db9-123">Nome del profilo di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="78db9-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="78db9-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="78db9-124">ActivityDefinitionId</span></span>|<span data-ttu-id="78db9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="78db9-125">xs:string</span></span>|<span data-ttu-id="78db9-126">ID di definizione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="78db9-126">The activity definition id.</span></span>|  
|<span data-ttu-id="78db9-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78db9-127">AppDomain</span></span>|<span data-ttu-id="78db9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="78db9-128">xs:string</span></span>|<span data-ttu-id="78db9-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="78db9-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
