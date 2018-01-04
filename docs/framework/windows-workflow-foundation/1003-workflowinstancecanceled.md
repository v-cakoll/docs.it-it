---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b264450703090edfcf99f9584c16d33eb82a76e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="cf54d-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="cf54d-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="cf54d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cf54d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf54d-104">ID</span><span class="sxs-lookup"><span data-stu-id="cf54d-104">ID</span></span>|<span data-ttu-id="cf54d-105">1003</span><span class="sxs-lookup"><span data-stu-id="cf54d-105">1003</span></span>|  
|<span data-ttu-id="cf54d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cf54d-106">Keywords</span></span>|<span data-ttu-id="cf54d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cf54d-107">WFRuntime</span></span>|  
|<span data-ttu-id="cf54d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="cf54d-108">Level</span></span>|<span data-ttu-id="cf54d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="cf54d-109">Information</span></span>|  
|<span data-ttu-id="cf54d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="cf54d-110">Channel</span></span>|<span data-ttu-id="cf54d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cf54d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cf54d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf54d-112">Description</span></span>  
 <span data-ttu-id="cf54d-113">Indica che un'istanza del flusso di lavoro è stata completata nello stato Canceled.</span><span class="sxs-lookup"><span data-stu-id="cf54d-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cf54d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="cf54d-114">Message</span></span>  
 <span data-ttu-id="cf54d-115">WorkflowInstance con ID: '%1' completata nello stato Canceled.</span><span class="sxs-lookup"><span data-stu-id="cf54d-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cf54d-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cf54d-116">Details</span></span>  
  
|<span data-ttu-id="cf54d-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="cf54d-117">Data Item Name</span></span>|<span data-ttu-id="cf54d-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="cf54d-118">Data Item Type</span></span>|<span data-ttu-id="cf54d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf54d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cf54d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="cf54d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="cf54d-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cf54d-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="cf54d-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cf54d-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cf54d-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cf54d-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
