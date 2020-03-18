---
title: Conservazione dell'ordine in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
ms.openlocfilehash: 5b067fa277816e6105d37047c6c4996a4cbb9b5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138214"
---
# <a name="order-preservation-in-plinq"></a>Conservazione dell'ordine in PLINQ
In PLINQ, l'obiettivo è ottimizzare le prestazioni, mantenendo la correttezza. Una query deve essere eseguita il più velocemente possibile ma comunque produrre i risultati corretti. In alcuni casi, la correttezza richiede il mantenimento dell'ordine della sequenza di origine, ma l'ordinamento può essere oneroso a livello di risorse di calcolo. Pertanto, per impostazione predefinita, PLINQ non mantiene l'ordine della sequenza di origine. Da questo punto di vista, PLINQ è simile a [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], ma differisce da LINQ to Objects, che mantiene l'ordinamento.  
  
 Per eseguire l'override del comportamento predefinito, è possibile attivare il mantenimento dell'ordine usando l'operatore <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> nella sequenza di origine. È quindi possibile disattivare il mantenimento dell'ordine in un secondo momento nella query usando il metodo <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>. Con entrambi i metodi, la query viene elaborata in base alle regole euristiche che determinano se scegliere l'esecuzione parallela o sequenziale per la query. Per altre informazioni, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
 L'esempio seguente mostra una query parallela non ordinata che applica un filtro per individuare tutti gli elementi che soddisfano una condizione, senza tentare di ordinare i risultati in alcun modo.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 Questa query non produce necessariamente le prime 1000 città nella sequenza di origine che soddisfano la condizione, ma piuttosto un set di 1000 città che soddisfano la condizione. Gli operatori di query PLINQ partizionano la sequenza di origine in più sottosequenze che vengono elaborate come attività simultanee. Se non viene specificato di mantenere l'ordine, i risultati di ogni partizione vengono passati alla fase successiva della query in ordine arbitrario. Inoltre, una partizione potrebbe produrre un subset di risultati prima di continuare a elaborare gli elementi rimanenti. L'ordine risultante potrebbe essere diverso ogni volta. L'applicazione non può controllare questo comportamento perché dipende dalla modalità di pianificazione dei thread del sistema operativo.  
  
 Nell'esempio seguente viene eseguito l'override del comportamento predefinito tramite l'operatore <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> nella sequenza di origine. Ciò assicura che il metodo <xref:System.Linq.ParallelEnumerable.Take%2A> restituisca le prime 1000 città nella sequenza di origine che soddisfano la condizione.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Tuttavia, questa query probabilmente non viene eseguita altrettanto velocemente della versione non ordinata perché deve tenere traccia dell'ordine originale per tutte le partizioni e assicurarsi che l'ordine sia coerente al momento dell'unione. È pertanto consigliabile usare <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> solo quando è necessario e solo per le parti della query che lo richiedono. Quando non occorre più mantenere l'ordine, usare <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> per disattivare questo comportamento. L'esempio ottiene questo risultato tramite la composizione di due query.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Si noti che PLINQ mantiene l'ordinamento di una sequenza da operatori che impongono l'ordine per il resto della query. In altre parole, gli operatori come <xref:System.Linq.ParallelEnumerable.OrderBy%2A> e <xref:System.Linq.ParallelEnumerable.ThenBy%2A> vengono gestiti come se fossero seguiti da una chiamata a <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
## <a name="query-operators-and-ordering"></a>Operatori di query e di ordinamento  
 Gli operatori di query seguenti introducono il mantenimento dell'ordine in tutte le successive operazioni in una query o fino a quando non viene chiamato <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>:  
  
- <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 Gli operatori di query PLINQ seguenti possono richiedere in alcuni casi sequenze di origine ordinate per produrre risultati corretti:  
  
- <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
- <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Alcuni operatori di query PLINQ si comportano in modo diverso, a seconda che la sequenza di origine sia ordinata o non ordinata. Questi operatori sono elencati nella tabella seguente.  
  
|Operatore|Risultato quando la sequenza di origine è ordinata|Risultato quando la sequenza di origine non è ordinata|  
|--------------|------------------------------------------------|--------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Output non deterministico per operazioni non associative o non commutative|Output non deterministico per operazioni non associative o non commutative|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|Output non deterministico per operazioni non associative o non commutative|Output non deterministico per operazioni non associative o non commutative|  
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
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Esecuzione non deterministica in parallelo|Esecuzione non deterministica in parallelo|  
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
|<xref:System.Linq.ParallelEnumerable.Range%2A>|Non applicabile (stessa impostazione predefinita di <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|Non applicabile (stessa impostazione predefinita di <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Inverte|Non effettua alcuna operazione.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Select%2A> (indicizzato)|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A> (indicizzato)|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Confronto ordinato|Confronto non ordinato|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Ignora i primi elementi *n*|Ignora tutti gli elementi *n*|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Risultati ordinati|Non deterministico Esegue SkipWhile sull'ordine arbitrario corrente|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Output non deterministico per operazioni non associative o non commutative|Output non deterministico per operazioni non associative o non commutative|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Accetta i primi `n` elementi|Accetta `n` elementi|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Risultati ordinati|Non deterministico Esegue TakeWhile sull'ordine arbitrario corrente|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Supplemento di `OrderBy`|Supplemento di `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Supplemento di `OrderBy`|Supplemento di `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|Non applicabile|Non applicabile|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Where%2A> (indicizzato)|Risultati ordinati|Risultati non ordinati|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Risultati ordinati|Risultati non ordinati|  
  
 I risultati non ordinati non vengono disposti attivamente in ordine casuale, ma semplicemente non viene loro applicata alcuna logica speciale di ordinamento. In alcuni casi, una query non ordinata può mantenere l'ordine della sequenza di origine. Per le query che usano l'operatore Select indicizzato, PLINQ garantisce che gli elementi di output vengano restituiti nell'ordine crescente di indice, ma non viene in alcun modo garantito quali indici verranno assegnati a quali elementi.  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
