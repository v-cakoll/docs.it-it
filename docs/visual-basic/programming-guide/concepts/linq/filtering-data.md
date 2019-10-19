---
title: Filtraggio dei dati (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 27765247daa2155e685b1cd2bfccebb3216ca672
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582441"
---
# <a name="filtering-data-visual-basic"></a>Filtraggio dei dati (Visual Basic)

Il filtro si riferisce all'operazione in base alla quale il set di risultati viene limitato in modo da contenere solo gli elementi che corrispondono a una condizione specificata. È anche noto come selezione.

Nella figura seguente vengono illustrati i risultati del filtro di una sequenza di caratteri. Il predicato per l'operazione di filtro specifica che il carattere deve essere 'A'.

![Diagramma che illustra un'operazione di filtro LINQ](./media/filtering-data/linq-filter-operation.png)

La sezione seguente elenca i metodi dell'operatore query standard che esegue la selezione.

## <a name="methods"></a>Metodi

|Nome metodo|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|
|-----------------|-----------------|------------------------------------------|----------------------|
|OfType|Seleziona i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.|Non applicabile.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|Dove|Seleziona i valori che si basano su una funzione di predicato.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Esempi di sintassi delle espressioni di query

Nell'esempio seguente viene usato il `Where` per filtrare da una matrice le stringhe con una lunghezza specifica.

```vb
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}

Dim query = From word In words
            Where word.Length = 3
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Procedura: Filtrare i risultati di una query](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [Procedura: eseguire una query sui metadati di un assembly tramite reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Procedura: eseguire una query per i file con un nome o un attributo specificato (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Procedura: ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
