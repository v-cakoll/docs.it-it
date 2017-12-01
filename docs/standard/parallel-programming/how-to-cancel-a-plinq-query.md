---
title: 'Procedura: annullare una query PLINQ'
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
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a>Procedura: annullare una query PLINQ
Gli esempi seguenti mostrano due modi per annullare una query PLINQ. Nel primo esempio viene illustrato come annullare una query che è costituito principalmente da attraversamento di dati. Nel secondo esempio viene illustrato come annullare una query che contiene una funzione utente che è dispendiosa.  
  
> [!NOTE]
>  Quando "Just My Code" è abilitato, Visual interruzione sulla riga che genera l'eccezione e verrà visualizzato un messaggio di errore simile a "eccezione non gestita dal codice utente". Questo errore non è grave. È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti. Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.  
>   
>  Lo scopo di questo esempio consiste nell'illustrare l'uso ed è possibile che l'esecuzione non sia più veloce rispetto alla query LINQ to Objects sequenziale equivalente. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 Il framework PLINQ non esegue il rollback di una singola <xref:System.OperationCanceledException> in un <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> devono essere gestiti in un blocco catch separato. Se uno o più utente genera un oggetto OperationCanceledException (utilizzando un riferimento esterno <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) ma non altre eccezioni e la query è stata definita come `AsParallel().WithCancellation(externalCT)`, PLINQ genererà un singolo <xref:System.OperationCanceledException> (externalCT) anziché un oggetto <xref:System.AggregateException?displayProperty=nameWithType>. Tuttavia, se un utente delegato genera un <xref:System.OperationCanceledException>e un altro delegato genera un altro tipo di eccezione, quindi entrambe le eccezioni verranno incluse in un <xref:System.AggregateException>.  
  
 Le indicazioni generali al momento dell'annullamento sono come segue:  
  
1.  Se si esegue l'annullamento di delegato dell'utente è necessario informare PLINQ esterno <xref:System.Threading.CancellationToken> e generare un <xref:System.OperationCanceledException>(externalCT).  
  
2.  Se si verifica l'annullamento e non altri vengono generate eccezioni, è necessario gestire un <xref:System.OperationCanceledException> anziché un oggetto <xref:System.AggregateException>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come gestire l'annullamento quando si dispone di una funzione dispendiosa a livello di codice utente.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 Quando si gestisce l'annullamento nel codice utente, non è necessario utilizzare <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> nella definizione della query. Tuttavia, è consigliabile farlo perché <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> non ha alcun effetto sulle prestazioni delle query e consente l'annullamento deve essere gestito da operatori di query e il codice utente.  
  
 Per garantire velocità di risposta del sistema, si consiglia di verificare la disponibilità di annullamento circa una volta al millisecondo. Tuttavia, qualsiasi periodo fino a 10 millisecondi viene considerata accettabile. Questa frequenza senza un impatto negativo sulle prestazioni del codice.  
  
 Quando viene eliminato un enumeratore, ad esempio quando il codice esce da un ciclo foreach (For Each in Visual Basic) che esegue l'iterazione sui risultati di query, quindi la query è stata annullata, ma viene generata alcuna eccezione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Annullamento in thread gestiti](../../../docs/standard/threading/cancellation-in-managed-threads.md)
