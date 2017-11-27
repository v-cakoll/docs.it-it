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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f430e7b58d5aba277b0a35a20f1f5fdb707bce9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="bb282-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="bb282-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bb282-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bb282-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb282-104">ID</span><span class="sxs-lookup"><span data-stu-id="bb282-104">ID</span></span>|<span data-ttu-id="bb282-105">1013</span><span class="sxs-lookup"><span data-stu-id="bb282-105">1013</span></span>|  
|<span data-ttu-id="bb282-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="bb282-106">Keywords</span></span>|<span data-ttu-id="bb282-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bb282-107">WFRuntime</span></span>|  
|<span data-ttu-id="bb282-108">Livello</span><span class="sxs-lookup"><span data-stu-id="bb282-108">Level</span></span>|<span data-ttu-id="bb282-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="bb282-109">Verbose</span></span>|  
|<span data-ttu-id="bb282-110">Canale</span><span class="sxs-lookup"><span data-stu-id="bb282-110">Channel</span></span>|<span data-ttu-id="bb282-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bb282-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bb282-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb282-112">Description</span></span>  
 <span data-ttu-id="bb282-113">Indica che ExecuteActivityWorkItem è stato completato</span><span class="sxs-lookup"><span data-stu-id="bb282-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="bb282-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="bb282-114">Message</span></span>  
 <span data-ttu-id="bb282-115">ExecuteActivityWorkItem completato per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="bb282-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bb282-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bb282-116">Details</span></span>  
  
|<span data-ttu-id="bb282-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="bb282-117">Data Item Name</span></span>|<span data-ttu-id="bb282-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="bb282-118">Data Item Type</span></span>|<span data-ttu-id="bb282-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb282-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bb282-120">Attività</span><span class="sxs-lookup"><span data-stu-id="bb282-120">Activity</span></span>|<span data-ttu-id="bb282-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb282-121">xs:string</span></span>|<span data-ttu-id="bb282-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="bb282-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bb282-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bb282-123">DisplayName</span></span>|<span data-ttu-id="bb282-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb282-124">xs:string</span></span>|<span data-ttu-id="bb282-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="bb282-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bb282-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bb282-126">InstanceId</span></span>|<span data-ttu-id="bb282-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb282-127">xs:string</span></span>|<span data-ttu-id="bb282-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="bb282-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bb282-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bb282-129">AppDomain</span></span>|<span data-ttu-id="bb282-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bb282-130">xs:string</span></span>|<span data-ttu-id="bb282-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bb282-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
