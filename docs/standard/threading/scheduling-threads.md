---
title: Pianificazione di thread
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a382dbea239b66e60d666a0e2e7add01d6d7bd54
ms.sourcegitcommit: c66ba2df2d2ecfb214f85ee0687d298e4941c1a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2018
ms.locfileid: "42753870"
---
# <a name="scheduling-threads"></a>Pianificazione di thread

A ogni thread è assegnata una priorità specifica. Ai thread creati all'interno di Common Language Runtime viene inizialmente assegnata la priorità <xref:System.Threading.ThreadPriority.Normal?displayProperty=nameWithType>. I thread creati esternamente al runtime conservano la priorità che avevano prima di entrare nell'ambiente gestito. È possibile ottenere o impostare la priorità di un thread con la proprietà <xref:System.Threading.Thread.Priority?displayProperty=nameWithType>.  
  
 L'esecuzione dei thread viene pianificata in base alla relativa priorità. Anche se i thread vengono eseguiti all'interno del runtime, a tutti i thread vengono assegnati intervalli di tempo del processore dal sistema operativo. I dettagli dell'algoritmo di pianificazione usato per determinare l'ordine in cui vengono eseguiti i thread varia in base al sistema operativo. In alcuni sistemi operativi, il thread con la priorità più alta (tra quelli eseguibili) è sempre pianificato per essere eseguito per primo. Se sono disponibili più thread con la stessa priorità, l'utilità di pianificazione scorre tali thread assegnando a ciascuno di essi un intervallo di tempo fisso per la loro esecuzione. Finché un thread con una priorità più alta è disponibile per l'esecuzione, i thread con priorità inferiore non verranno eseguiti. Quando non sono più presenti thread eseguibili con una priorità specifica, l'utilità di pianificazione passa alla successiva priorità più bassa e pianifica l'esecuzione dei thread associati a tale priorità. Se un thread con priorità maggiore diventa eseguibile, il thread con priorità inferiore viene interrotto e viene di nuovo consentita l'esecuzione del thread con priorità superiore. Oltre a quanto precedentemente detto, il sistema operativo può anche regolare le priorità dei thread in modo dinamico quando l'interfaccia utente di un'applicazione viene spostata in background dal primo piano. Altri sistemi operativi potrebbero scegliere di usare un algoritmo di pianificazione diverso.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Threading gestito e non gestito in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
