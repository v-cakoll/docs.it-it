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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba48f19de1be3cfd2461e159b91fa365e24ee750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="b6f72-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="b6f72-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="b6f72-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b6f72-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6f72-104">ID</span><span class="sxs-lookup"><span data-stu-id="b6f72-104">ID</span></span>|<span data-ttu-id="b6f72-105">57398</span><span class="sxs-lookup"><span data-stu-id="b6f72-105">57398</span></span>|  
|<span data-ttu-id="b6f72-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b6f72-106">Keywords</span></span>|<span data-ttu-id="b6f72-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b6f72-107">WFServices</span></span>|  
|<span data-ttu-id="b6f72-108">Livello</span><span class="sxs-lookup"><span data-stu-id="b6f72-108">Level</span></span>|<span data-ttu-id="b6f72-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="b6f72-109">Warning</span></span>|  
|<span data-ttu-id="b6f72-110">Canale</span><span class="sxs-lookup"><span data-stu-id="b6f72-110">Channel</span></span>|<span data-ttu-id="b6f72-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b6f72-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6f72-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6f72-112">Description</span></span>  
 <span data-ttu-id="b6f72-113">Indica che il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="b6f72-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6f72-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="b6f72-114">Message</span></span>  
 <span data-ttu-id="b6f72-115">Il sistema ha raggiunto il limite impostato per la velocità 'MaxConcurrentInstances'.</span><span class="sxs-lookup"><span data-stu-id="b6f72-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="b6f72-116">Il limite per questa velocità è stato impostato su %1.</span><span class="sxs-lookup"><span data-stu-id="b6f72-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="b6f72-117">Il valore della velocità può essere modificato cambiando l'attributo 'maxConcurrentInstances' nell'elemento serviceThrottle o modificando la proprietà 'MaxConcurrentInstances' nel comportamento ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="b6f72-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6f72-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b6f72-118">Details</span></span>  
  
|<span data-ttu-id="b6f72-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="b6f72-119">Data Item Name</span></span>|<span data-ttu-id="b6f72-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="b6f72-120">Data Item Type</span></span>|<span data-ttu-id="b6f72-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6f72-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6f72-122">Nome</span><span class="sxs-lookup"><span data-stu-id="b6f72-122">Name</span></span>|<span data-ttu-id="b6f72-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6f72-123">xs:string</span></span>|<span data-ttu-id="b6f72-124">Nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b6f72-124">The name of the item.</span></span>|  
|<span data-ttu-id="b6f72-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6f72-125">AppDomain</span></span>|<span data-ttu-id="b6f72-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6f72-126">xs:string</span></span>|<span data-ttu-id="b6f72-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b6f72-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
