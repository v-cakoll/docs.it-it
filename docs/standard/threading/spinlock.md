---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a>SpinLock
Il <xref:System.Threading.SpinLock> struttura è una primitiva di sincronizzazione di basso livello a esclusione reciproca che ruota in attesa di acquisire un blocco. Nei computer multicore, quando prevede tempi di attesa sono brevi e il conflitto è minimo, <xref:System.Threading.SpinLock> può risultare più efficace rispetto ad altri tipi di blocchi. Tuttavia, è consigliabile utilizzare <xref:System.Threading.SpinLock> solo quando è determinare il profilo di <xref:System.Threading.Monitor?displayProperty=nameWithType> (metodo) o <xref:System.Threading.Interlocked> metodi rallentano in modo significativo le prestazioni del programma.  
  
 <xref:System.Threading.SpinLock>può produrre l'intervallo di tempo del thread, anche se non ha ancora acquisito il blocco. Ciò avviene per evitare l'inversione di priorità di thread e per consentire al garbage collector di avanzamento del lavoro. Quando si utilizza un <xref:System.Threading.SpinLock>, verificare che nessun thread può contenere il blocco per più di un intervallo di tempo molto breve, e che nessun thread può restare bloccata mentre mantiene il blocco.  
  
 Poiché SpinLock è un tipo valore, è necessario passarlo in modo esplicito per riferimento se si prevede due copie per fare riferimento allo stesso blocco.  
  
 Per ulteriori informazioni sull'utilizzo di questo tipo, vedere <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Per un esempio, vedere [procedura: utilizzare SpinLock per la sincronizzazione di basso livello](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock>supporta un *thread*-*rilevamento* modalità da utilizzare durante la fase di sviluppo per rilevare il thread che contiene il blocco in un momento specifico. Modalità di rilevamento thread è molto utile per il debug, ma si consiglia di disattivare nella versione di rilascio del programma in quanto può ridurre le prestazioni. Per ulteriori informazioni, vedere [come: la modalità di rilevamento abilitare Thread in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md)
