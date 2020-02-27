---
title: Iteratori
ms.date: 07/20/2015
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
ms.openlocfilehash: 2789ac66690ebfd472b9bae5ccf08b1bdfaa0922
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628735"
---
# <a name="iterators-visual-basic"></a><span data-ttu-id="5c1a1-102">Iteratori (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c1a1-102">Iterators (Visual Basic)</span></span>

<span data-ttu-id="5c1a1-103">Un *iteratore* può essere usato per scorrere le raccolte come gli elenchi e le matrici.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>

<span data-ttu-id="5c1a1-104">Un metodo iteratore o funzione di accesso `get` esegue un'iterazione personalizzata su una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="5c1a1-105">Un metodo iteratore usa l'istruzione [yield](../../../visual-basic/language-reference/statements/yield-statement.md) per restituire un elemento alla volta.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-105">An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="5c1a1-106">Quando viene raggiunta un'istruzione `Yield`, la posizione corrente nel codice viene memorizzata.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-106">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="5c1a1-107">L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-107">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="5c1a1-108">Si utilizza un iteratore dal codice client utilizzando un [per ogni... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oppure tramite una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-108">You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>

<span data-ttu-id="5c1a1-109">Nell'esempio seguente, la prima iterazione del ciclo `For Each` fa procedere l'esecuzione nel metodo iteratore `SomeNumbers` fino al raggiungimento della prima istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-109">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="5c1a1-110">Questa iterazione restituisce un valore pari a 3 e viene mantenuta la posizione corrente nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="5c1a1-111">All'iterazione successiva del ciclo, l'esecuzione nel metodo iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="5c1a1-112">Questa iterazione restituisce un valore pari a 5 e viene ancora mantenuta la posizione corrente nel metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="5c1a1-113">Il ciclo termina quando si raggiunge la fine del metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-113">The loop completes when the end of the iterator method is reached.</span></span>

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

<span data-ttu-id="5c1a1-114">Il tipo restituito di un metodo iteratore o di una funzione di accesso `get` può essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="5c1a1-115">Per terminare l'iterazione, è possibile usare un'istruzione `Exit Function` o `Return`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-115">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>

<span data-ttu-id="5c1a1-116">Una Visual Basic funzione iteratore o una dichiarazione di funzione di accesso `get` include un modificatore [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) .</span><span class="sxs-lookup"><span data-stu-id="5c1a1-116">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>

<span data-ttu-id="5c1a1-117">Gli iteratori sono stati introdotti in Visual Basic in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-117">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>

<span data-ttu-id="5c1a1-118">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="5c1a1-118">**In this topic**</span></span>

