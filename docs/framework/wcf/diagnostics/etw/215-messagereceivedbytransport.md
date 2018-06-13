---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: a8ba90b88ef8dbe3c8651bc565da61aae16a0a4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460903"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="70a0e-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="70a0e-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="70a0e-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="70a0e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="70a0e-104">ID</span><span class="sxs-lookup"><span data-stu-id="70a0e-104">ID</span></span>|<span data-ttu-id="70a0e-105">215</span><span class="sxs-lookup"><span data-stu-id="70a0e-105">215</span></span>|  
|<span data-ttu-id="70a0e-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="70a0e-106">Keywords</span></span>|<span data-ttu-id="70a0e-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="70a0e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="70a0e-108">Livello</span><span class="sxs-lookup"><span data-stu-id="70a0e-108">Level</span></span>|<span data-ttu-id="70a0e-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="70a0e-109">Information</span></span>|  
|<span data-ttu-id="70a0e-110">Canale</span><span class="sxs-lookup"><span data-stu-id="70a0e-110">Channel</span></span>|<span data-ttu-id="70a0e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="70a0e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="70a0e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70a0e-112">Description</span></span>  
 <span data-ttu-id="70a0e-113">Questo evento si verifica quando un trasporto basato su TCP riceve un messaggio.</span><span class="sxs-lookup"><span data-stu-id="70a0e-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="70a0e-114">Si noti che a livello di trasporto è possibile che si verifichi lo scambio di più messaggi tra client e servizi per una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="70a0e-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="70a0e-115">Questo può dipendere dal comportamento dell'infrastruttura (un esempio valido può essere rappresentato dalla sicurezza).</span><span class="sxs-lookup"><span data-stu-id="70a0e-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="70a0e-116">Pertanto, il numero di eventi `MessageReceivedByTransport` generati varia in base all'associazione del servizio e alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="70a0e-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70a0e-117">Questo evento non viene generato per i trasporti unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="70a0e-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="70a0e-118">Messaggio</span><span class="sxs-lookup"><span data-stu-id="70a0e-118">Message</span></span>  
 <span data-ttu-id="70a0e-119">Il trasporto ha ricevuto un messaggio da '%1'.</span><span class="sxs-lookup"><span data-stu-id="70a0e-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="70a0e-120">Dettagli</span><span class="sxs-lookup"><span data-stu-id="70a0e-120">Details</span></span>  
  
|<span data-ttu-id="70a0e-121">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="70a0e-121">Data Item Name</span></span>|<span data-ttu-id="70a0e-122">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="70a0e-122">Data Item Type</span></span>|<span data-ttu-id="70a0e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70a0e-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="70a0e-124">Indirizzo di ascolto</span><span class="sxs-lookup"><span data-stu-id="70a0e-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="70a0e-125">Indirizzo che riceve il messaggio.</span><span class="sxs-lookup"><span data-stu-id="70a0e-125">The address that received the message.</span></span>|  
|<span data-ttu-id="70a0e-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="70a0e-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="70a0e-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="70a0e-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="70a0e-128">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="70a0e-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="70a0e-129">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="70a0e-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="70a0e-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="70a0e-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="70a0e-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="70a0e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
