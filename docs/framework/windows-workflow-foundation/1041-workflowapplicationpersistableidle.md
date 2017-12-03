---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="ed6f2-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="ed6f2-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="ed6f2-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ed6f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed6f2-104">ID</span><span class="sxs-lookup"><span data-stu-id="ed6f2-104">ID</span></span>|<span data-ttu-id="ed6f2-105">1041</span><span class="sxs-lookup"><span data-stu-id="ed6f2-105">1041</span></span>|  
|<span data-ttu-id="ed6f2-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ed6f2-106">Keywords</span></span>|<span data-ttu-id="ed6f2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ed6f2-107">WFRuntime</span></span>|  
|<span data-ttu-id="ed6f2-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ed6f2-108">Level</span></span>|<span data-ttu-id="ed6f2-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="ed6f2-109">Information</span></span>|  
|<span data-ttu-id="ed6f2-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ed6f2-110">Channel</span></span>|<span data-ttu-id="ed6f2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ed6f2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ed6f2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed6f2-112">Description</span></span>  
 <span data-ttu-id="ed6f2-113">Indica che un'applicazione flusso di lavoro è inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="ed6f2-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="ed6f2-114">L'applicazione flusso di lavoro verrà resa inattiva o persistente.</span><span class="sxs-lookup"><span data-stu-id="ed6f2-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ed6f2-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ed6f2-115">Message</span></span>  
 <span data-ttu-id="ed6f2-116">Workflowapplication con Id: '%1' è inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="ed6f2-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="ed6f2-117">Verrà effettuata l'azione seguente: %2.</span><span class="sxs-lookup"><span data-stu-id="ed6f2-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ed6f2-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ed6f2-118">Details</span></span>  
  
|<span data-ttu-id="ed6f2-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ed6f2-119">Data Item Name</span></span>|<span data-ttu-id="ed6f2-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ed6f2-120">Data Item Type</span></span>|<span data-ttu-id="ed6f2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed6f2-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ed6f2-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="ed6f2-122">WorkflowApplicationId</span></span>|<span data-ttu-id="ed6f2-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed6f2-123">xs:string</span></span>|<span data-ttu-id="ed6f2-124">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="ed6f2-124">The workflow application id</span></span>|  
|<span data-ttu-id="ed6f2-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="ed6f2-125">ActionTaken</span></span>|<span data-ttu-id="ed6f2-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed6f2-126">xs:string</span></span>|<span data-ttu-id="ed6f2-127">L'azione che verrà intrapresa sull'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ed6f2-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="ed6f2-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ed6f2-128">AppDomain</span></span>|<span data-ttu-id="ed6f2-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed6f2-129">xs:string</span></span>|<span data-ttu-id="ed6f2-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ed6f2-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
