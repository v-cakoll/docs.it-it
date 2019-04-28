---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: fb69c3c737a0e77b05e08ab8d8282069feb069bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761520"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="d62a7-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d62a7-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="d62a7-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d62a7-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="d62a7-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d62a7-104">Description</span></span>  
 <span data-ttu-id="d62a7-105">Il sistema ha raggiunto il limite impostato per la velocità ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="d62a7-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="d62a7-106">Il valore di velocità può essere modificato impostando la proprietà ManualFlowControlLimit su ServiceHost o InstanceContext, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d62a7-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="d62a7-107">Questa traccia viene generata quando il limite del controllo di flusso manuale è ridotto inizialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="d62a7-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="d62a7-108">Le successive modifiche a 0 non vengono tracciate.</span><span class="sxs-lookup"><span data-stu-id="d62a7-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="d62a7-109">Il limite di controllo del flusso sul contesto dell'istanza viene tracciato una sola volta per ogni contesto.</span><span class="sxs-lookup"><span data-stu-id="d62a7-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d62a7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d62a7-110">See also</span></span>

- [<span data-ttu-id="d62a7-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="d62a7-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d62a7-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="d62a7-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d62a7-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="d62a7-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
