---
title: Varianza nei delegati (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
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
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="bc17e-102">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc17e-102">Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="bc17e-103">.NET framework 3.5 è stato introdotto il supporto della varianza per la corrispondenza delle firme di metodo con i tipi delegati in tutti i delegati in c# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bc17e-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="bc17e-104">Ciò significa che è possibile assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più derivati (covarianza) i tipi o che accettano parametri con tipi meno derivati (controvarianza) rispetto a quello specificato dal tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="bc17e-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="bc17e-105">Ciò include delegati sia generici e non generica.</span><span class="sxs-lookup"><span data-stu-id="bc17e-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="bc17e-106">Ad esempio, si consideri il codice seguente, che dispone di due classi e due delegati: generico e non generici.</span><span class="sxs-lookup"><span data-stu-id="bc17e-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 <span data-ttu-id="bc17e-107">Quando si creano delegati del `SampleDelegate` o `SampleDelegate(Of A, R)` tipi, è possibile assegnare uno dei metodi seguenti per i delegati.</span><span class="sxs-lookup"><span data-stu-id="bc17e-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>  
  
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
  
 <span data-ttu-id="bc17e-108">Esempio di codice seguente viene illustrata la conversione implicita tra la firma del metodo e il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="bc17e-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
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
  
 <span data-ttu-id="bc17e-109">Per ulteriori esempi, vedere [utilizzando varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) e [utilizzando la varianza per i delegati generici azione (Visual Basic) e Func](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="bc17e-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="bc17e-110">Varianza nei parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="bc17e-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="bc17e-111">In .NET Framework 4 e versioni successive è possibile abilitare la conversione implicita tra delegati, in modo che i delegati generici con tipi diversi specificati dai parametri di tipo generico possono essere assegnati tra loro, se i tipi vengono ereditati da altra come richiesto dalla varianza.</span><span class="sxs-lookup"><span data-stu-id="bc17e-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="bc17e-112">Per abilitare la conversione implicita, è necessario dichiarare in modo esplicito i parametri generici di un delegato come covarianti o controvarianti utilizzando il `in` o `out` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="bc17e-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="bc17e-113">Esempio di codice seguente viene illustrato come creare un delegato con un parametro di tipo generico covariante.</span><span class="sxs-lookup"><span data-stu-id="bc17e-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
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
  
 <span data-ttu-id="bc17e-114">Se si utilizza solo il supporto della varianza per la corrispondenza delle firme di metodo con tipi delegati e non utilizzare il `in` e `out` le parole chiave, è possibile che in alcuni casi è possibile creare istanze di delegati con metodi o espressioni lambda identiche, ma non è possibile assegnare un delegato a un altro.</span><span class="sxs-lookup"><span data-stu-id="bc17e-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="bc17e-115">Nell'esempio di codice seguente, `SampleGenericDelegate(Of String)` non può essere convertito in modo esplicito in `SampleGenericDelegate(Of Object)`, sebbene `String` eredita `Object`.</span><span class="sxs-lookup"><span data-stu-id="bc17e-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="bc17e-116">È possibile risolvere questo problema contrassegnando il parametro generico `T` con il `out` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="bc17e-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="bc17e-117">Delegati generici con variante di parametri di tipo in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bc17e-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="bc17e-118">.NET framework 4 è stato introdotto il supporto della varianza per i parametri di tipo generico in diversi delegati generici esistenti:</span><span class="sxs-lookup"><span data-stu-id="bc17e-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="bc17e-119">`Action`delega dal <xref:System>spazio dei nomi, ad esempio, <xref:System.Action%601>e <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="bc17e-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="bc17e-120">`Func`delega dal <xref:System>spazio dei nomi, ad esempio, <xref:System.Func%601>e <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="bc17e-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="bc17e-121">Il <xref:System.Predicate%601>delegato</xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="bc17e-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="bc17e-122">Il <xref:System.Comparison%601>delegato</xref:System.Comparison%601></span><span class="sxs-lookup"><span data-stu-id="bc17e-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="bc17e-123">Il <xref:System.Converter%602>delegato</xref:System.Converter%602></span><span class="sxs-lookup"><span data-stu-id="bc17e-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="bc17e-124">Per ulteriori informazioni ed esempi, vedere [utilizzando la varianza per i delegati generici azione (Visual Basic) e Func](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="bc17e-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="bc17e-125">Dichiarazione dei parametri di tipo Variant in delegati generici</span><span class="sxs-lookup"><span data-stu-id="bc17e-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="bc17e-126">Se un delegato generico è covariante o parametri di tipo generico controvariante, può essere indicato come un *delegati generici varianti*.</span><span class="sxs-lookup"><span data-stu-id="bc17e-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="bc17e-127">È possibile dichiarare un parametro di tipo generico covarianti in un delegato generico utilizzando il `out` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="bc17e-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="bc17e-128">Di tipo covariante può essere utilizzato solo come un tipo restituito del metodo e non come un tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="bc17e-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="bc17e-129">Esempio di codice seguente viene illustrato come dichiarare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="bc17e-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
<span data-ttu-id="bc17e-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="bc17e-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="bc17e-131">È possibile dichiarare una controvariante del parametro di tipo generico in un delegato generico utilizzando il `in` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="bc17e-131">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="bc17e-132">Il tipo controvariante può essere utilizzato solo come un tipo di argomenti del metodo e non come un tipo restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="bc17e-132">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="bc17e-133">Esempio di codice seguente viene illustrato come dichiarare un delegato generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="bc17e-133">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
<span data-ttu-id="bc17e-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="bc17e-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
> <span data-ttu-id="bc17e-135"> `ByRef`i parametri in Visual Basic non possono essere contrassegnati come variant.</span><span class="sxs-lookup"><span data-stu-id="bc17e-135"> `ByRef` parameters in Visual Basic can't be marked as variant.</span></span>  
  
 <span data-ttu-id="bc17e-136">È inoltre possibile supportare sia la varianza e covarianza nello stesso delegato, ma per i parametri di tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="bc17e-136">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="bc17e-137">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="bc17e-137">This is shown in the following example.</span></span>  
  
<span data-ttu-id="bc17e-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="bc17e-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="bc17e-139">Creare un'istanza e richiamare delegati generici varianti</span><span class="sxs-lookup"><span data-stu-id="bc17e-139">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="bc17e-140">È possibile creare un'istanza e richiamare delegati varianti esattamente come si crea un'istanza e richiamare delegati invarianti.</span><span class="sxs-lookup"><span data-stu-id="bc17e-140">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="bc17e-141">Nell'esempio seguente viene creata un'istanza di delegato da un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="bc17e-141">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
<span data-ttu-id="bc17e-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="bc17e-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="bc17e-143">La combinazione dei delegati generici varianti</span><span class="sxs-lookup"><span data-stu-id="bc17e-143">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="bc17e-144">È consigliabile non combinare delegati varianti.</span><span class="sxs-lookup"><span data-stu-id="bc17e-144">You should not combine variant delegates.</span></span> <span data-ttu-id="bc17e-145">Il <xref:System.Delegate.Combine%2A>metodo non supporta la conversione di delegati varianti e prevede che i delegati per essere dello stesso tipo.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="bc17e-145">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="bc17e-146">Questo può causare un'eccezione in fase di esecuzione quando si combinano delegati utilizzando il <xref:System.Delegate.Combine%2A>(metodo) (in c# e Visual Basic) o tramite il `+` (operatore) (in c#), come illustrato nell'esempio di codice seguente.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="bc17e-146">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>  
  
<span data-ttu-id="bc17e-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="bc17e-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="bc17e-148">Varianza nei parametri di tipo generico per valore e tipi di riferimento</span><span class="sxs-lookup"><span data-stu-id="bc17e-148">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="bc17e-149">La varianza per i parametri di tipo generico è supportata per i tipi di riferimento solo.</span><span class="sxs-lookup"><span data-stu-id="bc17e-149">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="bc17e-150">Ad esempio, `DVariant(Of Int)`non può essere convertita implicitamente in `DVariant(Of Object)` o `DVariant(Of Long)`, poiché integer è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="bc17e-150">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="bc17e-151">Nell'esempio seguente viene illustrato che la varianza in tipo generico con parametri non è supportata per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="bc17e-151">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="bc17e-152">Conversione di tipo relaxed del delegato in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc17e-152">Relaxed Delegate Conversion in Visual Basic</span></span>  
 <span data-ttu-id="bc17e-153">Conversione di tipo relaxed del delegato consente una maggiore flessibilità in corrispondenza delle firme di metodo con i tipi delegati.</span><span class="sxs-lookup"><span data-stu-id="bc17e-153">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="bc17e-154">Ad esempio, consente di omettere le specifiche dei parametri e omettere i valori restituiti dalla funzione quando si assegna un metodo a un delegato.</span><span class="sxs-lookup"><span data-stu-id="bc17e-154">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="bc17e-155">Per ulteriori informazioni, vedere [conversione di tipo Relaxed del delegato](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="bc17e-155">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc17e-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc17e-156">See Also</span></span>  
 <span data-ttu-id="bc17e-157">[Generics](https://msdn.microsoft.com/library/ms172192) </span><span class="sxs-lookup"><span data-stu-id="bc17e-157">[Generics](https://msdn.microsoft.com/library/ms172192) </span></span>  
<span data-ttu-id="bc17e-158"> [Utilizzo della varianza per Func e azione delegati generici (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="bc17e-158"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