- [<span data-ttu-id="5c1a1-119">Iteratore semplice</span><span class="sxs-lookup"><span data-stu-id="5c1a1-119">Simple Iterator</span></span>](#BKMK_SimpleIterator)

- [<span data-ttu-id="5c1a1-120">Creazione di una classe Collection</span><span class="sxs-lookup"><span data-stu-id="5c1a1-120">Creating a Collection Class</span></span>](#BKMK_CollectionClass)

- [<span data-ttu-id="5c1a1-121">Blocchi try</span><span class="sxs-lookup"><span data-stu-id="5c1a1-121">Try Blocks</span></span>](#BKMK_TryBlocks)

- [<span data-ttu-id="5c1a1-122">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="5c1a1-122">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)

- [<span data-ttu-id="5c1a1-123">Uso di iteratori con un elenco generico</span><span class="sxs-lookup"><span data-stu-id="5c1a1-123">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)

- [<span data-ttu-id="5c1a1-124">Informazioni sulla sintassi</span><span class="sxs-lookup"><span data-stu-id="5c1a1-124">Syntax Information</span></span>](#BKMK_SyntaxInformation)

- [<span data-ttu-id="5c1a1-125">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="5c1a1-125">Technical Implementation</span></span>](#BKMK_Technical)

- [<span data-ttu-id="5c1a1-126">Uso degli iteratori</span><span class="sxs-lookup"><span data-stu-id="5c1a1-126">Use of Iterators</span></span>](#BKMK_UseOfIterators)

> [!NOTE]
> <span data-ttu-id="5c1a1-127">Per tutti gli esempi nell'argomento eccetto l'esempio di iteratore semplice, includere le istruzioni [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per gli spazi dei nomi `System.Collections` e `System.Collections.Generic`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-127">For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>

## <a name="BKMK_SimpleIterator"></a> <span data-ttu-id="5c1a1-128">Iteratore semplice</span><span class="sxs-lookup"><span data-stu-id="5c1a1-128">Simple Iterator</span></span>

<span data-ttu-id="5c1a1-129">Nell'esempio seguente è presente una singola istruzione `Yield` che si trova all'interno di un oggetto [per... Ciclo successivo](../../../visual-basic/language-reference/statements/for-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="5c1a1-129">The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="5c1a1-130">In `Main` ogni iterazione del corpo dell'istruzione `For Each` crea una chiamata alla funzione iteratore, che procede all'istruzione `Yield` successiva.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-130">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>

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

## <a name="BKMK_CollectionClass"></a> <span data-ttu-id="5c1a1-131">Creazione di una classe Collection</span><span class="sxs-lookup"><span data-stu-id="5c1a1-131">Creating a Collection Class</span></span>

<span data-ttu-id="5c1a1-132">Nell'esempio seguente la classe `DaysOfTheWeek` implementa l'interfaccia <xref:System.Collections.IEnumerable>, che richiede un metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-132">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="5c1a1-133">Il compilatore chiama implicitamente il metodo `GetEnumerator`, che restituisce un <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-133">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>

<span data-ttu-id="5c1a1-134">Il metodo `GetEnumerator` restituisce ogni stringa una alla volta utilizzando l'istruzione `Yield` e un modificatore di `Iterator` si trova nella dichiarazione di funzione.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-134">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>

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

<span data-ttu-id="5c1a1-135">Nell'esempio seguente viene creata una classe `Zoo` che contiene una raccolta di animali.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-135">The following example creates a `Zoo` class that contains a collection of animals.</span></span>

<span data-ttu-id="5c1a1-136">L'istruzione `For Each` che fa riferimento all'istanza della classe (`theZoo`) chiama implicitamente il metodo `GetEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-136">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="5c1a1-137">Le istruzioni `For Each` che fanno riferimento alle proprietà `Birds` e `Mammals` usano il metodo iteratore denominato `AnimalsForType`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-137">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>

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

## <a name="BKMK_TryBlocks"></a><span data-ttu-id="5c1a1-138">Blocchi try</span><span class="sxs-lookup"><span data-stu-id="5c1a1-138">Try Blocks</span></span>

<span data-ttu-id="5c1a1-139">Visual Basic consente un'istruzione `Yield` nel blocco `Try` di un oggetto [try... Rileva... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5c1a1-139">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="5c1a1-140">Un blocco di `Try` con un'istruzione `Yield` può avere `Catch` blocchi e può avere un blocco `Finally`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-140">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>

<span data-ttu-id="5c1a1-141">Nell'esempio seguente sono inclusi i blocchi `Try`, `Catch`e `Finally` in una funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-141">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="5c1a1-142">Il blocco `Finally` nella funzione iteratore viene eseguito prima del completamento dell'iterazione del `For Each`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-142">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>

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

<span data-ttu-id="5c1a1-143">Un'istruzione `Yield` non può trovarsi all'interno di un blocco di `Catch` o di un blocco di `Finally`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-143">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>

<span data-ttu-id="5c1a1-144">Se il corpo del `For Each` (anziché il metodo iteratore) genera un'eccezione, un blocco di `Catch` nella funzione iteratore non viene eseguito, ma viene eseguito un blocco di `Finally` nella funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-144">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="5c1a1-145">Un blocco `Catch` all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-145">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>

## <a name="BKMK_AnonymousMethods"></a><span data-ttu-id="5c1a1-146">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="5c1a1-146">Anonymous Methods</span></span>

<span data-ttu-id="5c1a1-147">In Visual Basic, una funzione anonima può essere una funzione iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-147">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="5c1a1-148">Ciò è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-148">The following example illustrates this.</span></span>

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

<span data-ttu-id="5c1a1-149">Nell'esempio seguente viene utilizzato un metodo non iteratore per la convalida degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-149">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="5c1a1-150">Il metodo restituisce il risultato di un iteratore anonimo che descrive gli elementi della raccolta.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-150">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>

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

<span data-ttu-id="5c1a1-151">Se la convalida è invece all'interno della funzione iteratore, la convalida non può essere eseguita fino all'inizio della prima iterazione del corpo `For Each`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-151">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>

## <a name="BKMK_GenericList"></a> <span data-ttu-id="5c1a1-152">Uso di iteratori con un elenco generico</span><span class="sxs-lookup"><span data-stu-id="5c1a1-152">Using Iterators with a Generic List</span></span>

<span data-ttu-id="5c1a1-153">Nell'esempio seguente la classe generica `Stack(Of T)` implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-153">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="5c1a1-154">Il metodo `Push` assegna valori a una matrice di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-154">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="5c1a1-155">Il metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> restituisce i valori della matrice tramite l'istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-155">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>

<span data-ttu-id="5c1a1-156">Oltre al metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> generico, è necessario implementare anche il metodo <xref:System.Collections.IEnumerable.GetEnumerator%2A> non generico,</span><span class="sxs-lookup"><span data-stu-id="5c1a1-156">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="5c1a1-157">poiché <xref:System.Collections.Generic.IEnumerable%601> eredita da <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-157">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="5c1a1-158">L'implementazione non generica rinvia all'implementazione generica.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-158">The non-generic implementation defers to the generic implementation.</span></span>

<span data-ttu-id="5c1a1-159">L'esempio usa iteratori denominati per supportare diversi modi di iterazione nella stessa raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-159">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="5c1a1-160">Questi iteratori denominati sono le proprietà `TopToBottom` e `BottomToTop` e il metodo `TopN`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-160">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>

<span data-ttu-id="5c1a1-161">La dichiarazione di proprietà `BottomToTop` include la parola chiave `Iterator`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-161">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>

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

## <a name="BKMK_SyntaxInformation"></a> <span data-ttu-id="5c1a1-162">Informazioni sulla sintassi</span><span class="sxs-lookup"><span data-stu-id="5c1a1-162">Syntax Information</span></span>

<span data-ttu-id="5c1a1-163">Un iteratore può verificarsi come metodo o funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-163">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="5c1a1-164">Un iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-164">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>

<span data-ttu-id="5c1a1-165">Deve esistere una conversione implicita dal tipo di espressione nell'istruzione `Yield` al tipo restituito dell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-165">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>

<span data-ttu-id="5c1a1-166">In Visual Basic, un metodo iteratore non può avere parametri di `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-166">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>

<span data-ttu-id="5c1a1-167">In Visual Basic, "yield" non è una parola riservata e ha un significato speciale solo quando viene usato in un metodo di `Iterator` o `get` funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-167">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>

## <a name="BKMK_Technical"></a> <span data-ttu-id="5c1a1-168">Implementazione tecnica</span><span class="sxs-lookup"><span data-stu-id="5c1a1-168">Technical Implementation</span></span>

<span data-ttu-id="5c1a1-169">Anche se si scrive un iteratore come metodo, il compilatore lo traduce in una classe annidata che, in pratica, è una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-169">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="5c1a1-170">Questa classe tiene traccia della posizione dell'iteratore purché il ciclo `For Each...Next` nel codice client sia continuo.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-170">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>

<span data-ttu-id="5c1a1-171">Per verificare le operazioni eseguite dal compilatore, è possibile usare lo strumento Ildsam.exe per visualizzare il codice Microsoft Intermediate Language generato per un metodo iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-171">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>

<span data-ttu-id="5c1a1-172">Quando si crea un iteratore per una [classe](../../language-reference/statements/class-statement.md) o uno [struct](../../language-reference/statements/structure-statement.md), non è necessario implementare l'intera interfaccia <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-172">When you create an iterator for a [class](../../language-reference/statements/class-statement.md) or [struct](../../language-reference/statements/structure-statement.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="5c1a1-173">Quando il compilatore rileva l'iteratore, genera automaticamente i metodi `Current`, `MoveNext` e `Dispose` dell'interfaccia <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-173">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>

<span data-ttu-id="5c1a1-174">In ogni iterazione successiva del ciclo `For Each…Next` (o alla chiamata diretta a `IEnumerator.MoveNext`), il corpo di codice iteratore successivo riprende dopo la precedente istruzione `Yield`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-174">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="5c1a1-175">Continua quindi con l'istruzione `Yield` successiva fino a quando non viene raggiunta la fine del corpo dell'iteratore o fino a quando non viene rilevata un'istruzione `Exit Function` o `Return`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-175">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>

<span data-ttu-id="5c1a1-176">Gli iteratori non supportano il metodo <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-176">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5c1a1-177">Per eseguire di nuovo l'iterazione dall'inizio, è necessario ottenere un nuovo iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-177">To re-iterate from the start, you must obtain a new iterator.</span></span>

<span data-ttu-id="5c1a1-178">Per ulteriori informazioni, vedere la [specifica del linguaggio Visual Basic](../../../visual-basic/reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c1a1-178">For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>

## <a name="BKMK_UseOfIterators"></a> <span data-ttu-id="5c1a1-179">Uso degli iteratori</span><span class="sxs-lookup"><span data-stu-id="5c1a1-179">Use of Iterators</span></span>

<span data-ttu-id="5c1a1-180">Gli iteratori consentono di mantenere la semplicità di un ciclo `For Each` quando è necessario usare codice complesso per popolare una sequenza di elenco.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-180">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="5c1a1-181">Ciò può risultare utile per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c1a1-181">This can be useful when you want to do the following:</span></span>

- <span data-ttu-id="5c1a1-182">Modificare la sequenza di elenco dopo la prima iterazione del ciclo `For Each`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-182">Modify the list sequence after the first `For Each` loop iteration.</span></span>

- <span data-ttu-id="5c1a1-183">Evitare il caricamento completo di un elenco di grandi dimensioni prima della prima iterazione di un ciclo `For Each`.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-183">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="5c1a1-184">Un esempio è un'operazione di recupero di paging per caricare un batch di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-184">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="5c1a1-185">Un altro esempio è il metodo <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, che implementa gli iteratori all'interno di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-185">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>

- <span data-ttu-id="5c1a1-186">Incapsulare la generazione dell'elenco nell'iteratore.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-186">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="5c1a1-187">Nel metodo iteratore è possibile compilare l'elenco e restituire quindi ogni risultato in un ciclo.</span><span class="sxs-lookup"><span data-stu-id="5c1a1-187">In the iterator method, you can build the list and then yield each result in a loop.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c1a1-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c1a1-188">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="5c1a1-189">Istruzione For Each...Next</span><span class="sxs-lookup"><span data-stu-id="5c1a1-189">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="5c1a1-190">Istruzione Yield</span><span class="sxs-lookup"><span data-stu-id="5c1a1-190">Yield Statement</span></span>](../../../visual-basic/language-reference/statements/yield-statement.md)
- [<span data-ttu-id="5c1a1-191">Iterator</span><span class="sxs-lookup"><span data-stu-id="5c1a1-191">Iterator</span></span>](../../../visual-basic/language-reference/modifiers/iterator.md)
