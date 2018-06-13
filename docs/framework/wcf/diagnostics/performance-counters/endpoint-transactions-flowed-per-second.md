---
title: 'Endpoint: transazioni propagate al secondo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: ff3d76025bbae0759dba005adbd62609701c5a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471282"
---
# <a name="endpoint-transactions-flowed-per-second"></a>Endpoint: transazioni propagate al secondo
Nome contatore: transazioni propagate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di transazioni propagate alle operazioni per l'endpoint al secondo. Questo contatore viene incrementato ogni volta che è presente un ID di transazione nel messaggio inviato all'endpoint.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
