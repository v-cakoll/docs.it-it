---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458349"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="64f07-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="64f07-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="64f07-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="64f07-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64f07-104">Id</span><span class="sxs-lookup"><span data-stu-id="64f07-104">ID</span></span>|<span data-ttu-id="64f07-105">205</span><span class="sxs-lookup"><span data-stu-id="64f07-105">205</span></span>|  
|<span data-ttu-id="64f07-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="64f07-106">Keywords</span></span>|<span data-ttu-id="64f07-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="64f07-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="64f07-108">Livello</span><span class="sxs-lookup"><span data-stu-id="64f07-108">Level</span></span>|<span data-ttu-id="64f07-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="64f07-109">Information</span></span>|  
|<span data-ttu-id="64f07-110">Canale</span><span class="sxs-lookup"><span data-stu-id="64f07-110">Channel</span></span>|<span data-ttu-id="64f07-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="64f07-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="64f07-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64f07-112">Description</span></span>  
 <span data-ttu-id="64f07-113">Questo evento viene generato precedentemente alla chiamata a un metodo da parte dell'elemento `OperationInvoker` predefinito del modello di servizi.</span><span class="sxs-lookup"><span data-stu-id="64f07-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="64f07-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="64f07-114">Message</span></span>  
 <span data-ttu-id="64f07-115">Metodo '%1' richiamato da OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="64f07-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="64f07-116">Informazioni sul chiamante: '%2'.</span><span class="sxs-lookup"><span data-stu-id="64f07-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="64f07-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="64f07-117">Details</span></span>  
  
|<span data-ttu-id="64f07-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="64f07-118">Data Item Name</span></span>|<span data-ttu-id="64f07-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="64f07-119">Data Item Type</span></span>|<span data-ttu-id="64f07-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64f07-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="64f07-121">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="64f07-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="64f07-122">Nome CLR del metodo richiamato dall'elemento `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="64f07-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="64f07-123">Informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="64f07-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="64f07-124">Indirizzo IP e numero di porta del client nel formato 'IndirizzoIP:NumeroPorta'.</span><span class="sxs-lookup"><span data-stu-id="64f07-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="64f07-125">I due valori vengono recuperati dalla proprietà 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' del messaggio all'interno del contesto dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="64f07-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="64f07-126">Per le associazioni non TCP questo valore è `null`.</span><span class="sxs-lookup"><span data-stu-id="64f07-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="64f07-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="64f07-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="64f07-128">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="64f07-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="64f07-129">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="64f07-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="64f07-130">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="64f07-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="64f07-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="64f07-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="64f07-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="64f07-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
