---
title: 'Servizio: chiamate non riuscite al secondo'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 5431144a4618b146a10dfaa3bbdaae34c519319e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315780"
---
# <a name="service-calls-failed-per-second"></a>Servizio: chiamate non riuscite al secondo
Nome contatore: chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate al secondo ricevute dal servizio aventi eccezioni non gestite.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.  
  
 Nel codice gestito, vengono generate eccezioni quando si verificano condizioni di errore.  
  
 Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questo servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica e gestione degli errori in contratti e servizi](../../specifying-and-handling-faults-in-contracts-and-services.md)
