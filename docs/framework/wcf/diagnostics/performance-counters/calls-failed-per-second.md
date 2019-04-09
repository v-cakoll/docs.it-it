---
title: Chiamate non riuscite al secondo
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: ff9320b0990a0543bbb1da553d040ff5a4b4fed9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178620"
---
# <a name="calls-failed-per-second"></a>Chiamate non riuscite al secondo
Nome contatore: Chiamate non riuscite al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate al secondo con eccezioni non gestite presenti in questa operazione.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Questo contatore viene incrementato ogni volta che si verifica un'eccezione non gestita in questa operazione.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica e gestione di errori in contratti e servizi](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
