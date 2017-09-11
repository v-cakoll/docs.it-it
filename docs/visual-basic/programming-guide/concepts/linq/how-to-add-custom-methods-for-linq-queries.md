---
title: 'Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="562db-102">Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="562db-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>
<span data-ttu-id="562db-103">È possibile estendere il set di metodi che è possibile utilizzare per le query LINQ aggiungendo metodi di estensione per il <xref:System.Collections.Generic.IEnumerable%601>interfaccia.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="562db-104">Oltre alla media standard o un numero massimo di operazioni, ad esempio, è possibile creare un metodo di aggregazione personalizzato per un singolo valore da una sequenza di valori di calcolo.</span><span class="sxs-lookup"><span data-stu-id="562db-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="562db-105">È inoltre possibile creare un metodo che funziona come un filtro personalizzato o una trasformazione di dati specifico per una sequenza di valori e restituisce una nuova sequenza.</span><span class="sxs-lookup"><span data-stu-id="562db-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="562db-106">Esempi di tali metodi sono <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>e <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="562db-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>  
  
 <span data-ttu-id="562db-107">Quando si estende il <xref:System.Collections.Generic.IEnumerable%601>interfaccia, è possibile applicare i metodi personalizzati per qualsiasi raccolta enumerabile.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="562db-108">Per ulteriori informazioni, vedere [metodi di estensione](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="562db-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="adding-an-aggregate-method"></a><span data-ttu-id="562db-109">Aggiunta di un metodo di aggregazione</span><span class="sxs-lookup"><span data-stu-id="562db-109">Adding an Aggregate Method</span></span>  
 <span data-ttu-id="562db-110">Un metodo di aggregazione calcola un singolo valore da un set di valori.</span><span class="sxs-lookup"><span data-stu-id="562db-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="562db-111">LINQ fornisce diversi metodi di aggregazione, tra cui <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>e <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="562db-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="562db-112">È possibile creare il proprio metodo di aggregazione mediante l'aggiunta di un metodo di estensione per il <xref:System.Collections.Generic.IEnumerable%601>interfaccia.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="562db-113">Esempio di codice seguente viene illustrato come creare un metodo di estensione denominato `Median` per calcolare un valore medio per una sequenza di numeri di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="562db-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>  
  
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
  
 <span data-ttu-id="562db-114">Chiamare questo metodo di estensione per qualsiasi raccolta enumerabile nello stesso modo chiamare altri metodi di aggregazione dal <xref:System.Collections.Generic.IEnumerable%601>interfaccia.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="562db-115">In Visual Basic, è possibile utilizzare una chiamata al metodo o una sintassi di query standard per il `Aggregate` o `Group By` clausola.</span><span class="sxs-lookup"><span data-stu-id="562db-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="562db-116">Per ulteriori informazioni, vedere [clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) e [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="562db-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="562db-117">Esempio di codice seguente viene illustrato come utilizzare il `Median` metodo per una matrice di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="562db-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>  
  
<span data-ttu-id="562db-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="562db-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="562db-120">L'overload di un metodo di aggregazione per accettare tipi diversi</span><span class="sxs-lookup"><span data-stu-id="562db-120">Overloading an Aggregate Method to Accept Various Types</span></span>  
 <span data-ttu-id="562db-121">È possibile eseguire l'overload del metodo di aggregazione in modo che accetti le sequenze di vario tipo.</span><span class="sxs-lookup"><span data-stu-id="562db-121">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="562db-122">L'approccio standard consiste nel creare un overload per ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="562db-122">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="562db-123">Un altro approccio consiste nel creare un overload che accettano un tipo generico e convertirlo in un tipo specifico tramite un delegato.</span><span class="sxs-lookup"><span data-stu-id="562db-123">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="562db-124">È inoltre possibile combinare entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="562db-124">You can also combine both approaches.</span></span>  
  
#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="562db-125">Per creare un overload per ogni tipo</span><span class="sxs-lookup"><span data-stu-id="562db-125">To create an overload for each type</span></span>  
 <span data-ttu-id="562db-126">È possibile creare un overload specifico per ogni tipo che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="562db-126">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="562db-127">Esempio di codice seguente viene illustrato un overload di `Median` metodo per la `integer` tipo.</span><span class="sxs-lookup"><span data-stu-id="562db-127">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>  
  
<span data-ttu-id="562db-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="562db-129">È ora possibile chiamare il `Median` overload per entrambe `integer` e `double` tipi, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="562db-129">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>  
  
<span data-ttu-id="562db-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="562db-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="562db-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="562db-133">Per creare un overload generico</span><span class="sxs-lookup"><span data-stu-id="562db-133">To create a generic overload</span></span>  
 <span data-ttu-id="562db-134">È inoltre possibile creare un overload che accetta una sequenza di oggetti generici.</span><span class="sxs-lookup"><span data-stu-id="562db-134">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="562db-135">Questo overload accetta un delegato come parametro e lo utilizza per convertire una sequenza di oggetti di un tipo generico a un tipo specifico.</span><span class="sxs-lookup"><span data-stu-id="562db-135">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>  
  
 <span data-ttu-id="562db-136">Nel codice seguente viene illustrato un overload di `Median` metodo che accetta il <xref:System.Func%602>delegato come parametro.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="562db-136">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="562db-137">Questo delegato accetta un oggetto di tipo generico T e restituisce un oggetto di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="562db-137">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 <span data-ttu-id="562db-138">È ora possibile chiamare il `Median` metodo per una sequenza di oggetti di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="562db-138">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="562db-139">Se il tipo non dispone di un proprio overload del metodo, è necessario passare un parametro delegato.</span><span class="sxs-lookup"><span data-stu-id="562db-139">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="562db-140">In Visual Basic, è possibile utilizzare un'espressione lambda a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="562db-140">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="562db-141">Inoltre, se si utilizza il `Aggregate` o `Group By` clausola anziché la chiamata al metodo, è possibile passare qualsiasi valore o espressione che si trova nell'ambito di questa clausola.</span><span class="sxs-lookup"><span data-stu-id="562db-141">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>  
  
 <span data-ttu-id="562db-142">Esempio di codice seguente viene illustrato come chiamare il `Median` metodo per una matrice di integer e una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="562db-142">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="562db-143">Per le stringhe, viene calcolato il valore mediano per la lunghezza delle stringhe nella matrice.</span><span class="sxs-lookup"><span data-stu-id="562db-143">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="562db-144">Nell'esempio viene illustrato come passare il <xref:System.Func%602>parametro per delegare il `Median` metodo per ogni case.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="562db-144">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>  
  
<span data-ttu-id="562db-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="562db-146">Aggiunta di un metodo che restituisce una raccolta</span><span class="sxs-lookup"><span data-stu-id="562db-146">Adding a Method That Returns a Collection</span></span>  
 <span data-ttu-id="562db-147">È possibile estendere il <xref:System.Collections.Generic.IEnumerable%601>interfaccia con un metodo di query personalizzato che restituisce una sequenza di valori.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-147">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="562db-148">In questo caso, il metodo deve restituire una raccolta di tipo <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-148">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="562db-149">Tali metodi consente di applicare filtri o trasformazioni di dati in una sequenza di valori.</span><span class="sxs-lookup"><span data-stu-id="562db-149">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>  
  
 <span data-ttu-id="562db-150">Nell'esempio seguente viene illustrato come creare un metodo di estensione denominato `AlternateElements` che restituisce tutti gli altri elementi in una raccolta, a partire dal primo elemento.</span><span class="sxs-lookup"><span data-stu-id="562db-150">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>  
  
<span data-ttu-id="562db-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="562db-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="562db-152">È possibile chiamare questo metodo di estensione per qualsiasi raccolta enumerabile come chiamare altri metodi di <xref:System.Collections.Generic.IEnumerable%601>interfaccia, come illustrato nel codice seguente:</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-152">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="562db-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="562db-153">See Also</span></span>  
 <span data-ttu-id="562db-154"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="562db-154"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="562db-155"> [Metodi di estensione](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="562db-155"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
