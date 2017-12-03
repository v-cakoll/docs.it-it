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
ms.openlocfilehash: a0b286264cee3d9a0c2ef1df1c6f215240148f98
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="82971-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="82971-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="82971-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="82971-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82971-104">ID</span><span class="sxs-lookup"><span data-stu-id="82971-104">ID</span></span>|<span data-ttu-id="82971-105">221</span><span class="sxs-lookup"><span data-stu-id="82971-105">221</span></span>|  
|<span data-ttu-id="82971-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="82971-106">Keywords</span></span>|<span data-ttu-id="82971-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82971-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="82971-108">Livello</span><span class="sxs-lookup"><span data-stu-id="82971-108">Level</span></span>|<span data-ttu-id="82971-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="82971-109">Information</span></span>|  
|<span data-ttu-id="82971-110">Canale</span><span class="sxs-lookup"><span data-stu-id="82971-110">Channel</span></span>|<span data-ttu-id="82971-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="82971-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="82971-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82971-112">Description</span></span>  
 <span data-ttu-id="82971-113">Questo evento viene generato quando il modello di servizi riceve un messaggio dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="82971-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="82971-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="82971-114">Message</span></span>  
 <span data-ttu-id="82971-115">Il dispatcher ha ricevuto un messaggio dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="82971-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="82971-116">ID di correlazione == '%1'.</span><span class="sxs-lookup"><span data-stu-id="82971-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="82971-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="82971-117">Details</span></span>  
  
|<span data-ttu-id="82971-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="82971-118">Data Item Name</span></span>|<span data-ttu-id="82971-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="82971-119">Data Item Type</span></span>|<span data-ttu-id="82971-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82971-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="82971-121">ID correlazione</span><span class="sxs-lookup"><span data-stu-id="82971-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="82971-122">ID attività utilizzato per correlare un evento `MessageSentToTransport` da un servizio o un client all'elemento `MessageReceivedFromTransport` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="82971-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="82971-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="82971-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="82971-124">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="82971-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="82971-125">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="82971-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="82971-126">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="82971-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="82971-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="82971-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="82971-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="82971-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
