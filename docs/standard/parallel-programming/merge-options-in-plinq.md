---
title: Opzioni di merge in PLINQ
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a>Opzioni di merge in PLINQ
Quando una query è in esecuzione come partizioni PLINQ parallele, la sequenza di origine in modo che più thread possano funzionare su parti diverse contemporaneamente, in genere su un thread separato. Se i risultati devono essere utilizzati in un unico thread, ad esempio, in un `foreach` (`For Each` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) ciclo, quindi i risultati di ogni thread devono essere uniti in un'unica sequenza. Il tipo di unione che PLINQ esegue dipende dagli operatori presenti nella query. Ad esempio, gli operatori che impongono un nuovo ordine i risultati devono memorizzare nel buffer tutti gli elementi da tutti i thread. Dalla prospettiva del thread consumer, che corrisponde anche che dell'utente dell'applicazione, potrebbe essere eseguita una query completamente memorizzato nel buffer per un periodo di tempo prima che il primo risultato significativo. Altri operatori, per impostazione predefinita, sono parzialmente memorizzata nel buffer; producono i risultati in batch. Un operatore, <xref:System.Linq.ParallelEnumerable.ForAll%2A> non memorizzato nel buffer per impostazione predefinita. Restituisce tutti gli elementi di tutti i thread immediatamente.  
  
 Tramite il <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> (metodo), come illustrato nell'esempio seguente, è possibile fornire un suggerimento a PLINQ che indica il tipo di unione da eseguire.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Per un esempio completo, vedere [procedura: specificare le opzioni di Merge in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Se la query specifica non supporta l'opzione richiesta, quindi l'opzione verrà ignorata. Nella maggior parte dei casi, non è necessario specificare un'opzione di merge per una query PLINQ. Tuttavia, in alcuni casi può risultare tramite test e misurazioni che una query viene eseguita meglio in una modalità non predefinito. Un utilizzo comune di questa opzione è per forzare un operatore di unione di blocco per trasmettere i risultati per fornire una maggiore efficienza di risposta interfaccia utente.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 Il <xref:System.Linq.ParallelMergeOptions> enumerazione include le opzioni seguenti che specificano, per le forme di query supportate, come viene prodotto l'output finale della query quando vengono usati i risultati in un unico thread:  
  
-   `Not Buffered`  
  
     Il <xref:System.Linq.ParallelMergeOptions.NotBuffered> opzione fa sì che ogni elemento elaborato venga restituito da ogni thread, non appena viene prodotto. Questo comportamento è analogo a "" il flusso di output. Se il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operatore è presente nella query, `NotBuffered` mantiene l'ordine degli elementi di origine. Anche se `NotBuffered` viene avviato, generando risultati non appena ma sono disponibili, il tempo totale necessario per generare tutti i risultati potrebbe comunque essere più lungo di utilizzando una delle altre opzioni di unione.  
  
-   `Auto Buffered`  
  
     Quando si utilizza l'opzione <xref:System.Linq.ParallelMergeOptions.AutoBuffered>, tramite la query vengono raccolti gli elementi in un buffer, quindi viene passato periodicamente il contenuto del buffer in un unico blocco al thread consumer. Questo comportamento è analogo a restituire i dati di origine in "blocchi" anziché il comportamento di "streaming" `NotBuffered`. `AutoBuffered`può richiedere più `NotBuffered` per rendere disponibile il primo elemento nel thread consumer. Le dimensioni del buffer e l'esatto comportamento di produzione non sono configurabili e possono variare a seconda di vari fattori correlati alla query.  
  
-   `FullyBuffered`  
  
     Il <xref:System.Linq.ParallelMergeOptions.FullyBuffered> opzione fa sì che l'output dell'intera query da memorizzare nel buffer prima di tutti gli elementi vengono restituiti. Quando si utilizza questa opzione, può richiedere più tempo prima che il primo elemento è disponibile nel thread consumer, ma i risultati completi possono comunque essere prodotti più veloce tramite le altre opzioni.  
  
## <a name="query-operators-that-support-merge-options"></a>Operatori di query che supportano le opzioni di unione  
 Nella tabella seguente vengono elencati gli operatori che supportano tutte le modalità di opzione di unione, soggetto alle restrizioni specificate.  
  
|Operatore|Restrizioni|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Nessuno|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Nessuno|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Query non ordinate che hanno solo un'origine matrice o elenco.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Nessuno|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Nessuno|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Query non ordinate che hanno solo un'origine matrice o elenco.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Nessuno|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Nessuna|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Nessuna|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Nessuna|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Nessuno|  
  
 Tutti gli altri operatori di query PLINQ potrebbero ignorare le opzioni di unione fornito dall'utente. Alcuni operatori di query, ad esempio, <xref:System.Linq.ParallelEnumerable.Reverse%2A> e <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, possono produrre elementi fino a quando tutti i prodotti e riordinati. Pertanto, quando <xref:System.Linq.ParallelMergeOptions> viene utilizzato in una query che contiene anche un operatore, ad esempio <xref:System.Linq.ParallelEnumerable.Reverse%2A>, il comportamento di tipo merge non essere applicato nella query solo dopo che l'operatore ha generato i risultati.  
  
 La possibilità di alcuni operatori di gestire le opzioni di unione dipende dal tipo della sequenza di origine e se il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operatore è stato utilizzato nella query. <xref:System.Linq.ParallelEnumerable.ForAll%2A>è sempre <xref:System.Linq.ParallelMergeOptions.NotBuffered> ; produce immediatamente gli elementi. <xref:System.Linq.ParallelEnumerable.OrderBy%2A>è sempre <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; deve ordinare l'intero elenco prima di produrre elementi.  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Procedura: Specificare le opzioni di merge in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
