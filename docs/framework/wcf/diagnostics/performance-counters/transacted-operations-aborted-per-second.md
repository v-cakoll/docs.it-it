---
title: Operazioni transazionali interrotte ogni secondo
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417482"
---
# <a name="transacted-operations-aborted-per-second"></a>Operazioni transazionali interrotte ogni secondo
Nome contatorte: operazioni transazionali interrotte ogni secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di operazioni transazionali interrotte in questo servizio in un secondo.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
