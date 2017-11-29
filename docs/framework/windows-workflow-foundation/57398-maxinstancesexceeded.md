---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7417d2e0e850017e65910be32e7449255f0761c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="853d8-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="853d8-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="853d8-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="853d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="853d8-104">ID</span><span class="sxs-lookup"><span data-stu-id="853d8-104">ID</span></span>|<span data-ttu-id="853d8-105">57398</span><span class="sxs-lookup"><span data-stu-id="853d8-105">57398</span></span>|  
|<span data-ttu-id="853d8-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="853d8-106">Keywords</span></span>|<span data-ttu-id="853d8-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="853d8-107">WFServices</span></span>|  
|<span data-ttu-id="853d8-108">Livello</span><span class="sxs-lookup"><span data-stu-id="853d8-108">Level</span></span>|<span data-ttu-id="853d8-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="853d8-109">Warning</span></span>|  
|<span data-ttu-id="853d8-110">Canale</span><span class="sxs-lookup"><span data-stu-id="853d8-110">Channel</span></span>|<span data-ttu-id="853d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="853d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="853d8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853d8-112">Description</span></span>  
 <span data-ttu-id="853d8-113">Indica che il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="853d8-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="853d8-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="853d8-114">Message</span></span>  
 <span data-ttu-id="853d8-115">Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="853d8-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="853d8-116">Il limite per questa velocità è stato impostato su %1.</span><span class="sxs-lookup"><span data-stu-id="853d8-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="853d8-117">Il valore della velocità può essere modificato cambiando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="853d8-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="853d8-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="853d8-118">Details</span></span>  
  
|<span data-ttu-id="853d8-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="853d8-119">Data Item Name</span></span>|<span data-ttu-id="853d8-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="853d8-120">Data Item Type</span></span>|<span data-ttu-id="853d8-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853d8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="853d8-122">Nome</span><span class="sxs-lookup"><span data-stu-id="853d8-122">Name</span></span>|<span data-ttu-id="853d8-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="853d8-123">xs:string</span></span>|<span data-ttu-id="853d8-124">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="853d8-124">The name of the item.</span></span>|  
|<span data-ttu-id="853d8-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="853d8-125">AppDomain</span></span>|<span data-ttu-id="853d8-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="853d8-126">xs:string</span></span>|<span data-ttu-id="853d8-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="853d8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
