---
title: 1033 - StartRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df5502c3d2cb1e9ec9454ed43c3a468a27307d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="1ff65-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="1ff65-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1ff65-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1ff65-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ff65-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ff65-104">ID</span></span>|<span data-ttu-id="1ff65-105">1040</span><span class="sxs-lookup"><span data-stu-id="1ff65-105">1033</span></span>|  
|<span data-ttu-id="1ff65-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1ff65-106">Keywords</span></span>|<span data-ttu-id="1ff65-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1ff65-107">WFRuntime</span></span>|  
|<span data-ttu-id="1ff65-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1ff65-108">Level</span></span>|<span data-ttu-id="1ff65-109">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="1ff65-109">Verbose</span></span>|  
|<span data-ttu-id="1ff65-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1ff65-110">Channel</span></span>|<span data-ttu-id="1ff65-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1ff65-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ff65-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ff65-112">Description</span></span>  
 <span data-ttu-id="1ff65-113">Indica che viene avviata l'esecuzione di RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="1ff65-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ff65-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1ff65-114">Message</span></span>  
 <span data-ttu-id="1ff65-115">Avvio dell'esecuzione di un elemento di lavoro del runtime per l'attività '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="1ff65-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ff65-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1ff65-116">Details</span></span>  
  
|<span data-ttu-id="1ff65-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1ff65-117">Data Item Name</span></span>|<span data-ttu-id="1ff65-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1ff65-118">Data Item Type</span></span>|<span data-ttu-id="1ff65-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ff65-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ff65-120">Attività</span><span class="sxs-lookup"><span data-stu-id="1ff65-120">Activity</span></span>|<span data-ttu-id="1ff65-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ff65-121">xs:string</span></span>|<span data-ttu-id="1ff65-122">Il nome del tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="1ff65-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="1ff65-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1ff65-123">DisplayName</span></span>|<span data-ttu-id="1ff65-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ff65-124">xs:string</span></span>|<span data-ttu-id="1ff65-125">Nome visualizzato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1ff65-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="1ff65-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1ff65-126">InstanceId</span></span>|<span data-ttu-id="1ff65-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ff65-127">xs:string</span></span>|<span data-ttu-id="1ff65-128">L'ID dell'istanza dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1ff65-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1ff65-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ff65-129">AppDomain</span></span>|<span data-ttu-id="1ff65-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ff65-130">xs:string</span></span>|<span data-ttu-id="1ff65-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1ff65-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
