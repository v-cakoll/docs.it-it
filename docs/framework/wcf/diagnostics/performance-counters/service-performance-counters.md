---
title: Contatori delle prestazioni del servizio
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 929ddcb2f271b7488270ea39e7a3a0037158c855
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320034"
---
# <a name="service-performance-counters"></a><span data-ttu-id="87a7b-102">Contatori delle prestazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="87a7b-102">Service Performance Counters</span></span>
<span data-ttu-id="87a7b-103">I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio.</span><span class="sxs-lookup"><span data-stu-id="87a7b-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="87a7b-104">Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe).</span><span class="sxs-lookup"><span data-stu-id="87a7b-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="87a7b-105">Le istanze vengono denominate usando il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="87a7b-105">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> <span data-ttu-id="87a7b-106">Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="87a7b-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="87a7b-107">Quando il nome di un'istanza del contatore Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.</span><span class="sxs-lookup"><span data-stu-id="87a7b-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a7b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87a7b-108">See also</span></span>

- [<span data-ttu-id="87a7b-109">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="87a7b-109">Performance Counters</span></span>](index.md)
