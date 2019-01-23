---
title: Contatori delle prestazioni del servizio
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bf0b12e6d4954c0a1392554d7269a7d539a77dc1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545595"
---
# <a name="service-performance-counters"></a>Contatori delle prestazioni del servizio
I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio. Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe). Le istanze vengono denominate usando il modello seguente:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni. Quando un nome di istanza dei contatori Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.  
  
## <a name="see-also"></a>Vedere anche
- [Contatori delle prestazioni](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
