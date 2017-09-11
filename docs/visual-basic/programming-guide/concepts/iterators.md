---
title: Iteratori (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c38609878c10ff3234b5a33ec44d678d24c11d7f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="iterators-visual-basic"></a><span data-ttu-id="c671a-102">Iteratori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c671a-102">Iterators (Visual Basic)</span></span>
<span data-ttu-id="c671a-103">Un *iteratore* può essere utilizzato per scorrere le raccolte quali elenchi e matrici.</span><span class="sxs-lookup"><span data-stu-id="c671a-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="c671a-104">Un metodo iteratore o `get` della funzione di accesso esegue un'iterazione personalizzata su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="c671a-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="c671a-105">Utilizza un metodo iteratore il [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) istruzione per restituire un elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="c671a-105">An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="c671a-106">Quando un `Yield` viene raggiunta l'istruzione, viene memorizzata la posizione corrente nel codice.</span><span class="sxs-lookup"><span data-stu-id="c671a-106">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="c671a-107">L'esecuzione viene riavviata da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="c671a-108">Si utilizza un iteratore dal codice client tramite un [For Each... Avanti](../../../visual-basic/language-reference/statements/for-each-next-statement.md) istruzione, o tramite una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="c671a-108">You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="c671a-109">Nell'esempio seguente, la prima iterazione del `For Each` cause dei cicli di esecuzione continuare con la `SomeNumbers` metodo iteratore al primo `Yield` viene raggiunta l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c671a-109">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="c671a-110">Questa iterazione restituisce un valore pari a 3, e viene mantenuta la posizione corrente nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="c671a-111">Nell'iterazione successiva del ciclo, l'esecuzione nel metodo iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un `Yield` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c671a-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="c671a-112">Questa iterazione restituisce un valore pari a 5 e anche in questo caso viene mantenuta la posizione corrente nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="c671a-113">Il ciclo termina quando viene raggiunta la fine del metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In SomeNumbers()  
        Console.Write(number & " ")  
    Next  
    ' Output: 3 5 8  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function SomeNumbers() As System.Collections.IEnumerable  
    Yield 3  
    Yield 5  
    Yield 8  
End Function  
```  
  
 <span data-ttu-id="c671a-114">Il tipo restituito di un metodo iteratore o `get` funzione di accesso può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="c671a-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="c671a-115">È possibile utilizzare un `Exit Function` o `Return` istruzione per terminare l'iterazione.</span><span class="sxs-lookup"><span data-stu-id="c671a-115">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="c671a-116">Una funzione iteratore di Visual Basic o `get` la dichiarazione di funzione di accesso include un [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) modificatore.</span><span class="sxs-lookup"><span data-stu-id="c671a-116">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
 <span data-ttu-id="c671a-117">Gli iteratori sono state introdotte in Visual Basic in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="c671a-117">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="c671a-118">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="c671a-118">**In this topic**</span></span>  
  
-   [<span data-ttu-id="c671a-119">Iteratore semplice</span><span class="sxs-lookup"><span data-stu-id="c671a-119">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="c671a-120">Creazione di una classe di raccolta</span><span class="sxs-lookup"><span data-stu-id="c671a-120">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="c671a-121">Blocchi try</span><span class="sxs-lookup"><span data-stu-id="c671a-121">Try Blocks</span></span>](#BKMK_TryBlocks)  
  
-   [<span data-ttu-id="c671a-122">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="c671a-122">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)  
  
-   [<span data-ttu-id="c671a-123">Utilizzo di iteratori con un elenco generico</span><span class="sxs-lookup"><span data-stu-id="c671a-123">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="c671a-124">Informazioni sulla sintassi</span><span class="sxs-lookup"><span data-stu-id="c671a-124">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="c671a-125">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="c671a-125">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="c671a-126">Utilizzo di iteratori</span><span class="sxs-lookup"><span data-stu-id="c671a-126">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="c671a-127">Per tutti gli esempi nell'argomento, ad eccezione di esempio iteratore semplice, includere [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) le istruzioni per la `System.Collections` e `System.Collections.Generic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c671a-127">For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <span data-ttu-id="c671a-128"><a name="BKMK_SimpleIterator"></a>Iteratore semplice</span><span class="sxs-lookup"><span data-stu-id="c671a-128"><a name="BKMK_SimpleIterator"></a> Simple Iterator</span></span>  
 <span data-ttu-id="c671a-129">Nell'esempio seguente ha un solo `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo.</span><span class="sxs-lookup"><span data-stu-id="c671a-129">The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="c671a-130">In `Main`, ogni iterazione del `For Each` corpo dell'istruzione crea una chiamata alla funzione iteratore, che procede alla successiva `Yield` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c671a-130">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    ' Output: 6 8 10 12 14 16 18  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As System.Collections.Generic.IEnumerable(Of Integer)  
  
    ' Yield even numbers in the range.  
    For number As Integer = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
##  <span data-ttu-id="c671a-131"><a name="BKMK_CollectionClass"></a>Creazione di una classe di raccolta</span><span class="sxs-lookup"><span data-stu-id="c671a-131"><a name="BKMK_CollectionClass"></a> Creating a Collection Class</span></span>  
 <span data-ttu-id="c671a-132">Nell'esempio seguente, il `DaysOfTheWeek` implementa il <xref:System.Collections.IEnumerable>interfaccia, che richiede un <xref:System.Collections.IEnumerable.GetEnumerator%2A>(metodo).</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="c671a-132">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="c671a-133">Il compilatore chiama implicitamente il `GetEnumerator` metodo, che restituisce un <xref:System.Collections.IEnumerator>.</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="c671a-133">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="c671a-134">Il `GetEnumerator` metodo restituisce ogni stringa uno alla volta utilizzando il `Yield` istruzione e un `Iterator` modificatore è nella dichiarazione di funzione.</span><span class="sxs-lookup"><span data-stu-id="c671a-134">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>  
  
```vb  
Sub Main()  
    Dim days As New DaysOfTheWeek()  
    For Each day As String In days  
        Console.Write(day & " ")  
    Next  
    ' Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey()  
End Sub  
  
Private Class DaysOfTheWeek  
    Implements IEnumerable  
  
    Public days =  
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        ' Yield each day of the week.  
        For i As Integer = 0 To days.Length - 1  
            Yield days(i)  
        Next  
    End Function  
End Class  
```  
  
 <span data-ttu-id="c671a-135">Nell'esempio seguente viene creato un `Zoo` classe che contiene una raccolta di animali.</span><span class="sxs-lookup"><span data-stu-id="c671a-135">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="c671a-136">Il `For Each` istruzione che fa riferimento all'istanza della classe (`theZoo`) chiama implicitamente il `GetEnumerator` metodo.</span><span class="sxs-lookup"><span data-stu-id="c671a-136">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="c671a-137">Il `For Each` istruzioni che fanno riferimento le `Birds` e `Mammals` proprietà il `AnimalsForType` denominato iterator (metodo).</span><span class="sxs-lookup"><span data-stu-id="c671a-137">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
```vb  
Sub Main()  
    Dim theZoo As New Zoo()  
  
    theZoo.AddMammal("Whale")  
    theZoo.AddMammal("Rhinoceros")  
    theZoo.AddBird("Penguin")  
    theZoo.AddBird("Warbler")  
  
    For Each name As String In theZoo  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros Penguin Warbler  
  
    For Each name As String In theZoo.Birds  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Penguin Warbler  
  
    For Each name As String In theZoo.Mammals  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros  
  
    Console.ReadKey()  
End Sub  
  
Public Class Zoo  
    Implements IEnumerable  
  
    ' Private members.  
    Private animals As New List(Of Animal)  
  
    ' Public methods.  
    Public Sub AddMammal(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})  
    End Sub  
  
    Public Sub AddBird(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})  
    End Sub  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        For Each theAnimal As Animal In animals  
            Yield theAnimal.Name  
        Next  
    End Function  
  
    ' Public members.  
    Public ReadOnly Property Mammals As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Mammal)  
        End Get  
    End Property  
  
    Public ReadOnly Property Birds As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Bird)  
        End Get  
    End Property  
  
    ' Private methods.  
    Private Iterator Function AnimalsForType( _  
    ByVal type As Animal.TypeEnum) As IEnumerable  
        For Each theAnimal As Animal In animals  
            If (theAnimal.Type = type) Then  
                Yield theAnimal.Name  
            End If  
        Next  
    End Function  
  
    ' Private class.  
    Private Class Animal  
        Public Enum TypeEnum  
            Bird  
            Mammal  
        End Enum  
  
        Public Property Name As String  
        Public Property Type As TypeEnum  
    End Class  
End Class  
```  
  
##  <span data-ttu-id="c671a-138"><a name="BKMK_TryBlocks"></a>Blocchi try</span><span class="sxs-lookup"><span data-stu-id="c671a-138"><a name="BKMK_TryBlocks"></a> Try Blocks</span></span>  
 <span data-ttu-id="c671a-139">Visual Basic consente una `Yield` istruzione nel `Try` blocco di un [Try... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c671a-139">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="c671a-140">Oggetto `Try` blocco che ha un `Yield` istruzione possono essere presenti `Catch` blocca e può avere un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="c671a-140">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="c671a-141">L'esempio seguente include `Try`, `Catch`, e `Finally` blocchi in una funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-141">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="c671a-142">Il `Finally` blocco nella funzione iteratore esegue prima la `For Each` al termine dell'iterazione.</span><span class="sxs-lookup"><span data-stu-id="c671a-142">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In Test()  
        Console.WriteLine(number)  
    Next  
    Console.WriteLine("For Each is done.")  
  
    ' Output:  
    '  3  
    '  4  
    '  Something happened. Yields are done.  
    '  Finally is called.  
    '  For Each is done.  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function Test() As IEnumerable(Of Integer)  
    Try  
        Yield 3  
        Yield 4  
        Throw New Exception("Something happened. Yields are done.")  
        Yield 5  
        Yield 6  
    Catch ex As Exception  
        Console.WriteLine(ex.Message)  
    Finally  
        Console.WriteLine("Finally is called.")  
    End Try  
End Function  
```  
  
 <span data-ttu-id="c671a-143">Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="c671a-143">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="c671a-144">Se il `For Each` corpo (anziché il metodo iteratore) genera un'eccezione, un `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` try nella funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-144">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="c671a-145">Oggetto `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-145">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
##  <span data-ttu-id="c671a-146"><a name="BKMK_AnonymousMethods"></a>Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="c671a-146"><a name="BKMK_AnonymousMethods"></a> Anonymous Methods</span></span>  
 <span data-ttu-id="c671a-147">In Visual Basic, una funzione anonima può essere una funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-147">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="c671a-148">Questa condizione è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c671a-148">The following example illustrates this.</span></span>  
  
```vb  
Dim iterateSequence = Iterator Function() _  
                      As IEnumerable(Of Integer)  
                          Yield 1  
                          Yield 2  
                      End Function  
  
For Each number As Integer In iterateSequence()  
    Console.Write(number & " ")  
Next  
' Output: 1 2  
Console.ReadKey()  
```  
  
 <span data-ttu-id="c671a-149">Nell'esempio seguente è un metodo iteratore non convalida gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="c671a-149">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="c671a-150">Il metodo restituisce il risultato di un iteratore anonimo che descrive gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="c671a-150">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In GetSequence(5, 10)  
        Console.Write(number & " ")  
    Next  
    ' Output: 5 6 7 8 9 10  
    Console.ReadKey()  
End Sub  
  
Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _  
As IEnumerable  
    ' Validate the arguments.  
    If low < 1 Then  
        Throw New ArgumentException("low is too low")  
    End If  
    If high > 140 Then  
        Throw New ArgumentException("high is too high")  
    End If  
  
    ' Return an anonymous iterator function.  
    Dim iterateSequence = Iterator Function() As IEnumerable  
                              For index = low To high  
                                  Yield index  
                              Next  
                          End Function  
    Return iterateSequence()  
End Function  
```  
  
 <span data-ttu-id="c671a-151">Se la convalida è invece all'interno della funzione iteratore, la convalida non può essere eseguita fino all'inizio della prima iterazione del `For Each` corpo.</span><span class="sxs-lookup"><span data-stu-id="c671a-151">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>  
  
##  <span data-ttu-id="c671a-152"><a name="BKMK_GenericList"></a>Utilizzo di iteratori con un elenco generico</span><span class="sxs-lookup"><span data-stu-id="c671a-152"><a name="BKMK_GenericList"></a> Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="c671a-153">Nell'esempio seguente, il `Stack(Of T)` classe generica implementa il <xref:System.Collections.Generic.IEnumerable%601>interfaccia generica.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="c671a-153">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="c671a-154">Il `Push` metodo assegna valori a una matrice di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="c671a-154">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="c671a-155">Il <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>metodo restituisce i valori della matrice utilizzando la `Yield` istruzione.</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="c671a-155">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>  
  
 <span data-ttu-id="c671a-156">Oltre a generica <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>metodo, non generica <xref:System.Collections.IEnumerable.GetEnumerator%2A>metodo deve anche essere implementato.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="c671a-156">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="c671a-157">In questo modo <xref:System.Collections.Generic.IEnumerable%601>eredita da <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="c671a-157">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="c671a-158">L'implementazione non generica rinvia all'implementazione generica.</span><span class="sxs-lookup"><span data-stu-id="c671a-158">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="c671a-159">L'esempio Usa iteratori denominati per supportare diversi modi per scorrere la raccolta dei dati stessa.</span><span class="sxs-lookup"><span data-stu-id="c671a-159">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="c671a-160">Questi denominato iteratori sono il `TopToBottom` e `BottomToTop` proprietà e `TopN` metodo.</span><span class="sxs-lookup"><span data-stu-id="c671a-160">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="c671a-161">Il `BottomToTop` dichiarazione di proprietà include il `Iterator` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="c671a-161">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>  
  
```vb  
Sub Main()  
    Dim theStack As New Stack(Of Integer)  
  
    ' Add items to the stack.  
    For number As Integer = 0 To 9  
        theStack.Push(number)  
    Next  
  
    ' Retrieve items from the stack.  
    ' For Each is allowed because theStack implements  
    ' IEnumerable(Of Integer).  
    For Each number As Integer In theStack  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    ' For Each is allowed, because theStack.TopToBottom  
    ' returns IEnumerable(Of Integer).  
    For Each number As Integer In theStack.TopToBottom  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    For Each number As Integer In theStack.BottomToTop  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 0 1 2 3 4 5 6 7 8 9   
  
    For Each number As Integer In theStack.TopN(7)  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey()  
End Sub  
  
Public Class Stack(Of T)  
    Implements IEnumerable(Of T)  
  
    Private values As T() = New T(99) {}  
    Private top As Integer = 0  
  
    Public Sub Push(ByVal t As T)  
        values(top) = t  
        top = top + 1  
    End Sub  
  
    Public Function Pop() As T  
        top = top - 1  
        Return values(top)  
    End Function  
  
    ' This function implements the GetEnumerator method. It allows  
    ' an instance of the class to be used in a For Each statement.  
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _  
        Implements IEnumerable(Of T).GetEnumerator  
  
        For index As Integer = top - 1 To 0 Step -1  
            Yield values(index)  
        Next  
    End Function  
  
    Public Iterator Function GetEnumerator1() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        Yield GetEnumerator()  
    End Function  
  
    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)  
        Get  
            Return Me  
        End Get  
    End Property  
  
    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)  
        Get  
            For index As Integer = 0 To top - 1  
                Yield values(index)  
            Next  
        End Get  
    End Property  
  
    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _  
        As IEnumerable(Of T)  
  
        ' Return less than itemsFromTop if necessary.  
        Dim startIndex As Integer =  
            If(itemsFromTop >= top, 0, top - itemsFromTop)  
  
        For index As Integer = top - 1 To startIndex Step -1  
            Yield values(index)  
        Next  
    End Function  
