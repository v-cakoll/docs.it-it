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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="fd153-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="fd153-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="fd153-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fd153-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd153-104">ID</span><span class="sxs-lookup"><span data-stu-id="fd153-104">ID</span></span>|<span data-ttu-id="fd153-105">1002</span><span class="sxs-lookup"><span data-stu-id="fd153-105">1002</span></span>|  
|<span data-ttu-id="fd153-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fd153-106">Keywords</span></span>|<span data-ttu-id="fd153-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fd153-107">WFRuntime</span></span>|  
|<span data-ttu-id="fd153-108">Livello</span><span class="sxs-lookup"><span data-stu-id="fd153-108">Level</span></span>|<span data-ttu-id="fd153-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="fd153-109">Information</span></span>|  
|<span data-ttu-id="fd153-110">Canale</span><span class="sxs-lookup"><span data-stu-id="fd153-110">Channel</span></span>|<span data-ttu-id="fd153-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fd153-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd153-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd153-112">Description</span></span>  
 <span data-ttu-id="fd153-113">Indica che un'applicazione flusso di lavoro è terminata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fd153-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd153-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fd153-114">Message</span></span>  
 <span data-ttu-id="fd153-115">WorkflowApplication con ID: '%1' terminata.</span><span class="sxs-lookup"><span data-stu-id="fd153-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="fd153-116">È stata completata nello stato Faulted con un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fd153-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd153-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fd153-117">Details</span></span>  
  
|<span data-ttu-id="fd153-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="fd153-118">Data Item Name</span></span>|<span data-ttu-id="fd153-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="fd153-119">Data Item Type</span></span>|<span data-ttu-id="fd153-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd153-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd153-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="fd153-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="fd153-122">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fd153-122">The workflow application id</span></span>|  
|<span data-ttu-id="fd153-123">Eccezione</span><span class="sxs-lookup"><span data-stu-id="fd153-123">Exception</span></span>|`xs:string`|<span data-ttu-id="fd153-124">Dettagli dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fd153-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="fd153-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd153-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fd153-126">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fd153-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
