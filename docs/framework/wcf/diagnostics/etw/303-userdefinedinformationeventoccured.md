---
title: 303 - UserDefinedInformationEventOccured
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bd4d94d457793eb036f037cc6dc22bff6d26ee2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="9a251-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="9a251-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="9a251-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9a251-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a251-104">Id</span><span class="sxs-lookup"><span data-stu-id="9a251-104">ID</span></span>|<span data-ttu-id="9a251-105">303</span><span class="sxs-lookup"><span data-stu-id="9a251-105">303</span></span>|  
|<span data-ttu-id="9a251-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9a251-106">Keywords</span></span>|<span data-ttu-id="9a251-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="9a251-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="9a251-108">Livello</span><span class="sxs-lookup"><span data-stu-id="9a251-108">Level</span></span>|<span data-ttu-id="9a251-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="9a251-109">Information</span></span>|  
|<span data-ttu-id="9a251-110">Canale</span><span class="sxs-lookup"><span data-stu-id="9a251-110">Channel</span></span>|<span data-ttu-id="9a251-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9a251-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9a251-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a251-112">Description</span></span>  
 <span data-ttu-id="9a251-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="9a251-113">This event is emitted from user code.</span></span> <span data-ttu-id="9a251-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un evento informativo definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="9a251-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="9a251-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="9a251-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="9a251-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="9a251-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9a251-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="9a251-117">Message</span></span>  
 <span data-ttu-id="9a251-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="9a251-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="9a251-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9a251-119">Details</span></span>  
  
|<span data-ttu-id="9a251-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="9a251-120">Data Item Name</span></span>|<span data-ttu-id="9a251-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="9a251-121">Data Item Type</span></span>|<span data-ttu-id="9a251-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a251-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9a251-123">nome</span><span class="sxs-lookup"><span data-stu-id="9a251-123">Name</span></span>|`xs:string`|<span data-ttu-id="9a251-124">Nome dell'evento definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="9a251-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="9a251-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="9a251-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="9a251-126">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="9a251-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9a251-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9a251-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9a251-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9a251-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9a251-129">Payload</span><span class="sxs-lookup"><span data-stu-id="9a251-129">Payload</span></span>|`xs:string`|<span data-ttu-id="9a251-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="9a251-130">The user-defined payload of the event.</span></span>|
