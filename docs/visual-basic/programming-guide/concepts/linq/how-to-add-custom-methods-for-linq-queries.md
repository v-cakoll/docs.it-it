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
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="a7b65-102">Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7b65-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>

<span data-ttu-id="a7b65-103">È possibile estendere il set di metodi da usare per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a7b65-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="a7b65-104">Oltre alla media standard o a un numero massimo di operazioni, ad esempio, è possibile creare un metodo di aggregazione personalizzato per calcolare un singolo valore da una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="a7b65-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="a7b65-105">È anche possibile creare un metodo che funzioni come un filtro personalizzato o una trasformazione di dati specifica per una sequenza di valori che restituisca una nuova sequenza.</span><span class="sxs-lookup"><span data-stu-id="a7b65-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="a7b65-106">Esempi di tali metodi sono <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> e <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7b65-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="a7b65-107">Quando si estende l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, è possibile applicare i metodi personalizzati a qualsiasi raccolta enumerabile.</span><span class="sxs-lookup"><span data-stu-id="a7b65-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="a7b65-108">Per altre informazioni, vedere [Metodi di estensione](../../language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a7b65-108">For more information, see [Extension Methods](../../language-features/procedures/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="a7b65-109">Aggiunta di un metodo di aggregazione</span><span class="sxs-lookup"><span data-stu-id="a7b65-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="a7b65-110">Un metodo di aggregazione calcola un singolo valore da un set di valori.</span><span class="sxs-lookup"><span data-stu-id="a7b65-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="a7b65-111">LINQ offre diversi metodi di aggregazione, tra cui <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> e <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7b65-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="a7b65-112">È possibile creare il proprio metodo di aggregazione aggiungendo un metodo di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a7b65-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="a7b65-113">L'esempio di codice seguente illustra come creare un metodo di estensione denominato `Median` per calcolare un valore mediano per una sequenza di numeri di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="a7b65-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

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

<span data-ttu-id="a7b65-114">Chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo in cui si chiamano altri metodi di aggregazione dall'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a7b65-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

> [!NOTE]
> <span data-ttu-id="a7b65-115">In Visual Basic, è possibile usare una chiamata al metodo o una sintassi di query standard per la `Aggregate` `Group By` clausola o.</span><span class="sxs-lookup"><span data-stu-id="a7b65-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="a7b65-116">Per ulteriori informazioni, vedere clausola [Aggregate](../../../language-reference/queries/aggregate-clause.md) e [clausola Group by](../../../language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7b65-116">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>

<span data-ttu-id="a7b65-117">L'esempio di codice seguente illustra come usare il metodo `Median` di una matrice di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="a7b65-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

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

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="a7b65-118">Overload di un metodo di aggregazione per accettare tipi diversi</span><span class="sxs-lookup"><span data-stu-id="a7b65-118">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="a7b65-119">È possibile eseguire l'overload del metodo di aggregazione in modo che accetti sequenze di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="a7b65-119">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="a7b65-120">L'approccio standard consiste nel creare un overload per ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="a7b65-120">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="a7b65-121">Un altro approccio consiste nel creare un overload che accetti un tipo generico e lo converta in un tipo specifico tramite un delegato.</span><span class="sxs-lookup"><span data-stu-id="a7b65-121">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="a7b65-122">È anche possibile combinare entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="a7b65-122">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="a7b65-123">Per creare un overload per ogni tipo</span><span class="sxs-lookup"><span data-stu-id="a7b65-123">To create an overload for each type</span></span>

<span data-ttu-id="a7b65-124">È possibile creare un overload specifico per ogni tipo che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="a7b65-124">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="a7b65-125">Nell'esempio di codice seguente viene illustrato l'overload del metodo `Median` per il tipo `integer`.</span><span class="sxs-lookup"><span data-stu-id="a7b65-125">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

<span data-ttu-id="a7b65-126">È ora possibile chiamare gli overload `Median` per entrambi i tipi `integer` e `double`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a7b65-126">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

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

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="a7b65-127">Per creare un overload generico</span><span class="sxs-lookup"><span data-stu-id="a7b65-127">To create a generic overload</span></span>

<span data-ttu-id="a7b65-128">È anche possibile creare un overload che accetti una sequenza di oggetti generici.</span><span class="sxs-lookup"><span data-stu-id="a7b65-128">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="a7b65-129">Questo overload accetta un delegato come parametro e lo usa per convertire una sequenza di oggetti di un tipo generico in un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="a7b65-129">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="a7b65-130">Il codice seguente mostra un overload del metodo `Median` che accetta il delegato <xref:System.Func%602> come parametro.</span><span class="sxs-lookup"><span data-stu-id="a7b65-130">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="a7b65-131">Questo delegato accetta un oggetto di tipo generico T e restituisce un oggetto di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="a7b65-131">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

<span data-ttu-id="a7b65-132">È ora possibile chiamare il metodo `Median` per una sequenza di oggetti di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="a7b65-132">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="a7b65-133">Se il tipo non ha un proprio overload del metodo, è necessario passare un parametro del delegato.</span><span class="sxs-lookup"><span data-stu-id="a7b65-133">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="a7b65-134">In Visual Basic, è possibile usare un'espressione lambda a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="a7b65-134">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="a7b65-135">Inoltre, se si utilizza la `Aggregate` `Group By` clausola o invece della chiamata al metodo, è possibile passare qualsiasi valore o espressione nella clausola SCOPE this.</span><span class="sxs-lookup"><span data-stu-id="a7b65-135">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="a7b65-136">L'esempio di codice seguente illustra come chiamare il metodo `Median` per una matrice di numeri interi e una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="a7b65-136">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="a7b65-137">Per le stringhe, viene calcolato il valore mediano della lunghezza delle stringhe nella matrice.</span><span class="sxs-lookup"><span data-stu-id="a7b65-137">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="a7b65-138">L'esempio mostra come passare il parametro del delegato <xref:System.Func%602> al metodo `Median` per ogni caso.</span><span class="sxs-lookup"><span data-stu-id="a7b65-138">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

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

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="a7b65-139">Aggiunta di un metodo che restituisce una raccolta</span><span class="sxs-lookup"><span data-stu-id="a7b65-139">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="a7b65-140">È possibile estendere l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> con un metodo di query personalizzato che restituisce una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="a7b65-140">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="a7b65-141">In questo caso, il metodo deve restituire una raccolta di tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a7b65-141">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="a7b65-142">Tali metodi possono essere usati per applicare filtri o trasformazioni di dati in una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="a7b65-142">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="a7b65-143">Nell'esempio seguente viene illustrato come creare un metodo di estensione denominato `AlternateElements` che restituisce tutti gli altri elementi in una raccolta, a partire dal primo elemento.</span><span class="sxs-lookup"><span data-stu-id="a7b65-143">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

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

<span data-ttu-id="a7b65-144">È possibile chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo in cui si chiamano altri metodi dall'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a7b65-144">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a7b65-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7b65-145">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="a7b65-146">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="a7b65-146">Extension Methods</span></span>](../../language-features/procedures/extension-methods.md)
