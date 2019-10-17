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
# <a name="service-performance-counters"></a>Contatori delle prestazioni del servizio
I contatori delle prestazioni del servizio misurano il comportamento del servizio nel suo insieme e possono essere usati per diagnosticare le prestazioni dell'intero servizio. Sono reperibili nell'oggetto prestazione `ServiceModelService 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe). Le istanze vengono denominate usando il modello seguente:  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni. Quando il nome di un'istanza del contatore Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.  
  
## <a name="see-also"></a>Vedere anche

- [Contatori delle prestazioni](index.md)
