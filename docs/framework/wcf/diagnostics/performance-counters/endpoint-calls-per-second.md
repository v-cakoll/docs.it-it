---
title: 'Endpoint: chiamate al secondo'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: d639d881bcedd336c7bbabd28ec385f60ff54d43
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163787"
---
# <a name="endpoint-calls-per-second"></a>Endpoint: chiamate al secondo
Nome contatore: chiamate al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di chiamate all'endpoint al secondo.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
