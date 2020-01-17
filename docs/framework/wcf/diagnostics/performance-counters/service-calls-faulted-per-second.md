---
title: 'Servizio: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: ba470c565c042de6de53693e7b0e6d4682c5a75a
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163892"
---
# <a name="service-calls-faulted-per-second"></a>Servizio: chiamate non riuscite al secondo
Nome contatore: chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate a questo servizio che hanno restituito errori in un secondo.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Nelle applicazioni Windows Communication Foundation (WCF) i metodi di servizio comunicano l'elaborazione delle informazioni sugli errori mediante messaggi di errore SOAP. Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva. Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica e gestione degli errori in contratti e servizi](../../specifying-and-handling-faults-in-contracts-and-services.md)
