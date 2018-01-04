---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 842d6bb6172eed5f7382633119045ea7507fb955
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="0a79f-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="0a79f-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="0a79f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0a79f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a79f-104">ID</span><span class="sxs-lookup"><span data-stu-id="0a79f-104">ID</span></span>|<span data-ttu-id="0a79f-105">1006</span><span class="sxs-lookup"><span data-stu-id="0a79f-105">1006</span></span>|  
|<span data-ttu-id="0a79f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0a79f-106">Keywords</span></span>|<span data-ttu-id="0a79f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0a79f-107">WFRuntime</span></span>|  
|<span data-ttu-id="0a79f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0a79f-108">Level</span></span>|<span data-ttu-id="0a79f-109">Errore</span><span class="sxs-lookup"><span data-stu-id="0a79f-109">Error</span></span>|  
|<span data-ttu-id="0a79f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0a79f-110">Channel</span></span>|<span data-ttu-id="0a79f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0a79f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a79f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a79f-112">Description</span></span>  
 <span data-ttu-id="0a79f-113">Indica che un'applicazione flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0a79f-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0a79f-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0a79f-114">Message</span></span>  
 <span data-ttu-id="0a79f-115">WorkflowInstance con Id: '%1' ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0a79f-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="0a79f-116">Eccezione originata dall'attività '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0a79f-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="0a79f-117">Verrà effettuata l'azione seguente: %4.</span><span class="sxs-lookup"><span data-stu-id="0a79f-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a79f-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0a79f-118">Details</span></span>  
  
|<span data-ttu-id="0a79f-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0a79f-119">Data Item Name</span></span>|<span data-ttu-id="0a79f-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0a79f-120">Data Item Type</span></span>|<span data-ttu-id="0a79f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a79f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0a79f-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0a79f-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0a79f-123">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0a79f-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="0a79f-124">Eccezione</span><span class="sxs-lookup"><span data-stu-id="0a79f-124">Exception</span></span>|`xs:string`|<span data-ttu-id="0a79f-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0a79f-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="0a79f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0a79f-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0a79f-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0a79f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
