---
title: 'Servizio: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 94247356-2b29-4b50-b639-91ca8c1cf3a9
ms.openlocfilehash: 86eddc62fb9aec8eced49ae70865583f3a50eb85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474100"
---
# <a name="service-calls-faulted-per-second"></a>Servizio: chiamate non riuscite al secondo
Nome contatore: chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate a questo servizio che hanno restituito errori in un secondo.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Nelle applicazioni Windows Communication Foundation (WCF), informazioni sugli errori di elaborazione tramite messaggi di errore SOAP vengono comunicate dai metodi di servizio. Gli errori SOAP sono tipi di messaggio inclusi nei metadati per un'operazione del servizio e pertanto creano un contratto di errore che i client possono usare per rendere l'esecuzione più affidabile o interattiva. Dato che gli errori SOAP sono espressi ai client in formato XML, sono estremamente interoperativi.  
  
## <a name="see-also"></a>Vedere anche  
 [Specifica e gestione degli errori in contratti e servizi](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
