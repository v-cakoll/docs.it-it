---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: bffa6361df5a50748f45aa3004f7a307ad516d7b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580489"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="72aa2-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="72aa2-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="72aa2-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="72aa2-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="72aa2-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72aa2-104">Description</span></span>  
 <span data-ttu-id="72aa2-105">Il sistema ha raggiunto il limite impostato per la velocità ManualFlowControlLimit.</span><span class="sxs-lookup"><span data-stu-id="72aa2-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="72aa2-106">Il valore di velocità può essere modificato impostando la proprietà ManualFlowControlLimit su ServiceHost o InstanceContext, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="72aa2-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="72aa2-107">Questa traccia viene generata quando il limite del controllo di flusso manuale è ridotto inizialmente a 0.</span><span class="sxs-lookup"><span data-stu-id="72aa2-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="72aa2-108">Le successive modifiche a 0 non vengono tracciate.</span><span class="sxs-lookup"><span data-stu-id="72aa2-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="72aa2-109">Il limite di controllo del flusso sul contesto dell'istanza viene tracciato una sola volta per ogni contesto.</span><span class="sxs-lookup"><span data-stu-id="72aa2-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72aa2-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72aa2-110">See also</span></span>

- [<span data-ttu-id="72aa2-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="72aa2-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="72aa2-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="72aa2-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="72aa2-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="72aa2-113">Administration and Diagnostics</span></span>](../index.md)
