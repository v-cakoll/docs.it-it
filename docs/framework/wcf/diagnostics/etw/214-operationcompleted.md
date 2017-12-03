---
title: 214 - OperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09a8dc1994da30c0f0c180640e3f66c8806e4528
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="214---operationcompleted"></a><span data-ttu-id="c41d7-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="c41d7-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="c41d7-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c41d7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c41d7-104">ID</span><span class="sxs-lookup"><span data-stu-id="c41d7-104">ID</span></span>|<span data-ttu-id="c41d7-105">214</span><span class="sxs-lookup"><span data-stu-id="c41d7-105">214</span></span>|  
|<span data-ttu-id="c41d7-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c41d7-106">Keywords</span></span>|<span data-ttu-id="c41d7-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c41d7-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="c41d7-108">Livello</span><span class="sxs-lookup"><span data-stu-id="c41d7-108">Level</span></span>|<span data-ttu-id="c41d7-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="c41d7-109">Information</span></span>|  
|<span data-ttu-id="c41d7-110">Canale</span><span class="sxs-lookup"><span data-stu-id="c41d7-110">Channel</span></span>|<span data-ttu-id="c41d7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c41d7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c41d7-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c41d7-112">Description</span></span>  
 <span data-ttu-id="c41d7-113">Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha completato una chiamata a un metodo senza che quest'ultimo generasse un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="c41d7-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c41d7-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c41d7-114">Message</span></span>  
 <span data-ttu-id="c41d7-115">Chiamata al metodo '%1' da parte di OperationInvoker completata.</span><span class="sxs-lookup"><span data-stu-id="c41d7-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="c41d7-116">Durata della chiamata al metodo: '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="c41d7-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c41d7-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c41d7-117">Details</span></span>  
  
|<span data-ttu-id="c41d7-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="c41d7-118">Data Item Name</span></span>|<span data-ttu-id="c41d7-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="c41d7-119">Data Item Type</span></span>|<span data-ttu-id="c41d7-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c41d7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c41d7-121">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="c41d7-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="c41d7-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="c41d7-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="c41d7-123">Durata</span><span class="sxs-lookup"><span data-stu-id="c41d7-123">Duration</span></span>|`xs:long`|<span data-ttu-id="c41d7-124">Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="c41d7-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="c41d7-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="c41d7-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="c41d7-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="c41d7-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="c41d7-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="c41d7-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="c41d7-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="c41d7-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="c41d7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c41d7-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="c41d7-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c41d7-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
