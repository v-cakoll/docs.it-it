---
title: Messaggi di messaggistica affidabile eliminati al secondo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45664449"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Messaggi di messaggistica affidabile eliminati al secondo
Nome contatore: sessioni di messaggistica affidabile rilasciate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero complessivo di messaggi di messaggistica affidabile rilasciati in questo servizio in un secondo.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
