---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d54930a29a24dab97ce403c2808fb74b8cbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="37dbb-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="37dbb-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="37dbb-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37dbb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37dbb-104">Id</span><span class="sxs-lookup"><span data-stu-id="37dbb-104">ID</span></span>|<span data-ttu-id="37dbb-105">301</span><span class="sxs-lookup"><span data-stu-id="37dbb-105">301</span></span>|  
|<span data-ttu-id="37dbb-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="37dbb-106">Keywords</span></span>|<span data-ttu-id="37dbb-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="37dbb-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="37dbb-108">Livello</span><span class="sxs-lookup"><span data-stu-id="37dbb-108">Level</span></span>|<span data-ttu-id="37dbb-109">Errore</span><span class="sxs-lookup"><span data-stu-id="37dbb-109">Error</span></span>|  
|<span data-ttu-id="37dbb-110">Canale</span><span class="sxs-lookup"><span data-stu-id="37dbb-110">Channel</span></span>|<span data-ttu-id="37dbb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="37dbb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37dbb-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37dbb-112">Description</span></span>  
 <span data-ttu-id="37dbb-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="37dbb-113">This event is emitted from user code.</span></span> <span data-ttu-id="37dbb-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un errore definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="37dbb-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="37dbb-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="37dbb-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="37dbb-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="37dbb-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37dbb-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="37dbb-117">Message</span></span>  
 <span data-ttu-id="37dbb-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="37dbb-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="37dbb-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="37dbb-119">Details</span></span>  
  
|<span data-ttu-id="37dbb-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="37dbb-120">Data Item Name</span></span>|<span data-ttu-id="37dbb-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="37dbb-121">Data Item Type</span></span>|<span data-ttu-id="37dbb-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37dbb-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37dbb-123">nome</span><span class="sxs-lookup"><span data-stu-id="37dbb-123">Name</span></span>|`xs:string`|<span data-ttu-id="37dbb-124">Nome dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="37dbb-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="37dbb-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="37dbb-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="37dbb-126">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="37dbb-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="37dbb-127">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="37dbb-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="37dbb-128">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="37dbb-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="37dbb-129">Payload</span><span class="sxs-lookup"><span data-stu-id="37dbb-129">Payload</span></span>|`xs:string`|<span data-ttu-id="37dbb-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="37dbb-130">The user-defined payload of the event.</span></span>|