End Class  
  
```  
  
##  <span data-ttu-id="c671a-162"><a name="BKMK_SyntaxInformation"></a>Informazioni sulla sintassi</span><span class="sxs-lookup"><span data-stu-id="c671a-162"><a name="BKMK_SyntaxInformation"></a> Syntax Information</span></span>  
 <span data-ttu-id="c671a-163">Un iteratore può verificarsi come un metodo o `get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="c671a-163">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="c671a-164">Un iteratore non può trovarsi in un evento, costruttore di istanza, un costruttore statico o distruttore statico.</span><span class="sxs-lookup"><span data-stu-id="c671a-164">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="c671a-165">Deve esistere una conversione implicita dal tipo di espressione nel `Yield` istruzione per il tipo restituito dell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-165">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="c671a-166">In Visual Basic, un metodo iteratore non può contenere `ByRef` parametri.</span><span class="sxs-lookup"><span data-stu-id="c671a-166">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="c671a-167">In Visual Basic "Yield" non è una parola riservata e ha un significato speciale solo quando viene utilizzato in un `Iterator` metodo o `get` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="c671a-167">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>  
  
##  <span data-ttu-id="c671a-168"><a name="BKMK_Technical"></a>Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="c671a-168"><a name="BKMK_Technical"></a> Technical Implementation</span></span>  
 <span data-ttu-id="c671a-169">Anche se si scrive un iteratore di un metodo, il compilatore traduce in una classe annidata che, in pratica, una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="c671a-169">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="c671a-170">Questa classe tiene traccia della posizione dell'iteratore purché il `For Each...Next` ciclo nel codice client continua.</span><span class="sxs-lookup"><span data-stu-id="c671a-170">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="c671a-171">Per visualizzare il compilatore esegue, è possibile utilizzare lo strumento Ildasm.exe per visualizzare il codice Microsoft intermediate language che viene generato per un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-171">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="c671a-172">Quando si crea un iteratore per un [classe](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), non è necessario implementare l'intera <xref:System.Collections.IEnumerator>interfaccia.</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="c671a-172">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="c671a-173">Quando il compilatore rileva l'iteratore, viene generato automaticamente il `Current`, `MoveNext`, e `Dispose` metodi di <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>interfaccia.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="c671a-173">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="c671a-174">In ogni iterazione successiva del `For Each…Next` ciclo (o alla chiamata diretta a `IEnumerator.MoveNext`), il corpo di codice successivo iteratore riprende dopo la precedente `Yield` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c671a-174">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="c671a-175">Quindi continua fino alla successiva `Yield` istruzione fino a quando non viene raggiunta la fine del corpo dell'iteratore, o fino a quando un `Exit Function` o `Return` viene rilevata un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c671a-175">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>  
  
 <span data-ttu-id="c671a-176">Gli iteratori non supportano il <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>(metodo).</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c671a-176">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="c671a-177">Per reiterare dall'inizio, è necessario ottenere un nuovo iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-177">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="c671a-178">Per ulteriori informazioni, vedere il [specifiche del linguaggio Visual Basic](../../../visual-basic/reference/language-specification.md).</span><span class="sxs-lookup"><span data-stu-id="c671a-178">For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
