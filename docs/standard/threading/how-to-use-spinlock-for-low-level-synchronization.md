---
title: 'Procedura: Usare SpinLock per la sincronizzazione di basso livello'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
ms.openlocfilehash: ad254cb6208bff868e5fc689c502b7ddcc175ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137959"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Procedura: Usare SpinLock per la sincronizzazione di basso livello

L'esempio seguente illustra come usare un oggetto <xref:System.Threading.SpinLock>. In questo esempio la sezione critica esegue una quantità minima di lavoro, quindi è ideale per l'uso di <xref:System.Threading.SpinLock>. Aumentando leggermente il lavoro, aumentano le prestazioni di <xref:System.Threading.SpinLock> rispetto a un blocco standard. Tuttavia, esiste un punto in cui uno SpinLock diventa più costoso di un blocco standard. È possibile usare la funzionalità del profilo di concorrenza negli strumenti di profilatura per vedere quale tipo di blocco fornisce prestazioni migliori nel programma. Per altre informazioni, vedere [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 È possibile usare <xref:System.Threading.SpinLock> quando un blocco su una risorsa condivisa non verrà mantenuto per molto tempo. In questi casi, nei computer multicore può essere efficiente per il thread bloccato l'azione di ruotare per alcuni cicli finché il blocco non viene rilasciato. Ruotando, il thread non diventa bloccato, che è un processo intensivo della CPU. <xref:System.Threading.SpinLock> interrompe la rotazione in determinate condizioni per evitare l'esaurimento dei processori logici o l'inversione di priorità nei sistemi con hyperthreading.  
  
 Questo esempio usa la classe <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, che richiede la sincronizzazione utente per l'accesso a thread multipli. Nelle applicazioni destinate a .NET Framework versione 4, è anche possibile usare <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, che non richiede alcun blocco dell'utente.  
  
 Si noti l'uso di `false` (`False` in Visual Basic) nella chiamata a <xref:System.Threading.SpinLock.Exit%2A?displayProperty=nameWithType>. Questo fornisce prestazioni ottimali. Specificare `true` (`True` in Visual Basic) nelle architetture IA64 per usare il limite di memoria, che scarica il buffer di scrittura per garantire che il blocco sia ora disponibile per l'uscita di altri thread.  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti e funzionalità del threading](threading-objects-and-features.md)
- [Istruzione lock (C#)](../../csharp/language-reference/keywords/lock-statement.md)
- [Istruzione SyncLock (Visual Basic)](../../visual-basic/language-reference/statements/synclock-statement.md)
