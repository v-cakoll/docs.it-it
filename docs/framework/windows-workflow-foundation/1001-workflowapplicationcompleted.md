---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509795"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="2e6c4-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="2e6c4-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="2e6c4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2e6c4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e6c4-104">ID</span><span class="sxs-lookup"><span data-stu-id="2e6c4-104">ID</span></span>|<span data-ttu-id="2e6c4-105">1001</span><span class="sxs-lookup"><span data-stu-id="2e6c4-105">1001</span></span>|  
|<span data-ttu-id="2e6c4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2e6c4-106">Keywords</span></span>|<span data-ttu-id="2e6c4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2e6c4-107">WFRuntime</span></span>|  
|<span data-ttu-id="2e6c4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2e6c4-108">Level</span></span>|<span data-ttu-id="2e6c4-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2e6c4-109">Information</span></span>|  
|<span data-ttu-id="2e6c4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2e6c4-110">Channel</span></span>|<span data-ttu-id="2e6c4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2e6c4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2e6c4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e6c4-112">Description</span></span>  
 <span data-ttu-id="2e6c4-113">Indica che un'applicazione flusso di lavoro è stata completata nello stato Closed.</span><span class="sxs-lookup"><span data-stu-id="2e6c4-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2e6c4-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2e6c4-114">Message</span></span>  
 <span data-ttu-id="2e6c4-115">WorkflowInstance con ID: '%1' completata nello stato Closed.</span><span class="sxs-lookup"><span data-stu-id="2e6c4-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2e6c4-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2e6c4-116">Details</span></span>  
  
|<span data-ttu-id="2e6c4-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2e6c4-117">Data Item Name</span></span>|<span data-ttu-id="2e6c4-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2e6c4-118">Data Item Type</span></span>|<span data-ttu-id="2e6c4-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e6c4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2e6c4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2e6c4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2e6c4-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2e6c4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="2e6c4-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2e6c4-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2e6c4-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2e6c4-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
