---
title: Contatori delle prestazioni del servizio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: de51c6d0a3070f8bba8a2c77f9c028e7cfbc944d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="service-performance-counters"></a><span data-ttu-id="e8e73-102">Contatori delle prestazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="e8e73-102">Service Performance Counters</span></span>
<span data-ttu-id="e8e73-103">I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="e8e73-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="e8e73-104">Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="e8e73-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="e8e73-105">Le istanze vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="e8e73-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="e8e73-106">Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e8e73-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="e8e73-107">Quando il nome dell'istanza di un contatore [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la lunghezza massima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] sostituisce una parte del nome dell'istanza con un valore hash.</span><span class="sxs-lookup"><span data-stu-id="e8e73-107">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e73-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8e73-108">See Also</span></span>  
 [<span data-ttu-id="e8e73-109">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e8e73-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
