---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b0a96f1e3ba72a226d9b1a871382a27db61c57e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="205---operationinvoked"></a><span data-ttu-id="be218-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="be218-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="be218-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="be218-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be218-104">ID</span><span class="sxs-lookup"><span data-stu-id="be218-104">ID</span></span>|<span data-ttu-id="be218-105">205</span><span class="sxs-lookup"><span data-stu-id="be218-105">205</span></span>|  
|<span data-ttu-id="be218-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="be218-106">Keywords</span></span>|<span data-ttu-id="be218-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="be218-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="be218-108">Livello</span><span class="sxs-lookup"><span data-stu-id="be218-108">Level</span></span>|<span data-ttu-id="be218-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="be218-109">Information</span></span>|  
|<span data-ttu-id="be218-110">Canale</span><span class="sxs-lookup"><span data-stu-id="be218-110">Channel</span></span>|<span data-ttu-id="be218-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="be218-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="be218-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be218-112">Description</span></span>  
 <span data-ttu-id="be218-113">Questo evento viene generato precedentemente alla chiamata a un metodo da parte dell'elemento `OperationInvoker` predefinito del modello di servizi.</span><span class="sxs-lookup"><span data-stu-id="be218-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="be218-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="be218-114">Message</span></span>  
 <span data-ttu-id="be218-115">Metodo '%1' richiamato da OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="be218-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="be218-116">Informazioni sul chiamante: '%2'.</span><span class="sxs-lookup"><span data-stu-id="be218-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="be218-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="be218-117">Details</span></span>  
  
|<span data-ttu-id="be218-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="be218-118">Data Item Name</span></span>|<span data-ttu-id="be218-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="be218-119">Data Item Type</span></span>|<span data-ttu-id="be218-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be218-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="be218-121">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="be218-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="be218-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="be218-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="be218-123">Informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="be218-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="be218-124">Indirizzo IP e numero di porta del client nel formato 'IndirizzoIP:NumeroPorta'.</span><span class="sxs-lookup"><span data-stu-id="be218-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="be218-125">I due valori vengono recuperati dalla proprietà 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' del messaggio all'interno del contesto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="be218-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="be218-126">Per le associazioni non TCP questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="be218-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="be218-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="be218-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="be218-128">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="be218-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="be218-129">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="be218-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="be218-130">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="be218-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="be218-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="be218-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="be218-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="be218-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
