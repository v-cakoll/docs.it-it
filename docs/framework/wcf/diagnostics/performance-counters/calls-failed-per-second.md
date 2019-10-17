---
title: Chiamate non riuscite al secondo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: e7c0b53f4c2b1a7e87a5791b44e452ec9146c459
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321115"
---
# <a name="calls-failed-per-second"></a>Chiamate non riuscite al secondo
Nome contatore: chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate al secondo con eccezioni non gestite presenti in questa operazione.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questa operazione.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica e gestione degli errori in contratti e servizi](../../specifying-and-handling-faults-in-contracts-and-services.md)
