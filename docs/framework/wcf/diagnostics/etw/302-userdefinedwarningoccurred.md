---
title: 302 - UserDefinedWarningOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae455c9eec2335fcf6eb5473932bd8d9e5d2db95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="0c196-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="0c196-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="0c196-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0c196-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c196-104">Id</span><span class="sxs-lookup"><span data-stu-id="0c196-104">ID</span></span>|<span data-ttu-id="0c196-105">302</span><span class="sxs-lookup"><span data-stu-id="0c196-105">302</span></span>|  
|<span data-ttu-id="0c196-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0c196-106">Keywords</span></span>|<span data-ttu-id="0c196-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="0c196-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="0c196-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0c196-108">Level</span></span>|<span data-ttu-id="0c196-109">Avviso</span><span class="sxs-lookup"><span data-stu-id="0c196-109">Warning</span></span>|  
|<span data-ttu-id="0c196-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0c196-110">Channel</span></span>|<span data-ttu-id="0c196-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0c196-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0c196-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c196-112">Description</span></span>  
 <span data-ttu-id="0c196-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="0c196-113">This event is emitted from user code.</span></span> <span data-ttu-id="0c196-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un evento di avviso definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="0c196-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="0c196-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="0c196-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="0c196-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="0c196-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0c196-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0c196-117">Message</span></span>  
 <span data-ttu-id="0c196-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="0c196-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="0c196-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0c196-119">Details</span></span>  
  
|<span data-ttu-id="0c196-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0c196-120">Data Item Name</span></span>|<span data-ttu-id="0c196-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0c196-121">Data Item Type</span></span>|<span data-ttu-id="0c196-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c196-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0c196-123">nome</span><span class="sxs-lookup"><span data-stu-id="0c196-123">Name</span></span>|`xs:string`|<span data-ttu-id="0c196-124">Nome dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0c196-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="0c196-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="0c196-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="0c196-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="0c196-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0c196-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="0c196-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0c196-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0c196-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0c196-129">Payload</span><span class="sxs-lookup"><span data-stu-id="0c196-129">Payload</span></span>|`xs:string`|<span data-ttu-id="0c196-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0c196-130">The user-defined payload of the event.</span></span>|
