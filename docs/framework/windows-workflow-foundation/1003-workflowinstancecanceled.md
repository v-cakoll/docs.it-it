---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008629"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="90dc6-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="90dc6-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="90dc6-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="90dc6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90dc6-104">Id</span><span class="sxs-lookup"><span data-stu-id="90dc6-104">ID</span></span>|<span data-ttu-id="90dc6-105">1003</span><span class="sxs-lookup"><span data-stu-id="90dc6-105">1003</span></span>|  
|<span data-ttu-id="90dc6-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="90dc6-106">Keywords</span></span>|<span data-ttu-id="90dc6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="90dc6-107">WFRuntime</span></span>|  
|<span data-ttu-id="90dc6-108">Livello</span><span class="sxs-lookup"><span data-stu-id="90dc6-108">Level</span></span>|<span data-ttu-id="90dc6-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="90dc6-109">Information</span></span>|  
|<span data-ttu-id="90dc6-110">Canale</span><span class="sxs-lookup"><span data-stu-id="90dc6-110">Channel</span></span>|<span data-ttu-id="90dc6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="90dc6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="90dc6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90dc6-112">Description</span></span>  
 <span data-ttu-id="90dc6-113">Indica che un'istanza del flusso di lavoro è stata completata nello stato Canceled.</span><span class="sxs-lookup"><span data-stu-id="90dc6-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="90dc6-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="90dc6-114">Message</span></span>  
 <span data-ttu-id="90dc6-115">WorkflowInstance con ID: '%1' completata nello stato Canceled.</span><span class="sxs-lookup"><span data-stu-id="90dc6-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="90dc6-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="90dc6-116">Details</span></span>  
  
|<span data-ttu-id="90dc6-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="90dc6-117">Data Item Name</span></span>|<span data-ttu-id="90dc6-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="90dc6-118">Data Item Type</span></span>|<span data-ttu-id="90dc6-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90dc6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="90dc6-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="90dc6-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="90dc6-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="90dc6-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="90dc6-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="90dc6-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="90dc6-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="90dc6-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
