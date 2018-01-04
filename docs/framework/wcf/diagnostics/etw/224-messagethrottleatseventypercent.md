---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e7d35407fe22dc913f7122163006035717d60d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="5d26a-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="5d26a-102">224 - MessageThrottleAtSeventyPercent</span></span>
## <a name="properties"></a><span data-ttu-id="5d26a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5d26a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d26a-104">Id</span><span class="sxs-lookup"><span data-stu-id="5d26a-104">ID</span></span>|<span data-ttu-id="5d26a-105">224</span><span class="sxs-lookup"><span data-stu-id="5d26a-105">224</span></span>|  
|<span data-ttu-id="5d26a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5d26a-106">Keywords</span></span>|<span data-ttu-id="5d26a-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5d26a-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5d26a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5d26a-108">Level</span></span>|<span data-ttu-id="5d26a-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="5d26a-109">Warning</span></span>|  
|<span data-ttu-id="5d26a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5d26a-110">Channel</span></span>|<span data-ttu-id="5d26a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5d26a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d26a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d26a-112">Description</span></span>  
 <span data-ttu-id="5d26a-113">Se viene superata una delle velocità del servizio principali, viene generato l'evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="5d26a-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="5d26a-114">Se il picco dell'attività rallenta e il valore corrente della velocità è pari al 70% del limite corrente, viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="5d26a-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="5d26a-115">Questo evento viene generato solo una volta, in quanto l'attività sta rallentando.</span><span class="sxs-lookup"><span data-stu-id="5d26a-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="5d26a-116">Se il valore corrente si aggira attorno al limite del 70% (ad esempio, 70, 69, 70, 71, 70, 69), solo alla prima occorrenza di 70% verrà generato un evento.</span><span class="sxs-lookup"><span data-stu-id="5d26a-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="5d26a-117">Una volta generato l'evento, le future occorrenze di superamento del limite della velocità genereranno un evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="5d26a-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d26a-118">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5d26a-118">Message</span></span>  
 <span data-ttu-id="5d26a-119">Il limite di velocità '%1' di '%2' è al 70%.</span><span class="sxs-lookup"><span data-stu-id="5d26a-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d26a-120">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5d26a-120">Details</span></span>  
  
|<span data-ttu-id="5d26a-121">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5d26a-121">Data Item Name</span></span>|<span data-ttu-id="5d26a-122">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5d26a-122">Data Item Type</span></span>|<span data-ttu-id="5d26a-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d26a-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d26a-124">Nome velocità</span><span class="sxs-lookup"><span data-stu-id="5d26a-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="5d26a-125">Nome della velocità superata:</span><span class="sxs-lookup"><span data-stu-id="5d26a-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="5d26a-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="5d26a-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="5d26a-127">Limit</span><span class="sxs-lookup"><span data-stu-id="5d26a-127">Limit</span></span>|`xs:long`|<span data-ttu-id="5d26a-128">Limite attualmente configurato della velocità.</span><span class="sxs-lookup"><span data-stu-id="5d26a-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="5d26a-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="5d26a-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="5d26a-130">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="5d26a-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5d26a-131">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5d26a-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5d26a-132">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5d26a-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5d26a-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d26a-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5d26a-134">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d26a-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
