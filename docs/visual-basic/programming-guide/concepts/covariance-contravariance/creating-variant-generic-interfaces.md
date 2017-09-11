---
title: Creazione di interfacce generiche Variant (Visual Basic) | Documenti di Microsoft
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
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
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
ms.openlocfilehash: a2cbf0a204a5a3af45f55a14c011518c7021f5b4
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="e0a48-102">Creazione di interfacce generiche Variant (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0a48-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="e0a48-103">È possibile dichiarare parametri di tipo generico nelle interfacce come covariante o controvariante.</span><span class="sxs-lookup"><span data-stu-id="e0a48-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="e0a48-104">*La covarianza* consente ai metodi di interfaccia di tipi restituiti sono più derivati da quello definito dai parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="e0a48-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="e0a48-105">*La controvarianza* consente metodi di interfaccia di disporre di tipi di argomenti che sono meno derivati rispetto a quello specificato dai parametri generici.</span><span class="sxs-lookup"><span data-stu-id="e0a48-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="e0a48-106">Un'interfaccia generica che è covariante o controvariante parametri di tipo generico viene chiamato *variante*.</span><span class="sxs-lookup"><span data-stu-id="e0a48-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0a48-107">.NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="e0a48-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="e0a48-108">Per l'elenco delle interfacce variante in .NET Framework, vedere [varianza nelle interfacce generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="e0a48-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="e0a48-109">Dichiarazione di interfacce generiche Variant</span><span class="sxs-lookup"><span data-stu-id="e0a48-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="e0a48-110">È possibile dichiarare interfacce generiche variant utilizzando il `in` e `out` le parole chiave per i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="e0a48-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e0a48-111"> `ByRef`in Visual Basic non possono essere variant.</span><span class="sxs-lookup"><span data-stu-id="e0a48-111"> `ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="e0a48-112">Tipi di valore non supportano inoltre la varianza.</span><span class="sxs-lookup"><span data-stu-id="e0a48-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="e0a48-113">È possibile dichiarare un parametro di tipo generico covariante mediante il `out` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="e0a48-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="e0a48-114">Il tipo covariante deve soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0a48-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="e0a48-115">Il tipo viene utilizzato solo come tipo restituito dei metodi di interfaccia e non come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="e0a48-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="e0a48-116">Come illustrato nell'esempio seguente, in cui il tipo `R` viene dichiarato covariante.</span><span class="sxs-lookup"><span data-stu-id="e0a48-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="e0a48-117">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="e0a48-117">There is one exception to this rule.</span></span> <span data-ttu-id="e0a48-118">Se si dispone di un delegato generico controvariante come parametro di metodo, è possibile utilizzare il tipo come parametro di tipo generico per il delegato.</span><span class="sxs-lookup"><span data-stu-id="e0a48-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="e0a48-119">Questo comportamento è illustrato il tipo `R` nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="e0a48-120">Per ulteriori informazioni, vedere [varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [utilizzando la varianza per i delegati generici azione (Visual Basic) e Func](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="e0a48-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="e0a48-121">Il tipo non viene utilizzato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e0a48-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="e0a48-122">Come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="e0a48-123">È possibile dichiarare una controvariante del parametro di tipo generico utilizzando il `in` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="e0a48-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="e0a48-124">Il tipo controvariante può essere utilizzato solo come un tipo di argomenti del metodo e non come un tipo restituito dei metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e0a48-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="e0a48-125">Il tipo di controvariante può essere utilizzato anche per i vincoli generici.</span><span class="sxs-lookup"><span data-stu-id="e0a48-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="e0a48-126">Il codice seguente viene illustrato come dichiarare un'interfaccia controvariante e utilizzare un vincolo generico per uno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="e0a48-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="e0a48-127">È anche possibile supportare sia la covarianza e controvarianza nella stessa interfaccia, ma per i parametri di tipo diverso, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="e0a48-128">In Visual Basic, è possibile dichiarare gli eventi nelle interfacce variante senza specificare il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="e0a48-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="e0a48-129">Inoltre, un'interfaccia variante non può disporre di strutture, enumerazioni o classi annidate, ma è possibile disporre di interfacce annidate.</span><span class="sxs-lookup"><span data-stu-id="e0a48-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="e0a48-130">Come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-130">This is illustrated in the following code.</span></span>  
  
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
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="e0a48-131">Implementazione di interfacce generiche Variant</span><span class="sxs-lookup"><span data-stu-id="e0a48-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="e0a48-132">Implementare le interfacce generiche variant nelle classi utilizzando la stessa sintassi utilizzata per le interfacce invarianti.</span><span class="sxs-lookup"><span data-stu-id="e0a48-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="e0a48-133">Esempio di codice seguente viene illustrato come implementare un'interfaccia covariante in una classe generica.</span><span class="sxs-lookup"><span data-stu-id="e0a48-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
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
  
 <span data-ttu-id="e0a48-134">Le classi che implementano interfacce variant sono invariabili.</span><span class="sxs-lookup"><span data-stu-id="e0a48-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="e0a48-135">Si consideri il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-135">For example, consider the following code.</span></span>  
  
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
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="e0a48-136">Estensione di interfacce generiche Variant</span><span class="sxs-lookup"><span data-stu-id="e0a48-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="e0a48-137">Quando si estende un'interfaccia generica variant, è necessario utilizzare il `in` e `out` le parole chiave per specificare in modo esplicito se l'interfaccia derivata supporta la varianza.</span><span class="sxs-lookup"><span data-stu-id="e0a48-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="e0a48-138">Il compilatore non deduce la varianza dall'interfaccia che viene esteso.</span><span class="sxs-lookup"><span data-stu-id="e0a48-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="e0a48-139">Si consideri ad esempio le interfacce seguenti.</span><span class="sxs-lookup"><span data-stu-id="e0a48-139">For example, consider the following interfaces.</span></span>  
  
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
  
 <span data-ttu-id="e0a48-140">Nel `Invariant(Of T)` interfaccia, il parametro di tipo generico `T` è invariante, mentre in `IExtCovariant (Of Out T)`il parametro di tipo è covariante, anche se entrambe le interfacce estendono la stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e0a48-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="e0a48-141">La stessa regola viene applicata ai parametri di tipo generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="e0a48-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="e0a48-142">È possibile creare un'interfaccia che estende l'interfaccia del parametro di tipo generico in cui `T` è covariante e l'interfaccia in cui è controvariante in estende il parametro di tipo generico dell'interfaccia `T` è invariante.</span><span class="sxs-lookup"><span data-stu-id="e0a48-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="e0a48-143">Come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="e0a48-144">Tuttavia, se un parametro di tipo generico `T` è dichiarato covariante in un'unica interfaccia, non è possibile dichiararlo controvariante nell'interfaccia di estensione, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e0a48-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="e0a48-145">Come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="e0a48-146">Evitare l'ambiguità</span><span class="sxs-lookup"><span data-stu-id="e0a48-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="e0a48-147">Quando si implementano le interfacce generiche variant, varianza può talvolta causare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="e0a48-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="e0a48-148">Questa evenienza deve essere evitata.</span><span class="sxs-lookup"><span data-stu-id="e0a48-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="e0a48-149">Ad esempio, se si implementa in modo esplicito la stessa interfaccia generica variante con parametri di tipo generico diversi in una classe, è possibile creare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="e0a48-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="e0a48-150">Il compilatore non genera un errore in questo caso, ma non viene specificato quale implementazione dell'interfaccia verrà scelto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e0a48-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="e0a48-151">Questo potrebbe causare bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="e0a48-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="e0a48-152">Si consideri l'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a48-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0a48-153">Con `Option Strict Off`, Visual Basic genera un avviso del compilatore quando vi è un'implementazione dell'interfaccia ambigua.</span><span class="sxs-lookup"><span data-stu-id="e0a48-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="e0a48-154">Con `Option Strict On`, Visual Basic genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e0a48-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
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
  
 <span data-ttu-id="e0a48-155">In questo esempio, non viene specificato come il `pets.GetEnumerator` metodo sceglie tra `Cat` e `Dog`.</span><span class="sxs-lookup"><span data-stu-id="e0a48-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="e0a48-156">Ciò potrebbe causare problemi nel codice.</span><span class="sxs-lookup"><span data-stu-id="e0a48-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a48-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0a48-157">See Also</span></span>  
 <span data-ttu-id="e0a48-158">[Varianza nelle interfacce generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="e0a48-158">[Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
<span data-ttu-id="e0a48-159"> [Utilizzo della varianza per i delegati generici azione (Visual Basic) e Func](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="e0a48-159"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
