---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f896055d958947e54ee77bb812b8d424e6f4f94f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="51b36-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="51b36-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="51b36-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="51b36-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51b36-104">ID</span><span class="sxs-lookup"><span data-stu-id="51b36-104">ID</span></span>|<span data-ttu-id="51b36-105">204</span><span class="sxs-lookup"><span data-stu-id="51b36-105">204</span></span>|  
|<span data-ttu-id="51b36-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51b36-106">Keywords</span></span>|<span data-ttu-id="51b36-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="51b36-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="51b36-108">Livello</span><span class="sxs-lookup"><span data-stu-id="51b36-108">Level</span></span>|<span data-ttu-id="51b36-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="51b36-109">Information</span></span>|  
|<span data-ttu-id="51b36-110">Canale</span><span class="sxs-lookup"><span data-stu-id="51b36-110">Channel</span></span>|<span data-ttu-id="51b36-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="51b36-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="51b36-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51b36-112">Description</span></span>  
 <span data-ttu-id="51b36-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeCall` su un controllo dei parametri client.</span><span class="sxs-lookup"><span data-stu-id="51b36-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="51b36-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="51b36-114">Message</span></span>  
 <span data-ttu-id="51b36-115">'BeforeCall' richiamato dal dispatcher in un elemento ClientParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="51b36-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="51b36-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="51b36-116">Details</span></span>  
  
|<span data-ttu-id="51b36-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="51b36-117">Data Item Name</span></span>|<span data-ttu-id="51b36-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="51b36-118">Data Item Type</span></span>|<span data-ttu-id="51b36-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51b36-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="51b36-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="51b36-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="51b36-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="51b36-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="51b36-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="51b36-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="51b36-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="51b36-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="51b36-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="51b36-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="51b36-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="51b36-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="51b36-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="51b36-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="51b36-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="51b36-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
