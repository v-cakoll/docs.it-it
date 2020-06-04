---
title: Varianza nei delegati
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 86ea9f3f744381bcff71a88e9d88485cafa4a568
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375616"
---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="b47d4-102">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b47d4-102">Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="b47d4-103">.NET Framework 3,5 ha introdotto il supporto della varianza per le firme di metodo corrispondenti con tipi delegati in tutti i delegati in C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b47d4-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="b47d4-104">Ciò significa che è possibile assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="b47d4-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="b47d4-105">Sono inclusi sia i delegati generici che quelli non generici.</span><span class="sxs-lookup"><span data-stu-id="b47d4-105">This includes both generic and non-generic delegates.</span></span>

<span data-ttu-id="b47d4-106">Ad esempio, si consideri il codice seguente, che ha due classi e due delegati: generico e non generico.</span><span class="sxs-lookup"><span data-stu-id="b47d4-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

<span data-ttu-id="b47d4-107">Quando si creano i delegati dei tipi `SampleDelegate` o `SampleDelegate(Of A, R)` è possibile assegnare uno qualsiasi dei metodi seguenti ai delegati.</span><span class="sxs-lookup"><span data-stu-id="b47d4-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

<span data-ttu-id="b47d4-108">L'esempio di codice seguente viene illustra la conversione implicita tra la firma del metodo e il tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="b47d4-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

