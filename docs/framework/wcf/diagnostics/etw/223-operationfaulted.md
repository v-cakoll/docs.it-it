---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: cf4a455d80a1a0ac09e99bad967c1feba3653842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61596537"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="e3ae4-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="e3ae4-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="e3ae4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e3ae4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3ae4-104">Id</span><span class="sxs-lookup"><span data-stu-id="e3ae4-104">ID</span></span>|<span data-ttu-id="e3ae4-105">223</span><span class="sxs-lookup"><span data-stu-id="e3ae4-105">223</span></span>|  
|<span data-ttu-id="e3ae4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e3ae4-106">Keywords</span></span>|<span data-ttu-id="e3ae4-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e3ae4-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e3ae4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e3ae4-108">Level</span></span>|<span data-ttu-id="e3ae4-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="e3ae4-109">Warning</span></span>|  
|<span data-ttu-id="e3ae4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e3ae4-110">Channel</span></span>|<span data-ttu-id="e3ae4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e3ae4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e3ae4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3ae4-112">Description</span></span>  
 <span data-ttu-id="e3ae4-113">Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha incontrato un'eccezione derivante da `FaultException` in fase di richiamo del metodo.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e3ae4-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e3ae4-114">Message</span></span>  
 <span data-ttu-id="e3ae4-115">Il metodo '%1' ha generato FaultException quando è stato richiamato da OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="e3ae4-116">Durata della chiamata al metodo: '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e3ae4-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e3ae4-117">Details</span></span>  
  
|<span data-ttu-id="e3ae4-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e3ae4-118">Data Item Name</span></span>|<span data-ttu-id="e3ae4-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e3ae4-119">Data Item Type</span></span>|<span data-ttu-id="e3ae4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3ae4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e3ae4-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="e3ae4-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="e3ae4-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="e3ae4-123">Durata</span><span class="sxs-lookup"><span data-stu-id="e3ae4-123">Duration</span></span>|`xs:long`|<span data-ttu-id="e3ae4-124">Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="e3ae4-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="e3ae4-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="e3ae4-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e3ae4-127">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e3ae4-128">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e3ae4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e3ae4-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e3ae4-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e3ae4-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
