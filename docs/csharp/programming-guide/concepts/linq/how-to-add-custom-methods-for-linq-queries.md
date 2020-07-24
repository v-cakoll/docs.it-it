---
title: Come aggiungere metodi personalizzati per le query LINQ (C#)
description: Informazioni su come estendere il set di metodi che è possibile usare per le query LINQ aggiungendo metodi di estensione all' <T> interfaccia IEnumerable in C#.
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: fac0eb4e14eb3bb36313232a7d7fa3060c0ac171
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103599"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="c800e-103">Come aggiungere metodi personalizzati per le query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c800e-103">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="c800e-104">È possibile estendere il set di metodi da usare per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c800e-104">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="c800e-105">Oltre alla media standard o a un numero massimo di operazioni, ad esempio, è possibile creare un metodo di aggregazione personalizzato per calcolare un singolo valore da una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="c800e-105">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="c800e-106">È anche possibile creare un metodo che funzioni come un filtro personalizzato o una trasformazione di dati specifica per una sequenza di valori che restituisca una nuova sequenza.</span><span class="sxs-lookup"><span data-stu-id="c800e-106">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="c800e-107">Esempi di tali metodi sono <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> e <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="c800e-107">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="c800e-108">Quando si estende l'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, è possibile applicare i metodi personalizzati a qualsiasi raccolta enumerabile.</span><span class="sxs-lookup"><span data-stu-id="c800e-108">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="c800e-109">Per altre informazioni, vedere [Metodi di estensione](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c800e-109">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="c800e-110">Aggiunta di un metodo di aggregazione</span><span class="sxs-lookup"><span data-stu-id="c800e-110">Adding an Aggregate Method</span></span>

<span data-ttu-id="c800e-111">Un metodo di aggregazione calcola un singolo valore da un set di valori.</span><span class="sxs-lookup"><span data-stu-id="c800e-111">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="c800e-112">LINQ offre diversi metodi di aggregazione, tra cui <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> e <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="c800e-112">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="c800e-113">È possibile creare il proprio metodo di aggregazione aggiungendo un metodo di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c800e-113">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="c800e-114">L'esempio di codice seguente illustra come creare un metodo di estensione denominato `Median` per calcolare un valore mediano per una sequenza di numeri di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="c800e-114">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        var countOfElementsInTheSet = source?.Count() ?? 0;

        if (countOfElementsInTheSet == 0)
        {
            throw new InvalidOperationException("Cannot compute median for a null or empty set.");
        }

        var sortedList = (from number in source
                         orderby number
                         select number).ToList();

        int itemIndex = countOfElementsInTheSet / 2;

        if (countOfElementsInTheSet % 2 == 0)
        {
            // Even number of items.
            return (sortedList[itemIndex] + sortedList[itemIndex - 1]) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList[itemIndex];
        }
    }
}
```

<span data-ttu-id="c800e-115">Chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo in cui si chiamano altri metodi di aggregazione dall'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c800e-115">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="c800e-116">L'esempio di codice seguente illustra come usare il metodo `Median` di una matrice di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="c800e-116">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
*/
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="c800e-117">Overload di un metodo di aggregazione per accettare tipi diversi</span><span class="sxs-lookup"><span data-stu-id="c800e-117">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="c800e-118">È possibile eseguire l'overload del metodo di aggregazione in modo che accetti sequenze di tipi diversi.</span><span class="sxs-lookup"><span data-stu-id="c800e-118">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="c800e-119">L'approccio standard consiste nel creare un overload per ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="c800e-119">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="c800e-120">Un altro approccio consiste nel creare un overload che accetti un tipo generico e lo converta in un tipo specifico tramite un delegato.</span><span class="sxs-lookup"><span data-stu-id="c800e-120">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="c800e-121">È anche possibile combinare entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="c800e-121">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="c800e-122">Per creare un overload per ogni tipo</span><span class="sxs-lookup"><span data-stu-id="c800e-122">To create an overload for each type</span></span>

<span data-ttu-id="c800e-123">È possibile creare un overload specifico per ogni tipo che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="c800e-123">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="c800e-124">Nell'esempio di codice seguente viene illustrato l'overload del metodo `Median` per il tipo `integer`.</span><span class="sxs-lookup"><span data-stu-id="c800e-124">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

<span data-ttu-id="c800e-125">È ora possibile chiamare gli overload `Median` per entrambi i tipi `integer` e `double`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c800e-125">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
int[] numbers2 = { 1, 2, 3, 4, 5 };

var query2 = numbers2.Median();

Console.WriteLine("int: Median = " + query2);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
 Integer: Median = 3
*/
```

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="c800e-126">Per creare un overload generico</span><span class="sxs-lookup"><span data-stu-id="c800e-126">To create a generic overload</span></span>

