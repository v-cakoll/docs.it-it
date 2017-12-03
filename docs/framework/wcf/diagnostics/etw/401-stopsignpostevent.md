---
title: 401- StopSignPostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30e796dec45035e6b68659400ebbae1357137b27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="f766d-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="f766d-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="f766d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f766d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f766d-104">ID</span><span class="sxs-lookup"><span data-stu-id="f766d-104">ID</span></span>|<span data-ttu-id="f766d-105">401</span><span class="sxs-lookup"><span data-stu-id="f766d-105">401</span></span>|  
|<span data-ttu-id="f766d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f766d-106">Keywords</span></span>|<span data-ttu-id="f766d-107">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f766d-107">Troubleshooting</span></span>|  
|<span data-ttu-id="f766d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f766d-108">Level</span></span>|<span data-ttu-id="f766d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="f766d-109">Information</span></span>|  
|<span data-ttu-id="f766d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f766d-110">Channel</span></span>|<span data-ttu-id="f766d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f766d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f766d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f766d-112">Description</span></span>  
 <span data-ttu-id="f766d-113">Questo evento contrassegna la fine di un'attività end-to-end</span><span class="sxs-lookup"><span data-stu-id="f766d-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="f766d-114">contenente il nome dell’attività.</span><span class="sxs-lookup"><span data-stu-id="f766d-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f766d-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f766d-115">Message</span></span>  
 <span data-ttu-id="f766d-116">Limite dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f766d-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f766d-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f766d-117">Details</span></span>  
  
|<span data-ttu-id="f766d-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f766d-118">Data Item Name</span></span>|<span data-ttu-id="f766d-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f766d-119">Data Item Type</span></span>|<span data-ttu-id="f766d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f766d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f766d-121">Dati estesi</span><span class="sxs-lookup"><span data-stu-id="f766d-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="f766d-122">Nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="f766d-122">The name of the activity.</span></span>|  
|<span data-ttu-id="f766d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f766d-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f766d-124">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f766d-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
