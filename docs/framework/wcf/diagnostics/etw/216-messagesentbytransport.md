---
title: 216 - MessageSentByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b35f46ae7a214ab45e4062928de82c4da6541a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="6a730-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="6a730-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="6a730-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6a730-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a730-104">ID</span><span class="sxs-lookup"><span data-stu-id="6a730-104">ID</span></span>|<span data-ttu-id="6a730-105">216</span><span class="sxs-lookup"><span data-stu-id="6a730-105">216</span></span>|  
|<span data-ttu-id="6a730-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a730-106">Keywords</span></span>|<span data-ttu-id="6a730-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6a730-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6a730-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6a730-108">Level</span></span>|<span data-ttu-id="6a730-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6a730-109">Information</span></span>|  
|<span data-ttu-id="6a730-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6a730-110">Channel</span></span>|<span data-ttu-id="6a730-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6a730-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6a730-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a730-112">Description</span></span>  
 <span data-ttu-id="6a730-113">Questo evento si verifica nel caso in cui un trasporto basato su TCP invia un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6a730-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="6a730-114">A livello di trasporto è possibile scambiare più messaggi tra client e servizi per una sola operazione.</span><span class="sxs-lookup"><span data-stu-id="6a730-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="6a730-115">Ciò può essere dovuto a un comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza).</span><span class="sxs-lookup"><span data-stu-id="6a730-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="6a730-116">Pertanto, il numero di **MessageSentByTransport** gli eventi generati variano in base all'associazione del servizio e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="6a730-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6a730-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6a730-117">Message</span></span>  
 <span data-ttu-id="6a730-118">Il trasporto ha inviato un messaggio a '%1'.</span><span class="sxs-lookup"><span data-stu-id="6a730-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6a730-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6a730-119">Details</span></span>  
  
|<span data-ttu-id="6a730-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6a730-120">Data Item Name</span></span>|<span data-ttu-id="6a730-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6a730-121">Data Item Type</span></span>|<span data-ttu-id="6a730-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a730-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6a730-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="6a730-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="6a730-124">L'indirizzo a cui è stato inviato il messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="6a730-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="6a730-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="6a730-125">HostReference</span></span>|<span data-ttu-id="6a730-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="6a730-126">xs:string</span></span>|<span data-ttu-id="6a730-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="6a730-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6a730-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="6a730-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6a730-129">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6a730-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6a730-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6a730-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6a730-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6a730-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
