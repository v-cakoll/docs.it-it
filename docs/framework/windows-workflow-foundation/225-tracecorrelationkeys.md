---
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: 0bb54387dbd738a01225008edfc45ecb7297cd00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755662"
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="8c607-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="8c607-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="8c607-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8c607-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c607-104">Id</span><span class="sxs-lookup"><span data-stu-id="8c607-104">ID</span></span>|<span data-ttu-id="8c607-105">225</span><span class="sxs-lookup"><span data-stu-id="8c607-105">225</span></span>|  
|<span data-ttu-id="8c607-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8c607-106">Keywords</span></span>|<span data-ttu-id="8c607-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8c607-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8c607-108">Livello</span><span class="sxs-lookup"><span data-stu-id="8c607-108">Level</span></span>|<span data-ttu-id="8c607-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="8c607-109">Information</span></span>|  
|<span data-ttu-id="8c607-110">Canale</span><span class="sxs-lookup"><span data-stu-id="8c607-110">Channel</span></span>|<span data-ttu-id="8c607-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8c607-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8c607-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c607-112">Description</span></span>  
 <span data-ttu-id="8c607-113">Questo evento viene generato quando per un servizio flusso di lavoro viene usata la correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="8c607-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="8c607-114">Contiene le chiavi di correlazione applicate per correlare un messaggio a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="8c607-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8c607-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8c607-115">Message</span></span>  
 <span data-ttu-id="8c607-116">Chiave di correlazione '%1' calcolata usando i valori '%2' nell'ambito padre '%3'.</span><span class="sxs-lookup"><span data-stu-id="8c607-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8c607-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8c607-117">Details</span></span>  
  
|<span data-ttu-id="8c607-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="8c607-118">Data Item Name</span></span>|<span data-ttu-id="8c607-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="8c607-119">Data Item Type</span></span>|<span data-ttu-id="8c607-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c607-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8c607-121">Chiave di istanza</span><span class="sxs-lookup"><span data-stu-id="8c607-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="8c607-122">Chiave generata dai valori di correlazione.</span><span class="sxs-lookup"><span data-stu-id="8c607-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="8c607-123">Valori</span><span class="sxs-lookup"><span data-stu-id="8c607-123">Values</span></span>|`xs:string`|<span data-ttu-id="8c607-124">Valori usati per calcolare la chiave dell'istanza di correlazione.</span><span class="sxs-lookup"><span data-stu-id="8c607-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="8c607-125">Ambito padre</span><span class="sxs-lookup"><span data-stu-id="8c607-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="8c607-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="8c607-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="8c607-127">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="8c607-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8c607-128">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="8c607-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8c607-129">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="8c607-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8c607-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8c607-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8c607-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8c607-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
