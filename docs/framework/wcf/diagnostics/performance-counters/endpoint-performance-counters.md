---
title: Contatori delle prestazioni dell'endpoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc5fa1b3600489cb2d5f31c263019ae5006edf65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-performance-counters"></a>Contatori delle prestazioni dell'endpoint
I contatori delle prestazioni dell'endpoint consentono di raccogliere dati che indicano il livello di efficienza con cui un endpoint accetta i messaggi. Questi contatori si trovano nell'oggetto prestazione `ServiceModelEndpoint 4.0.0.0` quando si utilizza Performance Monitor per visualizzare le prestazioni. Le istanze vengono denominate usando il modello seguente:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 I dati sono simili a quelli raccolti per le singole operazioni, ma vengono aggregati soltanto nell'endpoint.  
  
> [!CAUTION]
>  Esiste un limite di lunghezza per il nome dell'istanza di un contatore delle prestazioni. Quando il nome dell'istanza di un contatore [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] supera la lunghezza massima, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] sostituisce una parte del nome dell'istanza con un valore hash.  
  
## <a name="see-also"></a>Vedere anche  
 [Contatori delle prestazioni](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
