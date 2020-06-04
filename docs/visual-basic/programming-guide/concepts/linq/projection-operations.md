---
title: Operazioni di proiezione
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: 4795bdaba53949b34fe380ea9c51025ce43c40db
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396337"
---
# <a name="projection-operations-visual-basic"></a>Operazioni di proiezione (Visual Basic)

La proiezione si riferisce all'operazione di trasformazione di un oggetto in un nuovo form costituito spesso solo dalle proprietà che verranno usate successivamente. Utilizzando la proiezione, è possibile costruire un nuovo tipo compilato in base a ogni oggetto. È possibile proiettare una proprietà ed eseguirvi una funzione matematica. È anche possibile proiettare l'oggetto originale senza modificarlo.

Nella sezione seguente sono elencati i metodi dell'operatore query standard che eseguono la proiezione.

## <a name="methods"></a>Metodi

|Nome metodo|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|
|-----------------|-----------------|------------------------------------------|----------------------|
|Select|Proietta i valori che si basano su una funzione di trasformazione.|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|
|SelectMany|Proietta le sequenze di valori che si basano su una funzione di trasformazione semplificandoli in un'unica sequenza.|Usare più clausole `From`|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query

### <a name="select"></a>Select

L'esempio seguente usa la clausola `Select` per proiettare la prima lettera di ogni stringa di un elenco di stringhe.

```vb
Dim words = New List(Of String) From {"an", "apple", "a", "day"}

Dim query = From word In words
            Select word.Substring(0, 1)

Dim sb As New System.Text.StringBuilder()
For Each letter As String In query
    sb.AppendLine(letter)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' a
' a
' a
' d
```

### <a name="selectmany"></a>SelectMany

Nell'esempio seguente vengono utilizzate più `From` clausole per proiettare ogni parola da ogni stringa in un elenco di stringhe.

```vb
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}

Dim query = From phrase In phrases
            From word In phrase.Split(" "c)
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' an
' apple
' a
' day
' the
' quick
' brown
' fox
```

## <a name="select-versus-selectmany"></a>Confronto tra Select e SelectMany

La funzione di `Select()` e `SelectMany()` è produrre uno o più valori risultato dai valori di origine. `Select()` produce un valore risultato per ogni valore di origine. Il risultato complessivo è pertanto una raccolta contenente lo stesso numero di elementi della raccolta di origine. Al contrario, `SelectMany()` produce un singolo risultato complessivo che contiene sottoraccolte concatenate di ogni valore di origine. La funzione di trasformazione passata come argomento a `SelectMany()` deve restituire una sequenza enumerabile di valori per ogni valore di origine. Queste sequenze enumerabili vengono quindi concatenate da `SelectMany()` per creare un'unica grande sequenza.

Le due figure seguenti illustrano la differenza concettuale tra le azioni di questi due metodi. In ogni caso, si supponga che la funzione del selettore (trasformazione) selezioni la matrice di fiori di ogni valore di origine.

La figura mostra che `Select()` restituisce una raccolta contenente lo stesso numero di elementi della raccolta di origine.

![Elemento grafico che illustra l'azione di Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)

La figura mostra che `SelectMany()` concatena la sequenza intermedia di matrici in un unico valore risultato finale contenente tutti i valori di ogni matrice intermedia.

![Elemento grafico che illustra l'azione di SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )

### <a name="code-example"></a>Esempio di codice

L'esempio seguente confronta il comportamento di `Select()` e `SelectMany()`. Il codice crea un "bouquet" di fiori prendendo i primi due elementi di ogni elenco di nomi di fiori nella raccolta di origine. In questo esempio, il "valore singolo" usato dalla funzione di trasformazione <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> è anch'esso una raccolta di valori. Questo richiede il ciclo `For Each` aggiuntivo in modo da enumerare tutte le stringhe di ogni sottosequenza.

```vb
Class Bouquet
    Public Flowers As List(Of String)
End Class

Sub SelectVsSelectMany()
    Dim bouquets = New List(Of Bouquet) From {
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}

    Dim output As New System.Text.StringBuilder

    ' Select()
    Dim query1 = bouquets.Select(Function(b) b.Flowers)

    output.AppendLine("Using Select():")
    For Each flowerList In query1
        For Each str As String In flowerList
            output.AppendLine(str)
        Next
    Next

    ' SelectMany()
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)

    output.AppendLine(vbCrLf & "Using SelectMany():")
    For Each str As String In query2
        output.AppendLine(str)
    Next

    ' Display the output
    MsgBox(output.ToString())

    ' This code produces the following output:
    '
    ' Using Select():
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

    ' Using SelectMany()
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

End Sub
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Clausola SELECT](../../../language-reference/queries/select-clause.md)
- [Procedura: Combinare dati utilizzando join](../../language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)
- [Procedura: popolare raccolte di oggetti da più origini (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Procedura: restituire un risultato di query LINQ come tipo specifico](../../language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)
- [Procedura: suddividere un file in molti file usando i gruppi (LINQ) (Visual Basic)](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
