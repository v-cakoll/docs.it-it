---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 144ab1a4a2fd313dc7817846e3e0118145cd3f8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="16329-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="16329-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="16329-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="16329-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16329-104">ID</span><span class="sxs-lookup"><span data-stu-id="16329-104">ID</span></span>|<span data-ttu-id="16329-105">3502</span><span class="sxs-lookup"><span data-stu-id="16329-105">3502</span></span>|  
|<span data-ttu-id="16329-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="16329-106">Keywords</span></span>|<span data-ttu-id="16329-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="16329-107">WFServices</span></span>|  
|<span data-ttu-id="16329-108">Livello</span><span class="sxs-lookup"><span data-stu-id="16329-108">Level</span></span>|<span data-ttu-id="16329-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="16329-109">Information</span></span>|  
|<span data-ttu-id="16329-110">Canale</span><span class="sxs-lookup"><span data-stu-id="16329-110">Channel</span></span>|<span data-ttu-id="16329-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="16329-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="16329-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16329-112">Description</span></span>  
 <span data-ttu-id="16329-113">Indica che OperationDescription è stato dedotto da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="16329-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="16329-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="16329-114">Message</span></span>  
 <span data-ttu-id="16329-115">OperationDescription con Name= '%1'' nel contratto '%2' dedotta da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="16329-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="16329-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="16329-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="16329-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="16329-117">Details</span></span>  
  
|<span data-ttu-id="16329-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="16329-118">Data Item Name</span></span>|<span data-ttu-id="16329-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="16329-119">Data Item Type</span></span>|<span data-ttu-id="16329-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16329-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="16329-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="16329-121">OperationName</span></span>|<span data-ttu-id="16329-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="16329-122">xs:string</span></span>|<span data-ttu-id="16329-123">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="16329-123">The name of the operation.</span></span>|  
|<span data-ttu-id="16329-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="16329-124">ContractName</span></span>|<span data-ttu-id="16329-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="16329-125">xs:string</span></span>|<span data-ttu-id="16329-126">Nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="16329-126">The name of the contract.</span></span>|  
|<span data-ttu-id="16329-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="16329-127">IsOneWay</span></span>|<span data-ttu-id="16329-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="16329-128">xs:string</span></span>|<span data-ttu-id="16329-129">True o False che indica se il contratto è unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="16329-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="16329-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="16329-130">AppDomain</span></span>|<span data-ttu-id="16329-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="16329-131">xs:string</span></span>|<span data-ttu-id="16329-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="16329-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
