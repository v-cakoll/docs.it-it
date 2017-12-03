---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2603621eb23747275e6db22a1743c5260967c6a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="6bbb0-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="6bbb0-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="6bbb0-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6bbb0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6bbb0-104">ID</span><span class="sxs-lookup"><span data-stu-id="6bbb0-104">ID</span></span>|<span data-ttu-id="6bbb0-105">1005</span><span class="sxs-lookup"><span data-stu-id="6bbb0-105">1005</span></span>|  
|<span data-ttu-id="6bbb0-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6bbb0-106">Keywords</span></span>|<span data-ttu-id="6bbb0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6bbb0-107">WFRuntime</span></span>|  
|<span data-ttu-id="6bbb0-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6bbb0-108">Level</span></span>|<span data-ttu-id="6bbb0-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6bbb0-109">Information</span></span>|  
|<span data-ttu-id="6bbb0-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6bbb0-110">Channel</span></span>|<span data-ttu-id="6bbb0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6bbb0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6bbb0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbb0-112">Description</span></span>  
 <span data-ttu-id="6bbb0-113">Indica che un'applicazione flusso di lavoro è diventata inattiva.</span><span class="sxs-lookup"><span data-stu-id="6bbb0-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6bbb0-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6bbb0-114">Message</span></span>  
 <span data-ttu-id="6bbb0-115">WorkflowApplication con ID: '%1' inattiva.</span><span class="sxs-lookup"><span data-stu-id="6bbb0-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6bbb0-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6bbb0-116">Details</span></span>  
  
|<span data-ttu-id="6bbb0-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6bbb0-117">Data Item Name</span></span>|<span data-ttu-id="6bbb0-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6bbb0-118">Data Item Type</span></span>|<span data-ttu-id="6bbb0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbb0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6bbb0-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="6bbb0-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="6bbb0-121">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6bbb0-121">The workflow application id</span></span>|  
|<span data-ttu-id="6bbb0-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6bbb0-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6bbb0-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6bbb0-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
