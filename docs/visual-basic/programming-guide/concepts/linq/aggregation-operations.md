---
title: Operazioni di aggregazione (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 72268e27fdf6d573279e98438fd884a076e0c8a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817240"
---
# <a name="aggregation-operations-visual-basic"></a>Operazioni di aggregazione (Visual Basic)
Un'operazione di aggregazione calcola un singolo valore da una raccolta di valori. Un esempio di operazione di aggregazione è rappresentato dal calcolo della temperatura media giornaliera dai valori della temperatura giornaliera di un mese.  
  
 La figura seguente illustra i risultati di due operazioni di aggregazione diverse in una sequenza di numeri. La prima operazione somma i numeri. La seconda operazione restituisce il valore massimo nella sequenza.  
  
 ![Figura che illustra operazioni di aggregazione LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 La sezione seguente elenca i metodi degli operatori di query standard che eseguono operazioni di aggregazione.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi delle espressioni di Query Visual Basic|Altre informazioni|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Aggregate|Esegue un'operazione di aggregazione personalizzata sui valori di una raccolta.|Non applicabile.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Media|Calcola il valore medio di una raccolta di valori.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Conteggio|Conta gli elementi in una raccolta e, facoltativamente, solo gli elementi che soddisfano una funzione di predicato.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Conta gli elementi in una raccolta di grandi dimensioni e, facoltativamente, solo gli elementi che soddisfano una funzione di predicato.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Max|Determina il valore massimo in una raccolta.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Min|Determina il valore minimo in una raccolta.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Calcola la somma dei valori in una raccolta.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query  
  
### <a name="average"></a>Media  
 Il codice seguente viene illustrato come utilizzare il `Aggregate Into Average` clausola in Visual Basic per calcolare la temperatura media in una matrice di numeri che rappresentano le temperature.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Conteggio  
 Il codice seguente viene illustrato come utilizzare il `Aggregate Into Count` clausola in Visual Basic per contare il numero di valori in una matrice che sono maggiori o uguali a 80.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  
 Il codice seguente viene illustrato come utilizzare il `Aggregate Into LongCount` clausola per contare il numero di valori in una matrice.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Max  
 Il codice seguente viene illustrato come utilizzare il `Aggregate Into Max` clausola per la quale calcolare la temperatura massima in una matrice di numeri che rappresentano le temperature.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Min  
 Il codice seguente viene illustrato come utilizzare il `Aggregate Into Min` clausola per la quale calcolare la temperatura minima in una matrice di numeri che rappresentano le temperature.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>Sum  
 Il codice seguente viene illustrato come utilizzare il `Aggregate Into Sum` clausola per calcolare l'importo di spesa totale da una matrice di valori che rappresentano le spese.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Procedura: Calcolare i valori di colonna in un File di testo CSV (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Procedura: Conteggio, somma o Media di dati](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Procedura: Trovare il valore minimo o massimo in un risultato di Query](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [Procedura: Eseguire una query per i File più grande o in un albero di Directory (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Procedura: Eseguire una query per il numero totale di byte in un Set di cartelle (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
