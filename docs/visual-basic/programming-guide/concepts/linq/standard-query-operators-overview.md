---
title: Cenni preliminari sugli operatori di query standard
ms.date: 07/20/2015
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
ms.openlocfilehash: 0f68d175b526a9da86853272c47b5e7d7b4a5992
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201088"
---
# <a name="standard-query-operators-overview-visual-basic"></a>Panoramica degli operatori query standard (Visual Basic)

Gli *operatori di query standard* sono metodi che costituiscono il modello LINQ. La maggior parte di questi metodi agisce sulle sequenze. Una sequenza è un oggetto il cui tipo implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> o l'interfaccia <xref:System.Linq.IQueryable%601>. Gli operatori di query standard forniscono le funzionalità di query che includono filtro, proiezione, aggregazione, ordinamento e altro ancora.

Sono disponibili due set di operatori di query standard LINQ, uno che agisce sugli oggetti di tipo <xref:System.Collections.Generic.IEnumerable%601> e l'altro che agisce sugli oggetti di tipo <xref:System.Linq.IQueryable%601>. I metodi che costituiscono ogni set sono membri statici delle classi <xref:System.Linq.Enumerable> e <xref:System.Linq.Queryable>, rispettivamente. Vengono definiti come *metodi di estensione* del tipo su cui agiscono. Ciò significa che possono essere chiamati usando la sintassi del metodo statico o la sintassi del metodo di istanza.

Inoltre, molti metodi degli operatori query standard agiscono su tipi diversi da quelli basati su <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>. Il tipo <xref:System.Linq.Enumerable> definisce questi due diversi metodi che agiscono entrambi su oggetti di tipo <xref:System.Collections.IEnumerable>. Questi metodi, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> e <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, consentono l'esecuzione di query su una Collection senza parametri o non generica nel modello LINQ A tale scopo, crea una raccolta fortemente tipizzata di oggetti. La classe <xref:System.Linq.Queryable> definisce due metodi simili, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> e <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, che agiscono su oggetti di tipo <xref:System.Linq.Queryable>.

Gli operatori di query standard presentano una durata di esecuzione diversa, a seconda che restituiscano un valore singleton o una sequenza di valori. Questi metodi che restituiscono un valore singleton, ad esempio <xref:System.Linq.Enumerable.Average%2A> e <xref:System.Linq.Enumerable.Sum%2A>, vengono eseguiti immediatamente. I metodi che restituiscono una sequenza rinviano l'esecuzione della query e restituiscono un oggetto enumerabile.

Nel caso dei metodi che agiscono sulle Collection in memoria, ovvero i metodi che estendono <xref:System.Collections.Generic.IEnumerable%601>, l'oggetto enumerabile restituito acquisisce gli argomenti passati al metodo. Quando l'oggetto viene enumerato, viene utilizzata la logica dell'operatore query e vengono restituiti i risultati della query.

I metodi che estendono <xref:System.Linq.IQueryable%601> non implementano invece il comportamento delle query, ma compilano un albero delle espressioni che rappresenta la query da eseguire. L'elaborazione delle query viene gestita dall'oggetto <xref:System.Linq.IQueryable%601> di origine.

Le chiamate ai metodi della query possono essere concatenate in una query, consentendo alle query di diventare arbitrariamente complesse.

Nell'esempio di codice seguente viene illustrato come usare gli operatori di query standard per ottenere informazioni su una sequenza.

```vb
Dim sentence = "the quick brown fox jumps over the lazy dog"
' Split the string into individual words to create a collection.
Dim words = sentence.Split(" "c)

Dim query = From word In words
            Group word.ToUpper() By word.Length Into gr = Group
            Order By Length _
            Select Length, GroupedWords = gr

Dim output As New System.Text.StringBuilder
For Each obj In query
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))
    For Each word As String In obj.GroupedWords
        output.AppendLine(word)
    Next
Next

'Display the output
MsgBox(output.ToString())

' This code example produces the following output:
'
' Words of length 3:
' THE
' FOX
' THE
' DOG
' Words of length 4:
' OVER
' LAZY
' Words of length 5:
' QUICK
' BROWN
' JUMPS
```

## <a name="query-expression-syntax"></a>Sintassi delle espressioni di query

Alcuni degli operatori di query standard usati più di frequente dispongono di sintassi dedicata delle parole chiave per i linguaggi C# e Visual Basic che consente di chiamare gli operatori come parte di un'*espressione di * *query*. Per ulteriori informazioni sugli operatori di query standard che hanno parole chiave dedicate e le relative sintassi corrispondenti, vedere [sintassi delle espressioni di query per gli operatori di query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).

## <a name="extending-the-standard-query-operators"></a>Estensione degli operatori di query standard

È possibile estendere il set di operatori di query standard creando metodi specifici del dominio appropriati per la tecnologia o il dominio di destinazione. È possibile anche sostituire gli operatori di query standard con implementazioni personalizzate che forniscono servizi aggiuntivi, ad esempio la valutazione remota, la conversione delle query e l'ottimizzazione. Per un esempio, vedere <xref:System.Linq.Enumerable.AsEnumerable%2A>.

## <a name="related-sections"></a>Sezioni correlate

I collegamenti riportati di seguito consentono di passare ad argomenti che forniscono informazioni aggiuntive sui vari operatori di query standard in base alla funzionalità.

- [Ordinamento dei dati](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)

- [Operazioni set (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)

- [Filtraggio dei dati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)

- [Operazioni del quantificatore (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)

- [Operazioni di proiezione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)

- [Partizionamento dei dati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)

- [Operazioni di join (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)

- [Raggruppamento di dati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)

- [Operazioni di generazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)

- [Operazioni di uguaglianza (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)

- [Operazioni sugli elementi (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)

- [Conversione di tipi di dati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)

- [Operazioni di concatenazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)

- [Operazioni di aggregazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Introduzione a LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [Sintassi delle espressioni di query per gli operatori di query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [Classificazione degli operatori di query standard in base alla modalità di esecuzione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
- [Metodi di estensione](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
