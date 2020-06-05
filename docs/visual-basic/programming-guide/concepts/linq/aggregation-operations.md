---
title: Operazioni di aggregazione
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 8e2c9698de67dc4def348a03c9d69713a6130f31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383793"
---
# <a name="aggregation-operations-visual-basic"></a>Operazioni di aggregazione (Visual Basic)
Un'operazione di aggregazione calcola un singolo valore da una raccolta di valori. Un esempio di operazione di aggregazione è rappresentato dal calcolo della temperatura media giornaliera dai valori della temperatura giornaliera di un mese.  
  
 La figura seguente illustra i risultati di due operazioni di aggregazione diverse in una sequenza di numeri. La prima operazione somma i numeri. La seconda operazione restituisce il valore massimo nella sequenza.  
  
 ![Figura che illustra operazioni di aggregazione LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 La sezione seguente elenca i metodi degli operatori di query standard che eseguono operazioni di aggregazione.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Aggregate|Esegue un'operazione di aggregazione personalizzata sui valori di una raccolta.|Non applicabile.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Media|Calcola il valore medio di una raccolta di valori.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Conteggio|Conta gli elementi in una raccolta e, facoltativamente, solo gli elementi che soddisfano una funzione di predicato.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Conta gli elementi in una raccolta di grandi dimensioni e, facoltativamente, solo gli elementi che soddisfano una funzione di predicato.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Max|Determina il valore massimo in una raccolta.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Min|Determina il valore minimo in una raccolta.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Somma|Calcola la somma dei valori in una raccolta.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query  
  
### <a name="average"></a>Media  
 Nell'esempio di codice seguente viene usata la `Aggregate Into Average` clausola in Visual Basic per calcolare la temperatura media in una matrice di numeri che rappresentano le temperature.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Conteggio  
 Nell'esempio di codice seguente viene usata la `Aggregate Into Count` clausola in Visual Basic per conteggiare il numero di valori in una matrice che sono maggiori o uguali a 80.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  
 Nell'esempio di codice seguente viene usata la `Aggregate Into LongCount` clausola per contare il numero di valori in una matrice.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Max  
 Nell'esempio di codice seguente viene usata la `Aggregate Into Max` clausola per calcolare la temperatura massima in una matrice di numeri che rappresentano le temperature.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Min  
 Nell'esempio di codice seguente viene usata la `Aggregate Into Min` clausola per calcolare la temperatura minima in una matrice di numeri che rappresentano le temperature.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>Somma  
 Nell'esempio di codice seguente viene usata la `Aggregate Into Sum` clausola per calcolare l'importo totale delle spese da una matrice di valori che rappresentano le spese.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [Procedura: calcolare i valori di colonna in un file di testo CSV (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Procedura: Conteggio, somma o media di dati](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Procedura: Trovare il valore minimo o massimo in un risultato di query](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ) (Visual Basic)](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Procedura: eseguire una query per il numero totale di byte in un set di cartelle (LINQ) (Visual Basic)](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
