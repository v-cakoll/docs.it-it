---
title: 206 - ErrorHandlerInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 84470cbaf7ba7951ef59b130c696462079216cde
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="9572f-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="9572f-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9572f-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="9572f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9572f-104">ID</span><span class="sxs-lookup"><span data-stu-id="9572f-104">ID</span></span>|<span data-ttu-id="9572f-105">206</span><span class="sxs-lookup"><span data-stu-id="9572f-105">206</span></span>|  
|<span data-ttu-id="9572f-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9572f-106">Keywords</span></span>|<span data-ttu-id="9572f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9572f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9572f-108">Livello</span><span class="sxs-lookup"><span data-stu-id="9572f-108">Level</span></span>|<span data-ttu-id="9572f-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="9572f-109">Information</span></span>|  
|<span data-ttu-id="9572f-110">Canale</span><span class="sxs-lookup"><span data-stu-id="9572f-110">Channel</span></span>|<span data-ttu-id="9572f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9572f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9572f-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9572f-112">Description</span></span>  
 <span data-ttu-id="9572f-113">Questo evento viene generato dopo che un `ErrorHandler` ha avuto la possibilità di gestire un'eccezione verificatasi in un'operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="9572f-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9572f-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="9572f-114">Message</span></span>  
 <span data-ttu-id="9572f-115">Il Dispatcher ha richiamato ErrorHandler di tipo '%1' con un'eccezione di tipo '%3'.</span><span class="sxs-lookup"><span data-stu-id="9572f-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="9572f-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="9572f-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9572f-117">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9572f-117">Details</span></span>  
  
|<span data-ttu-id="9572f-118">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="9572f-118">Data Item Name</span></span>|<span data-ttu-id="9572f-119">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="9572f-119">Data Item Type</span></span>|<span data-ttu-id="9572f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9572f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9572f-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="9572f-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="9572f-122">Nome completo CLR del tipo dell'elemento `ErrorHandler` richiamato.</span><span class="sxs-lookup"><span data-stu-id="9572f-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="9572f-123">Handled</span><span class="sxs-lookup"><span data-stu-id="9572f-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="9572f-124">`true` se l'errore è stato gestito. In caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9572f-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="9572f-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="9572f-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="9572f-126">Nome completo CLR dell'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="9572f-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="9572f-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="9572f-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="9572f-128">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="9572f-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9572f-129">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9572f-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9572f-130">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9572f-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9572f-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9572f-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9572f-132">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9572f-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
