---
title: Messaggi non elaborabili in coda al secondo
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 6407cce120f5d534f88a12591ea2ad09bb5130d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473259"
---
# <a name="queued-poison-messages-per-second"></a>Messaggi non elaborabili in coda al secondo
Nome contatore: messaggi non elaborabili in coda al secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di messaggi al secondo contrassegnati come non elaborabili dal trasporto in coda in questo servizio.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
