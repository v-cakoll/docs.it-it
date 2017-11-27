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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a1f74ebfef7a2582f3eb25c3571cd05c4518ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="5be8e-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="5be8e-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="5be8e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5be8e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5be8e-104">ID</span><span class="sxs-lookup"><span data-stu-id="5be8e-104">ID</span></span>|<span data-ttu-id="5be8e-105">225</span><span class="sxs-lookup"><span data-stu-id="5be8e-105">225</span></span>|  
|<span data-ttu-id="5be8e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5be8e-106">Keywords</span></span>|<span data-ttu-id="5be8e-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5be8e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5be8e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5be8e-108">Level</span></span>|<span data-ttu-id="5be8e-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="5be8e-109">Information</span></span>|  
|<span data-ttu-id="5be8e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5be8e-110">Channel</span></span>|<span data-ttu-id="5be8e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5be8e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5be8e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5be8e-112">Description</span></span>  
 <span data-ttu-id="5be8e-113">Questo evento viene generato quando per un servizio flusso di lavoro viene usata la correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="5be8e-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="5be8e-114">Contiene le chiavi di correlazione applicate per correlare un messaggio a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="5be8e-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5be8e-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5be8e-115">Message</span></span>  
 <span data-ttu-id="5be8e-116">Chiave di correlazione '%1' calcolata usando i valori '%2' nell'ambito padre '%3'.</span><span class="sxs-lookup"><span data-stu-id="5be8e-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5be8e-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5be8e-117">Details</span></span>  
  
|<span data-ttu-id="5be8e-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5be8e-118">Data Item Name</span></span>|<span data-ttu-id="5be8e-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5be8e-119">Data Item Type</span></span>|<span data-ttu-id="5be8e-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5be8e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5be8e-121">Chiave di istanza</span><span class="sxs-lookup"><span data-stu-id="5be8e-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="5be8e-122">Chiave generata dai valori di correlazione.</span><span class="sxs-lookup"><span data-stu-id="5be8e-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="5be8e-123">Valori</span><span class="sxs-lookup"><span data-stu-id="5be8e-123">Values</span></span>|`xs:string`|<span data-ttu-id="5be8e-124">Valori usati per calcolare la chiave dell'istanza di correlazione.</span><span class="sxs-lookup"><span data-stu-id="5be8e-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="5be8e-125">Ambito padre</span><span class="sxs-lookup"><span data-stu-id="5be8e-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="5be8e-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="5be8e-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="5be8e-127">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="5be8e-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5be8e-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5be8e-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5be8e-129">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5be8e-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5be8e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5be8e-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5be8e-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5be8e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
