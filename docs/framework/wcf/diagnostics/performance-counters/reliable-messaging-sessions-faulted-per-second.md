---
title: Sessioni di messaggistica affidabile con errori per secondo
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: 4dd247131182aca65a837095144673690cb134c8
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163943"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Sessioni di messaggistica affidabile con errori per secondo
Nome contatore: sessioni di messaggistica affidabile con errori al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di sessioni di messaggistica affidabile con errori per il servizio in un secondo.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
