---
title: 'Procedura: Aggiungere metodi personalizzati per query LINQ'
ms.date: 07/20/2015
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
ms.openlocfilehash: 55004441d2d1d74556da6841f28d113b876d1048
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400604"
---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic)

È possibile estendere il set di metodi da usare per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>. Oltre alla media standard o a un numero massimo di operazioni, ad esempio, è possibile creare un metodo di aggregazione personalizzato per calcolare un singolo valore da una sequenza di valori. È anche possibile creare un metodo che funzioni come un filtro personalizzato o una trasformazione di dati specifica per una sequenza di valori che restituisca una nuova sequenza. Esempi di tali metodi sono <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> e <xref:System.Linq.Enumerable.Reverse%2A>.

Quando si estende l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, è possibile applicare i metodi personalizzati a qualsiasi raccolta enumerabile. Per altre informazioni, vedere [Metodi di estensione](../../language-features/procedures/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Aggiunta di un metodo di aggregazione

Un metodo di aggregazione calcola un singolo valore da un set di valori. LINQ offre diversi metodi di aggregazione, tra cui <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> e <xref:System.Linq.Enumerable.Max%2A>. È possibile creare il proprio metodo di aggregazione aggiungendo un metodo di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.

L'esempio di codice seguente illustra come creare un metodo di estensione denominato `Median` per calcolare un valore mediano per una sequenza di numeri di tipo `double`.

```vb
Imports System.Runtime.CompilerServices

Module LINQExtension

    ' Extension method for the IEnumerable(of T) interface.
    ' The method accepts only values of the Double type.
    <Extension()>
    Function Median(ByVal source As IEnumerable(Of Double)) As Double
        If source.Count = 0 Then
            Throw New InvalidOperationException("Cannot compute median for an empty set.")
        End If

        Dim sortedSource = From number In source
                           Order By number

        Dim itemIndex = sortedSource.Count \ 2

        If sortedSource.Count Mod 2 = 0 Then
            ' Even number of items in list.
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2
        Else
            ' Odd number of items in list.
            Return sortedSource(itemIndex)
        End If
    End Function
End Module
```

Chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo in cui si chiamano altri metodi di aggregazione dall'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.

> [!NOTE]
> In Visual Basic, è possibile usare una chiamata al metodo o una sintassi di query standard per la `Aggregate` `Group By` clausola o. Per ulteriori informazioni, vedere clausola [Aggregate](../../../language-reference/queries/aggregate-clause.md) e [clausola Group by](../../../language-reference/queries/group-by-clause.md).

L'esempio di codice seguente illustra come usare il metodo `Median` di una matrice di tipo `double`.

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Overload di un metodo di aggregazione per accettare tipi diversi

È possibile eseguire l'overload del metodo di aggregazione in modo che accetti sequenze di tipi diversi. L'approccio standard consiste nel creare un overload per ogni tipo. Un altro approccio consiste nel creare un overload che accetti un tipo generico e lo converta in un tipo specifico tramite un delegato. È anche possibile combinare entrambi gli approcci.

#### <a name="to-create-an-overload-for-each-type"></a>Per creare un overload per ogni tipo

È possibile creare un overload specifico per ogni tipo che si vuole supportare. Nell'esempio di codice seguente viene illustrato l'overload del metodo `Median` per il tipo `integer`.

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

È ora possibile chiamare gli overload `Median` per entrambi i tipi `integer` e `double`, come illustrato nel codice seguente:

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
Dim numbers2() As Integer = {1, 2, 3, 4, 5}

Dim query2 = Aggregate num In numbers2 Into Median()

Console.WriteLine("Integer: Median = " & query2)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
' Integer: Median = 3
```

#### <a name="to-create-a-generic-overload"></a>Per creare un overload generico

È anche possibile creare un overload che accetti una sequenza di oggetti generici. Questo overload accetta un delegato come parametro e lo usa per convertire una sequenza di oggetti di un tipo generico in un tipo specifico.

Il codice seguente mostra un overload del metodo `Median` che accetta il delegato <xref:System.Func%602> come parametro. Questo delegato accetta un oggetto di tipo generico T e restituisce un oggetto di tipo `double`.

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

È ora possibile chiamare il metodo `Median` per una sequenza di oggetti di qualsiasi tipo. Se il tipo non ha un proprio overload del metodo, è necessario passare un parametro del delegato. In Visual Basic, è possibile usare un'espressione lambda a questo scopo. Inoltre, se si utilizza la `Aggregate` `Group By` clausola o invece della chiamata al metodo, è possibile passare qualsiasi valore o espressione nella clausola SCOPE this.

L'esempio di codice seguente illustra come chiamare il metodo `Median` per una matrice di numeri interi e una matrice di stringhe. Per le stringhe, viene calcolato il valore mediano della lunghezza delle stringhe nella matrice. L'esempio mostra come passare il parametro del delegato <xref:System.Func%602> al metodo `Median` per ogni caso.

```vb
Dim numbers3() As Integer = {1, 2, 3, 4, 5}

' You can use num as a parameter for the Median method
' so that the compiler will implicitly convert its value to double.
' If there is no implicit conversion, the compiler will
' display an error message.

Dim query3 = Aggregate num In numbers3 Into Median(num)

Console.WriteLine("Integer: Median = " & query3)

Dim numbers4() As String = {"one", "two", "three", "four", "five"}

' With the generic overload, you can also use numeric properties of objects.

Dim query4 = Aggregate str In numbers4 Into Median(str.Length)

Console.WriteLine("String: Median = " & query4)

' This code produces the following output:
'
' Integer: Median = 3
' String: Median = 4
```

## <a name="adding-a-method-that-returns-a-collection"></a>Aggiunta di un metodo che restituisce una raccolta

È possibile estendere l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> con un metodo di query personalizzato che restituisce una sequenza di valori. In questo caso, il metodo deve restituire una raccolta di tipo <xref:System.Collections.Generic.IEnumerable%601>. Tali metodi possono essere usati per applicare filtri o trasformazioni di dati in una sequenza di valori.

Nell'esempio seguente viene illustrato come creare un metodo di estensione denominato `AlternateElements` che restituisce tutti gli altri elementi in una raccolta, a partire dal primo elemento.

```vb
' Extension method for the IEnumerable(of T) interface.
' The method returns every other element of a sequence.

<Extension()>
Function AlternateElements(Of T)(
    ByVal source As IEnumerable(Of T)
    ) As IEnumerable(Of T)

    Dim list As New List(Of T)
    Dim i = 0
    For Each element In source
        If (i Mod 2 = 0) Then
            list.Add(element)
        End If
        i = i + 1
    Next
    Return list
End Function
```

È possibile chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo in cui si chiamano altri metodi dall'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, come illustrato nel codice seguente:

```vb
Dim strings() As String = {"a", "b", "c", "d", "e"}

Dim query = strings.AlternateElements()

For Each element In query
    Console.WriteLine(element)
Next

' This code produces the following output:
'
' a
' c
' e
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.IEnumerable%601>
- [Metodi di estensione](../../language-features/procedures/extension-methods.md)
