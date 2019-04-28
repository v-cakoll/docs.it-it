---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925229"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="95e49-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="95e49-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="95e49-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="95e49-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95e49-104">Id</span><span class="sxs-lookup"><span data-stu-id="95e49-104">ID</span></span>|<span data-ttu-id="95e49-105">1008</span><span class="sxs-lookup"><span data-stu-id="95e49-105">1008</span></span>|  
|<span data-ttu-id="95e49-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="95e49-106">Keywords</span></span>|<span data-ttu-id="95e49-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="95e49-107">WFRuntime</span></span>|  
|<span data-ttu-id="95e49-108">Livello</span><span class="sxs-lookup"><span data-stu-id="95e49-108">Level</span></span>|<span data-ttu-id="95e49-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="95e49-109">Information</span></span>|  
|<span data-ttu-id="95e49-110">Canale</span><span class="sxs-lookup"><span data-stu-id="95e49-110">Channel</span></span>|<span data-ttu-id="95e49-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="95e49-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="95e49-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95e49-112">Description</span></span>  
 <span data-ttu-id="95e49-113">Indica che un'applicazione flusso di lavoro è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="95e49-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="95e49-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="95e49-114">Message</span></span>  
 <span data-ttu-id="95e49-115">WorkflowInstance con ID: '%1' scaricata.</span><span class="sxs-lookup"><span data-stu-id="95e49-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="95e49-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="95e49-116">Details</span></span>  
  
|<span data-ttu-id="95e49-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="95e49-117">Data Item Name</span></span>|<span data-ttu-id="95e49-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="95e49-118">Data Item Type</span></span>|<span data-ttu-id="95e49-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95e49-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="95e49-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="95e49-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="95e49-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95e49-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="95e49-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="95e49-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="95e49-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="95e49-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
