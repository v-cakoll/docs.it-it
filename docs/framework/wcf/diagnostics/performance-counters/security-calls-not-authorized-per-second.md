---
title: Chiamate di sicurezza non autorizzate al secondo
ms.date: 03/30/2017
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
ms.openlocfilehash: 2986ba241ef9b6c110a4742f77320469cdf5f07a
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163930"
---
# <a name="security-calls-not-authorized-per-second"></a>Chiamate di sicurezza non autorizzate al secondo
Nome contatore: chiamate di sicurezza non autorizzate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate non autorizzate per l'operazione al secondo.  
  
 Questo contatore viene incrementato quando il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> restituisce `false`. Indica che il messaggio in ingresso proviene da un utente valido ed è adeguatamente protetto, ma l'utente non è autorizzato a eseguire attività specifiche.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
