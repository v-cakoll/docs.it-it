---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d1eaf3cf107a6b5e244cc2d9372ee68d387ef6c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510666"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="67b3e-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="67b3e-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="67b3e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="67b3e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67b3e-104">ID</span><span class="sxs-lookup"><span data-stu-id="67b3e-104">ID</span></span>|<span data-ttu-id="67b3e-105">1004</span><span class="sxs-lookup"><span data-stu-id="67b3e-105">1004</span></span>|  
|<span data-ttu-id="67b3e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="67b3e-106">Keywords</span></span>|<span data-ttu-id="67b3e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="67b3e-107">WFRuntime</span></span>|  
|<span data-ttu-id="67b3e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="67b3e-108">Level</span></span>|<span data-ttu-id="67b3e-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="67b3e-109">Information</span></span>|  
|<span data-ttu-id="67b3e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="67b3e-110">Channel</span></span>|<span data-ttu-id="67b3e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="67b3e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="67b3e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67b3e-112">Description</span></span>  
 <span data-ttu-id="67b3e-113">Indica che un'istanza di flusso di lavoro è stata interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="67b3e-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="67b3e-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="67b3e-114">Message</span></span>  
 <span data-ttu-id="67b3e-115">WorkflowInstance con ID: '%1' interrotta con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="67b3e-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="67b3e-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="67b3e-116">Details</span></span>  
  
|<span data-ttu-id="67b3e-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="67b3e-117">Data Item Name</span></span>|<span data-ttu-id="67b3e-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="67b3e-118">Data Item Type</span></span>|<span data-ttu-id="67b3e-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67b3e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="67b3e-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="67b3e-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="67b3e-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="67b3e-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="67b3e-122">Eccezione</span><span class="sxs-lookup"><span data-stu-id="67b3e-122">Exception</span></span>|`xs:string`|<span data-ttu-id="67b3e-123">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="67b3e-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="67b3e-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="67b3e-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="67b3e-125">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="67b3e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
