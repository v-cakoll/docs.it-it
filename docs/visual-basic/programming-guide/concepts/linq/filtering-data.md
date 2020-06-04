---
title: Filtraggio dei dati
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: f7a1aa76dc93cc03952e55f5f8fc3f75176a3f9f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383417"
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
|Where|Seleziona i valori che si basano su una funzione di predicato.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Esempio di sintassi delle espressioni di query

Nell'esempio seguente viene usato `Where` per filtrare da una matrice le stringhe con una lunghezza specifica.

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
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Clausola WHERE](../../../language-reference/queries/where-clause.md)
- [Procedura: Filtrare i risultati di una query](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [Procedura: eseguire una query sui metadati di un assembly tramite reflection (LINQ) (Visual Basic)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Procedura: eseguire una query per i file con un nome o un attributo specificato (Visual Basic)](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Procedura: ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
