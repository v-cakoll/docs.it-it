---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781765"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="2fda3-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="2fda3-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="2fda3-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2fda3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fda3-104">Id</span><span class="sxs-lookup"><span data-stu-id="2fda3-104">ID</span></span>|<span data-ttu-id="2fda3-105">217</span><span class="sxs-lookup"><span data-stu-id="2fda3-105">217</span></span>|  
|<span data-ttu-id="2fda3-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2fda3-106">Keywords</span></span>|<span data-ttu-id="2fda3-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2fda3-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2fda3-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2fda3-108">Level</span></span>|<span data-ttu-id="2fda3-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2fda3-109">Information</span></span>|  
|<span data-ttu-id="2fda3-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2fda3-110">Channel</span></span>|<span data-ttu-id="2fda3-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2fda3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2fda3-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fda3-112">Description</span></span>  
 <span data-ttu-id="2fda3-113">Questo evento viene generato dai client prima che un'operazione venga inviata al servizio.</span><span class="sxs-lookup"><span data-stu-id="2fda3-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2fda3-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2fda3-114">Message</span></span>  
 <span data-ttu-id="2fda3-115">Esecuzione dell'azione client '%1' associata al contratto '%2'.</span><span class="sxs-lookup"><span data-stu-id="2fda3-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="2fda3-116">Il messaggio verrà inviato a '%3'.</span><span class="sxs-lookup"><span data-stu-id="2fda3-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2fda3-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2fda3-117">Details</span></span>  
  
|<span data-ttu-id="2fda3-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2fda3-118">Data Item Name</span></span>|<span data-ttu-id="2fda3-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2fda3-119">Data Item Type</span></span>|<span data-ttu-id="2fda3-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fda3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2fda3-121">Operazione</span><span class="sxs-lookup"><span data-stu-id="2fda3-121">Action</span></span>|`xs:string`|<span data-ttu-id="2fda3-122">Intestazione dell'azione SOAP del messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="2fda3-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="2fda3-123">Nome contratto</span><span class="sxs-lookup"><span data-stu-id="2fda3-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="2fda3-124">Nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="2fda3-124">The name of the contract.</span></span> <span data-ttu-id="2fda3-125">Esempio: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="2fda3-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="2fda3-126">Destinazione</span><span class="sxs-lookup"><span data-stu-id="2fda3-126">Destination</span></span>|`xs:string`|<span data-ttu-id="2fda3-127">Indirizzo dell'endpoint servizio a cui viene inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2fda3-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="2fda3-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="2fda3-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="2fda3-129">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="2fda3-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2fda3-130">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="2fda3-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2fda3-131">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="2fda3-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2fda3-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2fda3-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2fda3-133">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2fda3-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
