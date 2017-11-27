---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 60367b33e1e57cce8646b4fcde79c7d4fd20a4cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="d7936-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="d7936-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="d7936-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d7936-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7936-104">ID</span><span class="sxs-lookup"><span data-stu-id="d7936-104">ID</span></span>|<span data-ttu-id="d7936-105">3503</span><span class="sxs-lookup"><span data-stu-id="d7936-105">3503</span></span>|  
|<span data-ttu-id="d7936-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d7936-106">Keywords</span></span>|<span data-ttu-id="d7936-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d7936-107">WFServices</span></span>|  
|<span data-ttu-id="d7936-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d7936-108">Level</span></span>|<span data-ttu-id="d7936-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="d7936-109">Warning</span></span>|  
|<span data-ttu-id="d7936-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d7936-110">Channel</span></span>|<span data-ttu-id="d7936-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d7936-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d7936-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7936-112">Description</span></span>  
 <span data-ttu-id="d7936-113">Indica che è stato trovato un elemento CorrelationQuery duplicato.</span><span class="sxs-lookup"><span data-stu-id="d7936-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="d7936-114">La query duplicata non verrà usata per il calcolo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="d7936-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d7936-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d7936-115">Message</span></span>  
 <span data-ttu-id="d7936-116">CorrelationQuery duplicata trovata con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="d7936-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="d7936-117">La query duplicata non verrà usata per il calcolo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="d7936-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d7936-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d7936-118">Details</span></span>  
  
|<span data-ttu-id="d7936-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d7936-119">Data Item Name</span></span>|<span data-ttu-id="d7936-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d7936-120">Data Item Type</span></span>|<span data-ttu-id="d7936-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7936-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d7936-122">Dove</span><span class="sxs-lookup"><span data-stu-id="d7936-122">Where</span></span>|<span data-ttu-id="d7936-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7936-123">xs:string</span></span>|<span data-ttu-id="d7936-124">La parte Where della query di correlazione.</span><span class="sxs-lookup"><span data-stu-id="d7936-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="d7936-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d7936-125">AppDomain</span></span>|<span data-ttu-id="d7936-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7936-126">xs:string</span></span>|<span data-ttu-id="d7936-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d7936-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
