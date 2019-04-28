---
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 83f39be84a8d62962b85652b0e39b537c92e612c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781764"
---
# <a name="218---clientoperationcompleted"></a><span data-ttu-id="cfc27-102">218 - ClientOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="cfc27-102">218 - ClientOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="cfc27-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cfc27-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfc27-104">Id</span><span class="sxs-lookup"><span data-stu-id="cfc27-104">ID</span></span>|<span data-ttu-id="cfc27-105">218</span><span class="sxs-lookup"><span data-stu-id="cfc27-105">218</span></span>|  
|<span data-ttu-id="cfc27-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cfc27-106">Keywords</span></span>|<span data-ttu-id="cfc27-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cfc27-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cfc27-108">Livello</span><span class="sxs-lookup"><span data-stu-id="cfc27-108">Level</span></span>|<span data-ttu-id="cfc27-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="cfc27-109">Information</span></span>|  
|<span data-ttu-id="cfc27-110">Canale</span><span class="sxs-lookup"><span data-stu-id="cfc27-110">Channel</span></span>|<span data-ttu-id="cfc27-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cfc27-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cfc27-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfc27-112">Description</span></span>  
 <span data-ttu-id="cfc27-113">Questo evento viene generato dai client al termine di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="cfc27-113">This event is emitted by clients just after an operation completes.</span></span> <span data-ttu-id="cfc27-114">Per le operazioni unidirezionali, si tratta del momento successivo all'invio di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="cfc27-114">For one-way operations, this is just after the message is sent successfully.</span></span> <span data-ttu-id="cfc27-115">Per le operazioni request-response, si tratta del momento successivo alla ricezione della risposta.</span><span class="sxs-lookup"><span data-stu-id="cfc27-115">For request-response operations this is after the response is received.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cfc27-116">Messaggio</span><span class="sxs-lookup"><span data-stu-id="cfc27-116">Message</span></span>  
 <span data-ttu-id="cfc27-117">L'azione client '%1' associata al contratto '%2' è completa.</span><span class="sxs-lookup"><span data-stu-id="cfc27-117">The Client completed executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="cfc27-118">Il messaggio è stato inviato a '%3'.</span><span class="sxs-lookup"><span data-stu-id="cfc27-118">The message was sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cfc27-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cfc27-119">Details</span></span>  
  
|<span data-ttu-id="cfc27-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="cfc27-120">Data Item Name</span></span>|<span data-ttu-id="cfc27-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="cfc27-121">Data Item Type</span></span>|<span data-ttu-id="cfc27-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfc27-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cfc27-123">Operazione</span><span class="sxs-lookup"><span data-stu-id="cfc27-123">Action</span></span>|<span data-ttu-id="cfc27-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cfc27-124">xs:string</span></span>|<span data-ttu-id="cfc27-125">Intestazione dell'azione SOAP del messaggio in uscita.</span><span class="sxs-lookup"><span data-stu-id="cfc27-125">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="cfc27-126">Nome contratto</span><span class="sxs-lookup"><span data-stu-id="cfc27-126">Contract Name</span></span>|`xs:string`|<span data-ttu-id="cfc27-127">Nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="cfc27-127">The name of the contract.</span></span> <span data-ttu-id="cfc27-128">Esempio: ICalculator.</span><span class="sxs-lookup"><span data-stu-id="cfc27-128">Example: ICalculator.</span></span>|  
|<span data-ttu-id="cfc27-129">Destinazione</span><span class="sxs-lookup"><span data-stu-id="cfc27-129">Destination</span></span>|`xs:string`|<span data-ttu-id="cfc27-130">Indirizzo dell'endpoint servizio a cui è stato inviato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cfc27-130">The address of the service endpoint that the message was sent to.</span></span>|  
|<span data-ttu-id="cfc27-131">HostReference</span><span class="sxs-lookup"><span data-stu-id="cfc27-131">HostReference</span></span>|`xs:string`|<span data-ttu-id="cfc27-132">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="cfc27-132">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cfc27-133">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="cfc27-133">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cfc27-134">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="cfc27-134">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cfc27-135">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cfc27-135">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cfc27-136">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cfc27-136">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
