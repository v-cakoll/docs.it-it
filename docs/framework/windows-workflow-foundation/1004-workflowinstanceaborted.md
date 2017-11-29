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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7394ebbcb14850af89d906b0b573c4f677346825
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="4d2d4-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="4d2d4-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="4d2d4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4d2d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d2d4-104">ID</span><span class="sxs-lookup"><span data-stu-id="4d2d4-104">ID</span></span>|<span data-ttu-id="4d2d4-105">1004</span><span class="sxs-lookup"><span data-stu-id="4d2d4-105">1004</span></span>|  
|<span data-ttu-id="4d2d4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="4d2d4-106">Keywords</span></span>|<span data-ttu-id="4d2d4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4d2d4-107">WFRuntime</span></span>|  
|<span data-ttu-id="4d2d4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="4d2d4-108">Level</span></span>|<span data-ttu-id="4d2d4-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="4d2d4-109">Information</span></span>|  
|<span data-ttu-id="4d2d4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="4d2d4-110">Channel</span></span>|<span data-ttu-id="4d2d4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4d2d4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4d2d4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d2d4-112">Description</span></span>  
 <span data-ttu-id="4d2d4-113">Indica che un'istanza di flusso di lavoro è stata interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d2d4-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4d2d4-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="4d2d4-114">Message</span></span>  
 <span data-ttu-id="4d2d4-115">WorkflowInstance con ID: '%1' interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d2d4-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4d2d4-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4d2d4-116">Details</span></span>  
  
|<span data-ttu-id="4d2d4-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="4d2d4-117">Data Item Name</span></span>|<span data-ttu-id="4d2d4-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="4d2d4-118">Data Item Type</span></span>|<span data-ttu-id="4d2d4-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d2d4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4d2d4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4d2d4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="4d2d4-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4d2d4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4d2d4-122">Eccezione</span><span class="sxs-lookup"><span data-stu-id="4d2d4-122">Exception</span></span>|`xs:string`|<span data-ttu-id="4d2d4-123">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4d2d4-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="4d2d4-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4d2d4-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4d2d4-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4d2d4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
