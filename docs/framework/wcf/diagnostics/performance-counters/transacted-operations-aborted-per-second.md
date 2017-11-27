---
title: Operazioni transazionali interrotte ogni secondo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 96ef8181b95d8614ae6cbfeaa468b0138d1129d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transacted-operations-aborted-per-second"></a>Operazioni transazionali interrotte ogni secondo
Nome contatorte: operazioni transazionali interrotte ogni secondo.  
  
## <a name="description"></a>Descrizione  
 Numero di operazioni transazionali interrotte in questo servizio in un secondo.  
  
 Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
