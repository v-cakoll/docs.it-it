---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d027f549e86095c732d0e60df3faded44a39fd2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="210---messagethrottleexceeded"></a><span data-ttu-id="836d3-102">210 - MessageThrottleExceeded</span><span class="sxs-lookup"><span data-stu-id="836d3-102">210 - MessageThrottleExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="836d3-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="836d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="836d3-104">ID</span><span class="sxs-lookup"><span data-stu-id="836d3-104">ID</span></span>|<span data-ttu-id="836d3-105">210</span><span class="sxs-lookup"><span data-stu-id="836d3-105">210</span></span>|  
|<span data-ttu-id="836d3-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="836d3-106">Keywords</span></span>|<span data-ttu-id="836d3-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="836d3-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="836d3-108">Livello</span><span class="sxs-lookup"><span data-stu-id="836d3-108">Level</span></span>|<span data-ttu-id="836d3-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="836d3-109">Warning</span></span>|  
|<span data-ttu-id="836d3-110">Canale</span><span class="sxs-lookup"><span data-stu-id="836d3-110">Channel</span></span>|<span data-ttu-id="836d3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="836d3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="836d3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="836d3-112">Description</span></span>  
 <span data-ttu-id="836d3-113">Questo evento viene generato quando viene superata una delle tre velocità del servizio principali.</span><span class="sxs-lookup"><span data-stu-id="836d3-113">This event is emitted when one of the three main service throttles have been exceeded.</span></span> <span data-ttu-id="836d3-114">L'evento viene generato solo quando il limite di velocità viene superato in fase iniziale.</span><span class="sxs-lookup"><span data-stu-id="836d3-114">Note that this event is only emitted when the throttle limit is initially exceeded.</span></span> <span data-ttu-id="836d3-115">Se ad esempio il limite di velocità per le chiamate simultanee è 10, l'11ª chiamata simultanea comporta un evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="836d3-115">For example, if the throttle limit for concurrent calls is 10, the 11th concurrent call results in a `MessageThrottleExceeded` event.</span></span> <span data-ttu-id="836d3-116">La 12ª chiamata non comporta un altro evento.</span><span class="sxs-lookup"><span data-stu-id="836d3-116">The 12th call does not result in another event.</span></span> <span data-ttu-id="836d3-117">Un'attività che si aggira intorno al limite non comporta inoltre un altro evento, per evitare un flusso di eventi problematico.</span><span class="sxs-lookup"><span data-stu-id="836d3-117">Additionally, to avoid a noisy event stream, activity that hovers around the limit does not result in another event.</span></span> <span data-ttu-id="836d3-118">In questo esempio, se due chiamate vengono completate, saranno presenti 9 chiamate simultanee.</span><span class="sxs-lookup"><span data-stu-id="836d3-118">In this example, if a couple of calls complete then there are 9 concurrent calls.</span></span> <span data-ttu-id="836d3-119">Se in seguito entrano altre due chiamate, il valore corrente sarà nuovamente 11.</span><span class="sxs-lookup"><span data-stu-id="836d3-119">If subsequently two more calls come in, the current value is again 11.</span></span> <span data-ttu-id="836d3-120">Questa situazione non comporta un altro evento.</span><span class="sxs-lookup"><span data-stu-id="836d3-120">This does not result in another event.</span></span> <span data-ttu-id="836d3-121">Se il valore corrente corrisponde al 70% del limite di velocità, viene generato un evento diverso che indica che l'attività è rallentata.</span><span class="sxs-lookup"><span data-stu-id="836d3-121">When the current value falls to 70 percent of the throttle limit a different event is emitted that indicates that the activity has slowed.</span></span> <span data-ttu-id="836d3-122">Un'attività futura che supera il limite comporta un altro evento `MessageThrottleExceeded` generato.</span><span class="sxs-lookup"><span data-stu-id="836d3-122">Future activity that exceeds the limit results in another `MessageThrottleExceeded` event being emitted.</span></span> <span data-ttu-id="836d3-123">In questo esempio, se la quantità di chiamate simultanee corrisponde a 7 e quindi nuovamente a 11, viene generato un altro evento `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="836d3-123">In this example, if the amount of concurrent calls falls to 7 and then again reaches 11 and another `MessageThrottleExceeded` event is emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="836d3-124">Messaggio</span><span class="sxs-lookup"><span data-stu-id="836d3-124">Message</span></span>  
 <span data-ttu-id="836d3-125">È stato raggiunto il limite di velocità '%1' di '%2'.</span><span class="sxs-lookup"><span data-stu-id="836d3-125">The '%1' throttle limit of '%2' was hit.</span></span>  
  
## <a name="details"></a><span data-ttu-id="836d3-126">Dettagli</span><span class="sxs-lookup"><span data-stu-id="836d3-126">Details</span></span>  
  
|<span data-ttu-id="836d3-127">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="836d3-127">Data Item Name</span></span>|<span data-ttu-id="836d3-128">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="836d3-128">Data Item Type</span></span>|<span data-ttu-id="836d3-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="836d3-129">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="836d3-130">Nome velocità</span><span class="sxs-lookup"><span data-stu-id="836d3-130">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="836d3-131">Nome della velocità superata:</span><span class="sxs-lookup"><span data-stu-id="836d3-131">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="836d3-132">`MaxConcurrentCalls`, `MaxConcurrentInstances` o `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="836d3-132">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="836d3-133">Limit</span><span class="sxs-lookup"><span data-stu-id="836d3-133">Limit</span></span>|`xs:long`|<span data-ttu-id="836d3-134">Limite attualmente configurato della velocità.</span><span class="sxs-lookup"><span data-stu-id="836d3-134">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="836d3-135">HostReference</span><span class="sxs-lookup"><span data-stu-id="836d3-135">HostReference</span></span>|`xs:string`|<span data-ttu-id="836d3-136">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="836d3-136">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="836d3-137">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="836d3-137">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="836d3-138">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="836d3-138">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="836d3-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="836d3-139">AppDomain</span></span>|`xs:string`|<span data-ttu-id="836d3-140">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="836d3-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
