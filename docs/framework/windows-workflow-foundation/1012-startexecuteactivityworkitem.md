---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a3b03e8ac24bc1652b88b71e8c25862a07c194f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="b0698-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b0698-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b0698-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b0698-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0698-104">ID</span><span class="sxs-lookup"><span data-stu-id="b0698-104">ID</span></span>|<span data-ttu-id="b0698-105">1012</span><span class="sxs-lookup"><span data-stu-id="b0698-105">1012</span></span>|  
|<span data-ttu-id="b0698-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b0698-106">Keywords</span></span>|<span data-ttu-id="b0698-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b0698-107">WFRuntime</span></span>|  
|<span data-ttu-id="b0698-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b0698-108">Level</span></span>|<span data-ttu-id="b0698-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="b0698-109">Verbose</span></span>|  
|<span data-ttu-id="b0698-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b0698-110">Channel</span></span>|<span data-ttu-id="b0698-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b0698-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b0698-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0698-112">Description</span></span>  
 <span data-ttu-id="b0698-113">Indica che viene avviata l'esecuzione di ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="b0698-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b0698-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b0698-114">Message</span></span>  
 <span data-ttu-id="b0698-115">Avvio dell'esecuzione di ExecuteActivityWorkItem per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b0698-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b0698-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b0698-116">Details</span></span>  
  
|<span data-ttu-id="b0698-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b0698-117">Data Item Name</span></span>|<span data-ttu-id="b0698-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b0698-118">Data Item Type</span></span>|<span data-ttu-id="b0698-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0698-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b0698-120">Attività</span><span class="sxs-lookup"><span data-stu-id="b0698-120">Activity</span></span>|<span data-ttu-id="b0698-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b0698-121">xs:string</span></span>|<span data-ttu-id="b0698-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="b0698-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b0698-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b0698-123">DisplayName</span></span>|<span data-ttu-id="b0698-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b0698-124">xs:string</span></span>|<span data-ttu-id="b0698-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b0698-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b0698-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b0698-126">InstanceId</span></span>|<span data-ttu-id="b0698-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b0698-127">xs:string</span></span>|<span data-ttu-id="b0698-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b0698-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b0698-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b0698-129">AppDomain</span></span>|<span data-ttu-id="b0698-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b0698-130">xs:string</span></span>|<span data-ttu-id="b0698-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b0698-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
