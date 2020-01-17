---
title: Messaggi in coda rifiutati al secondo
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 805b4f5d1e7882f38cfcc76ad63451d735389d5f
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163969"
---
# <a name="queued-rejected-messages-per-second"></a>Messaggi in coda rifiutati al secondo
Nome contatore: messaggi in coda rifiutati al secondo  
  
## <a name="description"></a>Descrizione  
 Numero di messaggi rifiutati dal trasporto in coda di questo servizio al secondo.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
