---
title: 'Endpoint: transazioni propagate al secondo'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064959"
---
# <a name="endpoint-transactions-flowed-per-second"></a>Endpoint: transazioni propagate al secondo
Nome contatore: transazioni propagate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di transazioni propagate alle operazioni per l'endpoint al secondo. Questo contatore viene incrementato ogni volta che è presente un ID di transazione nel messaggio inviato all'endpoint.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
