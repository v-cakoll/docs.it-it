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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1b2bf2841c04dcdc74bf64a0169b95caa6c8a36a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="9d342-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="9d342-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="9d342-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9d342-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d342-104">ID</span><span class="sxs-lookup"><span data-stu-id="9d342-104">ID</span></span>|<span data-ttu-id="9d342-105">216</span><span class="sxs-lookup"><span data-stu-id="9d342-105">216</span></span>|  
|<span data-ttu-id="9d342-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d342-106">Keywords</span></span>|<span data-ttu-id="9d342-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d342-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9d342-108">Livello</span><span class="sxs-lookup"><span data-stu-id="9d342-108">Level</span></span>|<span data-ttu-id="9d342-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="9d342-109">Information</span></span>|  
|<span data-ttu-id="9d342-110">Canale</span><span class="sxs-lookup"><span data-stu-id="9d342-110">Channel</span></span>|<span data-ttu-id="9d342-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9d342-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9d342-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d342-112">Description</span></span>  
 <span data-ttu-id="9d342-113">Questo evento si verifica nel caso in cui un trasporto basato su TCP invia un messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d342-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="9d342-114">A livello di trasporto è possibile scambiare più messaggi tra client e servizi per una sola operazione.</span><span class="sxs-lookup"><span data-stu-id="9d342-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="9d342-115">Ciò può essere dovuto a un comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza).</span><span class="sxs-lookup"><span data-stu-id="9d342-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="9d342-116">Pertanto, il numero di **MessageSentByTransport** gli eventi generati variano in base all'associazione del servizio e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d342-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9d342-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="9d342-117">Message</span></span>  
 <span data-ttu-id="9d342-118">Il trasporto ha inviato un messaggio a '%1'.</span><span class="sxs-lookup"><span data-stu-id="9d342-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9d342-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9d342-119">Details</span></span>  
  
|<span data-ttu-id="9d342-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="9d342-120">Data Item Name</span></span>|<span data-ttu-id="9d342-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="9d342-121">Data Item Type</span></span>|<span data-ttu-id="9d342-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d342-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9d342-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="9d342-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="9d342-124">L'indirizzo a cui è stato inviato il messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="9d342-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="9d342-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="9d342-125">HostReference</span></span>|<span data-ttu-id="9d342-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d342-126">xs:string</span></span>|<span data-ttu-id="9d342-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="9d342-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9d342-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9d342-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9d342-129">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9d342-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9d342-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9d342-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9d342-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9d342-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
