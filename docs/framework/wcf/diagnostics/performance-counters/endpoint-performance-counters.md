---
title: Contatori delle prestazioni dell'endpoint
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 2352bc82998c8e87e72f331104446bac4fcb9fda
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040576"
---
# <a name="endpoint-performance-counters"></a>Contatori delle prestazioni dell'endpoint
I contatori delle prestazioni dell'endpoint consentono di raccogliere dati che indicano il livello di efficienza con cui un endpoint accetta i messaggi. Questi contatori si trovano nell'oggetto prestazione `ServiceModelEndpoint 4.0.0.0` quando si utilizza Performance Monitor per visualizzare le prestazioni. Le istanze vengono denominate usando il modello seguente:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 I dati sono simili a quelli raccolti per le singole operazioni, ma vengono aggregati soltanto nell'endpoint.  
  
> [!CAUTION]
> Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni. Quando il nome di un'istanza del contatore Windows Communication Foundation (WCF) supera la lunghezza massima, WCF sostituisce una parte del nome dell'istanza con un valore hash.  
  
## <a name="see-also"></a>Vedere anche

- [Contatori delle prestazioni](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
