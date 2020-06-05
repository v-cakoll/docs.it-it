---
title: Ordinamento dei dati
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: a5ccff745995ed7f41731cf98fb7c49d3247d994
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406794"
---
# <a name="sorting-data-visual-basic"></a>Ordinamento dei dati (Visual Basic)

Un'operazione di ordinamento consente di ordinare gli elementi di una sequenza in base a uno o più attributi. Il primo criterio di ordinamento consente di applicare un ordinamento principale agli elementi. Specificando un secondo criterio di ordinamento, è possibile ordinare gli elementi all'interno di ogni gruppo di ordinamento principale.

La figura seguente illustra i risultati di un'operazione di ordinamento alfabetico in una sequenza di caratteri.

![Immagine che illustra un'operazione di ordinamento alfabetico.](./media/sorting-data/alphabetical-sort-operation.png)

La sezione seguente elenca i metodi dell'operatore query standard che ordina i dati.

## <a name="methods"></a>Metodi

|Nome metodo|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|
|-----------------|-----------------|------------------------------------------|----------------------|
|OrderBy|Ordina i valori in ordine crescente.|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|OrderByDescending|Ordina i valori in ordine decrescente.|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|ThenBy|Esegue un ordinamento secondario crescente.|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|ThenByDescending|Esegue un ordinamento secondario decrescente.|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|Reverse|Inverte l'ordine degli elementi in una Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query

### <a name="primary-sort-examples"></a>Esempi di ordinamento primario

#### <a name="primary-ascending-sort"></a>Ordinamento primario crescente

Nell'esempio seguente viene illustrato come usare la clausola `Order By` in una query LINQ per ordinare le stringhe in una matrice in base alla lunghezza di stringa, in ordine crescente.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a>Ordinamento primario decrescente

Nell'esempio seguente viene illustrato come usare la clausola `Order By Descending` in una query LINQ per ordinare le stringhe in base alla prima lettera, in ordine decrescente.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a>Esempi di ordinamento secondario

#### <a name="secondary-ascending-sort"></a>Ordinamento secondario crescente

Nell'esempio seguente viene illustrato come usare la clausola `Order By` in una query LINQ per eseguire un ordinamento primario e secondario delle stringhe in una matrice. Le stringhe vengono ordinate prima in base alla lunghezza e poi in base alla prima lettera della stringa, in ordine crescente.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a>Ordinamento secondario in ordine decrescente

L'esempio seguente illustra come usare la clausola `Order By Descending` in una query LINQ per eseguire un ordinamento primario, in ordine crescente, e un ordinamento secondario, in ordine decrescente. Le stringhe vengono ordinate principalmente in base alla lunghezza e poi in base alla prima lettera della stringa.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Clausola Order By](../../../language-reference/queries/order-by-clause.md)
- [Procedura: Ordinare i risultati di query](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [Procedura: ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
