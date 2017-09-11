---
title: Varianza nelle interfacce generiche (Visual Basic) | Documenti di Microsoft
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
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
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
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="65350-102">Varianza nelle interfacce generiche (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65350-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="65350-103">.NET framework 4 introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="65350-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="65350-104">Il supporto della varianza consente la conversione implicita di classi che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="65350-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="65350-105">Le interfacce seguenti sono ora variant:</span><span class="sxs-lookup"><span data-stu-id="65350-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="65350-106"><xref:System.Collections.Generic.IEnumerable%601>(T è covariante)</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="65350-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="65350-107"><xref:System.Collections.Generic.IEnumerator%601>(T è covariante)</xref:System.Collections.Generic.IEnumerator%601></span><span class="sxs-lookup"><span data-stu-id="65350-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="65350-108"><xref:System.Linq.IQueryable%601>(T è covariante)</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="65350-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="65350-109"><xref:System.Linq.IGrouping%602>(`TKey` e `TElement` sono covarianti)</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="65350-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="65350-110"><xref:System.Collections.Generic.IComparer%601>(T è controvariante)</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="65350-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="65350-111"><xref:System.Collections.Generic.IEqualityComparer%601>(T è controvariante)</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="65350-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="65350-112"><xref:System.IComparable%601>(T è controvariante)</xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="65350-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="65350-113">La covarianza consente a un metodo per restituire un tipo più derivato da quello definito dal parametro di tipo generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65350-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="65350-114">Per illustrare la funzionalità di covarianza, considerare le seguenti interfacce generiche: `IEnumerable(Of Object)` e `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="65350-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="65350-115">Il `IEnumerable(Of String)` interfaccia non eredita il `IEnumerable(Of Object)` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65350-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="65350-116">Tuttavia, il `String` tipo ereditare il `Object` tipo e in alcuni casi è consigliabile assegnare gli oggetti di queste interfacce tra loro.</span><span class="sxs-lookup"><span data-stu-id="65350-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="65350-117">Come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="65350-117">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="65350-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="65350-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="65350-119">Nelle versioni precedenti di .NET Framework, questo codice causa un errore di compilazione in Visual Basic con `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="65350-119">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="65350-120">Ma ora è possibile utilizzare `strings` invece di `objects`, come illustrato nell'esempio precedente, in quanto il <xref:System.Collections.Generic.IEnumerable%601>interfaccia è covariante.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="65350-120">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="65350-121">La controvarianza consente a un metodo di tipi di argomenti che sono meno derivati rispetto a quello specificato dal parametro generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65350-121">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="65350-122">Per illustrare la controvarianza, si supponga di aver creato un `BaseComparer` per confrontare le istanze della classe di `BaseClass` (classe).</span><span class="sxs-lookup"><span data-stu-id="65350-122">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="65350-123">La classe `BaseComparer` implementa l'interfaccia `IEqualityComparer(Of BaseClass)`.</span><span class="sxs-lookup"><span data-stu-id="65350-123">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="65350-124">Poiché il <xref:System.Collections.Generic.IEqualityComparer%601>interfaccia è controvariante, è possibile utilizzare `BaseComparer` per confrontare le istanze di classi che ereditano la `BaseClass` classe</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="65350-124">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="65350-125">Come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="65350-125">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="65350-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="65350-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="65350-127">Per ulteriori esempi, vedere [utilizzando varianza nelle interfacce per le raccolte generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="65350-127">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="65350-128">Varianza nelle interfacce generiche è supportata per i tipi di riferimento solo.</span><span class="sxs-lookup"><span data-stu-id="65350-128">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="65350-129">Tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="65350-129">Value types do not support variance.</span></span> <span data-ttu-id="65350-130">Ad esempio, `IEnumerable(Of Integer)` non può essere convertita implicitamente in `IEnumerable(Of Object)`, in quanto i valori integer sono rappresentati da un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="65350-130">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
<span data-ttu-id="65350-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="65350-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="65350-132">È inoltre importante ricordare che le classi che implementano interfacce variant sono ancora invariate.</span><span class="sxs-lookup"><span data-stu-id="65350-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="65350-133">Ad esempio, sebbene <xref:System.Collections.Generic.List%601>implementa l'interfaccia covariante <xref:System.Collections.Generic.IEnumerable%601>, non è possibile convertire in modo implicito `List(Of Object)` a `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="65350-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="65350-134">Come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="65350-134">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="65350-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65350-135">See Also</span></span>  
 <span data-ttu-id="65350-136">[Utilizzo della varianza nelle interfacce per le raccolte generiche (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="65350-136">[Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span></span>  
<span data-ttu-id="65350-137"> [Creazione di interfacce generiche Variant (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="65350-137"> [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span></span>  
<span data-ttu-id="65350-138"> [Interfacce generiche](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span><span class="sxs-lookup"><span data-stu-id="65350-138"> [Generic Interfaces](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span></span>  
<span data-ttu-id="65350-139"> [Varianza nei delegati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="65350-139"> [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span></span>
