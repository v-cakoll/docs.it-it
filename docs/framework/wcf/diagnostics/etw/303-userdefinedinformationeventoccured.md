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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc291469721915f399fe5acfa3200716939fee4c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="1159f-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="1159f-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="1159f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1159f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1159f-104">ID</span><span class="sxs-lookup"><span data-stu-id="1159f-104">ID</span></span>|<span data-ttu-id="1159f-105">303</span><span class="sxs-lookup"><span data-stu-id="1159f-105">303</span></span>|  
|<span data-ttu-id="1159f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="1159f-106">Keywords</span></span>|<span data-ttu-id="1159f-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="1159f-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="1159f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="1159f-108">Level</span></span>|<span data-ttu-id="1159f-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="1159f-109">Information</span></span>|  
|<span data-ttu-id="1159f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="1159f-110">Channel</span></span>|<span data-ttu-id="1159f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1159f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1159f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1159f-112">Description</span></span>  
 <span data-ttu-id="1159f-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="1159f-113">This event is emitted from user code.</span></span> <span data-ttu-id="1159f-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un evento informativo definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="1159f-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="1159f-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="1159f-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="1159f-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="1159f-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1159f-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="1159f-117">Message</span></span>  
 <span data-ttu-id="1159f-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="1159f-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="1159f-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1159f-119">Details</span></span>  
  
|<span data-ttu-id="1159f-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="1159f-120">Data Item Name</span></span>|<span data-ttu-id="1159f-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="1159f-121">Data Item Type</span></span>|<span data-ttu-id="1159f-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1159f-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1159f-123">Nome</span><span class="sxs-lookup"><span data-stu-id="1159f-123">Name</span></span>|`xs:string`|<span data-ttu-id="1159f-124">Nome dell'evento definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="1159f-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="1159f-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="1159f-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="1159f-126">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="1159f-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1159f-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="1159f-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1159f-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1159f-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1159f-129">Payload</span><span class="sxs-lookup"><span data-stu-id="1159f-129">Payload</span></span>|`xs:string`|<span data-ttu-id="1159f-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1159f-130">The user-defined payload of the event.</span></span>|
