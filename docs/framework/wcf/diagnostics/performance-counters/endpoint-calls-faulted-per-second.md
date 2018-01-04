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
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 842270d6e570767c25c414307be941f24b01dd07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-calls-faulted-per-second"></a>Endpoint: chiamate non riuscite al secondo
Nome contatore: chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate a questo endpoint che hanno restituito errori in un secondo.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Nelle applicazioni [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], le informazioni sugli errori di elaborazione vengono comunicate dai metodi di servizio tramite messaggi di errore SOAP. Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva. Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.  
  
## <a name="see-also"></a>Vedere anche  
 [Specifica e gestione degli errori in contratti e servizi](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
