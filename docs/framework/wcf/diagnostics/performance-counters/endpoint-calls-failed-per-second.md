---
title: 'Endpoint: chiamate non riuscite al secondo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5da436c5e8159ff922c36172490a28e854bbee8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-failed-per-second"></a>Endpoint: chiamate non riuscite al secondo
Nome contatore: chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate al secondo con eccezioni non gestite ricevute dall'endpoint.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita all'endpoint.  
  
## <a name="see-also"></a>Vedere anche  
 [Specifica e gestione degli errori in contratti e servizi](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
