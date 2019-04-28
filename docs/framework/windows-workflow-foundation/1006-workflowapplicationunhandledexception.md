---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924709"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="41d2a-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="41d2a-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="41d2a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="41d2a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="41d2a-104">Id</span><span class="sxs-lookup"><span data-stu-id="41d2a-104">ID</span></span>|<span data-ttu-id="41d2a-105">1006</span><span class="sxs-lookup"><span data-stu-id="41d2a-105">1006</span></span>|  
|<span data-ttu-id="41d2a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="41d2a-106">Keywords</span></span>|<span data-ttu-id="41d2a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="41d2a-107">WFRuntime</span></span>|  
|<span data-ttu-id="41d2a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="41d2a-108">Level</span></span>|<span data-ttu-id="41d2a-109">Error</span><span class="sxs-lookup"><span data-stu-id="41d2a-109">Error</span></span>|  
|<span data-ttu-id="41d2a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="41d2a-110">Channel</span></span>|<span data-ttu-id="41d2a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="41d2a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="41d2a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41d2a-112">Description</span></span>  
 <span data-ttu-id="41d2a-113">Indica che un'applicazione flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="41d2a-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="41d2a-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="41d2a-114">Message</span></span>  
 <span data-ttu-id="41d2a-115">WorkflowInstance con Id: '%1' ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="41d2a-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="41d2a-116">Eccezione originata dall'attività '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="41d2a-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="41d2a-117">Le seguenti azioni vengono intraprese: %4.</span><span class="sxs-lookup"><span data-stu-id="41d2a-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="41d2a-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="41d2a-118">Details</span></span>  
  
|<span data-ttu-id="41d2a-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="41d2a-119">Data Item Name</span></span>|<span data-ttu-id="41d2a-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="41d2a-120">Data Item Type</span></span>|<span data-ttu-id="41d2a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41d2a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="41d2a-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="41d2a-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="41d2a-123">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="41d2a-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="41d2a-124">Eccezione</span><span class="sxs-lookup"><span data-stu-id="41d2a-124">Exception</span></span>|`xs:string`|<span data-ttu-id="41d2a-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="41d2a-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="41d2a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="41d2a-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="41d2a-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="41d2a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
