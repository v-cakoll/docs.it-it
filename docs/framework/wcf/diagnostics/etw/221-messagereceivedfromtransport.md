---
title: 221 - MessageReceivedFromTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 139ca9e0fbe4d3f59d3d593f7785d5fb65e64702
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="5889d-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="5889d-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="5889d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5889d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5889d-104">Id</span><span class="sxs-lookup"><span data-stu-id="5889d-104">ID</span></span>|<span data-ttu-id="5889d-105">221</span><span class="sxs-lookup"><span data-stu-id="5889d-105">221</span></span>|  
|<span data-ttu-id="5889d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5889d-106">Keywords</span></span>|<span data-ttu-id="5889d-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5889d-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5889d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5889d-108">Level</span></span>|<span data-ttu-id="5889d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="5889d-109">Information</span></span>|  
|<span data-ttu-id="5889d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5889d-110">Channel</span></span>|<span data-ttu-id="5889d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5889d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5889d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5889d-112">Description</span></span>  
 <span data-ttu-id="5889d-113">Questo evento viene generato quando il modello di servizi riceve un messaggio dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="5889d-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5889d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5889d-114">Message</span></span>  
 <span data-ttu-id="5889d-115">Il dispatcher ha ricevuto un messaggio dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="5889d-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="5889d-116">ID di correlazione == '%1'.</span><span class="sxs-lookup"><span data-stu-id="5889d-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5889d-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5889d-117">Details</span></span>  
  
|<span data-ttu-id="5889d-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5889d-118">Data Item Name</span></span>|<span data-ttu-id="5889d-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5889d-119">Data Item Type</span></span>|<span data-ttu-id="5889d-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5889d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5889d-121">ID correlazione</span><span class="sxs-lookup"><span data-stu-id="5889d-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="5889d-122">ID attività utilizzato per correlare un evento `MessageSentToTransport` da un servizio o un client all'elemento `MessageReceivedFromTransport` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5889d-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="5889d-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="5889d-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="5889d-124">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="5889d-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5889d-125">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5889d-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5889d-126">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5889d-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5889d-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5889d-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5889d-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5889d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
