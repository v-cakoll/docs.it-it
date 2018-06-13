---
title: 'Endpoint: messaggi di messaggistica affidabile rilasciati al secondo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: a87e5fef0c13e239959a386f108af3c4cebae7f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472284"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Endpoint: messaggi di messaggistica affidabile rilasciati al secondo
Nome contatore: sessioni di messaggistica affidabile rilasciate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero totale di messaggi di messaggistica affidabile eliminati in questo endpoint al secondo.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
