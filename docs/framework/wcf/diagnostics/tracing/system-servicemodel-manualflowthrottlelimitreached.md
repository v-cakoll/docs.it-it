---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f149423fc8c0cd2a25834742d7c8b79ad8d8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="5dbef-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="5dbef-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="5dbef-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="5dbef-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="5dbef-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5dbef-104">Description</span></span>  
 <span data-ttu-id="5dbef-105">Il sistema ha raggiunto il limite impostato per la velocità ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="5dbef-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="5dbef-106">Il valore di velocità può essere modificato impostando la proprietà ManualFlowControlLimit su ServiceHost o InstanceContext, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5dbef-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="5dbef-107">Questa traccia viene generata quando il limite del controllo di flusso manuale è ridotto inizialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="5dbef-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="5dbef-108">Le successive modifiche a 0 non vengono tracciate.</span><span class="sxs-lookup"><span data-stu-id="5dbef-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="5dbef-109">Il limite di controllo del flusso sul contesto dell'istanza viene tracciato una sola volta per ogni contesto.</span><span class="sxs-lookup"><span data-stu-id="5dbef-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dbef-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dbef-110">See Also</span></span>  
 [<span data-ttu-id="5dbef-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="5dbef-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="5dbef-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="5dbef-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="5dbef-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="5dbef-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
