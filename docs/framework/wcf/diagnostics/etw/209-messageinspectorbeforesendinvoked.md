---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3341f9ae5600536a7d824034582bf232f5be90ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="e6654-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="e6654-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="e6654-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e6654-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6654-104">ID</span><span class="sxs-lookup"><span data-stu-id="e6654-104">ID</span></span>|<span data-ttu-id="e6654-105">209</span><span class="sxs-lookup"><span data-stu-id="e6654-105">209</span></span>|  
|<span data-ttu-id="e6654-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e6654-106">Keywords</span></span>|<span data-ttu-id="e6654-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e6654-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e6654-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e6654-108">Level</span></span>|<span data-ttu-id="e6654-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="e6654-109">Information</span></span>|  
|<span data-ttu-id="e6654-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e6654-110">Channel</span></span>|<span data-ttu-id="e6654-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e6654-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e6654-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6654-112">Description</span></span>  
 <span data-ttu-id="e6654-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeSend` su un controllo dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="e6654-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e6654-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e6654-114">Message</span></span>  
 <span data-ttu-id="e6654-115">'BeforeSendRequest' richiamato dal dispatcher in un elemento MessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="e6654-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e6654-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e6654-116">Details</span></span>  
  
|<span data-ttu-id="e6654-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e6654-117">Data Item Name</span></span>|<span data-ttu-id="e6654-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e6654-118">Data Item Type</span></span>|<span data-ttu-id="e6654-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6654-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e6654-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e6654-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e6654-121">Nome completo CLR del tipo dell'elemento `MessageInspector` richiamato.</span><span class="sxs-lookup"><span data-stu-id="e6654-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="e6654-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e6654-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e6654-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="e6654-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e6654-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="e6654-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e6654-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e6654-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e6654-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e6654-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e6654-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e6654-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
