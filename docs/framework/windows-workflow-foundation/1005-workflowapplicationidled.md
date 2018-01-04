---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc9f8f72000fe283baa5bb2814e41051c1424983
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="fb2d3-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="fb2d3-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="fb2d3-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fb2d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb2d3-104">ID</span><span class="sxs-lookup"><span data-stu-id="fb2d3-104">ID</span></span>|<span data-ttu-id="fb2d3-105">1005</span><span class="sxs-lookup"><span data-stu-id="fb2d3-105">1005</span></span>|  
|<span data-ttu-id="fb2d3-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fb2d3-106">Keywords</span></span>|<span data-ttu-id="fb2d3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fb2d3-107">WFRuntime</span></span>|  
|<span data-ttu-id="fb2d3-108">Livello</span><span class="sxs-lookup"><span data-stu-id="fb2d3-108">Level</span></span>|<span data-ttu-id="fb2d3-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="fb2d3-109">Information</span></span>|  
|<span data-ttu-id="fb2d3-110">Canale</span><span class="sxs-lookup"><span data-stu-id="fb2d3-110">Channel</span></span>|<span data-ttu-id="fb2d3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fb2d3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fb2d3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb2d3-112">Description</span></span>  
 <span data-ttu-id="fb2d3-113">Indica che un'applicazione flusso di lavoro è diventata inattiva.</span><span class="sxs-lookup"><span data-stu-id="fb2d3-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fb2d3-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fb2d3-114">Message</span></span>  
 <span data-ttu-id="fb2d3-115">WorkflowApplication con ID: '%1' inattiva.</span><span class="sxs-lookup"><span data-stu-id="fb2d3-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fb2d3-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fb2d3-116">Details</span></span>  
  
|<span data-ttu-id="fb2d3-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="fb2d3-117">Data Item Name</span></span>|<span data-ttu-id="fb2d3-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="fb2d3-118">Data Item Type</span></span>|<span data-ttu-id="fb2d3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb2d3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fb2d3-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fb2d3-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="fb2d3-121">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fb2d3-121">The workflow application id</span></span>|  
|<span data-ttu-id="fb2d3-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fb2d3-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fb2d3-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fb2d3-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
