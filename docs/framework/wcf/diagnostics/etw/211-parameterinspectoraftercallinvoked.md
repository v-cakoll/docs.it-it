---
title: 211 - ParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69a9b6fe30a4ffa7f72e70b5aef740b2b772dd69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="d76ac-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="d76ac-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d76ac-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="d76ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d76ac-104">ID</span><span class="sxs-lookup"><span data-stu-id="d76ac-104">ID</span></span>|<span data-ttu-id="d76ac-105">211</span><span class="sxs-lookup"><span data-stu-id="d76ac-105">211</span></span>|  
|<span data-ttu-id="d76ac-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d76ac-106">Keywords</span></span>|<span data-ttu-id="d76ac-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d76ac-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d76ac-108">Livello</span><span class="sxs-lookup"><span data-stu-id="d76ac-108">Level</span></span>|<span data-ttu-id="d76ac-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="d76ac-109">Information</span></span>|  
|<span data-ttu-id="d76ac-110">Canale</span><span class="sxs-lookup"><span data-stu-id="d76ac-110">Channel</span></span>|<span data-ttu-id="d76ac-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d76ac-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d76ac-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d76ac-112">Description</span></span>  
 <span data-ttu-id="d76ac-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterCall` su un `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="d76ac-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d76ac-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="d76ac-114">Message</span></span>  
 <span data-ttu-id="d76ac-115">Il dispatcher ha richiamato 'AfterCall' in un ParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="d76ac-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d76ac-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d76ac-116">Details</span></span>  
  
|<span data-ttu-id="d76ac-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="d76ac-117">Data Item Name</span></span>|<span data-ttu-id="d76ac-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="d76ac-118">Data Item Type</span></span>|<span data-ttu-id="d76ac-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d76ac-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d76ac-120">Nome tipo</span><span class="sxs-lookup"><span data-stu-id="d76ac-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="d76ac-121">Nome completo CLR del tipo dell'elemento `ParameterInspector` richiamato.</span><span class="sxs-lookup"><span data-stu-id="d76ac-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="d76ac-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d76ac-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d76ac-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="d76ac-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d76ac-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d76ac-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d76ac-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d76ac-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d76ac-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d76ac-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d76ac-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d76ac-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
