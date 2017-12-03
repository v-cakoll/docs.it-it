---
title: 225 - TraceCorrelationKeys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f4b6eb5df59977de91f1651a47a96cdf44bcf29
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="d2543-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="d2543-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="d2543-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d2543-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2543-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2543-104">ID</span></span>|<span data-ttu-id="d2543-105">225</span><span class="sxs-lookup"><span data-stu-id="d2543-105">225</span></span>|  
|<span data-ttu-id="d2543-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2543-106">Keywords</span></span>|<span data-ttu-id="d2543-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d2543-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d2543-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d2543-108">Level</span></span>|<span data-ttu-id="d2543-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="d2543-109">Information</span></span>|  
|<span data-ttu-id="d2543-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d2543-110">Channel</span></span>|<span data-ttu-id="d2543-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d2543-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2543-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2543-112">Description</span></span>  
 <span data-ttu-id="d2543-113">Questo evento viene generato quando per un servizio flusso di lavoro viene usata la correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="d2543-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="d2543-114">Contiene le chiavi di correlazione applicate per correlare un messaggio a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="d2543-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2543-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d2543-115">Message</span></span>  
 <span data-ttu-id="d2543-116">Chiave di correlazione '%1' calcolata usando i valori '%2' nell'ambito padre '%3'.</span><span class="sxs-lookup"><span data-stu-id="d2543-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2543-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d2543-117">Details</span></span>  
  
|<span data-ttu-id="d2543-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d2543-118">Data Item Name</span></span>|<span data-ttu-id="d2543-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d2543-119">Data Item Type</span></span>|<span data-ttu-id="d2543-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2543-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2543-121">Chiave di istanza</span><span class="sxs-lookup"><span data-stu-id="d2543-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="d2543-122">Chiave generata dai valori di correlazione.</span><span class="sxs-lookup"><span data-stu-id="d2543-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="d2543-123">Valori</span><span class="sxs-lookup"><span data-stu-id="d2543-123">Values</span></span>|`xs:string`|<span data-ttu-id="d2543-124">Valori usati per calcolare la chiave dell'istanza di correlazione.</span><span class="sxs-lookup"><span data-stu-id="d2543-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="d2543-125">Ambito padre</span><span class="sxs-lookup"><span data-stu-id="d2543-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="d2543-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="d2543-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="d2543-127">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="d2543-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d2543-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d2543-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d2543-129">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d2543-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d2543-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2543-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d2543-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d2543-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
