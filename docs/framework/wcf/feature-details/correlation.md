---
title: Correlazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d15609db250e4743ae2a7a1b6c3c355600704f02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="correlation"></a><span data-ttu-id="a76be-102">Correlazione</span><span class="sxs-lookup"><span data-stu-id="a76be-102">Correlation</span></span>
<span data-ttu-id="a76be-103">Nel caso in cui le applicazioni del servizio flusso di lavoro comunichino con gli altri servizi, è importante che i messaggi vengano inviati all'istanza del flusso di lavoro appropriata.</span><span class="sxs-lookup"><span data-stu-id="a76be-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="a76be-104">La correlazione fornisce il meccanismo adibito a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="a76be-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="a76be-105">Gli argomenti in questa sezione forniscono una panoramica della correlazione e del relativo utilizzo in vari scenari del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a76be-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a76be-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a76be-106">In This Section</span></span>  
 [<span data-ttu-id="a76be-107">Panoramica della correlazione</span><span class="sxs-lookup"><span data-stu-id="a76be-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="a76be-108">Offre una panoramica dei tipi di correlazione disponibili in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a76be-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="a76be-109">Scambio del contesto</span><span class="sxs-lookup"><span data-stu-id="a76be-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="a76be-110">Descrive la correlazione di scambio del contesto.</span><span class="sxs-lookup"><span data-stu-id="a76be-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="a76be-111">Duplex durevole</span><span class="sxs-lookup"><span data-stu-id="a76be-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="a76be-112">Descrive la correlazione duplex durevole.</span><span class="sxs-lookup"><span data-stu-id="a76be-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="a76be-113">Contenuto in base</span><span class="sxs-lookup"><span data-stu-id="a76be-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="a76be-114">Descrive la correlazione basata sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="a76be-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="a76be-115">Request / Reply</span><span class="sxs-lookup"><span data-stu-id="a76be-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="a76be-116">Descrive la correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="a76be-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="a76be-117">Risoluzione dei problemi di correlazione</span><span class="sxs-lookup"><span data-stu-id="a76be-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="a76be-118">Fornisce i metodi per la risoluzione dei problemi relativi alla correlazione.</span><span class="sxs-lookup"><span data-stu-id="a76be-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76be-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a76be-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="a76be-120">Correlazione basata sul contenuto</span><span class="sxs-lookup"><span data-stu-id="a76be-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="a76be-121">Calcolatrice correlata</span><span class="sxs-lookup"><span data-stu-id="a76be-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
