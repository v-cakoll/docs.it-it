---
title: 223 - OperationFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a04ed11db97d02a90e016ee1825b303375a23412
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="223---operationfaulted"></a><span data-ttu-id="76667-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="76667-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="76667-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="76667-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76667-104">ID</span><span class="sxs-lookup"><span data-stu-id="76667-104">ID</span></span>|<span data-ttu-id="76667-105">223</span><span class="sxs-lookup"><span data-stu-id="76667-105">223</span></span>|  
|<span data-ttu-id="76667-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="76667-106">Keywords</span></span>|<span data-ttu-id="76667-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="76667-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="76667-108">Livello</span><span class="sxs-lookup"><span data-stu-id="76667-108">Level</span></span>|<span data-ttu-id="76667-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="76667-109">Warning</span></span>|  
|<span data-ttu-id="76667-110">Canale</span><span class="sxs-lookup"><span data-stu-id="76667-110">Channel</span></span>|<span data-ttu-id="76667-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="76667-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76667-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76667-112">Description</span></span>  
 <span data-ttu-id="76667-113">Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha incontrato un'eccezione derivante da `FaultException` in fase di richiamo del metodo.</span><span class="sxs-lookup"><span data-stu-id="76667-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76667-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="76667-114">Message</span></span>  
 <span data-ttu-id="76667-115">Il metodo '%1' ha generato FaultException quando è stato richiamato da OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="76667-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="76667-116">Durata della chiamata al metodo: '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="76667-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76667-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="76667-117">Details</span></span>  
  
|<span data-ttu-id="76667-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="76667-118">Data Item Name</span></span>|<span data-ttu-id="76667-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="76667-119">Data Item Type</span></span>|<span data-ttu-id="76667-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76667-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76667-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="76667-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="76667-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="76667-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="76667-123">Durata</span><span class="sxs-lookup"><span data-stu-id="76667-123">Duration</span></span>|`xs:long`|<span data-ttu-id="76667-124">Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="76667-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="76667-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="76667-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="76667-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="76667-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="76667-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="76667-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="76667-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="76667-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="76667-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76667-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="76667-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="76667-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
