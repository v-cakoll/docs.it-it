---
title: Barriera
ms.date: 09/14/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 5aa34f7f39f4b9b626bea29372cf984f3cefb361
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138155"
---
# <a name="barrier"></a>Barriera

Una classe <xref:System.Threading.Barrier?displayProperty=nameWithType> è una primitiva di sincronizzazione definita dall'utente che permette a più thread (noti come *partecipanti*) di lavorare contemporaneamente su un algoritmo in fasi diverse. Ogni partecipante viene eseguito fino al raggiungimento del punto barriera nel codice. La barriera rappresenta la fine di una fase di lavoro. Quando un partecipante raggiunge la barriera, si blocca fino al raggiungimento della stessa barriera da parte di tutti i partecipanti. Dopo che tutti i partecipanti hanno raggiunto la barriera, è possibile richiamare facoltativamente un'azione post- fase. Questa azione post- fase può essere usata per eseguire azioni da parte di un singolo thread mentre tutti gli altri thread rimangono bloccati. Dopo l'esecuzione dell'azione, tutti i partecipanti verranno sbloccati.  
  
 Il frammento di codice seguente mostra un modello di barriera di base.  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 Per un esempio completo, vedere [Procedura: Sincronizzare operazioni simultanee con una barriera](how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="adding-and-removing-participants"></a>Aggiunta e rimozione di partecipanti

 Quando si crea un'istanza di <xref:System.Threading.Barrier>, specificare il numero di partecipanti. È anche possibile aggiungere o rimuovere dinamicamente i partecipanti in qualsiasi momento. Se ad esempio un partecipante risolve la propria parte di problema, sarà possibile archiviare il risultato, arrestare l'esecuzione in quel thread e chiamare <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> per ridurre il numero di partecipanti nella barriera. Quando si aggiunge un partecipante chiamando <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, il valore restituito specifica il numero di fase attuale, che potrebbe essere utile per inizializzare il lavoro del nuovo partecipante.  
  
## <a name="broken-barriers"></a>Barriere interrotte

 Se un partecipante non riesce a raggiungere la barriera, possono verificarsi deadlock. Per evitare questi deadlock, usare gli overload del metodo <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> per specificare un periodo di timeout e un token di annullamento. Questi overload restituiscono un valore booleano che ogni partecipante può controllare prima di passare alla fase successiva.  
  
## <a name="post-phase-exceptions"></a>Eccezioni di post-fase

 Se il delegato post-fase genera un'eccezione, ne verrà eseguito il wrapping in un oggetto <xref:System.Threading.BarrierPostPhaseException>, che viene quindi propagato a tutti i partecipanti.  
  
## <a name="barrier-versus-continuewhenall"></a>Confronto tra barriera e ContinueWhenAll

 Le barriere risultano particolarmente utili quando i thread eseguono più fasi nei cicli. Se il codice richiede solo una o due fasi di lavoro, prendere in considerazione l'uso di oggetti <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> con qualsiasi tipo di join implicito, inclusi i seguenti:  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 Per altre informazioni, vedere [Concatenamento di attività tramite attività di continuazione](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti e funzionalità del threading](threading-objects-and-features.md)
- [Procedura: Sincronizzare operazioni simultanee con una barriera](how-to-synchronize-concurrent-operations-with-a-barrier.md)
