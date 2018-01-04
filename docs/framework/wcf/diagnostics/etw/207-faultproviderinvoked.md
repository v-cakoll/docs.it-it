---
title: 207 - FaultProviderInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9035739f8625a07e8bf2b9bce2fe109880676405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="ec2cf-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="ec2cf-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ec2cf-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="ec2cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec2cf-104">ID</span><span class="sxs-lookup"><span data-stu-id="ec2cf-104">ID</span></span>|<span data-ttu-id="ec2cf-105">207</span><span class="sxs-lookup"><span data-stu-id="ec2cf-105">207</span></span>|  
|<span data-ttu-id="ec2cf-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ec2cf-106">Keywords</span></span>|<span data-ttu-id="ec2cf-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ec2cf-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ec2cf-108">Livello</span><span class="sxs-lookup"><span data-stu-id="ec2cf-108">Level</span></span>|<span data-ttu-id="ec2cf-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="ec2cf-109">Information</span></span>|  
|<span data-ttu-id="ec2cf-110">Canale</span><span class="sxs-lookup"><span data-stu-id="ec2cf-110">Channel</span></span>|<span data-ttu-id="ec2cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ec2cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec2cf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec2cf-112">Description</span></span>  
 <span data-ttu-id="ec2cf-113">Questo evento viene generato dopo che è stato richiamato un elemento `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec2cf-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="ec2cf-114">Message</span></span>  
 <span data-ttu-id="ec2cf-115">FaultProvider di tipo '%1' richiamato dal dispatcher con un'eccezione di tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec2cf-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ec2cf-116">Details</span></span>  
  
|<span data-ttu-id="ec2cf-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="ec2cf-117">Data Item Name</span></span>|<span data-ttu-id="ec2cf-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="ec2cf-118">Data Item Type</span></span>|<span data-ttu-id="ec2cf-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec2cf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec2cf-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="ec2cf-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="ec2cf-121">Nome completo CLR del tipo dell'elemento `FaultProvider` richiamato.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="ec2cf-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="ec2cf-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="ec2cf-123">Nome completo CLR dell'eccezione usata da `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="ec2cf-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="ec2cf-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="ec2cf-125">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ec2cf-126">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ec2cf-127">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ec2cf-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ec2cf-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ec2cf-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ec2cf-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
