---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458683"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="6cabf-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="6cabf-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="6cabf-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6cabf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6cabf-104">Id</span><span class="sxs-lookup"><span data-stu-id="6cabf-104">ID</span></span>|<span data-ttu-id="6cabf-105">216</span><span class="sxs-lookup"><span data-stu-id="6cabf-105">216</span></span>|  
|<span data-ttu-id="6cabf-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6cabf-106">Keywords</span></span>|<span data-ttu-id="6cabf-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6cabf-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6cabf-108">Livello</span><span class="sxs-lookup"><span data-stu-id="6cabf-108">Level</span></span>|<span data-ttu-id="6cabf-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="6cabf-109">Information</span></span>|  
|<span data-ttu-id="6cabf-110">Canale</span><span class="sxs-lookup"><span data-stu-id="6cabf-110">Channel</span></span>|<span data-ttu-id="6cabf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6cabf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6cabf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6cabf-112">Description</span></span>  
 <span data-ttu-id="6cabf-113">Questo evento si verifica nel caso in cui un trasporto basato su TCP invia un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6cabf-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="6cabf-114">A livello di trasporto è possibile scambiare più messaggi tra client e servizi per una sola operazione.</span><span class="sxs-lookup"><span data-stu-id="6cabf-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="6cabf-115">Ciò può essere dovuto a un comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza).</span><span class="sxs-lookup"><span data-stu-id="6cabf-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="6cabf-116">Pertanto, il numero di **MessageSentByTransport** gli eventi generati variano in base all'associazione del servizio e la relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="6cabf-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6cabf-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="6cabf-117">Message</span></span>  
 <span data-ttu-id="6cabf-118">Il trasporto ha inviato un messaggio a '%1'.</span><span class="sxs-lookup"><span data-stu-id="6cabf-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6cabf-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6cabf-119">Details</span></span>  
  
|<span data-ttu-id="6cabf-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="6cabf-120">Data Item Name</span></span>|<span data-ttu-id="6cabf-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="6cabf-121">Data Item Type</span></span>|<span data-ttu-id="6cabf-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6cabf-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6cabf-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="6cabf-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="6cabf-124">L'indirizzo a cui è stato inviato il messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="6cabf-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="6cabf-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="6cabf-125">HostReference</span></span>|<span data-ttu-id="6cabf-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="6cabf-126">xs:string</span></span>|<span data-ttu-id="6cabf-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="6cabf-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6cabf-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="6cabf-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6cabf-129">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6cabf-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6cabf-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6cabf-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6cabf-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6cabf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
