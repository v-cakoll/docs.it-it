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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 297b3ad9a677d28d12d1b00fdaeec8ec94842263
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="6bf28-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="6bf28-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="6bf28-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6bf28-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6bf28-104">ID</span><span class="sxs-lookup"><span data-stu-id="6bf28-104">ID</span></span>|<span data-ttu-id="6bf28-105">1008</span><span class="sxs-lookup"><span data-stu-id="6bf28-105">1008</span></span>|  
|<span data-ttu-id="6bf28-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6bf28-106">Keywords</span></span>|<span data-ttu-id="6bf28-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6bf28-107">WFRuntime</span></span>|  
|<span data-ttu-id="6bf28-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6bf28-108">Level</span></span>|<span data-ttu-id="6bf28-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6bf28-109">Information</span></span>|  
|<span data-ttu-id="6bf28-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6bf28-110">Channel</span></span>|<span data-ttu-id="6bf28-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6bf28-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6bf28-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bf28-112">Description</span></span>  
 <span data-ttu-id="6bf28-113">Indica che un'applicazione flusso di lavoro è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="6bf28-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6bf28-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6bf28-114">Message</span></span>  
 <span data-ttu-id="6bf28-115">WorkflowInstance con ID: '%1' scaricata.</span><span class="sxs-lookup"><span data-stu-id="6bf28-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6bf28-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6bf28-116">Details</span></span>  
  
|<span data-ttu-id="6bf28-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6bf28-117">Data Item Name</span></span>|<span data-ttu-id="6bf28-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6bf28-118">Data Item Type</span></span>|<span data-ttu-id="6bf28-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bf28-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6bf28-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="6bf28-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="6bf28-121">ID istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6bf28-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="6bf28-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6bf28-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6bf28-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6bf28-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
