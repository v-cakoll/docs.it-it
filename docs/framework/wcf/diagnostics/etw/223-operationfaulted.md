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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcaea7b98bc57bcac901ac659786175a10799700
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="223---operationfaulted"></a><span data-ttu-id="10661-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="10661-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="10661-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="10661-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10661-104">Id</span><span class="sxs-lookup"><span data-stu-id="10661-104">ID</span></span>|<span data-ttu-id="10661-105">223</span><span class="sxs-lookup"><span data-stu-id="10661-105">223</span></span>|  
|<span data-ttu-id="10661-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="10661-106">Keywords</span></span>|<span data-ttu-id="10661-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="10661-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="10661-108">Livello</span><span class="sxs-lookup"><span data-stu-id="10661-108">Level</span></span>|<span data-ttu-id="10661-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="10661-109">Warning</span></span>|  
|<span data-ttu-id="10661-110">Canale</span><span class="sxs-lookup"><span data-stu-id="10661-110">Channel</span></span>|<span data-ttu-id="10661-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="10661-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10661-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10661-112">Description</span></span>  
 <span data-ttu-id="10661-113">Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha incontrato un'eccezione derivante da `FaultException` in fase di richiamo del metodo.</span><span class="sxs-lookup"><span data-stu-id="10661-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10661-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="10661-114">Message</span></span>  
 <span data-ttu-id="10661-115">Il metodo '%1' ha generato FaultException quando è stato richiamato da OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="10661-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="10661-116">Durata della chiamata al metodo: '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="10661-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10661-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="10661-117">Details</span></span>  
  
|<span data-ttu-id="10661-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="10661-118">Data Item Name</span></span>|<span data-ttu-id="10661-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="10661-119">Data Item Type</span></span>|<span data-ttu-id="10661-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10661-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10661-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="10661-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="10661-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="10661-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="10661-123">Durata</span><span class="sxs-lookup"><span data-stu-id="10661-123">Duration</span></span>|`xs:long`|<span data-ttu-id="10661-124">Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="10661-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="10661-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="10661-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="10661-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="10661-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="10661-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="10661-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="10661-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="10661-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="10661-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10661-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="10661-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="10661-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
