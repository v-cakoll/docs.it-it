---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f06e6cccd9c4ca2907b86372f609f8c72b5e189
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="b59ef-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="b59ef-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="b59ef-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b59ef-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b59ef-104">ID</span><span class="sxs-lookup"><span data-stu-id="b59ef-104">ID</span></span>|<span data-ttu-id="b59ef-105">3507</span><span class="sxs-lookup"><span data-stu-id="b59ef-105">3507</span></span>|  
|<span data-ttu-id="b59ef-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b59ef-106">Keywords</span></span>|<span data-ttu-id="b59ef-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b59ef-107">WFServices</span></span>|  
|<span data-ttu-id="b59ef-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b59ef-108">Level</span></span>|<span data-ttu-id="b59ef-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="b59ef-109">Information</span></span>|  
|<span data-ttu-id="b59ef-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b59ef-110">Channel</span></span>|<span data-ttu-id="b59ef-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b59ef-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b59ef-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b59ef-112">Description</span></span>  
 <span data-ttu-id="b59ef-113">Indica che un endpoint del servizio è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="b59ef-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b59ef-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b59ef-114">Message</span></span>  
 <span data-ttu-id="b59ef-115">È stato aggiunto un endpoint del servizio per l'indirizzo '%1', binding '%2' e contratto '%3'.</span><span class="sxs-lookup"><span data-stu-id="b59ef-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b59ef-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b59ef-116">Details</span></span>  
  
|<span data-ttu-id="b59ef-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b59ef-117">Data Item Name</span></span>|<span data-ttu-id="b59ef-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b59ef-118">Data Item Type</span></span>|<span data-ttu-id="b59ef-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b59ef-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b59ef-120">Address</span><span class="sxs-lookup"><span data-stu-id="b59ef-120">Address</span></span>|<span data-ttu-id="b59ef-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b59ef-121">xs:string</span></span>|<span data-ttu-id="b59ef-122">L'indirizzo dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b59ef-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="b59ef-123">Binding</span><span class="sxs-lookup"><span data-stu-id="b59ef-123">Binding</span></span>|<span data-ttu-id="b59ef-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b59ef-124">xs:string</span></span>|<span data-ttu-id="b59ef-125">L'associazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b59ef-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="b59ef-126">Contratto</span><span class="sxs-lookup"><span data-stu-id="b59ef-126">Contract</span></span>|<span data-ttu-id="b59ef-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b59ef-127">xs:string</span></span>|<span data-ttu-id="b59ef-128">Il contratto dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b59ef-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="b59ef-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b59ef-129">AppDomain</span></span>|<span data-ttu-id="b59ef-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b59ef-130">xs:string</span></span>|<span data-ttu-id="b59ef-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b59ef-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
