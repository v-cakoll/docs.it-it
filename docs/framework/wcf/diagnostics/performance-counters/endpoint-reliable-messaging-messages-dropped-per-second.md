---
title: 'Endpoint: Messaggi di messaggistica affidabile ignorati al secondo'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797202"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Endpoint: Messaggi di messaggistica affidabile ignorati al secondo
Nome contatore: Sessioni di messaggistica affidabile eliminati al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero totale di messaggi di messaggistica affidabile eliminati in questo endpoint al secondo.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
