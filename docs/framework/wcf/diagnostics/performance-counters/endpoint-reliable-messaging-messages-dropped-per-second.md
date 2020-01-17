---
title: 'Endpoint: messaggi di messaggistica affidabile rilasciati al secondo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 7dc52caea0233953dd72e77e4d662083f4a370e4
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164047"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Endpoint: messaggi di messaggistica affidabile rilasciati al secondo
Nome contatore: sessioni di messaggistica affidabile eliminate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero totale di messaggi di messaggistica affidabile eliminati in questo endpoint al secondo.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
