---
title: Opzioni di merge in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
ms.openlocfilehash: 623466e0e960ea991ae92e5de432171b70bad1d2
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588624"
---
# <a name="merge-options-in-plinq"></a>Opzioni di merge in PLINQ
Quando una query è in esecuzione come parallela, PLINQ partiziona la sequenza di origine in modo che più thread possano operare simultaneamente su parti diverse, in genere su thread separati. Se i risultati devono essere utilizzati in un unico thread, ad esempio in un ciclo `foreach` (`For Each` in Visual Basic), i risultati di ogni thread devono essere nuovamente uniti in un'unica sequenza. Il tipo di merge che PLINQ esegue dipende dagli operatori presenti nella query. Ad esempio, gli operatori che impongono un nuovo ordine nei risultati devono memorizzare nel buffer tutti gli elementi da tutti i thread. Dal punto di vista del thread consumer (che è anche quello dell'utente dell'applicazione), una query completamente memorizzata nel buffer potrebbe essere eseguita per un periodo considerevole di tempo prima che produca il primo risultato. Gli altri operatori, per impostazione predefinita, sono parzialmente memorizzati nel buffer e generano i risultati in batch. Un operatore, <xref:System.Linq.ParallelEnumerable.ForAll%2A>, non è memorizzato nel buffer per impostazione predefinita. Genera immediatamente tutti gli elementi di tutti i thread.  
  
 Usando il metodo <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>, come illustrato nell'esempio seguente, è possibile fornire un hint a PLINQ indicante il tipo di merge da eseguire.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Per l'esempio completo, vedere [Procedura: Specificare le opzioni di Merge in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Se la query specifica non può supportare l'opzione richiesta, l'opzione verrà ignorata. Nella maggior parte dei casi, non è necessario specificare un'opzione di merge per una query PLINQ. In alcuni casi, tuttavia, in base ai test e alle misurazioni, può risultare evidente che una query viene eseguita meglio in una modalità non predefinita. Un uso comune di questa opzione è quello di forzare un operatore di merge in blocchi per trasmettere i risultati e poter fornire un'interfaccia utente più reattiva.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 L'enumerazione <xref:System.Linq.ParallelMergeOptions> include le opzioni seguenti che specificano, per le forme di query supportate, come viene generato l'output finale della query quando i risultati vengono utilizzati in un unico thread:  
  
- `Not Buffered`  
  
     L'opzione <xref:System.Linq.ParallelMergeOptions.NotBuffered> fa in modo che ogni elemento elaborato venga restituito da ogni thread non appena viene prodotto. Questo comportamento è simile alla "trasmissione" dell'output. Se l'operatore <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> è presente nella query, `NotBuffered` mantiene l'ordine degli elementi di origine. Anche `NotBuffered` se inizia a produrre risultati non appena sono disponibili, il tempo totale per produrre tutti i risultati potrebbe essere ancora più lungo rispetto all'utilizzo di una delle altre opzioni di unione.  
  
- `Auto Buffered`  
  
     Quando si utilizza l'opzione <xref:System.Linq.ParallelMergeOptions.AutoBuffered>, tramite la query vengono raccolti gli elementi in un buffer, quindi viene passato periodicamente il contenuto del buffer in un unico blocco al thread consumer. Questo comportamento è simile alla generazione dei dati di origine in "blocchi" più che al comportamento di "trasmissione" di `NotBuffered`. `AutoBuffered` potrebbe impiegare più tempo di `NotBuffered` per rendere disponibile il primo elemento nel thread consumer. Le dimensioni del buffer e l'esatto comportamento di generazione non sono configurabili e possono variare a seconda dei fattori correlati alla query.  
  
- `FullyBuffered`  
  
     L'opzione <xref:System.Linq.ParallelMergeOptions.FullyBuffered> fa in modo che l'output dell'intera query venga memorizzato nel buffer prima che vengano generati elementi. Quando si usa questa opzione, può essere necessario più tempo prima che il primo elemento sia disponibile nel thread consumer, ma i risultati completi potrebbero tuttavia essere generati più velocemente che usando le altre opzioni.  
  
## <a name="query-operators-that-support-merge-options"></a>Operatori di query che supportano le opzioni di merge  
 La tabella seguente elenca gli operatori che supportano tutte le modalità delle opzioni di merge, soggette alle restrizioni specificate.  
  
|Operatore|Restrizioni|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Query non ordinate che hanno solo un'origine matrice o elenco.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Query non ordinate che hanno solo un'origine matrice o elenco.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|nessuno|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|nessuno|  
  
 Tutti gli altri operatori di query PLINQ potrebbero ignorare le opzioni di merge fornito dall'utente. Alcuni operatori di query, ad esempio <xref:System.Linq.ParallelEnumerable.Reverse%2A> e <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, non possono generare elementi finché tutti non sono stati prodotti e riordinati. Quando viene usato <xref:System.Linq.ParallelMergeOptions> in una query che contiene anche un operatore, ad esempio <xref:System.Linq.ParallelEnumerable.Reverse%2A>, il comportamento di merge non verrà quindi applicato nella query finché tale operatore non avrà prodotto i risultati.  
  
 La possibilità di alcuni operatori di gestire le opzioni di merge dipende dal tipo della sequenza di origine e dal fatto che l'operatore <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> sia stato usato in precedenza nella query. <xref:System.Linq.ParallelEnumerable.ForAll%2A> è sempre <xref:System.Linq.ParallelMergeOptions.NotBuffered>. Genera immediatamente gli elementi. <xref:System.Linq.ParallelEnumerable.OrderBy%2A> è sempre <xref:System.Linq.ParallelMergeOptions.FullyBuffered>. Deve ordinare l'intero elenco prima di generare gli elementi.  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
- [Procedura: specificare le opzioni di merge in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
