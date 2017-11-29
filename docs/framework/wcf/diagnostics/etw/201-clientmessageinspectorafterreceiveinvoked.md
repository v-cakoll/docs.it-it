---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 907f4404e234ada2cf084f531a4de8fcfc84d6c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="f0590-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="f0590-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f0590-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f0590-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0590-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0590-104">ID</span></span>|<span data-ttu-id="f0590-105">201</span><span class="sxs-lookup"><span data-stu-id="f0590-105">201</span></span>|  
|<span data-ttu-id="f0590-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f0590-106">Keywords</span></span>|<span data-ttu-id="f0590-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0590-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f0590-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f0590-108">Level</span></span>|<span data-ttu-id="f0590-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="f0590-109">Information</span></span>|  
|<span data-ttu-id="f0590-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f0590-110">Channel</span></span>|<span data-ttu-id="f0590-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f0590-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0590-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0590-112">Description</span></span>  
 <span data-ttu-id="f0590-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `AfterReceiveReply` su un controllo dei messaggi client.</span><span class="sxs-lookup"><span data-stu-id="f0590-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0590-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f0590-114">Message</span></span>  
 <span data-ttu-id="f0590-115">'AfterReceiveReply' richiamato dal dispatcher in un elemento ClientMessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="f0590-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0590-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f0590-116">Details</span></span>  
  
|<span data-ttu-id="f0590-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f0590-117">Data Item Name</span></span>|<span data-ttu-id="f0590-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f0590-118">Data Item Type</span></span>|<span data-ttu-id="f0590-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0590-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0590-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f0590-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f0590-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="f0590-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="f0590-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f0590-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f0590-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="f0590-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f0590-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="f0590-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f0590-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f0590-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f0590-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0590-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f0590-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f0590-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
