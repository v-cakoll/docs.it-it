---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: baf466bf63dcb9335a20eed8b563c222e09c7055
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="a63f9-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="a63f9-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="a63f9-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="a63f9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a63f9-104">ID</span><span class="sxs-lookup"><span data-stu-id="a63f9-104">ID</span></span>|<span data-ttu-id="a63f9-105">202</span><span class="sxs-lookup"><span data-stu-id="a63f9-105">202</span></span>|  
|<span data-ttu-id="a63f9-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a63f9-106">Keywords</span></span>|<span data-ttu-id="a63f9-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a63f9-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a63f9-108">Livello</span><span class="sxs-lookup"><span data-stu-id="a63f9-108">Level</span></span>|<span data-ttu-id="a63f9-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="a63f9-109">Information</span></span>|  
|<span data-ttu-id="a63f9-110">Canale</span><span class="sxs-lookup"><span data-stu-id="a63f9-110">Channel</span></span>|<span data-ttu-id="a63f9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a63f9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a63f9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a63f9-112">Description</span></span>  
 <span data-ttu-id="a63f9-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeSendRequest` su un controllo dei messaggi client.</span><span class="sxs-lookup"><span data-stu-id="a63f9-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a63f9-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="a63f9-114">Message</span></span>  
 <span data-ttu-id="a63f9-115">'BeforeSendRequest' richiamato dal dispatcher in un elemento ClientMessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="a63f9-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a63f9-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a63f9-116">Details</span></span>  
  
|<span data-ttu-id="a63f9-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="a63f9-117">Data Item Name</span></span>|<span data-ttu-id="a63f9-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="a63f9-118">Data Item Type</span></span>|<span data-ttu-id="a63f9-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a63f9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a63f9-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="a63f9-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="a63f9-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="a63f9-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="a63f9-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="a63f9-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="a63f9-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="a63f9-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a63f9-124">Il formato viene definito come ' nome sito Web dell'applicazione virtuale percorso &#124; Percorso virtuale servizio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a63f9-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a63f9-125">Esempio: ' Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a63f9-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a63f9-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a63f9-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a63f9-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a63f9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
