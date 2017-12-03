---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64dcdb3a928d2ec05cd7dac557b6db10cb4a6511
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="9955d-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9955d-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9955d-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9955d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9955d-104">ID</span><span class="sxs-lookup"><span data-stu-id="9955d-104">ID</span></span>|<span data-ttu-id="9955d-105">212</span><span class="sxs-lookup"><span data-stu-id="9955d-105">212</span></span>|  
|<span data-ttu-id="9955d-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9955d-106">Keywords</span></span>|<span data-ttu-id="9955d-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9955d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9955d-108">Livello</span><span class="sxs-lookup"><span data-stu-id="9955d-108">Level</span></span>|<span data-ttu-id="9955d-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="9955d-109">Information</span></span>|  
|<span data-ttu-id="9955d-110">Canale</span><span class="sxs-lookup"><span data-stu-id="9955d-110">Channel</span></span>|<span data-ttu-id="9955d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9955d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9955d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9955d-112">Description</span></span>  
 <span data-ttu-id="9955d-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeCall` su un `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="9955d-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9955d-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="9955d-114">Message</span></span>  
 <span data-ttu-id="9955d-115">Il dispatcher ha richiamato 'BeforeCall' in un ParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="9955d-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9955d-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9955d-116">Details</span></span>  
  
|<span data-ttu-id="9955d-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="9955d-117">Data Item Name</span></span>|<span data-ttu-id="9955d-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="9955d-118">Data Item Type</span></span>|<span data-ttu-id="9955d-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9955d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9955d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="9955d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="9955d-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="9955d-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="9955d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9955d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9955d-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="9955d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9955d-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9955d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9955d-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9955d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9955d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9955d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9955d-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9955d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
