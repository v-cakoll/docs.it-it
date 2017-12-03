---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 461c9e423abb7b34edec4135f05f8fcf66244cfc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="5174f-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="5174f-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="5174f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5174f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5174f-104">ID</span><span class="sxs-lookup"><span data-stu-id="5174f-104">ID</span></span>|<span data-ttu-id="5174f-105">202</span><span class="sxs-lookup"><span data-stu-id="5174f-105">202</span></span>|  
|<span data-ttu-id="5174f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5174f-106">Keywords</span></span>|<span data-ttu-id="5174f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5174f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5174f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="5174f-108">Level</span></span>|<span data-ttu-id="5174f-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="5174f-109">Information</span></span>|  
|<span data-ttu-id="5174f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="5174f-110">Channel</span></span>|<span data-ttu-id="5174f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5174f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5174f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5174f-112">Description</span></span>  
 <span data-ttu-id="5174f-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeSendRequest` su un controllo dei messaggi client.</span><span class="sxs-lookup"><span data-stu-id="5174f-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5174f-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="5174f-114">Message</span></span>  
 <span data-ttu-id="5174f-115">'BeforeSendRequest' richiamato dal dispatcher in un elemento ClientMessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="5174f-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5174f-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5174f-116">Details</span></span>  
  
|<span data-ttu-id="5174f-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="5174f-117">Data Item Name</span></span>|<span data-ttu-id="5174f-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="5174f-118">Data Item Type</span></span>|<span data-ttu-id="5174f-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5174f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5174f-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="5174f-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="5174f-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="5174f-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="5174f-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="5174f-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="5174f-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="5174f-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5174f-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5174f-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5174f-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5174f-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5174f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5174f-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5174f-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5174f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
