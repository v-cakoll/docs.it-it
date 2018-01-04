---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26491c1e2b20f4285aaedbcd12947cad3562f041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="3a505-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="3a505-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="3a505-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3a505-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a505-104">ID</span><span class="sxs-lookup"><span data-stu-id="3a505-104">ID</span></span>|<span data-ttu-id="3a505-105">1008</span><span class="sxs-lookup"><span data-stu-id="3a505-105">1008</span></span>|  
|<span data-ttu-id="3a505-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3a505-106">Keywords</span></span>|<span data-ttu-id="3a505-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3a505-107">WFRuntime</span></span>|  
|<span data-ttu-id="3a505-108">Livello</span><span class="sxs-lookup"><span data-stu-id="3a505-108">Level</span></span>|<span data-ttu-id="3a505-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="3a505-109">Information</span></span>|  
|<span data-ttu-id="3a505-110">Canale</span><span class="sxs-lookup"><span data-stu-id="3a505-110">Channel</span></span>|<span data-ttu-id="3a505-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3a505-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3a505-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a505-112">Description</span></span>  
 <span data-ttu-id="3a505-113">Indica che un'applicazione flusso di lavoro è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="3a505-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3a505-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="3a505-114">Message</span></span>  
 <span data-ttu-id="3a505-115">WorkflowInstance con ID: '%1' scaricata.</span><span class="sxs-lookup"><span data-stu-id="3a505-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3a505-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3a505-116">Details</span></span>  
  
|<span data-ttu-id="3a505-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="3a505-117">Data Item Name</span></span>|<span data-ttu-id="3a505-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="3a505-118">Data Item Type</span></span>|<span data-ttu-id="3a505-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a505-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3a505-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="3a505-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="3a505-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3a505-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3a505-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3a505-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3a505-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3a505-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
