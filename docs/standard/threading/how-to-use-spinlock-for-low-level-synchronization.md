---
title: 'Procedura: utilizzare SpinLock per la sincronizzazione di basso livello'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Procedura: utilizzare SpinLock per la sincronizzazione di basso livello
Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Threading.SpinLock>.  
  
## <a name="example"></a>Esempio  
 In questo esempio, la sezione critica esegue una quantità minima di lavoro, che rende un ottimo candidato per un <xref:System.Threading.SpinLock>. Aumentando il lavoro di una piccola quantità aumenta le prestazioni del <xref:System.Threading.SpinLock> rispetto a un blocco standard. Tuttavia, esiste un punto in cui uno SpinLock diventa più costoso di un blocco standard. È possibile usare la funzionalità del profilo di concorrenza negli strumenti di profilatura per vedere quale tipo di blocco fornisce prestazioni migliori nel programma. Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>potrebbe essere utile quando un blocco su una risorsa condivisa non viene mantenuto per molto tempo. In questi casi, nei computer multicore può essere efficiente per il thread bloccato l'azione di ruotare per alcuni cicli finché il blocco non viene rilasciato. Ruotando, il thread non diventa bloccato, che è un processo intensivo della CPU. <xref:System.Threading.SpinLock>interromperà lo spin in determinate condizioni per evitare l'esaurimento dei processori logici o di inversione di priorità nei sistemi con Hyper-Threading.  
  
 Questo esempio viene utilizzato il <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> (classe), che richiede la sincronizzazione di utente per l'accesso a thread multipli. Nelle applicazioni destinate a .NET Framework versione 4, un'altra opzione consiste nell'utilizzare il <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, che non richiede alcun blocco dell'utente.  
  
 Si noti l'uso di `false` (`False` in Visual Basic) nella chiamata a <xref:System.Threading.SpinLock.Exit%2A>. Questo fornisce prestazioni ottimali. Specificare `true` (`True`) nelle architetture IA64 per usare il limite di memoria, che scarica il buffer di scrittura per garantire che il blocco sia ora disponibile per l'uscita di altri thread.  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md)