##  <span data-ttu-id="c671a-179"><a name="BKMK_UseOfIterators"></a>Utilizzo di iteratori</span><span class="sxs-lookup"><span data-stu-id="c671a-179"><a name="BKMK_UseOfIterators"></a> Use of Iterators</span></span>  
 <span data-ttu-id="c671a-180">Gli iteratori consentono di gestire la semplicità di un `For Each` ciclo quando è necessario utilizzare codice complesso per popolare una sequenza di elenco.</span><span class="sxs-lookup"><span data-stu-id="c671a-180">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="c671a-181">Ciò può risultare utile quando si desidera eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c671a-181">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="c671a-182">Modificare la sequenza elenco dopo il primo `For Each` iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="c671a-182">Modify the list sequence after the first `For Each` loop iteration.</span></span>  
  
-   <span data-ttu-id="c671a-183">Evitare completamente il caricamento di un elenco di grandi dimensioni prima della prima iterazione di un `For Each` ciclo.</span><span class="sxs-lookup"><span data-stu-id="c671a-183">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="c671a-184">Un esempio è un'operazione di recupero di paging per caricare un batch di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="c671a-184">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="c671a-185">Un altro esempio è il <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>metodo, che implementa gli iteratori all'interno di .NET Framework.</xref:System.IO.DirectoryInfo.EnumerateFiles%2A></span><span class="sxs-lookup"><span data-stu-id="c671a-185">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="c671a-186">Incapsulare la generazione dell'elenco nell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="c671a-186">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="c671a-187">Nel metodo iteratore, è possibile compilare l'elenco e restituisce quindi ogni risultato in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="c671a-187">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c671a-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c671a-188">See Also</span></span>  
 <span data-ttu-id="c671a-189"><xref:System.Collections.Generic></xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="c671a-189"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="c671a-190"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="c671a-190"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="c671a-191"> [Per ogni corso... Next (istruzione)](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c671a-191"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="c671a-192"> [Istruzione yield](../../../visual-basic/language-reference/statements/yield-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c671a-192"> [Yield Statement](../../../visual-basic/language-reference/statements/yield-statement.md) </span></span>  
<span data-ttu-id="c671a-193"> [Iteratore](../../../visual-basic/language-reference/modifiers/iterator.md)</span><span class="sxs-lookup"><span data-stu-id="c671a-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span></span>
