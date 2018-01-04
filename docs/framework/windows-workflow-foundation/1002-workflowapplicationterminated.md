---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3f025be90a997839eec2edfea12a099b4c58f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="1bae6-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="1bae6-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="1bae6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1bae6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1bae6-104">ID</span><span class="sxs-lookup"><span data-stu-id="1bae6-104">ID</span></span>|<span data-ttu-id="1bae6-105">1002</span><span class="sxs-lookup"><span data-stu-id="1bae6-105">1002</span></span>|  
|<span data-ttu-id="1bae6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1bae6-106">Keywords</span></span>|<span data-ttu-id="1bae6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1bae6-107">WFRuntime</span></span>|  
|<span data-ttu-id="1bae6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1bae6-108">Level</span></span>|<span data-ttu-id="1bae6-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="1bae6-109">Information</span></span>|  
|<span data-ttu-id="1bae6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1bae6-110">Channel</span></span>|<span data-ttu-id="1bae6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1bae6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1bae6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bae6-112">Description</span></span>  
 <span data-ttu-id="1bae6-113">Indica che un'applicazione flusso di lavoro è terminata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1bae6-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1bae6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1bae6-114">Message</span></span>  
 <span data-ttu-id="1bae6-115">WorkflowApplication con ID: '%1' terminata.</span><span class="sxs-lookup"><span data-stu-id="1bae6-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="1bae6-116">È stata completata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1bae6-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1bae6-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1bae6-117">Details</span></span>  
  
|<span data-ttu-id="1bae6-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1bae6-118">Data Item Name</span></span>|<span data-ttu-id="1bae6-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1bae6-119">Data Item Type</span></span>|<span data-ttu-id="1bae6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bae6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1bae6-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="1bae6-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="1bae6-122">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1bae6-122">The workflow application id</span></span>|  
|<span data-ttu-id="1bae6-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="1bae6-123">Exception</span></span>|`xs:string`|<span data-ttu-id="1bae6-124">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1bae6-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="1bae6-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1bae6-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1bae6-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1bae6-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
