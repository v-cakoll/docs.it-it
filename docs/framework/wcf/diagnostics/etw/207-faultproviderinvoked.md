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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fe3698653be04119c84c5f423207458e9d033dc1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="8a875-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="8a875-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="8a875-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8a875-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a875-104">ID</span><span class="sxs-lookup"><span data-stu-id="8a875-104">ID</span></span>|<span data-ttu-id="8a875-105">207</span><span class="sxs-lookup"><span data-stu-id="8a875-105">207</span></span>|  
|<span data-ttu-id="8a875-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8a875-106">Keywords</span></span>|<span data-ttu-id="8a875-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8a875-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8a875-108">Livello</span><span class="sxs-lookup"><span data-stu-id="8a875-108">Level</span></span>|<span data-ttu-id="8a875-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="8a875-109">Information</span></span>|  
|<span data-ttu-id="8a875-110">Canale</span><span class="sxs-lookup"><span data-stu-id="8a875-110">Channel</span></span>|<span data-ttu-id="8a875-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8a875-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a875-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a875-112">Description</span></span>  
 <span data-ttu-id="8a875-113">Questo evento viene generato dopo che è stato richiamato un elemento `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="8a875-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a875-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="8a875-114">Message</span></span>  
 <span data-ttu-id="8a875-115">FaultProvider di tipo '%1' richiamato dal dispatcher con un'eccezione di tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="8a875-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a875-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8a875-116">Details</span></span>  
  
|<span data-ttu-id="8a875-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="8a875-117">Data Item Name</span></span>|<span data-ttu-id="8a875-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="8a875-118">Data Item Type</span></span>|<span data-ttu-id="8a875-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a875-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a875-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="8a875-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="8a875-121">Nome completo CLR del tipo dell'elemento `FaultProvider` richiamato.</span><span class="sxs-lookup"><span data-stu-id="8a875-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="8a875-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="8a875-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="8a875-123">Nome completo CLR dell'eccezione usata da `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="8a875-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="8a875-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="8a875-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="8a875-125">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="8a875-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8a875-126">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="8a875-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8a875-127">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="8a875-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8a875-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a875-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8a875-129">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8a875-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
