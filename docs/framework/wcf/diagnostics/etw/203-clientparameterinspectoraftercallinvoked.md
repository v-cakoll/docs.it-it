---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89aea40ece7717abf37c8a014e4b375e3b1df9a1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="d9bdf-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="d9bdf-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d9bdf-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d9bdf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9bdf-104">ID</span><span class="sxs-lookup"><span data-stu-id="d9bdf-104">ID</span></span>|<span data-ttu-id="d9bdf-105">203</span><span class="sxs-lookup"><span data-stu-id="d9bdf-105">203</span></span>|  
|<span data-ttu-id="d9bdf-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d9bdf-106">Keywords</span></span>|<span data-ttu-id="d9bdf-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d9bdf-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d9bdf-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d9bdf-108">Level</span></span>|<span data-ttu-id="d9bdf-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="d9bdf-109">Information</span></span>|  
|<span data-ttu-id="d9bdf-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d9bdf-110">Channel</span></span>|<span data-ttu-id="d9bdf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d9bdf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d9bdf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9bdf-112">Description</span></span>  
 <span data-ttu-id="d9bdf-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterCall` su un controllo dei parametri client.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d9bdf-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d9bdf-114">Message</span></span>  
 <span data-ttu-id="d9bdf-115">'AfterCall' richiamato dal dispatcher in un elemento ClientParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d9bdf-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d9bdf-116">Details</span></span>  
  
|<span data-ttu-id="d9bdf-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d9bdf-117">Data Item Name</span></span>|<span data-ttu-id="d9bdf-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d9bdf-118">Data Item Type</span></span>|<span data-ttu-id="d9bdf-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9bdf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d9bdf-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="d9bdf-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="d9bdf-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="d9bdf-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d9bdf-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d9bdf-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d9bdf-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d9bdf-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d9bdf-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d9bdf-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d9bdf-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
