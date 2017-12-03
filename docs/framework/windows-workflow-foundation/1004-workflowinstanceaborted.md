---
title: 1004 - WorkflowInstanceAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564e94d94dc5e3579dc4a80d734db78e90db91fb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="c3a55-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="c3a55-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="c3a55-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c3a55-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3a55-104">ID</span><span class="sxs-lookup"><span data-stu-id="c3a55-104">ID</span></span>|<span data-ttu-id="c3a55-105">1004</span><span class="sxs-lookup"><span data-stu-id="c3a55-105">1004</span></span>|  
|<span data-ttu-id="c3a55-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c3a55-106">Keywords</span></span>|<span data-ttu-id="c3a55-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c3a55-107">WFRuntime</span></span>|  
|<span data-ttu-id="c3a55-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c3a55-108">Level</span></span>|<span data-ttu-id="c3a55-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="c3a55-109">Information</span></span>|  
|<span data-ttu-id="c3a55-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c3a55-110">Channel</span></span>|<span data-ttu-id="c3a55-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c3a55-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3a55-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a55-112">Description</span></span>  
 <span data-ttu-id="c3a55-113">Indica che un'istanza di flusso di lavoro è stata interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c3a55-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3a55-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c3a55-114">Message</span></span>  
 <span data-ttu-id="c3a55-115">WorkflowInstance con ID: '%1' interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c3a55-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3a55-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c3a55-116">Details</span></span>  
  
|<span data-ttu-id="c3a55-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c3a55-117">Data Item Name</span></span>|<span data-ttu-id="c3a55-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c3a55-118">Data Item Type</span></span>|<span data-ttu-id="c3a55-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3a55-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3a55-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="c3a55-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="c3a55-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3a55-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="c3a55-122">Eccezione</span><span class="sxs-lookup"><span data-stu-id="c3a55-122">Exception</span></span>|`xs:string`|<span data-ttu-id="c3a55-123">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c3a55-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="c3a55-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c3a55-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c3a55-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c3a55-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
