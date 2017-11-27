---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a62a8448319e7b07a3ea302f00f2fa269bf654ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="518bb-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="518bb-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="518bb-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="518bb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="518bb-104">ID</span><span class="sxs-lookup"><span data-stu-id="518bb-104">ID</span></span>|<span data-ttu-id="518bb-105">1001</span><span class="sxs-lookup"><span data-stu-id="518bb-105">1001</span></span>|  
|<span data-ttu-id="518bb-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="518bb-106">Keywords</span></span>|<span data-ttu-id="518bb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="518bb-107">WFRuntime</span></span>|  
|<span data-ttu-id="518bb-108">Livello</span><span class="sxs-lookup"><span data-stu-id="518bb-108">Level</span></span>|<span data-ttu-id="518bb-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="518bb-109">Information</span></span>|  
|<span data-ttu-id="518bb-110">Canale</span><span class="sxs-lookup"><span data-stu-id="518bb-110">Channel</span></span>|<span data-ttu-id="518bb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="518bb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="518bb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="518bb-112">Description</span></span>  
 <span data-ttu-id="518bb-113">Indica che un'applicazione flusso di lavoro è stata completata nello stato Closed.</span><span class="sxs-lookup"><span data-stu-id="518bb-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="518bb-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="518bb-114">Message</span></span>  
 <span data-ttu-id="518bb-115">WorkflowInstance con ID: '%1' completata nello stato Closed.</span><span class="sxs-lookup"><span data-stu-id="518bb-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="518bb-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="518bb-116">Details</span></span>  
  
|<span data-ttu-id="518bb-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="518bb-117">Data Item Name</span></span>|<span data-ttu-id="518bb-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="518bb-118">Data Item Type</span></span>|<span data-ttu-id="518bb-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="518bb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="518bb-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="518bb-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="518bb-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="518bb-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="518bb-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="518bb-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="518bb-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="518bb-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
