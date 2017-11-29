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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 044d67bc2b721451ade04947484899266d288d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="185f5-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="185f5-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="185f5-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="185f5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="185f5-104">ID</span><span class="sxs-lookup"><span data-stu-id="185f5-104">ID</span></span>|<span data-ttu-id="185f5-105">3502</span><span class="sxs-lookup"><span data-stu-id="185f5-105">3502</span></span>|  
|<span data-ttu-id="185f5-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="185f5-106">Keywords</span></span>|<span data-ttu-id="185f5-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="185f5-107">WFServices</span></span>|  
|<span data-ttu-id="185f5-108">Livello</span><span class="sxs-lookup"><span data-stu-id="185f5-108">Level</span></span>|<span data-ttu-id="185f5-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="185f5-109">Information</span></span>|  
|<span data-ttu-id="185f5-110">Canale</span><span class="sxs-lookup"><span data-stu-id="185f5-110">Channel</span></span>|<span data-ttu-id="185f5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="185f5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="185f5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="185f5-112">Description</span></span>  
 <span data-ttu-id="185f5-113">Indica che OperationDescription è stato dedotto da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="185f5-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="185f5-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="185f5-114">Message</span></span>  
 <span data-ttu-id="185f5-115">OperationDescription con Name= '%1'' nel contratto '%2' dedotta da WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="185f5-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="185f5-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="185f5-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="185f5-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="185f5-117">Details</span></span>  
  
|<span data-ttu-id="185f5-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="185f5-118">Data Item Name</span></span>|<span data-ttu-id="185f5-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="185f5-119">Data Item Type</span></span>|<span data-ttu-id="185f5-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="185f5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="185f5-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="185f5-121">OperationName</span></span>|<span data-ttu-id="185f5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="185f5-122">xs:string</span></span>|<span data-ttu-id="185f5-123">Nome dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="185f5-123">The name of the operation.</span></span>|  
|<span data-ttu-id="185f5-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="185f5-124">ContractName</span></span>|<span data-ttu-id="185f5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="185f5-125">xs:string</span></span>|<span data-ttu-id="185f5-126">Nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="185f5-126">The name of the contract.</span></span>|  
|<span data-ttu-id="185f5-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="185f5-127">IsOneWay</span></span>|<span data-ttu-id="185f5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="185f5-128">xs:string</span></span>|<span data-ttu-id="185f5-129">True o False che indica se il contratto è unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="185f5-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="185f5-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="185f5-130">AppDomain</span></span>|<span data-ttu-id="185f5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="185f5-131">xs:string</span></span>|<span data-ttu-id="185f5-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="185f5-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
