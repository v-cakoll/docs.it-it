---
title: Contatori delle prestazioni del servizio
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 18a9e6336b70341f5da9c7b73cbd3f9bd3f958c7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044279"
---
# <a name="service-performance-counters"></a><span data-ttu-id="64cf6-102">Contatori delle prestazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="64cf6-102">Service Performance Counters</span></span>
<span data-ttu-id="64cf6-103">I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="64cf6-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="64cf6-104">Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="64cf6-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="64cf6-105">Le istanze vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="64cf6-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
> <span data-ttu-id="64cf6-106">Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64cf6-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="64cf6-107">Quando il nome di un'istanza del contatore Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.</span><span class="sxs-lookup"><span data-stu-id="64cf6-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64cf6-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64cf6-108">See also</span></span>

- [<span data-ttu-id="64cf6-109">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="64cf6-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
