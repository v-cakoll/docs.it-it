---
title: 403 - SuspendSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10e745ded72caa493119d7e27a5c777b2185b96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="de125-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="de125-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="de125-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="de125-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="de125-104">ID</span><span class="sxs-lookup"><span data-stu-id="de125-104">ID</span></span>|<span data-ttu-id="de125-105">403</span><span class="sxs-lookup"><span data-stu-id="de125-105">403</span></span>|  
|<span data-ttu-id="de125-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="de125-106">Keywords</span></span>|<span data-ttu-id="de125-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="de125-107">Troubleshooting</span></span>|  
|<span data-ttu-id="de125-108">Livello</span><span class="sxs-lookup"><span data-stu-id="de125-108">Level</span></span>|<span data-ttu-id="de125-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="de125-109">Information</span></span>|  
|<span data-ttu-id="de125-110">Canale</span><span class="sxs-lookup"><span data-stu-id="de125-110">Channel</span></span>|<span data-ttu-id="de125-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="de125-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="de125-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de125-112">Description</span></span>  
 <span data-ttu-id="de125-113">Questo evento contrassegna la sospensione di un'attività end-to-end</span><span class="sxs-lookup"><span data-stu-id="de125-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="de125-114">contenente il nome dell’attività.</span><span class="sxs-lookup"><span data-stu-id="de125-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="de125-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="de125-115">Message</span></span>  
 <span data-ttu-id="de125-116">Limite dell'attività.</span><span class="sxs-lookup"><span data-stu-id="de125-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="de125-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="de125-117">Details</span></span>  
  
|<span data-ttu-id="de125-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="de125-118">Data Item Name</span></span>|<span data-ttu-id="de125-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="de125-119">Data Item Type</span></span>|<span data-ttu-id="de125-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="de125-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="de125-121">Dati estesi</span><span class="sxs-lookup"><span data-stu-id="de125-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="de125-122">Nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="de125-122">The name of the activity.</span></span>|  
|<span data-ttu-id="de125-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="de125-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="de125-124">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="de125-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
