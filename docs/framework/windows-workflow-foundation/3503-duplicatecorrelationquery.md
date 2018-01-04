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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 997bdf4423364e9b5361635820849a6bde9e8960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="02e0f-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="02e0f-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="02e0f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="02e0f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02e0f-104">ID</span><span class="sxs-lookup"><span data-stu-id="02e0f-104">ID</span></span>|<span data-ttu-id="02e0f-105">3503</span><span class="sxs-lookup"><span data-stu-id="02e0f-105">3503</span></span>|  
|<span data-ttu-id="02e0f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="02e0f-106">Keywords</span></span>|<span data-ttu-id="02e0f-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="02e0f-107">WFServices</span></span>|  
|<span data-ttu-id="02e0f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="02e0f-108">Level</span></span>|<span data-ttu-id="02e0f-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="02e0f-109">Warning</span></span>|  
|<span data-ttu-id="02e0f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="02e0f-110">Channel</span></span>|<span data-ttu-id="02e0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="02e0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02e0f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02e0f-112">Description</span></span>  
 <span data-ttu-id="02e0f-113">Indica che è stato trovato un elemento CorrelationQuery duplicato.</span><span class="sxs-lookup"><span data-stu-id="02e0f-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="02e0f-114">La query duplicata non verrà usata per il calcolo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="02e0f-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02e0f-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="02e0f-115">Message</span></span>  
 <span data-ttu-id="02e0f-116">CorrelationQuery duplicata trovata con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="02e0f-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="02e0f-117">La query duplicata non verrà usata per il calcolo della correlazione.</span><span class="sxs-lookup"><span data-stu-id="02e0f-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02e0f-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="02e0f-118">Details</span></span>  
  
|<span data-ttu-id="02e0f-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="02e0f-119">Data Item Name</span></span>|<span data-ttu-id="02e0f-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="02e0f-120">Data Item Type</span></span>|<span data-ttu-id="02e0f-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02e0f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02e0f-122">Dove</span><span class="sxs-lookup"><span data-stu-id="02e0f-122">Where</span></span>|<span data-ttu-id="02e0f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="02e0f-123">xs:string</span></span>|<span data-ttu-id="02e0f-124">La parte Where della query di correlazione.</span><span class="sxs-lookup"><span data-stu-id="02e0f-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="02e0f-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02e0f-125">AppDomain</span></span>|<span data-ttu-id="02e0f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="02e0f-126">xs:string</span></span>|<span data-ttu-id="02e0f-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="02e0f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
