---
title: Varianza nelle interfacce generiche (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: 50a1aeb5c17a0f193b9e90ca2167ef298f7ed237
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787218"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="75dbd-102">Varianza nelle interfacce generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75dbd-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="75dbd-103">In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="75dbd-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="75dbd-104">Il supporto della varianza consente la conversione implicita delle classi che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="75dbd-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="75dbd-105">Le interfacce seguenti sono ora varianti:</span><span class="sxs-lookup"><span data-stu-id="75dbd-105">The following interfaces are now variant:</span></span>  
  
- <span data-ttu-id="75dbd-106"><xref:System.Collections.Generic.IEnumerable%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="75dbd-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
- <span data-ttu-id="75dbd-107"><xref:System.Collections.Generic.IEnumerator%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="75dbd-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
- <span data-ttu-id="75dbd-108"><xref:System.Linq.IQueryable%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="75dbd-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
- <span data-ttu-id="75dbd-109"><xref:System.Linq.IGrouping%602> (`TKey` e `TElement` sono covarianti)</span><span class="sxs-lookup"><span data-stu-id="75dbd-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
- <span data-ttu-id="75dbd-110"><xref:System.Collections.Generic.IComparer%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="75dbd-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
- <span data-ttu-id="75dbd-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="75dbd-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
- <span data-ttu-id="75dbd-112"><xref:System.IComparable%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="75dbd-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="75dbd-113">La covarianza consente a un metodo di avere un tipo restituito più derivato rispetto a quello definito dal parametro di tipo generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="75dbd-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="75dbd-114">Per illustrare la funzionalità di covarianza, considerare le seguenti interfacce generiche: `IEnumerable(Of Object)` e `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="75dbd-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="75dbd-115">L'interfaccia `IEnumerable(Of String)` non eredita l'interfaccia`IEnumerable(Of Object)`.</span><span class="sxs-lookup"><span data-stu-id="75dbd-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="75dbd-116">Tuttavia, il tipo `String` eredita il tipo `Object` e in alcuni casi è opportuno assegnare gli oggetti di ogni interfaccia all'altra.</span><span class="sxs-lookup"><span data-stu-id="75dbd-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="75dbd-117">Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="75dbd-117">This is shown in the following code example.</span></span>  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 <span data-ttu-id="75dbd-118">Nelle versioni precedenti di .NET Framework, questo codice causa un errore di compilazione in Visual Basic con `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="75dbd-118">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="75dbd-119">Ora è invece possibile usare `strings` anziché `objects`, come illustrato nell'esempio precedente, poiché l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> è covariante.</span><span class="sxs-lookup"><span data-stu-id="75dbd-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="75dbd-120">La controvarianza consente a un metodo di avere tipi di argomenti meno derivati rispetto a quelli specificati dal parametro generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="75dbd-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="75dbd-121">Per illustrare la controvarianza, si supponga di aver creato una classe `BaseComparer` per confrontare le istanze della classe `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="75dbd-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="75dbd-122">La classe `BaseComparer` implementa l'interfaccia `IEqualityComparer(Of BaseClass)`.</span><span class="sxs-lookup"><span data-stu-id="75dbd-122">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="75dbd-123">Poiché l'interfaccia `BaseClass` è ora controvariante, è possibile usare <xref:System.Collections.Generic.IEqualityComparer%601> per confrontare le istanze delle classi che ereditano la classe `BaseComparer`.</span><span class="sxs-lookup"><span data-stu-id="75dbd-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="75dbd-124">Queste operazioni sono illustrate nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="75dbd-124">This is shown in the following code example.</span></span>  
  
```vb  
' Simple hierarchy of classes.  
Class BaseClass  
End Class  
  
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
' Comparer class.  
Class BaseComparer  
    Implements IEqualityComparer(Of BaseClass)  
  
    Public Function Equals1(ByVal x As BaseClass,  
                            ByVal y As BaseClass) As Boolean _  
                            Implements IEqualityComparer(Of BaseClass).Equals  
        Return (x.Equals(y))  
    End Function  
  
    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _  
        Implements IEqualityComparer(Of BaseClass).GetHashCode  
        Return obj.GetHashCode  
    End Function  
End Class  
Sub Test()  
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer  
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to   
    ' IEqualityComparer(Of DerivedClass).  
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer  
End Sub  
```  
  
 <span data-ttu-id="75dbd-125">Per altri esempi, vedere [uso della varianza nelle interfacce per le raccolte generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="75dbd-125">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="75dbd-126">La varianza nelle interfacce generiche è supportata solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="75dbd-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="75dbd-127">I tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="75dbd-127">Value types do not support variance.</span></span> <span data-ttu-id="75dbd-128">Ad esempio, non è possibile convertire `IEnumerable(Of Integer)` in modo implicito in `IEnumerable(Of Object)` perché i valori integer sono rappresentati da un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="75dbd-128">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
```vb  
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)  
' The following statement generates a compiler error  
' with Option Strict On, because Integer is a value type.  
' Dim objects As IEnumerable(Of Object) = integers  
```  
  
 <span data-ttu-id="75dbd-129">È anche importante ricordare che le classi che implementano le interfacce varianti sono comunque invariabili.</span><span class="sxs-lookup"><span data-stu-id="75dbd-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="75dbd-130">Ad esempio, sebbene <xref:System.Collections.Generic.List%601> implementi l'interfaccia covariante <xref:System.Collections.Generic.IEnumerable%601>, non è possibile convertire `List(Of Object)` in `List(Of String)` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="75dbd-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="75dbd-131">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="75dbd-131">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="75dbd-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75dbd-132">See also</span></span>

- [<span data-ttu-id="75dbd-133">Uso della varianza nelle interfacce per le raccolte generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75dbd-133">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="75dbd-134">Creazione di interfacce generiche varianti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75dbd-134">Creating Variant Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)
- [<span data-ttu-id="75dbd-135">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="75dbd-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="75dbd-136">Varianza nei delegati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75dbd-136">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
