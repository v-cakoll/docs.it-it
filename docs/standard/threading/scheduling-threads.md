---
title: Pianificazione di thread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a>Pianificazione di thread
Ogni thread ha una priorità di thread assegnata. Thread creati all'interno di common language runtime viene inizialmente assegnata la priorità di **ThreadPriority**. Thread creati all'esterno del runtime conservano la priorità che avevano prima di entrare nell'ambiente gestito. È possibile ottenere o impostare la priorità di un thread con il **Priority** proprietà.  
  
 I thread sono pianificati per l'esecuzione in base alla priorità. Anche se l'esecuzione di thread all'interno del runtime, tutti i thread vengono assegnati gli intervalli di tempo processore dal sistema operativo. I dettagli dell'algoritmo di pianificazione utilizzato per determinare l'ordine in cui vengono eseguiti i thread varia con ogni sistema operativo. In alcuni sistemi operativi, il thread con la priorità più alta (dei thread che possono essere eseguite) è sempre pianificato da eseguire prima. Se più thread, con la stessa priorità sono tutti disponibili, l'utilità di pianificazione consente di scorrere i thread presenti in tale priorità, assegnazione di un intervallo di tempo predefinito in cui eseguire ogni thread. Fino a quando un thread con una priorità più alta è disponibile per l'esecuzione, i thread con priorità inferiore non verranno eseguiti. Quando sono presenti thread eseguibile non è più una determinata priorità, l'utilità di pianificazione si sposta la priorità più bassa successiva e pianifica il thread di priorità per l'esecuzione. Se un thread con priorità maggiore diventa runnable, viene interrotto il thread con priorità inferiore e il thread con priorità superiore è possibile eseguire ancora una volta. Nella parte superiore di tutte le risposte, il sistema operativo anche regolare le priorità dei thread in modo dinamico come un'interfaccia utente di spostamento tra i primo piano e sfondo. Altri sistemi operativi è possibile scegliere di utilizzare un algoritmo di programmazione diverso.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Threading gestito e non gestito in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
