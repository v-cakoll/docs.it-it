---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510757"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="a09b8-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="a09b8-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="a09b8-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a09b8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a09b8-104">ID</span><span class="sxs-lookup"><span data-stu-id="a09b8-104">ID</span></span>|<span data-ttu-id="a09b8-105">1006</span><span class="sxs-lookup"><span data-stu-id="a09b8-105">1006</span></span>|  
|<span data-ttu-id="a09b8-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a09b8-106">Keywords</span></span>|<span data-ttu-id="a09b8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a09b8-107">WFRuntime</span></span>|  
|<span data-ttu-id="a09b8-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a09b8-108">Level</span></span>|<span data-ttu-id="a09b8-109">Errore</span><span class="sxs-lookup"><span data-stu-id="a09b8-109">Error</span></span>|  
|<span data-ttu-id="a09b8-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a09b8-110">Channel</span></span>|<span data-ttu-id="a09b8-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a09b8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a09b8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a09b8-112">Description</span></span>  
 <span data-ttu-id="a09b8-113">Indica che un'applicazione flusso di lavoro ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="a09b8-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a09b8-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a09b8-114">Message</span></span>  
 <span data-ttu-id="a09b8-115">WorkflowInstance con Id: '%1' ha rilevato un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="a09b8-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="a09b8-116">Eccezione originata dall'attività '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="a09b8-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="a09b8-117">Verrà effettuata l'azione seguente: %4.</span><span class="sxs-lookup"><span data-stu-id="a09b8-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a09b8-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a09b8-118">Details</span></span>  
  
|<span data-ttu-id="a09b8-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a09b8-119">Data Item Name</span></span>|<span data-ttu-id="a09b8-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a09b8-120">Data Item Type</span></span>|<span data-ttu-id="a09b8-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a09b8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a09b8-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a09b8-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a09b8-123">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a09b8-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a09b8-124">Eccezione</span><span class="sxs-lookup"><span data-stu-id="a09b8-124">Exception</span></span>|`xs:string`|<span data-ttu-id="a09b8-125">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="a09b8-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="a09b8-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a09b8-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a09b8-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a09b8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
