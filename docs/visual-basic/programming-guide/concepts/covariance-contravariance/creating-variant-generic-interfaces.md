---
title: Creazione di interfacce generiche variant
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 884349159d2738d8481b217f9dab383483616f2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400642"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="af4db-102">Creazione di interfacce generiche varianti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af4db-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>

<span data-ttu-id="af4db-103">È possibile dichiarare parametri di tipo generico nelle interfacce come covarianti o controvarianti.</span><span class="sxs-lookup"><span data-stu-id="af4db-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="af4db-104">La *covarianza* consente ai metodi di interfaccia di avere tipi restituiti più derivati rispetto a quelli definiti dai parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="af4db-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="af4db-105">La *controvarianza* consente ai metodi di interfaccia di avere tipi di argomenti meno derivati rispetto a quelli specificati dai parametri generici.</span><span class="sxs-lookup"><span data-stu-id="af4db-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="af4db-106">Un'interfaccia generica che ha parametri di tipo generico varianti e covarianti è definita *variante*.</span><span class="sxs-lookup"><span data-stu-id="af4db-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="af4db-107">In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="af4db-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="af4db-108">Per l'elenco delle interfacce variant nella .NET Framework, vedere [varianza nelle interfacce generiche (Visual Basic)](variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="af4db-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="af4db-109">Dichiarazione delle interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="af4db-109">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="af4db-110">È possibile dichiarare le interfacce generiche varianti usando le parole chiave `in` e `out` per i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="af4db-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af4db-111">`ByRef`i parametri in Visual Basic non possono essere varianti.</span><span class="sxs-lookup"><span data-stu-id="af4db-111">`ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="af4db-112">Anche i tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="af4db-112">Value types also do not support variance.</span></span>

<span data-ttu-id="af4db-113">È possibile dichiarare un parametro di tipo generico covariante usando la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="af4db-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="af4db-114">Il tipo covariante deve soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af4db-114">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="af4db-115">Il tipo viene usato solo come tipo restituito dei metodi di interfaccia e non come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="af4db-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="af4db-116">Come illustrato nell'esempio seguente, il tipo `R` viene dichiarato covariante.</span><span class="sxs-lookup"><span data-stu-id="af4db-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    <span data-ttu-id="af4db-117">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="af4db-117">There is one exception to this rule.</span></span> <span data-ttu-id="af4db-118">Se si usa un delegato generico controvariante come parametro di metodo, è possibile usare il tipo come parametro di tipo generico per il delegato.</span><span class="sxs-lookup"><span data-stu-id="af4db-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="af4db-119">Questo aspetto è illustrato nell'esempio seguente dal tipo `R`.</span><span class="sxs-lookup"><span data-stu-id="af4db-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="af4db-120">Per altre informazioni, vedere [varianza nei delegati (Visual Basic)](variance-in-delegates.md) e [uso della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="af4db-120">For more information, see [Variance in Delegates (Visual Basic)](variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- <span data-ttu-id="af4db-121">Il tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="af4db-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="af4db-122">Questa situazione è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="af4db-122">This is illustrated in the following code.</span></span>

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

<span data-ttu-id="af4db-123">È possibile dichiarare un parametro di tipo generico controvariante usando la parola chiave `in`.</span><span class="sxs-lookup"><span data-stu-id="af4db-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="af4db-124">Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito dei metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="af4db-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="af4db-125">Il tipo controvariante può essere usato anche per i vincoli generici.</span><span class="sxs-lookup"><span data-stu-id="af4db-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="af4db-126">Il codice seguente illustra come dichiarare un'interfaccia controvariante e usare un vincolo generico per uno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="af4db-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

<span data-ttu-id="af4db-127">È anche possibile supportare sia la covarianza che la controvarianza nella stessa interfaccia, ma per parametri di tipo diverso, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="af4db-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

<span data-ttu-id="af4db-128">In Visual Basic non è possibile dichiarare gli eventi nelle interfacce variant senza specificare il tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="af4db-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="af4db-129">Inoltre, un'interfaccia variant non può includere classi, enumerazioni o strutture annidate, ma può avere interfacce nidificate.</span><span class="sxs-lookup"><span data-stu-id="af4db-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="af4db-130">Questa situazione è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="af4db-130">This is illustrated in the following code.</span></span>

```vb
Interface ICovariant(Of Out R)
    ' The following statement generates a compiler error.
    ' Event SampleEvent()
    ' The following statement specifies the delegate type and
    ' does not generate an error.
    Event AnotherEvent As EventHandler

    ' The following statements generate compiler errors,
    ' because a variant interface cannot have
    ' nested enums, classes, or structures.

    'Enum SampleEnum : test : End Enum
    'Class SampleClass : End Class
    'Structure SampleStructure : Dim value As Integer : End Structure

    ' Variant interfaces can have nested interfaces.
    Interface INested : End Interface
End Interface
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="af4db-131">Implementazione di interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="af4db-131">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="af4db-132">Implementare le interfacce generiche varianti nelle classi usando la stessa sintassi usata per le interfacce invariabili.</span><span class="sxs-lookup"><span data-stu-id="af4db-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="af4db-133">L'esempio di codice seguente illustra come implementare un'interfaccia covariante in una classe generica.</span><span class="sxs-lookup"><span data-stu-id="af4db-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```vb
Interface ICovariant(Of Out R)
    Function GetSomething() As R
End Interface

Class SampleImplementation(Of R)
    Implements ICovariant(Of R)
    Public Function GetSomething() As R _
    Implements ICovariant(Of R).GetSomething
        ' Some code.
    End Function
End Class
```

