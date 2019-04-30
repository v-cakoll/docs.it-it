---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: da1021b674b555b683f8f745f5a2a0073c9567e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967999"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="1e93b-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="1e93b-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="1e93b-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1e93b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e93b-104">Id</span><span class="sxs-lookup"><span data-stu-id="1e93b-104">ID</span></span>|<span data-ttu-id="1e93b-105">214</span><span class="sxs-lookup"><span data-stu-id="1e93b-105">214</span></span>|  
|<span data-ttu-id="1e93b-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1e93b-106">Keywords</span></span>|<span data-ttu-id="1e93b-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1e93b-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1e93b-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1e93b-108">Level</span></span>|<span data-ttu-id="1e93b-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="1e93b-109">Information</span></span>|  
|<span data-ttu-id="1e93b-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1e93b-110">Channel</span></span>|<span data-ttu-id="1e93b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1e93b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1e93b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e93b-112">Description</span></span>  
 <span data-ttu-id="1e93b-113">Questo evento viene generato quando l'elemento `OperationInvoker` predefinito del modello di servizi ha completato una chiamata a un metodo senza che quest'ultimo generasse un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1e93b-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1e93b-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1e93b-114">Message</span></span>  
 <span data-ttu-id="1e93b-115">Chiamata al metodo '%1' da parte di OperationInvoker completata.</span><span class="sxs-lookup"><span data-stu-id="1e93b-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="1e93b-116">Durata della chiamata al metodo: '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="1e93b-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1e93b-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1e93b-117">Details</span></span>  
  
|<span data-ttu-id="1e93b-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1e93b-118">Data Item Name</span></span>|<span data-ttu-id="1e93b-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1e93b-119">Data Item Type</span></span>|<span data-ttu-id="1e93b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e93b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1e93b-121">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="1e93b-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="1e93b-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="1e93b-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="1e93b-123">Durata</span><span class="sxs-lookup"><span data-stu-id="1e93b-123">Duration</span></span>|`xs:long`|<span data-ttu-id="1e93b-124">Durata, in millisecondi, necessaria all'elemento `OperationInvoker` per richiamare il metodo.</span><span class="sxs-lookup"><span data-stu-id="1e93b-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="1e93b-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="1e93b-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="1e93b-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="1e93b-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1e93b-127">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="1e93b-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1e93b-128">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1e93b-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1e93b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1e93b-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1e93b-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1e93b-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