<span data-ttu-id="c800e-127">È anche possibile creare un overload che accetti una sequenza di oggetti generici.</span><span class="sxs-lookup"><span data-stu-id="c800e-127">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="c800e-128">Questo overload accetta un delegato come parametro e lo usa per convertire una sequenza di oggetti di un tipo generico in un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="c800e-128">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="c800e-129">Il codice seguente mostra un overload del metodo `Median` che accetta il delegato <xref:System.Func%602> come parametro.</span><span class="sxs-lookup"><span data-stu-id="c800e-129">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="c800e-130">Questo delegato accetta un oggetto di tipo generico T e restituisce un oggetto di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="c800e-130">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

<span data-ttu-id="c800e-131">È ora possibile chiamare il metodo `Median` per una sequenza di oggetti di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="c800e-131">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="c800e-132">Se il tipo non ha un proprio overload del metodo, è necessario passare un parametro del delegato.</span><span class="sxs-lookup"><span data-stu-id="c800e-132">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="c800e-133">In C# è possibile usare un'espressione lambda a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="c800e-133">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="c800e-134">Solo in Visual Basic, se si usa la clausola `Aggregate` o `Group By` anziché la chiamata al metodo, è possibile passare qualsiasi valore o espressione che si trovi nell'ambito della clausola.</span><span class="sxs-lookup"><span data-stu-id="c800e-134">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="c800e-135">L'esempio di codice seguente illustra come chiamare il metodo `Median` per una matrice di numeri interi e una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="c800e-135">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="c800e-136">Per le stringhe, viene calcolato il valore mediano della lunghezza delle stringhe nella matrice.</span><span class="sxs-lookup"><span data-stu-id="c800e-136">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="c800e-137">L'esempio mostra come passare il parametro del delegato <xref:System.Func%602> al metodo `Median` per ogni caso.</span><span class="sxs-lookup"><span data-stu-id="c800e-137">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

```csharp
int[] numbers3 = { 1, 2, 3, 4, 5 };

/*
  You can use the num=>num lambda expression as a parameter for the Median method
  so that the compiler will implicitly convert its value to double.
  If there is no implicit conversion, the compiler will display an error message.
*/

var query3 = numbers3.Median(num => num);

Console.WriteLine("int: Median = " + query3);

string[] numbers4 = { "one", "two", "three", "four", "five" };

// With the generic overload, you can also use numeric properties of objects.

var query4 = numbers4.Median(str => str.Length);

Console.WriteLine("String: Median = " + query4);

/*
 This code produces the following output:

 Integer: Median = 3
 String: Median = 4
*/
```

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="c800e-138">Aggiunta di un metodo che restituisce una raccolta</span><span class="sxs-lookup"><span data-stu-id="c800e-138">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="c800e-139">È possibile estendere l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> con un metodo di query personalizzato che restituisce una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="c800e-139">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="c800e-140">In questo caso, il metodo deve restituire una raccolta di tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="c800e-140">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="c800e-141">Tali metodi possono essere usati per applicare filtri o trasformazioni di dati in una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="c800e-141">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="c800e-142">Nell'esempio seguente viene illustrato come creare un metodo di estensione denominato `AlternateElements` che restituisce tutti gli altri elementi in una raccolta, a partire dal primo elemento.</span><span class="sxs-lookup"><span data-stu-id="c800e-142">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

```csharp
// Extension method for the IEnumerable<T> interface.
// The method returns every other element of a sequence.

public static IEnumerable<T> AlternateElements<T>(this IEnumerable<T> source)
{
    List<T> list = new List<T>();

    int i = 0;

    foreach (var element in source)
    {
        if (i % 2 == 0)
        {
            list.Add(element);
        }

        i++;
    }

    return list;
}
```

<span data-ttu-id="c800e-143">È possibile chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo in cui si chiamano altri metodi dall'interfaccia <xref:System.Collections.Generic.IEnumerable%601>, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c800e-143">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

```csharp
string[] strings = { "a", "b", "c", "d", "e" };

var query = strings.AlternateElements();

foreach (var element in query)
{
    Console.WriteLine(element);
}
/*
 This code produces the following output:

 a
 c
 e
*/
```

## <a name="see-also"></a><span data-ttu-id="c800e-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c800e-144">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="c800e-145">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="c800e-145">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
