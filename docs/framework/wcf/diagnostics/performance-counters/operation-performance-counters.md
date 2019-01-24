---
title: Contatori delle prestazioni per l'operazione
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 16608132c6557f8612d42402a2cb2c49fcc29637
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566089"
---
# <a name="operation-performance-counters"></a>Contatori delle prestazioni per l'operazione
I contatori delle prestazioni per l'operazione si trovano nell'oggetto prestazione `ServiceModelOperation 4.0.0.0` in caso di visualizzazione con Performance Monitor (Perfmon.exe). Ogni operazione ha un'istanza singola. Ovvero, se un determinato contratto ha 10 operazioni, ad esso sono associate 10 istanze di contatore per l'operazione. Le istanze di oggetti vengono denominate usando il modello seguente:  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 Questo contatore consente di misurare come viene usata la chiamata e le prestazioni dell'operazione.  
  
> [!CAUTION]
>  Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni. Quando un nome di istanza dei contatori Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.  
  
## <a name="see-also"></a>Vedere anche
- [Contatori delle prestazioni](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
