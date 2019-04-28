---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781719"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="2e372-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="2e372-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="2e372-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2e372-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2e372-104">Id</span><span class="sxs-lookup"><span data-stu-id="2e372-104">ID</span></span>|<span data-ttu-id="2e372-105">221</span><span class="sxs-lookup"><span data-stu-id="2e372-105">221</span></span>|  
|<span data-ttu-id="2e372-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2e372-106">Keywords</span></span>|<span data-ttu-id="2e372-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2e372-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2e372-108">Livello</span><span class="sxs-lookup"><span data-stu-id="2e372-108">Level</span></span>|<span data-ttu-id="2e372-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2e372-109">Information</span></span>|  
|<span data-ttu-id="2e372-110">Canale</span><span class="sxs-lookup"><span data-stu-id="2e372-110">Channel</span></span>|<span data-ttu-id="2e372-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2e372-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2e372-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e372-112">Description</span></span>  
 <span data-ttu-id="2e372-113">Questo evento viene generato quando il modello di servizi riceve un messaggio dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="2e372-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2e372-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="2e372-114">Message</span></span>  
 <span data-ttu-id="2e372-115">Il dispatcher ha ricevuto un messaggio dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="2e372-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="2e372-116">ID di correlazione == '%1'.</span><span class="sxs-lookup"><span data-stu-id="2e372-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2e372-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2e372-117">Details</span></span>  
  
|<span data-ttu-id="2e372-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="2e372-118">Data Item Name</span></span>|<span data-ttu-id="2e372-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="2e372-119">Data Item Type</span></span>|<span data-ttu-id="2e372-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e372-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2e372-121">ID correlazione</span><span class="sxs-lookup"><span data-stu-id="2e372-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="2e372-122">ID attività utilizzato per correlare un evento `MessageSentToTransport` da un servizio o un client all'elemento `MessageReceivedFromTransport` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2e372-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="2e372-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="2e372-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="2e372-124">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="2e372-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2e372-125">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="2e372-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2e372-126">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="2e372-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2e372-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2e372-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2e372-128">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2e372-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
