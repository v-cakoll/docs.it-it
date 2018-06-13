---
title: 'Servizio: transazioni propagate al secondo'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 1151117c8537d4a8eaa4de60d14e314b55ce82d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474844"
---
# <a name="service-transactions-flowed-per-second"></a>Servizio: transazioni propagate al secondo
Nome contatore: transazioni propagate al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di transazioni propagate alle operazioni in questo servizio al secondo.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
