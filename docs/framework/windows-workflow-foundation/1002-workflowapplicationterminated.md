---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54ef06c3aded628e18325b78f55e80e4470ecd01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="0d81b-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="0d81b-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="0d81b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0d81b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d81b-104">ID</span><span class="sxs-lookup"><span data-stu-id="0d81b-104">ID</span></span>|<span data-ttu-id="0d81b-105">1002</span><span class="sxs-lookup"><span data-stu-id="0d81b-105">1002</span></span>|  
|<span data-ttu-id="0d81b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0d81b-106">Keywords</span></span>|<span data-ttu-id="0d81b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0d81b-107">WFRuntime</span></span>|  
|<span data-ttu-id="0d81b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0d81b-108">Level</span></span>|<span data-ttu-id="0d81b-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="0d81b-109">Information</span></span>|  
|<span data-ttu-id="0d81b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0d81b-110">Channel</span></span>|<span data-ttu-id="0d81b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0d81b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d81b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d81b-112">Description</span></span>  
 <span data-ttu-id="0d81b-113">Indica che un'applicazione flusso di lavoro è terminata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d81b-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d81b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0d81b-114">Message</span></span>  
 <span data-ttu-id="0d81b-115">WorkflowApplication con ID: '%1' terminata.</span><span class="sxs-lookup"><span data-stu-id="0d81b-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="0d81b-116">È stata completata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d81b-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d81b-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0d81b-117">Details</span></span>  
  
|<span data-ttu-id="0d81b-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0d81b-118">Data Item Name</span></span>|<span data-ttu-id="0d81b-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0d81b-119">Data Item Type</span></span>|<span data-ttu-id="0d81b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d81b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d81b-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="0d81b-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="0d81b-122">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0d81b-122">The workflow application id</span></span>|  
|<span data-ttu-id="0d81b-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="0d81b-123">Exception</span></span>|`xs:string`|<span data-ttu-id="0d81b-124">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0d81b-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="0d81b-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0d81b-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0d81b-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0d81b-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
