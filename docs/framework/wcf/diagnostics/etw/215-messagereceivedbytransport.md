---
title: 215 - MessageReceivedByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bf2336d1b5c9dda1dac2b38305d944a822bd253
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="f8b01-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="f8b01-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="f8b01-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f8b01-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8b01-104">ID</span><span class="sxs-lookup"><span data-stu-id="f8b01-104">ID</span></span>|<span data-ttu-id="f8b01-105">215</span><span class="sxs-lookup"><span data-stu-id="f8b01-105">215</span></span>|  
|<span data-ttu-id="f8b01-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f8b01-106">Keywords</span></span>|<span data-ttu-id="f8b01-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f8b01-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f8b01-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f8b01-108">Level</span></span>|<span data-ttu-id="f8b01-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="f8b01-109">Information</span></span>|  
|<span data-ttu-id="f8b01-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f8b01-110">Channel</span></span>|<span data-ttu-id="f8b01-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f8b01-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f8b01-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8b01-112">Description</span></span>  
 <span data-ttu-id="f8b01-113">Questo evento si verifica quando un trasporto basato su TCP riceve un messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8b01-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="f8b01-114">Si noti che a livello di trasporto è possibile che si verifichi lo scambio di più messaggi tra client e servizi per una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="f8b01-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="f8b01-115">Questo può dipendere dal comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza).</span><span class="sxs-lookup"><span data-stu-id="f8b01-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="f8b01-116">Pertanto, il numero di eventi `MessageReceivedByTransport` generati varia in base all'associazione del servizio e alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="f8b01-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8b01-117">Questo evento non viene generato per i trasporti unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="f8b01-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f8b01-118">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f8b01-118">Message</span></span>  
 <span data-ttu-id="f8b01-119">Il trasporto ha ricevuto un messaggio da '%1'.</span><span class="sxs-lookup"><span data-stu-id="f8b01-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f8b01-120">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f8b01-120">Details</span></span>  
  
|<span data-ttu-id="f8b01-121">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f8b01-121">Data Item Name</span></span>|<span data-ttu-id="f8b01-122">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f8b01-122">Data Item Type</span></span>|<span data-ttu-id="f8b01-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8b01-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f8b01-124">Indirizzo di ascolto</span><span class="sxs-lookup"><span data-stu-id="f8b01-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="f8b01-125">Indirizzo che riceve il messaggio.</span><span class="sxs-lookup"><span data-stu-id="f8b01-125">The address that received the message.</span></span>|  
|<span data-ttu-id="f8b01-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f8b01-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="f8b01-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="f8b01-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f8b01-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="f8b01-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f8b01-129">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f8b01-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f8b01-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f8b01-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f8b01-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f8b01-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
