---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 253daea49ed36e27a23c55f3baf252344c0a34f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="a47aa-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="a47aa-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a47aa-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a47aa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a47aa-104">ID</span><span class="sxs-lookup"><span data-stu-id="a47aa-104">ID</span></span>|<span data-ttu-id="a47aa-105">208</span><span class="sxs-lookup"><span data-stu-id="a47aa-105">208</span></span>|  
|<span data-ttu-id="a47aa-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a47aa-106">Keywords</span></span>|<span data-ttu-id="a47aa-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a47aa-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a47aa-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a47aa-108">Level</span></span>|<span data-ttu-id="a47aa-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="a47aa-109">Information</span></span>|  
|<span data-ttu-id="a47aa-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a47aa-110">Channel</span></span>|<span data-ttu-id="a47aa-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a47aa-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a47aa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a47aa-112">Description</span></span>  
 <span data-ttu-id="a47aa-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterReceive` su un controllo dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="a47aa-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a47aa-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a47aa-114">Message</span></span>  
 <span data-ttu-id="a47aa-115">'AfterReceiveReply' richiamato dal dispatcher in un elemento MessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="a47aa-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a47aa-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a47aa-116">Details</span></span>  
  
|<span data-ttu-id="a47aa-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a47aa-117">Data Item Name</span></span>|<span data-ttu-id="a47aa-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a47aa-118">Data Item Type</span></span>|<span data-ttu-id="a47aa-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a47aa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a47aa-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="a47aa-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="a47aa-121">Nome completo CLR del tipo dell'elemento `MessageInspector` richiamato.</span><span class="sxs-lookup"><span data-stu-id="a47aa-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="a47aa-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a47aa-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a47aa-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="a47aa-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a47aa-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a47aa-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a47aa-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a47aa-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a47aa-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a47aa-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a47aa-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a47aa-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
