---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781810"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="fccfe-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="fccfe-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="fccfe-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="fccfe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fccfe-104">Id</span><span class="sxs-lookup"><span data-stu-id="fccfe-104">ID</span></span>|<span data-ttu-id="fccfe-105">216</span><span class="sxs-lookup"><span data-stu-id="fccfe-105">216</span></span>|  
|<span data-ttu-id="fccfe-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="fccfe-106">Keywords</span></span>|<span data-ttu-id="fccfe-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fccfe-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="fccfe-108">Livello</span><span class="sxs-lookup"><span data-stu-id="fccfe-108">Level</span></span>|<span data-ttu-id="fccfe-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="fccfe-109">Information</span></span>|  
|<span data-ttu-id="fccfe-110">Canale</span><span class="sxs-lookup"><span data-stu-id="fccfe-110">Channel</span></span>|<span data-ttu-id="fccfe-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="fccfe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fccfe-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fccfe-112">Description</span></span>  
 <span data-ttu-id="fccfe-113">Questo evento si verifica nel caso in cui un trasporto basato su TCP invia un messaggio.</span><span class="sxs-lookup"><span data-stu-id="fccfe-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="fccfe-114">A livello di trasporto è possibile scambiare più messaggi tra client e servizi per una sola operazione.</span><span class="sxs-lookup"><span data-stu-id="fccfe-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="fccfe-115">Ciò può essere dovuto a un comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza).</span><span class="sxs-lookup"><span data-stu-id="fccfe-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="fccfe-116">Pertanto, il numero di **MessageSentByTransport** gli eventi generati variano in base all'associazione del servizio e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="fccfe-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fccfe-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="fccfe-117">Message</span></span>  
 <span data-ttu-id="fccfe-118">Il trasporto ha inviato un messaggio a '%1'.</span><span class="sxs-lookup"><span data-stu-id="fccfe-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fccfe-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fccfe-119">Details</span></span>  
  
|<span data-ttu-id="fccfe-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="fccfe-120">Data Item Name</span></span>|<span data-ttu-id="fccfe-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="fccfe-121">Data Item Type</span></span>|<span data-ttu-id="fccfe-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fccfe-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fccfe-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="fccfe-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="fccfe-124">L'indirizzo a cui è stato inviato il messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="fccfe-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="fccfe-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="fccfe-125">HostReference</span></span>|<span data-ttu-id="fccfe-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fccfe-126">xs:string</span></span>|<span data-ttu-id="fccfe-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="fccfe-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="fccfe-128">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="fccfe-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="fccfe-129">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="fccfe-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="fccfe-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fccfe-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fccfe-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fccfe-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
