---
title: 1013 - CompleteExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de9add3f537c1d8ff97c92892197598bcc7a4fe7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="8db02-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="8db02-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8db02-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8db02-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8db02-104">ID</span><span class="sxs-lookup"><span data-stu-id="8db02-104">ID</span></span>|<span data-ttu-id="8db02-105">1013</span><span class="sxs-lookup"><span data-stu-id="8db02-105">1013</span></span>|  
|<span data-ttu-id="8db02-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8db02-106">Keywords</span></span>|<span data-ttu-id="8db02-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8db02-107">WFRuntime</span></span>|  
|<span data-ttu-id="8db02-108">Livello</span><span class="sxs-lookup"><span data-stu-id="8db02-108">Level</span></span>|<span data-ttu-id="8db02-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="8db02-109">Verbose</span></span>|  
|<span data-ttu-id="8db02-110">Canale</span><span class="sxs-lookup"><span data-stu-id="8db02-110">Channel</span></span>|<span data-ttu-id="8db02-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8db02-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8db02-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db02-112">Description</span></span>  
 <span data-ttu-id="8db02-113">Indica che ExecuteActivityWorkItem è stato completato</span><span class="sxs-lookup"><span data-stu-id="8db02-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="8db02-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8db02-114">Message</span></span>  
 <span data-ttu-id="8db02-115">ExecuteActivityWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8db02-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8db02-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8db02-116">Details</span></span>  
  
|<span data-ttu-id="8db02-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="8db02-117">Data Item Name</span></span>|<span data-ttu-id="8db02-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="8db02-118">Data Item Type</span></span>|<span data-ttu-id="8db02-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8db02-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8db02-120">Attività</span><span class="sxs-lookup"><span data-stu-id="8db02-120">Activity</span></span>|<span data-ttu-id="8db02-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8db02-121">xs:string</span></span>|<span data-ttu-id="8db02-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="8db02-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8db02-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8db02-123">DisplayName</span></span>|<span data-ttu-id="8db02-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8db02-124">xs:string</span></span>|<span data-ttu-id="8db02-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8db02-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8db02-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8db02-126">InstanceId</span></span>|<span data-ttu-id="8db02-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8db02-127">xs:string</span></span>|<span data-ttu-id="8db02-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="8db02-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8db02-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8db02-129">AppDomain</span></span>|<span data-ttu-id="8db02-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8db02-130">xs:string</span></span>|<span data-ttu-id="8db02-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8db02-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
