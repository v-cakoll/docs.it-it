---
title: 222 - OperationFailed
ms.date: 03/30/2017
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
ms.openlocfilehash: c49aad0f93ce47b66306d75741267530dc6d3fe5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460738"
---
# <a name="222---operationfailed"></a><span data-ttu-id="a0a9c-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="a0a9c-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="a0a9c-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a0a9c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0a9c-104">Id</span><span class="sxs-lookup"><span data-stu-id="a0a9c-104">ID</span></span>|<span data-ttu-id="a0a9c-105">222</span><span class="sxs-lookup"><span data-stu-id="a0a9c-105">222</span></span>|  
|<span data-ttu-id="a0a9c-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a0a9c-106">Keywords</span></span>|<span data-ttu-id="a0a9c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a0a9c-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a0a9c-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a0a9c-108">Level</span></span>|<span data-ttu-id="a0a9c-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="a0a9c-109">Warning</span></span>|  
|<span data-ttu-id="a0a9c-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a0a9c-110">Channel</span></span>|<span data-ttu-id="a0a9c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a0a9c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a0a9c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0a9c-112">Description</span></span>  
 <span data-ttu-id="a0a9c-113">Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha incontrato un'eccezione in fase di richiamo del metodo.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="a0a9c-114">Le eccezioni derivanti da `FaultException` impediscono la generazione di questo evento.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a0a9c-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a0a9c-115">Message</span></span>  
 <span data-ttu-id="a0a9c-116">Il metodo '%1' ha generato un'eccezione non gestita quando è stato richiamato da OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="a0a9c-117">Durata della chiamata al metodo: '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a0a9c-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a0a9c-118">Details</span></span>  
  
|<span data-ttu-id="a0a9c-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a0a9c-119">Data Item Name</span></span>|<span data-ttu-id="a0a9c-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a0a9c-120">Data Item Type</span></span>|<span data-ttu-id="a0a9c-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0a9c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0a9c-122">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="a0a9c-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="a0a9c-123">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="a0a9c-124">Durata</span><span class="sxs-lookup"><span data-stu-id="a0a9c-124">Duration</span></span>|`xs:long`|<span data-ttu-id="a0a9c-125">Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="a0a9c-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="a0a9c-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="a0a9c-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a0a9c-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a0a9c-129">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a0a9c-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a0a9c-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a0a9c-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a0a9c-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
