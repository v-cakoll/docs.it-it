---
title: 'Servizio: Chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: d87d5f06d0c9a3849ec80a3d1c7badefde7cf372
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167492"
---
# <a name="service-calls-failed-per-second"></a>Servizio: Chiamate non riuscite al secondo
Nome contatore: Chiamate non riuscite al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate al secondo ricevute dal servizio aventi eccezioni non gestite.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.  
  
 Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.  
  
 Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questo servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica e gestione degli errori in contratti e servizi](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
