---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509769"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="37235-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="37235-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="37235-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37235-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37235-104">ID</span><span class="sxs-lookup"><span data-stu-id="37235-104">ID</span></span>|<span data-ttu-id="37235-105">1003</span><span class="sxs-lookup"><span data-stu-id="37235-105">1003</span></span>|  
|<span data-ttu-id="37235-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="37235-106">Keywords</span></span>|<span data-ttu-id="37235-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="37235-107">WFRuntime</span></span>|  
|<span data-ttu-id="37235-108">Livello</span><span class="sxs-lookup"><span data-stu-id="37235-108">Level</span></span>|<span data-ttu-id="37235-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="37235-109">Information</span></span>|  
|<span data-ttu-id="37235-110">Canale</span><span class="sxs-lookup"><span data-stu-id="37235-110">Channel</span></span>|<span data-ttu-id="37235-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="37235-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37235-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37235-112">Description</span></span>  
 <span data-ttu-id="37235-113">Indica che un'istanza del flusso di lavoro è stata completata nello stato Canceled.</span><span class="sxs-lookup"><span data-stu-id="37235-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37235-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="37235-114">Message</span></span>  
 <span data-ttu-id="37235-115">WorkflowInstance con ID: '%1' completata nello stato Canceled.</span><span class="sxs-lookup"><span data-stu-id="37235-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37235-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="37235-116">Details</span></span>  
  
|<span data-ttu-id="37235-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="37235-117">Data Item Name</span></span>|<span data-ttu-id="37235-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="37235-118">Data Item Type</span></span>|<span data-ttu-id="37235-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37235-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37235-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="37235-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="37235-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="37235-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="37235-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37235-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="37235-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="37235-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
