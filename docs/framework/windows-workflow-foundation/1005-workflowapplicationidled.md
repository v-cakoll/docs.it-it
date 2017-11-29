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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42d22a7187adc712c0f236111cecac89dd59e2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="f475c-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="f475c-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="f475c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f475c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f475c-104">ID</span><span class="sxs-lookup"><span data-stu-id="f475c-104">ID</span></span>|<span data-ttu-id="f475c-105">1005</span><span class="sxs-lookup"><span data-stu-id="f475c-105">1005</span></span>|  
|<span data-ttu-id="f475c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f475c-106">Keywords</span></span>|<span data-ttu-id="f475c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f475c-107">WFRuntime</span></span>|  
|<span data-ttu-id="f475c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f475c-108">Level</span></span>|<span data-ttu-id="f475c-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="f475c-109">Information</span></span>|  
|<span data-ttu-id="f475c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f475c-110">Channel</span></span>|<span data-ttu-id="f475c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f475c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f475c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f475c-112">Description</span></span>  
 <span data-ttu-id="f475c-113">Indica che un'applicazione flusso di lavoro è diventata inattiva.</span><span class="sxs-lookup"><span data-stu-id="f475c-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f475c-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f475c-114">Message</span></span>  
 <span data-ttu-id="f475c-115">WorkflowApplication con ID: '%1' inattiva.</span><span class="sxs-lookup"><span data-stu-id="f475c-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f475c-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f475c-116">Details</span></span>  
  
|<span data-ttu-id="f475c-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f475c-117">Data Item Name</span></span>|<span data-ttu-id="f475c-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f475c-118">Data Item Type</span></span>|<span data-ttu-id="f475c-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f475c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f475c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f475c-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f475c-121">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f475c-121">The workflow application id</span></span>|  
|<span data-ttu-id="f475c-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f475c-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f475c-123">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f475c-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
