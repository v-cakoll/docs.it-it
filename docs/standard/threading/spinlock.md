---
title: SpinLock
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7d1d95030d2bc9f9288ae134471c150a37291b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582259"
---
# <a name="spinlock"></a>SpinLock
La struttura <xref:System.Threading.SpinLock> è una primitiva di sincronizzazione di basso livello a esclusione reciproca che ruota in attesa di acquisire un blocco. Nei computer multicore, quando si prevedono tempi di attesa brevi e il conflitto è minimo, <xref:System.Threading.SpinLock> può avere prestazioni migliori rispetto ad altri tipi di blocchi. Tuttavia, è consigliabile usare <xref:System.Threading.SpinLock> solo quando mediante la profilatura si determina che il metodo <xref:System.Threading.Monitor?displayProperty=nameWithType> o i metodi <xref:System.Threading.Interlocked> rallentano in modo significativo le prestazioni del programma.  
  
 <xref:System.Threading.SpinLock> può produrre l'intervallo di tempo del thread, anche se non ha ancora acquisito il blocco. Ciò avviene per evitare l'inversione di priorità dei thread e per consentire a Garbage Collector di avanzare. Quando si usa un <xref:System.Threading.SpinLock>, verificare che nessun thread conservi il blocco per più di un intervallo di tempo molto breve, e che nessun thread possa restare bloccato mentre conserva il blocco.  
  
 Poiché SpinLock è un tipo di valore, è necessario passarlo in modo esplicito mediante riferimento se si prevede che le due copie facciano riferimento allo stesso blocco.  
  
 Per altre informazioni sull'uso di questo tipo, vedere <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Per un esempio, vedere [Procedura: Usare SpinLock per la sincronizzazione di basso livello](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock> supporta una modalità di *rilevamento*-*thread* da usare durante la fase di sviluppo per rilevare il thread che contiene il blocco in un momento specifico. La modalità di rilevamento thread è molto utile per il debug, ma si consiglia di disattivarla nella versione di rilascio del programma in quanto può ridurre le prestazioni. Per altre informazioni, vedere [Procedura: Abilitare la modalità di rilevamento thread in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md)
