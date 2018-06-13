---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 92ec664aead15470fbed576bf157d64d984ddebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460434"
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="db298-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="db298-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="db298-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="db298-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db298-104">Id</span><span class="sxs-lookup"><span data-stu-id="db298-104">Id</span></span>|<span data-ttu-id="db298-105">220</span><span class="sxs-lookup"><span data-stu-id="db298-105">220</span></span>|  
|<span data-ttu-id="db298-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="db298-106">Keywords</span></span>|<span data-ttu-id="db298-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="db298-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="db298-108">Livello</span><span class="sxs-lookup"><span data-stu-id="db298-108">Level</span></span>|<span data-ttu-id="db298-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="db298-109">Information</span></span>|  
|<span data-ttu-id="db298-110">Canale</span><span class="sxs-lookup"><span data-stu-id="db298-110">Channel</span></span>|<span data-ttu-id="db298-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="db298-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="db298-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db298-112">Description</span></span>  
 <span data-ttu-id="db298-113">Questo evento viene generato quando il modello di servizi invia un messaggio al trasporto.</span><span class="sxs-lookup"><span data-stu-id="db298-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db298-114">Questo evento non verrà generato per i trasporti unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="db298-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="db298-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="db298-115">Message</span></span>  
 <span data-ttu-id="db298-116">Il dispatcher ha inviato un messaggio al trasporto.</span><span class="sxs-lookup"><span data-stu-id="db298-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="db298-117">ID di correlazione == '%1'.</span><span class="sxs-lookup"><span data-stu-id="db298-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="db298-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="db298-118">Details</span></span>  
  
|<span data-ttu-id="db298-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="db298-119">Data Item Name</span></span>|<span data-ttu-id="db298-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="db298-120">Data Item Type</span></span>|<span data-ttu-id="db298-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db298-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="db298-122">ID correlazione</span><span class="sxs-lookup"><span data-stu-id="db298-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="db298-123">ID attività utilizzato per correlare un evento `MessageSentToTransport` da un servizio o un client all'elemento `MessageReceivedFromTransport` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="db298-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="db298-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="db298-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="db298-125">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="db298-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="db298-126">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso&#124;percorso virtuale servizio&#124;nomeservizio '.</span><span class="sxs-lookup"><span data-stu-id="db298-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="db298-127">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="db298-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="db298-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="db298-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="db298-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="db298-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