<span data-ttu-id="af4db-134">Le classi che implementano le interfacce varianti sono invariabili.</span><span class="sxs-lookup"><span data-stu-id="af4db-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="af4db-135">Si consideri il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="af4db-135">For example, consider the following code.</span></span>

```vb
 The interface is covariant.
Dim ibutton As ICovariant(Of Button) =
    New SampleImplementation(Of Button)
Dim iobj As ICovariant(Of Object) = ibutton

' The class is invariant.
Dim button As SampleImplementation(Of Button) =
    New SampleImplementation(Of Button)
' The following statement generates a compiler error
' because classes are invariant.
' Dim obj As SampleImplementation(Of Object) = button
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="af4db-136">Estensione di interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="af4db-136">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="af4db-137">Quando si estende un'interfaccia generica variante è necessario usare le parole chiave `in` e `out` per specificare in modo esplicito se l'interfaccia derivata supporta la varianza.</span><span class="sxs-lookup"><span data-stu-id="af4db-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="af4db-138">Il compilatore non deduce la varianza dall'interfaccia che viene estesa.</span><span class="sxs-lookup"><span data-stu-id="af4db-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="af4db-139">Si considerino ad esempio le interfacce seguenti.</span><span class="sxs-lookup"><span data-stu-id="af4db-139">For example, consider the following interfaces.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T)
End Interface

Interface IExtCovariant(Of Out T)
    Inherits ICovariant(Of T)
End Interface
```

<span data-ttu-id="af4db-140">Nell' `Invariant(Of T)` interfaccia, il parametro di tipo generico `T` è invariante, mentre nel `IExtCovariant (Of Out T)` parametro di tipo è covariante, sebbene entrambe le interfacce estendano la stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="af4db-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="af4db-141">La stessa regola viene applicata ai parametri di tipo generico controvarianti.</span><span class="sxs-lookup"><span data-stu-id="af4db-141">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="af4db-142">È possibile creare un'interfaccia che estende sia l'interfaccia in cui il parametro di tipo generico `T` è covariante, sia l'interfaccia in cui è controvariante se nell'interfaccia che viene estesa il parametro di tipo generico `T` è invariabile,</span><span class="sxs-lookup"><span data-stu-id="af4db-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="af4db-143">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="af4db-143">This is illustrated in the following code example.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

<span data-ttu-id="af4db-144">Tuttavia, se un parametro di tipo generico `T` è dichiarato covariante in una sola interfaccia, non è possibile dichiararlo controvariante nell'interfaccia da estendere o viceversa,</span><span class="sxs-lookup"><span data-stu-id="af4db-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="af4db-145">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="af4db-145">This is illustrated in the following code example.</span></span>

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="af4db-146">Evitare le ambiguità</span><span class="sxs-lookup"><span data-stu-id="af4db-146">Avoiding Ambiguity</span></span>

<span data-ttu-id="af4db-147">Quando si implementano le interfacce generiche varianti, la varianza può talvolta causare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="af4db-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="af4db-148">Questa evenienza deve essere evitata.</span><span class="sxs-lookup"><span data-stu-id="af4db-148">This should be avoided.</span></span>

<span data-ttu-id="af4db-149">Ad esempio, se si implementa in modo esplicito la stessa interfaccia generica variante con parametri di tipo generico diversi in una sola classe, è possibile creare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="af4db-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="af4db-150">Il compilatore non genera un errore in questo caso, ma non viene specificato quale implementazione dell'interfaccia verrà scelta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="af4db-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="af4db-151">Questo potrebbe causare bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="af4db-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="af4db-152">Si prenda in considerazione il seguente esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="af4db-152">Consider the following code example.</span></span>

> [!NOTE]
> <span data-ttu-id="af4db-153">Con `Option Strict Off` , Visual Basic genera un avviso del compilatore quando è presente un'implementazione ambigua dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="af4db-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="af4db-154">Con `Option Strict On` , Visual Basic genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="af4db-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>

```vb
' Simple class hierarchy.
Class Animal
End Class

Class Cat
    Inherits Animal
End Class

Class Dog
    Inherits Animal
End Class

' This class introduces ambiguity
' because IEnumerable(Of Out T) is covariant.
Class Pets
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)

    Public Function GetEnumerator() As IEnumerator(Of Cat) _
        Implements IEnumerable(Of Cat).GetEnumerator
        Console.WriteLine("Cat")
        ' Some code.
    End Function

    Public Function GetEnumerator1() As IEnumerator(Of Dog) _
        Implements IEnumerable(Of Dog).GetEnumerator
        Console.WriteLine("Dog")
        ' Some code.
    End Function

    Public Function GetEnumerator2() As IEnumerator _
        Implements IEnumerable.GetEnumerator
        ' Some code.
    End Function
End Class

Sub Main()
    Dim pets As IEnumerable(Of Animal) = New Pets()
    pets.GetEnumerator()
End Sub
```

<span data-ttu-id="af4db-155">In questo esempio non viene specificato in che modo il metodo `pets.GetEnumerator` sceglie tra `Cat` e `Dog`.</span><span class="sxs-lookup"><span data-stu-id="af4db-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="af4db-156">Ciò potrebbe causare problemi nel codice.</span><span class="sxs-lookup"><span data-stu-id="af4db-156">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="af4db-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af4db-157">See also</span></span>

- [<span data-ttu-id="af4db-158">Varianza nelle interfacce generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af4db-158">Variance in Generic Interfaces (Visual Basic)</span></span>](variance-in-generic-interfaces.md)
- [<span data-ttu-id="af4db-159">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af4db-159">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
