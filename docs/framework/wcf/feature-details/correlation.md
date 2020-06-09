---
title: Correlation
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: e7ccb58b11003638e15bdbc7b7aa326abbac1b71
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579709"
---
# <a name="correlation"></a><span data-ttu-id="45245-102">Correlation</span><span class="sxs-lookup"><span data-stu-id="45245-102">Correlation</span></span>
<span data-ttu-id="45245-103">Nel caso in cui le applicazioni del servizio flusso di lavoro comunichino con gli altri servizi, è importante che i messaggi vengano inviati all'istanza del flusso di lavoro appropriata.</span><span class="sxs-lookup"><span data-stu-id="45245-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="45245-104">La correlazione fornisce il meccanismo adibito a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="45245-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="45245-105">Gli argomenti in questa sezione forniscono una panoramica della correlazione e del relativo utilizzo in vari scenari del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="45245-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45245-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="45245-106">In This Section</span></span>  
 [<span data-ttu-id="45245-107">Panoramica della correlazione</span><span class="sxs-lookup"><span data-stu-id="45245-107">Correlation Overview</span></span>](correlation-overview.md)  
 <span data-ttu-id="45245-108">Offre una panoramica dei tipi di correlazione disponibili in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45245-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="45245-109">Duplex durevole</span><span class="sxs-lookup"><span data-stu-id="45245-109">Durable Duplex</span></span>](durable-duplex-correlation.md)  
 <span data-ttu-id="45245-110">Descrive la correlazione duplex durevole.</span><span class="sxs-lookup"><span data-stu-id="45245-110">Describes durable duplex correlation.</span></span>
  
 [<span data-ttu-id="45245-111">Request/Reply</span><span class="sxs-lookup"><span data-stu-id="45245-111">Request-Reply</span></span>](request-reply-correlation.md)  
 <span data-ttu-id="45245-112">Descrive la correlazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="45245-112">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="45245-113">Risoluzione dei problemi relativi alla correlazione</span><span class="sxs-lookup"><span data-stu-id="45245-113">Troubleshooting Correlation</span></span>](troubleshooting-correlation.md)  
 <span data-ttu-id="45245-114">Fornisce i metodi per la risoluzione dei problemi relativi alla correlazione.</span><span class="sxs-lookup"><span data-stu-id="45245-114">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45245-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45245-115">See also</span></span>

- <xref:System.ServiceModel.Activities.CorrelationHandle>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.Receive>
- <xref:System.ServiceModel.CorrelationQuery>