<span data-ttu-id="b47d4-109">Per altri esempi, vedere [uso della varianza nei delegati (Visual Basic)](using-variance-in-delegates.md) e [uso della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="b47d4-109">For more examples, see [Using Variance in Delegates (Visual Basic)](using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span></span>

## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="b47d4-110">Varianza nei parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="b47d4-110">Variance in Generic Type Parameters</span></span>

<span data-ttu-id="b47d4-111">In .NET Framework 4 e versioni successive è possibile abilitare la conversione implicita tra delegati, in modo che i delegati generici con tipi diversi specificati da parametri di tipo generico possano essere assegnati tra loro, se i tipi vengono ereditati l'uno dall'altro come richiesto dalla varianza.</span><span class="sxs-lookup"><span data-stu-id="b47d4-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>

<span data-ttu-id="b47d4-112">Per abilitare la conversione implicita, è necessario dichiarare esplicitamente i parametri generici in un delegato come covariante o controvariante usando la parola chiave `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="b47d4-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>

<span data-ttu-id="b47d4-113">L'esempio di codice seguente illustra come creare un delegato con un parametro di tipo generico covariante.</span><span class="sxs-lookup"><span data-stu-id="b47d4-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

<span data-ttu-id="b47d4-114">Se si usa solo il supporto della varianza per la corrispondenza delle firme del metodo con i tipi delegati e non si usano le parole chiave `in` e `out`, è possibile che in alcuni casi si possano creare istanze di delegati con metodi o espressioni lambda identici, ma non è possibile assegnare un delegato a un altro.</span><span class="sxs-lookup"><span data-stu-id="b47d4-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>

<span data-ttu-id="b47d4-115">Nell'esempio di codice seguente `SampleGenericDelegate(Of String)` non è possibile convertire in modo esplicito in `SampleGenericDelegate(Of Object)` , sebbene `String` erediti `Object` .</span><span class="sxs-lookup"><span data-stu-id="b47d4-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="b47d4-116">È possibile correggere questo problema contrassegnando il parametro generico `T` con la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="b47d4-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="b47d4-117">Delegati generici con parametri di tipo variante in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b47d4-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>

<span data-ttu-id="b47d4-118">In .NET framework 4 è stato introdotto il supporto della varianza per i parametri di tipo generico in diversi delegati generici esistenti:</span><span class="sxs-lookup"><span data-stu-id="b47d4-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>

- <span data-ttu-id="b47d4-119">Delegati `Action` dallo spazio dei nomi <xref:System>, ad esempio <xref:System.Action%601> e <xref:System.Action%602></span><span class="sxs-lookup"><span data-stu-id="b47d4-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>

- <span data-ttu-id="b47d4-120">Delegati `Func` dallo spazio dei nomi <xref:System>, ad esempio <xref:System.Func%601> e <xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="b47d4-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>

- <span data-ttu-id="b47d4-121">Delegato <xref:System.Predicate%601>.</span><span class="sxs-lookup"><span data-stu-id="b47d4-121">The <xref:System.Predicate%601> delegate</span></span>

- <span data-ttu-id="b47d4-122">Delegato <xref:System.Comparison%601>.</span><span class="sxs-lookup"><span data-stu-id="b47d4-122">The <xref:System.Comparison%601> delegate</span></span>

- <span data-ttu-id="b47d4-123">Delegato <xref:System.Converter%602>.</span><span class="sxs-lookup"><span data-stu-id="b47d4-123">The <xref:System.Converter%602> delegate</span></span>

<span data-ttu-id="b47d4-124">Per ulteriori informazioni ed esempi, vedere [utilizzo della varianza per i delegati generici Func e Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="b47d4-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span></span>

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="b47d4-125">Dichiarare parametri di tipo variante nei delegati generici</span><span class="sxs-lookup"><span data-stu-id="b47d4-125">Declaring Variant Type Parameters in Generic Delegates</span></span>

<span data-ttu-id="b47d4-126">Se un delegato generico ha parametri di tipo generico covariante o controvariante, può essere indicato come un *delegato generico variante*.</span><span class="sxs-lookup"><span data-stu-id="b47d4-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>

<span data-ttu-id="b47d4-127">È possibile dichiarare un parametro di tipo generico covariante in un delegato generico usando la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="b47d4-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="b47d4-128">Il tipo covariante può essere usato solo come tipo restituito del metodo e non come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="b47d4-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="b47d4-129">Nell'esempio di codice seguente viene illustrato come dichiarare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="b47d4-129">The following code example shows how to declare a covariant generic delegate.</span></span>

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

<span data-ttu-id="b47d4-130">È possibile dichiarare un parametro di tipo generico controvariante in un delegato generico usando la parola chiave `in`.</span><span class="sxs-lookup"><span data-stu-id="b47d4-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="b47d4-131">Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="b47d4-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="b47d4-132">Nell'esempio di codice seguente viene illustrato come dichiarare un delegato generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="b47d4-132">The following code example shows how to declare a contravariant generic delegate.</span></span>

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> <span data-ttu-id="b47d4-133">`ByRef`i parametri in Visual Basic non possono essere contrassegnati come Variant.</span><span class="sxs-lookup"><span data-stu-id="b47d4-133">`ByRef` parameters in Visual Basic can't be marked as variant.</span></span>

<span data-ttu-id="b47d4-134">È anche possibile supportare sia la varianza che la covarianza nello stesso delegato, ma per parametri di tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="b47d4-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="b47d4-135">come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b47d4-135">This is shown in the following example.</span></span>

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="b47d4-136">Creare un'istanza e richiamare delegati generici varianti</span><span class="sxs-lookup"><span data-stu-id="b47d4-136">Instantiating and Invoking Variant Generic Delegates</span></span>

<span data-ttu-id="b47d4-137">È possibile creare un'istanza e richiamare delegati varianti con la stessa procedura con cui si crea un'istanza e si richiamano i delegati invariabili.</span><span class="sxs-lookup"><span data-stu-id="b47d4-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="b47d4-138">Nell'esempio seguente viene creata un'istanza del delegato da un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="b47d4-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="b47d4-139">Combinare delegati generici varianti</span><span class="sxs-lookup"><span data-stu-id="b47d4-139">Combining Variant Generic Delegates</span></span>

<span data-ttu-id="b47d4-140">È consigliabile non combinare i delegati varianti.</span><span class="sxs-lookup"><span data-stu-id="b47d4-140">You should not combine variant delegates.</span></span> <span data-ttu-id="b47d4-141">Il metodo <xref:System.Delegate.Combine%2A> non supporta la conversione dei delegati varianti e prevede che i delegati siano esattamente dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="b47d4-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="b47d4-142">Questo può causare un'eccezione in fase di esecuzione quando si combinano delegati usando il <xref:System.Delegate.Combine%2A> Metodo (in c# e Visual Basic) o usando l' `+` operatore (in c#), come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b47d4-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="b47d4-143">Varianza nei parametri di tipo generico per tipi di valore e riferimento</span><span class="sxs-lookup"><span data-stu-id="b47d4-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>

<span data-ttu-id="b47d4-144">La varianza per i parametri di tipo generico è supportata solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="b47d4-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="b47d4-145">Ad esempio, `DVariant(Of Int)` non può essere convertito in modo implicito in `DVariant(Of Object)` o `DVariant(Of Long)` , perché Integer è un tipo valore.</span><span class="sxs-lookup"><span data-stu-id="b47d4-145">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>

<span data-ttu-id="b47d4-146">L'esempio seguente dimostra che la varianza nei parametri di tipo generico non è supportata per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="b47d4-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="b47d4-147">Conversione di delegati rilassati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b47d4-147">Relaxed Delegate Conversion in Visual Basic</span></span>

<span data-ttu-id="b47d4-148">La conversione di un delegato rilassato consente una maggiore flessibilità nelle firme dei metodi corrispondenti con i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="b47d4-148">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="b47d4-149">Ad esempio, consente di omettere le specifiche dei parametri e di omettere i valori restituiti della funzione quando si assegna un metodo a un delegato.</span><span class="sxs-lookup"><span data-stu-id="b47d4-149">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="b47d4-150">Per ulteriori informazioni, vedere [conversione di un delegato rilassato](../../language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="b47d4-150">For more information, see [Relaxed Delegate Conversion](../../language-features/delegates/relaxed-delegate-conversion.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b47d4-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b47d4-151">See also</span></span>

- [<span data-ttu-id="b47d4-152">Generics</span><span class="sxs-lookup"><span data-stu-id="b47d4-152">Generics</span></span>](../../../../standard/generics/index.md)
- [<span data-ttu-id="b47d4-153">Utilizzo della varianza per i delegati generici Func e Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b47d4-153">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
