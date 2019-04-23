---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: fb69c3c737a0e77b05e08ab8d8282069feb069bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095685"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="83429-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="83429-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="83429-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="83429-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="83429-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83429-104">Description</span></span>  
 <span data-ttu-id="83429-105">Il sistema ha raggiunto il limite impostato per la velocità ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="83429-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="83429-106">Il valore di velocità può essere modificato impostando la proprietà ManualFlowControlLimit su ServiceHost o InstanceContext, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="83429-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="83429-107">Questa traccia viene generata quando il limite del controllo di flusso manuale è ridotto inizialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="83429-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="83429-108">Le successive modifiche a 0 non vengono tracciate.</span><span class="sxs-lookup"><span data-stu-id="83429-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="83429-109">Il limite di controllo del flusso sul contesto dell'istanza viene tracciato una sola volta per ogni contesto.</span><span class="sxs-lookup"><span data-stu-id="83429-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83429-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83429-110">See also</span></span>

- [<span data-ttu-id="83429-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="83429-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="83429-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="83429-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="83429-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="83429-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
