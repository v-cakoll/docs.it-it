---
title: 'Endpoint: Sessioni di messaggistica affidabile con errori per secondo'
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: f6b48ec4c37c28588dd874a5bfa94a01a2f43b0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951242"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a>Endpoint: Sessioni di messaggistica affidabile con errori per secondo
Nome contatore: Sessioni di messaggistica affidabile con errori al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di sessioni di messaggistica affidabile con errori per l'endpoint al secondo.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
