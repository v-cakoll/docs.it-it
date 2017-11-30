---
title: Conservazione dell'ordine in PLINQ
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
helpviewer_keywords: PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 060459cf8f408e40ddc394fbcda6a022ec6379de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="order-preservation-in-plinq"></a>Conservazione dell'ordine in PLINQ
In PLINQ, l'obiettivo è ottimizzare le prestazioni, mantenendo la correttezza. Una query deve eseguire più velocemente possibile ma comunque ottenere i risultati corretti. In alcuni casi, la correttezza richiede l'ordine della sequenza di origine deve essere mantenuto; Tuttavia, l'ordinamento può essere onerosa. Pertanto, per impostazione predefinita, PLINQ non mantiene l'ordine della sequenza di origine. In questo senso, simile a PLINQ [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], ma differisce da LINQ to Objects, che conserva l'ordine.  
  
 Per eseguire l'override del comportamento predefinito, è possibile attivare la conservazione dell'ordine tramite il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operatore nella sequenza di origine. È quindi possibile disattivare la conservazione dell'ordine in un secondo momento nella query utilizzando il <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> metodo. Con entrambi i metodi, la query viene elaborata in base alle regole euristiche che determinano se eseguire la query come parallelo o sequenziale. Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
 Nell'esempio seguente viene illustrata una query parallela non ordinata che Filtra per tutti gli elementi che soddisfano una condizione, senza tentare di ordinare i risultati in alcun modo.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 Questa query non produce necessariamente le prime 1000 città nella sequenza di origine che soddisfano la condizione, ma piuttosto un set di 1000 città che soddisfano la condizione. Operatori di query PLINQ partizionare la sequenza di origine in più sottosequenze che vengono elaborati come attività simultanee. Se non viene specificata la conservazione dell'ordine, i risultati di ogni partizione verranno passati alla fase successiva della query in un ordine arbitrario. Inoltre, una partizione può produrre un subset dei relativi risultati prima di continuare a elaborare gli elementi rimanenti. L'ordine risulta potrebbe essere diverso ogni volta. L'applicazione non controlla questo comportamento perché dipende dalla modalità con cui il sistema operativo pianifica il thread.  
  
 Nell'esempio seguente viene eseguito l'override del comportamento predefinito tramite il <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> operatore nella sequenza di origine. In questo modo il <xref:System.Linq.ParallelEnumerable.Take%2A> metodo restituisce le prime 1000 città nella sequenza di origine che soddisfano la condizione.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Tuttavia, la query probabilmente non viene eseguito più velocemente la versione non ordinata perché deve tenere traccia dell'ordine originale in partizioni e in fase di tipo merge, verificare che l'ordinamento sia coerenza. È pertanto consigliabile utilizzare <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> solo quando è necessario e solo per quelle parti della query che lo richiedono. Quando la conservazione dell'ordine non è più necessario, utilizzare <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> per disattivarla. A questo scopo, nell'esempio seguente la composizione di due query.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Si noti che PLINQ mantiene l'ordinamento di una sequenza che impongono l'ordinamento degli operatori per il resto della query. In altre parole, gli operatori come <xref:System.Linq.ParallelEnumerable.OrderBy%2A> e <xref:System.Linq.ParallelEnumerable.ThenBy%2A> vengono considerati come se fossero seguiti da una chiamata a <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
## <a name="query-operators-and-ordering"></a>Gli operatori di query e di ordinamento  
 Gli operatori di query seguenti introducono conservazione dell'ordine in tutte le successive operazioni in una query o fino a quando <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> viene chiamato:  
  
-   <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 I seguenti operatori di query PLINQ possono richiedere, in alcuni casi, le sequenze di origine ordinato per ottenere risultati corretti:  
  
-   <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
-   <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Alcuni operatori di query PLINQ si comportano in modo diverso, a seconda che la sequenza di origine è ordinata o non ordinata. La tabella seguente elenca questi operatori.  
  
|Operatore|Risultato quando viene ordinata in sequenza di origine|Risultato quando non è ordinata la sequenza di origine|  
|--------------|------------------------------------------------|--------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Output non deterministico per operazioni associative o non commutative|Output non deterministico per operazioni associative o non commutative|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|Output non deterministico per operazioni associative o non commutative|Output non deterministico per operazioni associative o non commutative|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|Restituisce l'elemento specificato|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|Restituisce l'elemento specificato|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|Risultati non ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|Restituisce l'elemento specificato|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|Restituisce l'elemento specificato|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Esegue in modo non deterministico in parallelo|Esegue in modo non deterministico in parallelo|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|Restituisce l'elemento specificato|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|Restituisce l'elemento specificato|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|Riordina la sequenza|Avvia una nuova sezione ordinata|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|Riordina la sequenza|Avvia una nuova sezione ordinata|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|Non applicabile (stessa impostazione predefinita di <xref:System.Linq.ParallelEnumerable.AsParallel%2A> )|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|Non applicabile (stessa impostazione predefinita di <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Inverte|Non effettua alcuna operazione.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>(indicizzato)|Risultati ordinati|Risultati non ordinati.|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Risultati ordinati.|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>(indicizzato)|Risultati ordinati.|Risultati non ordinati.|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Confronto ordinato|Confronto non ordinato|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Ignora innanzitutto  *n*  elementi|Ignora qualsiasi  *n*  elementi|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Risultati ordinati.|Non è deterministico. Esegue SkipWhile sull'ordine arbitrario corrente|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Output non deterministico per operazioni associative o non commutative|Output non deterministico per operazioni associative o non commutative|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Accetta i primi `n` elementi|Accetta tutti `n` elementi|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Risultati ordinati|Non è deterministico. Esegue TakeWhile sull'ordine arbitrario corrente|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Supplementi`OrderBy`|Supplementi`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Supplementi`OrderBy`|Supplementi`OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>(indicizzato)|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Risultati ordinati|Risultati non ordinati|  
  
 Risultati non ordinati non vengono mescolati attivamente; semplicemente non hanno alcuna logica speciale di ordinamento applicata ad essi. In alcuni casi, una query non ordinata può mantenere l'ordine della sequenza di origine. Per le query che utilizzano l'operatore Select indicizzato, PLINQ garantisce che gli elementi di output verranno riprodotti nell'ordine crescente i indici, ma non fornisce alcuna garanzia in merito a quali indici non verrà assegnati agli elementi.  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
